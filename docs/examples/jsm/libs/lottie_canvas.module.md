[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `lottie_canvas.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 941 |
| 📊 Variables & Constants | 1643 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/lottie_canvas.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lottie` | `{ play: (animation: any) => void; pau...` | let/var | `{}` | ✗ |
| `svgNS` | `"http://www.w3.org/2000/svg"` | let/var | `'http://www.w3.org/2000/svg'` | ✗ |
| `locationHref` | `string` | let/var | `''` | ✗ |
| `_useWebWorker` | `boolean` | let/var | `false` | ✗ |
| `initialDefaultFrame` | `-999999` | let/var | `-999999` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `sources.length` | ✗ |
| `sourcePrototype` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.audios.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.audios.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.audios.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.audios.length` | ✗ |
| `audioControllerFactory` | `() => AudioController` | let/var | `(function () { function AudioController(audioFactory) { this.audios = []; thi...` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `arr` | `any[]` | let/var | `[]` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `createTypedArray` | `(type: any, len: any) => number[] \| ...` | let/var | `(function () { function createRegularArray(type, len) { var i = 0; var arr = ...` | ✗ |
| `subframeEnabled` | `boolean` | let/var | `true` | ✗ |
| `expressionsPlugin` | `any` | let/var | `null` | ✗ |
| `idPrefix$1` | `string` | let/var | `''` | ✗ |
| `_shouldRoundValues` | `boolean` | let/var | `false` | ✗ |
| `bmPow` | `(x: number, y: number) => number` | let/var | `Math.pow` | ✗ |
| `bmSqrt` | `(x: number) => number` | let/var | `Math.sqrt` | ✗ |
| `bmFloor` | `(x: number) => number` | let/var | `Math.floor` | ✗ |
| `bmMax` | `(...values: number[]) => number` | let/var | `Math.max` | ✗ |
| `bmMin` | `(...values: number[]) => number` | let/var | `Math.min` | ✗ |
| `BMMath` | `{ random: () => number; abs(val: any)...` | let/var | `{}` | ✗ |
| `propertyNames` | `string[]` | let/var | `['abs', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atanh', 'atan2', 'ceil', '...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `propertyNames.length` | ✗ |
| `tOfVal` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof val` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `val.length` | ✗ |
| `defaultCurveSegments` | `number` | let/var | `150` | ✗ |
| `degToRads` | `number` | let/var | `Math.PI / 180` | ✗ |
| `roundCorner` | `0.5519` | let/var | `0.5519` | ✗ |
| `_count` | `number` | let/var | `0` | ✗ |
| `createElementID` | `() => string` | let/var | `(function () { var _count = 0; return function createID() { _count += 1; retu...` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `g` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `f` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `any` | let/var | `*not shown*` | ✗ |
| `q` | `any` | let/var | `*not shown*` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `number` | let/var | `max - min` | ✗ |
| `h` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `number` | let/var | `(max === 0 ? 0 : d / max)` | ✗ |
| `v` | `number` | let/var | `max / 255` | ✗ |
| `colorMap` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `hex` | `any` | let/var | `*not shown*` | ✗ |
| `rgbToHex` | `(r: any, g: any, b: any) => string` | let/var | `(function () { var colorMap = []; var i; var hex; for (i = 0; i < 256; i += 1...` | ✗ |
| `_counterId` | `number` | let/var | `1` | ✗ |
| `processes` | `any[]` | let/var | `[]` | ✗ |
| `workerFn` | `any` | let/var | `*not shown*` | ✗ |
| `workerInstance` | `any` | let/var | `*not shown*` | ✗ |
| `workerProxy` | `{ onmessage: () => void; postMessage:...` | let/var | `{ onmessage: function () { }, postMessage: function (path) { workerFn({ data:...` | ✗ |
| `_workerSelf` | `{ postMessage: (data: any) => void; }` | let/var | `{ postMessage: function (data) { workerProxy.onmessage({ data: data, }); }, }` | ✗ |
| `blob` | `Blob` | let/var | `new Blob(['var _workerSelf = self; self.onmessage = ', fn.toString()], { type...` | ✗ |
| `layerData` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `layers.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `kLen` | `any` | let/var | `*not shown*` | ✗ |
| `maskProps` | `any` | let/var | `layerData.masksProperties` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `chars.length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `comps.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `arr.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `path.i.length` | ✗ |
| `animVersion` | `any` | let/var | `animVersionString ? animVersionString.split('.') : [100, 100, 100]` | ✗ |
| `minimumVersion` | `number[]` | let/var | `[4, 4, 14]` | ✗ |
| `documentData` | `any` | let/var | `textLayer.t.d` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `layers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `animationData.assets.length` | ✗ |
| `checkText` | `(animationData: any) => void` | let/var | `(function () { var minimumVersion = [4, 4, 14]; function updateTextLayer(text...` | ✗ |
| `minimumVersion` | `number[]` | let/var | `[4, 7, 99]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `animationData.chars.length` | ✗ |
| `charData` | `any` | let/var | `animationData.chars[i]` | ✗ |
| `checkChars` | `(animationData: any) => void` | let/var | `(function () { var minimumVersion = [4, 7, 99]; return function (animationDat...` | ✗ |
| `minimumVersion` | `number[]` | let/var | `[5, 7, 15]` | ✗ |
| `pathData` | `any` | let/var | `textLayer.t.p` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `layers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `animationData.assets.length` | ✗ |
| `checkPathProperties` | `(animationData: any) => void` | let/var | `(function () { var minimumVersion = [5, 7, 15]; function updateTextLayer(text...` | ✗ |
| `minimumVersion` | `number[]` | let/var | `[4, 1, 9]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapes.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `layers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `animationData.assets.length` | ✗ |
| `checkColors` | `(animationData: any) => void` | let/var | `(function () { var minimumVersion = [4, 1, 9]; function iterateShapes(shapes)...` | ✗ |
| `minimumVersion` | `number[]` | let/var | `[4, 4, 18]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `arr.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `layerData` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `layers.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `kLen` | `any` | let/var | `*not shown*` | ✗ |
| `maskProps` | `any` | let/var | `layerData.masksProperties` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `animationData.assets.length` | ✗ |
| `checkShapes` | `(animationData: any) => void` | let/var | `(function () { var minimumVersion = [4, 4, 18]; function completeClosingShape...` | ✗ |
| `moduleOb` | `{ completeData: (animationData: any) ...` | let/var | `{}` | ✗ |
| `response` | `any` | let/var | `*not shown*` | ✗ |
| `xhr` | `XMLHttpRequest` | let/var | `new XMLHttpRequest()` | ✗ |
| `animation` | `any` | let/var | `e.data.animation` | ✗ |
| `data` | `any` | let/var | `event.data` | ✗ |
| `id` | `any` | let/var | `data.id` | ✗ |
| `process` | `any` | let/var | `processes[id]` | ✗ |
| `id` | `string` | let/var | `'processId_' + _counterId` | ✗ |
| `dataManager` | `{ loadAnimation: (path: any, onComple...` | let/var | `(function () { var _counterId = 1; var processes = []; var workerFn; var work...` | ✗ |
| `proxyImage` | `any` | let/var | `(function () { var canvas = createTag('canvas'); canvas.width = 1; canvas.hei...` | ✗ |
| `path` | `string` | let/var | `''` | ✗ |
| `imagePath` | `any` | let/var | `assetData.p` | ✗ |
| `_count` | `number` | let/var | `0` | ✗ |
| `ob` | `{ img: any; assetData: any; }` | let/var | `{ img: img, assetData: assetData, }` | ✗ |
| `ob` | `{ img: any; assetData: any; }` | let/var | `{ img: img, assetData: assetData, }` | ✗ |
| `ob` | `{ assetData: any; }` | let/var | `{ assetData: data, }` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `assets.length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.images.length` | ✗ |
| `ImagePreloader` | `typeof ImagePreloaderFactory` | let/var | `(function () { var proxyImage = (function () { var canvas = createTag('canvas...` | ✗ |
| `callbacks` | `any` | let/var | `this._cbs[eventName]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this._cbs[eventName].length` | ✗ |
| `keys` | `{}` | let/var | `{}` | ✗ |
| `line` | `any` | let/var | `*not shown*` | ✗ |
| `keysCount` | `number` | let/var | `0` | ✗ |
| `markers` | `any[]` | let/var | `[]` | ✗ |
| `_marker` | `any` | let/var | `_markers[i]` | ✗ |
| `markerData` | `{ time: any; duration: any; }` | let/var | `{ time: _marker.tm, duration: _marker.dr, }` | ✗ |
| `markerParser` | `(_markers: any) => { time: any; durat...` | let/var | `( function () { function parsePayloadLines(payload) { var lines = payload.spl...` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.compositions.length` | ✗ |
| `ProjectInterface` | `() => { (name: any): any; composition...` | let/var | `(function () { function registerComposition(comp) { this.compositions.push(co...` | ✗ |
| `renderers` | `{}` | let/var | `{}` | ✗ |
| `animType` | `string` | let/var | `'svg'` | ✗ |
| `params` | `{ wrapper: any; animationData: any; }` | let/var | `{ wrapper: wrapper, animationData: animationData, }` | ✗ |
| `wrapperAttributes` | `any` | let/var | `wrapper.attributes` | ✗ |
| `loop` | `any` | let/var | `wrapperAttributes.getNamedItem('data-anim-loop') // eslint-disable-line no-ne...` | ✗ |
| `autoplay` | `any` | let/var | `wrapperAttributes.getNamedItem('data-anim-autoplay') // eslint-disable-line n...` | ✗ |
| `prerender` | `any` | let/var | `wrapperAttributes.getNamedItem('data-anim-prerender') // eslint-disable-line ...` | ✗ |
| `layers` | `any` | let/var | `this.animationData.layers` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `layers.length` | ✗ |
| `newLayers` | `any` | let/var | `data.layers` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `newLayers.length` | ✗ |
| `segments` | `any` | let/var | `this.animationData.segments` | ✗ |
| `segmentPath` | `string` | let/var | `this.path + this.fileName + '_' + this.segmentPos + '.json'` | ✗ |
| `segments` | `any` | let/var | `this.animationData.segments` | ✗ |
| `marker` | `any` | let/var | `*not shown*` | ✗ |
| `nextValue` | `number` | let/var | `this.currentRawFrame + value * this.frameModifier` | ✗ |
| `_isComplete` | `boolean` | let/var | `false` | ✗ |
| `pendingFrame` | `number` | let/var | `-1` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `arr.length` | ✗ |
| `path` | `string` | let/var | `''` | ✗ |
| `imagePath` | `any` | let/var | `assetData.p` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `number` | let/var | `this.assets.length` | ✗ |
| `error` | `BMRenderFrameErrorEvent` | let/var | `new BMRenderFrameErrorEvent(nativeError, this.currentFrame)` | ✗ |
| `error` | `BMConfigErrorEvent` | let/var | `new BMConfigErrorEvent(nativeError, this.currentFrame)` | ✗ |
| `moduleOb` | `{ registerAnimation: (element: any, a...` | let/var | `{}` | ✗ |
| `registeredAnimations` | `any[]` | let/var | `[]` | ✗ |
| `initTime` | `number` | let/var | `0` | ✗ |
| `len` | `number` | let/var | `0` | ✗ |
| `playingAnimationsNum` | `number` | let/var | `0` | ✗ |
| `_stopped` | `boolean` | let/var | `true` | ✗ |
| `_isFrozen` | `boolean` | let/var | `false` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `animItem` | `any` | let/var | `ev.target` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `animItem` | `AnimationItem` | let/var | `new AnimationItem()` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `lenAnims` | `number` | let/var | `registeredAnimations.length` | ✗ |
| `animations` | `any[]` | let/var | `[]` | ✗ |
| `animItem` | `AnimationItem` | let/var | `new AnimationItem()` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `elapsedTime` | `number` | let/var | `nowTime - initTime` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `lenAnims` | `number` | let/var | `animElements.length` | ✗ |
| `body` | `HTMLBodyElement` | let/var | `document.getElementsByTagName('body')[0]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `animationManager` | `{ registerAnimation: (element: any, a...` | let/var | `(function () { var moduleOb = {}; var registeredAnimations = []; var initTime...` | ✗ |
| `ob` | `{ getBezierEasing: (a: any, b: any, c...` | let/var | `{}` | ✗ |
| `beziers` | `{}` | let/var | `{}` | ✗ |
| `str` | `any` | let/var | `nm \|\| ('bez_' + a + '_' + b + '_' + c + '_' + d).replace(/\./g, 'p')` | ✗ |
| `bezEasing` | `BezierEasing` | let/var | `new BezierEasing([a, b, c, d])` | ✗ |
| `NEWTON_ITERATIONS` | `number` | let/var | `4` | ✗ |
| `NEWTON_MIN_SLOPE` | `number` | let/var | `0.001` | ✗ |
| `SUBDIVISION_PRECISION` | `number` | let/var | `0.0000001` | ✗ |
| `SUBDIVISION_MAX_ITERATIONS` | `number` | let/var | `10` | ✗ |
| `kSplineTableSize` | `number` | let/var | `11` | ✗ |
| `kSampleStepSize` | `number` | let/var | `1.0 / (kSplineTableSize - 1.0)` | ✗ |
| `float32ArraySupported` | `boolean` | let/var | `typeof Float32Array === 'function'` | ✗ |
| `currentX` | `any` | let/var | `*not shown*` | ✗ |
| `currentT` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `currentX` | `number` | let/var | `calcBezier(aGuessT, mX1, mX2) - aX` | ✗ |
| `mX1` | `any` | let/var | `this._p[0]` | ✗ |
| `mY1` | `any` | let/var | `this._p[1]` | ✗ |
| `mX2` | `any` | let/var | `this._p[2]` | ✗ |
| `mY2` | `any` | let/var | `this._p[3]` | ✗ |
| `mX1` | `any` | let/var | `this._p[0]` | ✗ |
| `mY1` | `any` | let/var | `this._p[1]` | ✗ |
| `mX2` | `any` | let/var | `this._p[2]` | ✗ |
| `mY2` | `any` | let/var | `this._p[3]` | ✗ |
| `mX1` | `any` | let/var | `this._p[0]` | ✗ |
| `mX2` | `any` | let/var | `this._p[2]` | ✗ |
| `mX1` | `any` | let/var | `this._p[0]` | ✗ |
| `mX2` | `any` | let/var | `this._p[2]` | ✗ |
| `mSampleValues` | `any[] \| Float32Array<ArrayBuffer>` | let/var | `this._mSampleValues` | ✗ |
| `intervalStart` | `number` | let/var | `0.0` | ✗ |
| `currentSample` | `number` | let/var | `1` | ✗ |
| `lastSample` | `number` | let/var | `kSplineTableSize - 1` | ✗ |
| `dist` | `number` | let/var | `(aX - mSampleValues[currentSample]) / (mSampleValues[currentSample + 1] - mSa...` | ✗ |
| `guessForT` | `number` | let/var | `intervalStart + dist * kSampleStepSize` | ✗ |
| `BezierFactory` | `{ getBezierEasing: (a: any, b: any, c...` | let/var | `(function () { /** * BezierEasing - use bezier curve for transition easing fu...` | ✗ |
| `pooling` | `{ double: (arr: any) => any; }` | let/var | `(function () { function double(arr) { return arr.concat(createSizedArray(arr....` | ✗ |
| `_length` | `number` | let/var | `0` | ✗ |
| `_maxLength` | `any` | let/var | `initialLength` | ✗ |
| `ob` | `{ newElement: () => any; release: (el...` | let/var | `{ newElement: newElement, release: release, }` | ✗ |
| `element` | `any` | let/var | `*not shown*` | ✗ |
| `poolFactory` | `(initialLength: any, _create: any, _r...` | let/var | `(function () { return function (initialLength, _create, _release) { var _leng...` | ✗ |
| `bezierLengthPool` | `{ newElement: () => any; release: (el...` | let/var | `(function () { function create() { return { addedLength: 0, percents: createT...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `element.lengths.length` | ✗ |
| `segmentsLengthPool` | `{ newElement: () => any; release: (el...` | let/var | `(function () { function create() { return { lengths: [], totalLength: 0, }; }...` | ✗ |
| `math` | `Math` | let/var | `Math` | ✗ |
| `det1` | `number` | let/var | `(x1 * y2) + (y1 * x3) + (x2 * y3) - (x3 * y2) - (y3 * x1) - (x2 * y1)` | ✗ |
| `diffDist` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `ptCoord` | `any` | let/var | `*not shown*` | ✗ |
| `perc` | `any` | let/var | `*not shown*` | ✗ |
| `addedLength` | `number` | let/var | `0` | ✗ |
| `ptDistance` | `any` | let/var | `*not shown*` | ✗ |
| `point` | `any[]` | let/var | `[]` | ✗ |
| `lastPoint` | `any[]` | let/var | `[]` | ✗ |
| `getBezierLength` | `(pt1: any, pt2: any, pt3: any, pt4: a...` | let/var | `(function () { return function (pt1, pt2, pt3, pt4) { var curveSegments = get...` | ✗ |
| `closed` | `any` | let/var | `shapeData.c` | ✗ |
| `pathV` | `any` | let/var | `shapeData.v` | ✗ |
| `pathO` | `any` | let/var | `shapeData.o` | ✗ |
| `pathI` | `any` | let/var | `shapeData.i` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapeData._length` | ✗ |
| `lengths` | `any` | let/var | `segmentsLength.lengths` | ✗ |
| `totalLength` | `number` | let/var | `0` | ✗ |
| `storedData` | `{}` | let/var | `{}` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `ptCoord` | `any` | let/var | `*not shown*` | ✗ |
| `perc` | `any` | let/var | `*not shown*` | ✗ |
| `addedLength` | `number` | let/var | `0` | ✗ |
| `ptDistance` | `any` | let/var | `*not shown*` | ✗ |
| `point` | `any` | let/var | `*not shown*` | ✗ |
| `lastPoint` | `any` | let/var | `null` | ✗ |
| `bezierData` | `BezierData` | let/var | `new BezierData(curveSegments)` | ✗ |
| `buildBezierData` | `(pt1: any, pt2: any, pt3: any, pt4: a...` | let/var | `(function () { var storedData = {}; return function (pt1, pt2, pt3, pt4) { va...` | ✗ |
| `percents` | `any` | let/var | `bezierData.percents` | ✗ |
| `lengths` | `any` | let/var | `bezierData.lengths` | ✗ |
| `len` | `any` | let/var | `percents.length` | ✗ |
| `lengthPos` | `number` | let/var | `perc * bezierData.addedLength` | ✗ |
| `lPerc` | `number` | let/var | `0` | ✗ |
| `dir` | `number` | let/var | `lengths[initPos] > lengthPos ? -1 : 1` | ✗ |
| `flag` | `boolean` | let/var | `true` | ✗ |
| `u1` | `number` | let/var | `1 - t1` | ✗ |
| `ptX` | `number` | let/var | `math.round((u1 * u1 * u1 * pt1[0] + (t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * ...` | ✗ |
| `ptY` | `number` | let/var | `math.round((u1 * u1 * u1 * pt1[1] + (t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * ...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `pt1.length` | ✗ |
| `u0` | `number` | let/var | `1 - t0` | ✗ |
| `u1` | `number` | let/var | `1 - t1` | ✗ |
| `u0u0u0` | `number` | let/var | `u0 * u0 * u0` | ✗ |
| `t0u0u0_3` | `number` | let/var | `t0 * u0 * u0 * 3` | ✗ |
| `t0t0u0_3` | `number` | let/var | `t0 * t0 * u0 * 3` | ✗ |
| `t0t0t0` | `number` | let/var | `t0 * t0 * t0` | ✗ |
| `u0u0u1` | `number` | let/var | `u0 * u0 * u1` | ✗ |
| `t0u0u1_3` | `number` | let/var | `t0 * u0 * u1 + u0 * t0 * u1 + u0 * u0 * t1` | ✗ |
| `t0t0u1_3` | `number` | let/var | `t0 * t0 * u1 + u0 * t0 * t1 + t0 * u0 * t1` | ✗ |
| `t0t0t1` | `number` | let/var | `t0 * t0 * t1` | ✗ |
| `u0u1u1` | `number` | let/var | `u0 * u1 * u1` | ✗ |
| `t0u1u1_3` | `number` | let/var | `t0 * u1 * u1 + u0 * t1 * u1 + u0 * u1 * t1` | ✗ |
| `t0t1u1_3` | `number` | let/var | `t0 * t1 * u1 + u0 * t1 * t1 + t0 * u1 * t1` | ✗ |
| `t0t1t1` | `number` | let/var | `t0 * t1 * t1` | ✗ |
| `u1u1u1` | `number` | let/var | `u1 * u1 * u1` | ✗ |
| `t1u1u1_3` | `number` | let/var | `t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * t1` | ✗ |
| `t1t1u1_3` | `number` | let/var | `t1 * t1 * u1 + u1 * t1 * t1 + t1 * u1 * t1` | ✗ |
| `t1t1t1` | `number` | let/var | `t1 * t1 * t1` | ✗ |
| `initFrame` | `number` | let/var | `initialDefaultFrame` | ✗ |
| `mathAbs` | `(x: number) => number` | let/var | `Math.abs` | ✗ |
| `offsetTime` | `any` | let/var | `this.offsetTime` | ✗ |
| `newValue` | `any` | let/var | `*not shown*` | ✗ |
| `iterationIndex` | `any` | let/var | `caching.lastIndex` | ✗ |
| `i` | `any` | let/var | `iterationIndex` | ✗ |
| `len` | `number` | let/var | `this.keyframes.length - 1` | ✗ |
| `flag` | `boolean` | let/var | `true` | ✗ |
| `keyData` | `any` | let/var | `*not shown*` | ✗ |
| `nextKeyData` | `any` | let/var | `*not shown*` | ✗ |
| `keyframeMetadata` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `kLen` | `any` | let/var | `*not shown*` | ✗ |
| `perc` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `fnc` | `any` | let/var | `*not shown*` | ✗ |
| `nextKeyTime` | `number` | let/var | `nextKeyData.t - offsetTime` | ✗ |
| `keyTime` | `number` | let/var | `keyData.t - offsetTime` | ✗ |
| `endValue` | `any` | let/var | `*not shown*` | ✗ |
| `bezierData` | `any` | let/var | `keyframeMetadata.bezierData` | ✗ |
| `ind` | `number` | let/var | `frameNum >= nextKeyTime ? bezierData.points.length - 1 : 0` | ✗ |
| `distanceInLine` | `number` | let/var | `bezierData.segmentLength * perc` | ✗ |
| `segmentPerc` | `any` | let/var | `*not shown*` | ✗ |
| `addedLength` | `any` | let/var | `(caching.lastFrame < frameNum && caching._lastKeyframeIndex === i) ? caching....` | ✗ |
| `outX` | `any` | let/var | `*not shown*` | ✗ |
| `outY` | `any` | let/var | `*not shown*` | ✗ |
| `inX` | `any` | let/var | `*not shown*` | ✗ |
| `inY` | `any` | let/var | `*not shown*` | ✗ |
| `keyValue` | `any` | let/var | `*not shown*` | ✗ |
| `time` | `number` | let/var | `(frameNum - keyTime) / (nextKeyTime - keyTime)` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `ax` | `any` | let/var | `a[0]` | ✗ |
| `ay` | `any` | let/var | `a[1]` | ✗ |
| `az` | `any` | let/var | `a[2]` | ✗ |
| `aw` | `any` | let/var | `a[3]` | ✗ |
| `bx` | `any` | let/var | `b[0]` | ✗ |
| `by` | `any` | let/var | `b[1]` | ✗ |
| `bz` | `any` | let/var | `b[2]` | ✗ |
| `bw` | `any` | let/var | `b[3]` | ✗ |
| `omega` | `any` | let/var | `*not shown*` | ✗ |
| `cosom` | `any` | let/var | `*not shown*` | ✗ |
| `sinom` | `any` | let/var | `*not shown*` | ✗ |
| `scale0` | `any` | let/var | `*not shown*` | ✗ |
| `scale1` | `any` | let/var | `*not shown*` | ✗ |
| `qx` | `any` | let/var | `quat[0]` | ✗ |
| `qy` | `any` | let/var | `quat[1]` | ✗ |
| `qz` | `any` | let/var | `quat[2]` | ✗ |
| `qw` | `any` | let/var | `quat[3]` | ✗ |
| `heading` | `number` | let/var | `values[0] * degToRads` | ✗ |
| `attitude` | `number` | let/var | `values[1] * degToRads` | ✗ |
| `bank` | `number` | let/var | `values[2] * degToRads` | ✗ |
| `w` | `number` | let/var | `c1 * c2 * c3 - s1 * s2 * s3` | ✗ |
| `x` | `number` | let/var | `s1 * s2 * c3 + c1 * c2 * s3` | ✗ |
| `y` | `number` | let/var | `s1 * c2 * c3 + c1 * s2 * s3` | ✗ |
| `z` | `number` | let/var | `c1 * s2 * c3 - s1 * c2 * s3` | ✗ |
| `frameNum` | `number` | let/var | `this.comp.renderedFrame - this.offsetTime` | ✗ |
| `initTime` | `number` | let/var | `this.keyframes[0].t - this.offsetTime` | ✗ |
| `endTime` | `number` | let/var | `this.keyframes[this.keyframes.length - 1].t - this.offsetTime` | ✗ |
| `multipliedValue` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.v.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.effectsSequence.length` | ✗ |
| `finalValue` | `any` | let/var | `this.kf ? this.pv : this.data.k` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `data.k.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `data.k.length` | ✗ |
| `s` | `any` | let/var | `*not shown*` | ✗ |
| `e` | `any` | let/var | `*not shown*` | ✗ |
| `to` | `any` | let/var | `*not shown*` | ✗ |
| `ti` | `any` | let/var | `*not shown*` | ✗ |
| `arrLen` | `any` | let/var | `data.k[0].s.length` | ✗ |
| `p` | `any` | let/var | `*not shown*` | ✗ |
| `ob` | `{ getProp: (elem: any, data: any, typ...` | let/var | `{ getProp: getProp, }` | ✗ |
| `PropertyFactory` | `{ getProp: (elem: any, data: any, typ...` | let/var | `(function () { var initFrame = initialDefaultFrame; var mathAbs = Math.abs; f...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.dynamicProperties.length` | ✗ |
| `pointPool` | `{ newElement: () => any; release: (el...` | let/var | `(function () { function create() { return createTypedArray('float32', 2); } r...` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `arr` | `any` | let/var | `*not shown*` | ✗ |
| `newPath` | `ShapePath` | let/var | `new ShapePath()` | ✗ |
| `vertices` | `any` | let/var | `this.v` | ✗ |
| `outPoints` | `any` | let/var | `this.o` | ✗ |
| `inPoints` | `any` | let/var | `this.i` | ✗ |
| `init` | `number` | let/var | `0` | ✗ |
| `cnt` | `number` | let/var | `this._length - 1` | ✗ |
| `len` | `number` | let/var | `this._length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapePath._length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shape._length === undefined ? shape.v.length : shape._length` | ✗ |
| `shapePool` | `{ newElement: () => any; release: (el...` | let/var | `(function () { function create() { return new ShapePath(); } function release...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `ob` | `{ newShapeCollection: () => any; rele...` | let/var | `{ newShapeCollection: newShapeCollection, release: release, }` | ✗ |
| `_length` | `number` | let/var | `0` | ✗ |
| `_maxLength` | `number` | let/var | `4` | ✗ |
| `shapeCollection` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapeCollection._length` | ✗ |
| `shapeCollectionPool` | `{ newShapeCollection: () => any; rele...` | let/var | `(function () { var ob = { newShapeCollection: newShapeCollection, release: re...` | ✗ |
| `initFrame` | `number` | let/var | `-999999` | ✗ |
| `iterationIndex` | `any` | let/var | `caching.lastIndex` | ✗ |
| `keyPropS` | `any` | let/var | `*not shown*` | ✗ |
| `keyPropE` | `any` | let/var | `*not shown*` | ✗ |
| `isHold` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `kLen` | `any` | let/var | `*not shown*` | ✗ |
| `perc` | `any` | let/var | `*not shown*` | ✗ |
| `vertexValue` | `any` | let/var | `*not shown*` | ✗ |
| `kf` | `any` | let/var | `this.keyframes` | ✗ |
| `i` | `any` | let/var | `iterationIndex` | ✗ |
| `len` | `number` | let/var | `kf.length - 1` | ✗ |
| `flag` | `boolean` | let/var | `true` | ✗ |
| `keyData` | `any` | let/var | `*not shown*` | ✗ |
| `nextKeyData` | `any` | let/var | `*not shown*` | ✗ |
| `keyframeMetadata` | `any` | let/var | `*not shown*` | ✗ |
| `fnc` | `any` | let/var | `*not shown*` | ✗ |
| `frameNum` | `number` | let/var | `this.comp.renderedFrame - this.offsetTime` | ✗ |
| `initTime` | `number` | let/var | `this.keyframes[0].t - this.offsetTime` | ✗ |
| `endTime` | `number` | let/var | `this.keyframes[this.keyframes.length - 1].t - this.offsetTime` | ✗ |
| `lastFrame` | `any` | let/var | `this._caching.lastFrame` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shape1._length` | ✗ |
| `finalValue` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.effectsSequence.length` | ✗ |
| `pathData` | `any` | let/var | `type === 3 ? data.pt.k : data.ks.k` | ✗ |
| `len` | `any` | let/var | `this.keyframes[0].s[0].i.length` | ✗ |
| `cPoint` | `number` | let/var | `roundCorner` | ✗ |
| `p0` | `any` | let/var | `this.p.v[0]` | ✗ |
| `p1` | `any` | let/var | `this.p.v[1]` | ✗ |
| `s0` | `number` | let/var | `this.s.v[0] / 2` | ✗ |
| `s1` | `number` | let/var | `this.s.v[1] / 2` | ✗ |
| `_cw` | `boolean` | let/var | `this.d !== 3` | ✗ |
| `_v` | `any` | let/var | `this.v` | ✗ |
| `EllShapeProperty` | `typeof EllShapePropertyFactory` | let/var | `(function () { var cPoint = roundCorner; function EllShapePropertyFactory(ele...` | ✗ |
| `numPts` | `number` | let/var | `Math.floor(this.pt.v) * 2` | ✗ |
| `angle` | `number` | let/var | `(Math.PI * 2) / numPts` | ✗ |
| `longFlag` | `boolean` | let/var | `true` | ✗ |
| `longRad` | `any` | let/var | `this.or.v` | ✗ |
| `shortRad` | `any` | let/var | `this.ir.v` | ✗ |
| `longRound` | `any` | let/var | `this.os.v` | ✗ |
| `shortRound` | `any` | let/var | `this.is.v` | ✗ |
| `longPerimSegment` | `number` | let/var | `(2 * Math.PI * longRad) / (numPts * 2)` | ✗ |
| `shortPerimSegment` | `number` | let/var | `(2 * Math.PI * shortRad) / (numPts * 2)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `rad` | `any` | let/var | `*not shown*` | ✗ |
| `roundness` | `any` | let/var | `*not shown*` | ✗ |
| `perimSegment` | `any` | let/var | `*not shown*` | ✗ |
| `currentAng` | `number` | let/var | `-Math.PI / 2` | ✗ |
| `dir` | `number` | let/var | `this.data.d === 3 ? -1 : 1` | ✗ |
| `x` | `number` | let/var | `rad * Math.cos(currentAng)` | ✗ |
| `y` | `number` | let/var | `rad * Math.sin(currentAng)` | ✗ |
| `ox` | `number` | let/var | `x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y)` | ✗ |
| `oy` | `number` | let/var | `x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y)` | ✗ |
| `angle` | `number` | let/var | `(Math.PI * 2) / numPts` | ✗ |
| `rad` | `any` | let/var | `this.or.v` | ✗ |
| `roundness` | `any` | let/var | `this.os.v` | ✗ |
| `perimSegment` | `number` | let/var | `(2 * Math.PI * rad) / (numPts * 4)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `currentAng` | `number` | let/var | `-Math.PI * 0.5` | ✗ |
| `dir` | `number` | let/var | `this.data.d === 3 ? -1 : 1` | ✗ |
| `x` | `number` | let/var | `rad * Math.cos(currentAng)` | ✗ |
| `y` | `number` | let/var | `rad * Math.sin(currentAng)` | ✗ |
| `ox` | `number` | let/var | `x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y)` | ✗ |
| `oy` | `number` | let/var | `x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y)` | ✗ |
| `StarShapeProperty` | `typeof StarShapePropertyFactory` | let/var | `(function () { function StarShapePropertyFactory(elem, data) { this.v = shape...` | ✗ |
| `p0` | `any` | let/var | `this.p.v[0]` | ✗ |
| `p1` | `any` | let/var | `this.p.v[1]` | ✗ |
| `v0` | `number` | let/var | `this.s.v[0] / 2` | ✗ |
| `v1` | `number` | let/var | `this.s.v[1] / 2` | ✗ |
| `cPoint` | `number` | let/var | `round * (1 - roundCorner)` | ✗ |
| `RectShapeProperty` | `typeof RectShapePropertyFactory` | let/var | `(function () { function RectShapePropertyFactory(elem, data) { this.v = shape...` | ✗ |
| `prop` | `any` | let/var | `*not shown*` | ✗ |
| `dataProp` | `any` | let/var | `type === 3 ? data.pt : data.ks` | ✗ |
| `keys` | `any` | let/var | `dataProp.k` | ✗ |
| `ob` | `{ getShapeProp: (elem: any, data: any...` | let/var | `{}` | ✗ |
| `ShapePropertyFactory` | `{ getShapeProp: (elem: any, data: any...` | let/var | `(function () { var initFrame = -999999; function interpolateShape(frameNum, p...` | ✗ |
| `_cos` | `(x: number) => number` | let/var | `Math.cos` | ✗ |
| `_sin` | `(x: number) => number` | let/var | `Math.sin` | ✗ |
| `_tan` | `(x: number) => number` | let/var | `Math.tan` | ✗ |
| `_rnd` | `(x: number) => number` | let/var | `Math.round` | ✗ |
| `_p` | `any` | let/var | `this.props` | ✗ |
| `a1` | `any` | let/var | `_p[0]` | ✗ |
| `b1` | `any` | let/var | `_p[1]` | ✗ |
| `c1` | `any` | let/var | `_p[2]` | ✗ |
| `d1` | `any` | let/var | `_p[3]` | ✗ |
| `e1` | `any` | let/var | `_p[4]` | ✗ |
| `f1` | `any` | let/var | `_p[5]` | ✗ |
| `g1` | `any` | let/var | `_p[6]` | ✗ |
| `h1` | `any` | let/var | `_p[7]` | ✗ |
| `i1` | `any` | let/var | `_p[8]` | ✗ |
| `j1` | `any` | let/var | `_p[9]` | ✗ |
| `k1` | `any` | let/var | `_p[10]` | ✗ |
| `l1` | `any` | let/var | `_p[11]` | ✗ |
| `m1` | `any` | let/var | `_p[12]` | ✗ |
| `n1` | `any` | let/var | `_p[13]` | ✗ |
| `o1` | `any` | let/var | `_p[14]` | ✗ |
| `p1` | `any` | let/var | `_p[15]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `determinant` | `number` | let/var | `this.props[0] * this.props[5] - this.props[1] * this.props[4]` | ✗ |
| `a` | `number` | let/var | `this.props[5] / determinant` | ✗ |
| `b` | `number` | let/var | `-this.props[1] / determinant` | ✗ |
| `c` | `number` | let/var | `-this.props[4] / determinant` | ✗ |
| `d` | `number` | let/var | `this.props[0] / determinant` | ✗ |
| `e` | `number` | let/var | `(this.props[4] * this.props[13] - this.props[5] * this.props[12]) / determinant` | ✗ |
| `f` | `number` | let/var | `-(this.props[0] * this.props[13] - this.props[1] * this.props[12]) / determinant` | ✗ |
| `inverseMatrix` | `(Anonymous function)` | let/var | `new Matrix()` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `pts.length` | ✗ |
| `retPts` | `any[]` | let/var | `[]` | ✗ |
| `p0` | `any` | let/var | `this.props[0]` | ✗ |
| `p1` | `any` | let/var | `this.props[1]` | ✗ |
| `p4` | `any` | let/var | `this.props[4]` | ✗ |
| `p5` | `any` | let/var | `this.props[5]` | ✗ |
| `p12` | `any` | let/var | `this.props[12]` | ✗ |
| `p13` | `any` | let/var | `this.props[13]` | ✗ |
| `arr` | `any` | let/var | `*not shown*` | ✗ |
| `_p` | `any` | let/var | `this.props` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `props` | `any` | let/var | `this.props` | ✗ |
| `cssValue` | `string` | let/var | `'matrix3d('` | ✗ |
| `v` | `number` | let/var | `10000` | ✗ |
| `v` | `number` | let/var | `10000` | ✗ |
| `props` | `any` | let/var | `this.props` | ✗ |
| `Matrix` | `typeof (Anonymous function)` | let/var | `(function () { var _cos = Math.cos; var _sin = Math.sin; var _tan = Math.tan;...` | ✗ |
| `standalone` | `string` | let/var | `'__[STANDALONE]__'` | ✗ |
| `animationData` | `string` | let/var | `'__[ANIMATIONDATA]__'` | ✗ |
| `renderer` | `string` | let/var | `''` | ✗ |
| `queryString` | `string` | let/var | `''` | ✗ |
| `index` | `number` | let/var | `scripts.length - 1` | ✗ |
| `myScript` | `HTMLScriptElement \| { src: string; }` | let/var | `scripts[index] \|\| { src: '', }` | ✗ |
| `ob` | `{ registerModifier: (nm: any, factory...` | let/var | `{}` | ✗ |
| `modifiers` | `{}` | let/var | `{}` | ✗ |
| `ShapeModifiers` | `{ registerModifier: (nm: any, factory...` | let/var | `(function () { var ob = {}; var modifiers = {}; ob.registerModifier = registe...` | ✗ |
| `shapeData` | `{ shape: any; data: any; localShapeCo...` | let/var | `{ shape: data.sh, data: data, localShapeCollection: shapeCollectionPool.newSh...` | ✗ |
| `segments` | `any[]` | let/var | `[]` | ✗ |
| `shapeSegments` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `segments.length` | ✗ |
| `segmentOb` | `any` | let/var | `*not shown*` | ✗ |
| `shapeS` | `any` | let/var | `*not shown*` | ✗ |
| `shapeE` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `pathsData.length` | ✗ |
| `s` | `any` | let/var | `*not shown*` | ✗ |
| `e` | `any` | let/var | `*not shown*` | ✗ |
| `o` | `number` | let/var | `(this.o.v % 360) / 360` | ✗ |
| `_s` | `any` | let/var | `s` | ✗ |
| `shapePaths` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.shapes.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `pathsData` | `any` | let/var | `*not shown*` | ✗ |
| `pathData` | `any` | let/var | `*not shown*` | ✗ |
| `totalShapeLength` | `any` | let/var | `*not shown*` | ✗ |
| `totalModifierLength` | `number` | let/var | `0` | ✗ |
| `segments` | `any[]` | let/var | `[]` | ✗ |
| `shapeData` | `any` | let/var | `*not shown*` | ✗ |
| `localShapeCollection` | `any` | let/var | `*not shown*` | ✗ |
| `shapeS` | `any` | let/var | `s` | ✗ |
| `shapeE` | `any` | let/var | `e` | ✗ |
| `addedLength` | `number` | let/var | `0` | ✗ |
| `edges` | `any` | let/var | `*not shown*` | ✗ |
| `lastShapeInCollection` | `any` | let/var | `shapeData.shape.paths.shapes[shapeData.shape.paths._length - 1]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `newPaths.length` | ✗ |
| `pathsData` | `any` | let/var | `shapeData.pathsData` | ✗ |
| `shapePaths` | `any` | let/var | `shapeData.shape.paths.shapes` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapeData.shape.paths._length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `addedLength` | `number` | let/var | `0` | ✗ |
| `currentLengthData` | `any` | let/var | `*not shown*` | ✗ |
| `segmentCount` | `any` | let/var | `*not shown*` | ✗ |
| `lengths` | `any` | let/var | `*not shown*` | ✗ |
| `segment` | `any` | let/var | `*not shown*` | ✗ |
| `shapes` | `any[]` | let/var | `[]` | ✗ |
| `initPos` | `any` | let/var | `*not shown*` | ✗ |
| `newShape` | `boolean` | let/var | `true` | ✗ |
| `segmentLength` | `any` | let/var | `lengths[j - 1].addedLength` | ✗ |
| `percent` | `number` | let/var | `amount / 100` | ✗ |
| `centerPoint` | `number[]` | let/var | `[0, 0]` | ✗ |
| `pathLength` | `any` | let/var | `path._length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `vX` | `any` | let/var | `*not shown*` | ✗ |
| `vY` | `any` | let/var | `*not shown*` | ✗ |
| `oX` | `any` | let/var | `*not shown*` | ✗ |
| `oY` | `any` | let/var | `*not shown*` | ✗ |
| `iX` | `any` | let/var | `*not shown*` | ✗ |
| `iY` | `any` | let/var | `*not shown*` | ✗ |
| `shapePaths` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.shapes.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `amount` | `any` | let/var | `this.amount.v` | ✗ |
| `shapeData` | `any` | let/var | `*not shown*` | ✗ |
| `localShapeCollection` | `any` | let/var | `*not shown*` | ✗ |
| `defaultVector` | `number[]` | let/var | `[0, 0]` | ✗ |
| `_mdf` | `undefined` | let/var | `this._mdf` | ✗ |
| `frameRate` | `any` | let/var | `*not shown*` | ✗ |
| `v1` | `any` | let/var | `*not shown*` | ✗ |
| `v2` | `any` | let/var | `*not shown*` | ✗ |
| `px` | `any` | let/var | `this.px` | ✗ |
| `py` | `any` | let/var | `this.py` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `data.or.k.length` | ✗ |
| `TransformPropertyFactory` | `{ getTransformProperty: (elem: any, d...` | let/var | `(function () { var defaultVector = [0, 0]; function applyToMatrix(mat) { var ...` | ✗ |
| `dir` | `number` | let/var | `inv ? -1 : 1` | ✗ |
| `scaleX` | `any` | let/var | `transform.s.v[0] + (1 - transform.s.v[0]) * (1 - perc)` | ✗ |
| `scaleY` | `any` | let/var | `transform.s.v[1] + (1 - transform.s.v[1]) * (1 - perc)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `elements.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `elements.length` | ✗ |
| `items` | `any` | let/var | `*not shown*` | ✗ |
| `itemsTransform` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `dir` | `any` | let/var | `*not shown*` | ✗ |
| `cont` | `any` | let/var | `*not shown*` | ✗ |
| `hasReloaded` | `boolean` | let/var | `false` | ✗ |
| `group` | `{ it: any; ty: string; }` | let/var | `{ it: this.cloneElements(this._elements), ty: 'gr', }` | ✗ |
| `renderFlag` | `any` | let/var | `*not shown*` | ✗ |
| `elems` | `any` | let/var | `this.elemsData[i].it` | ✗ |
| `transformData` | `any` | let/var | `elems[elems.length - 1]` | ✗ |
| `offset` | `any` | let/var | `this.o.v` | ✗ |
| `offsetModulo` | `number` | let/var | `offset % 1` | ✗ |
| `roundOffset` | `number` | let/var | `offset > 0 ? Math.floor(offset) : Math.ceil(offset)` | ✗ |
| `pProps` | `any` | let/var | `this.pMatrix.props` | ✗ |
| `rProps` | `any` | let/var | `this.rMatrix.props` | ✗ |
| `sProps` | `any` | let/var | `this.sMatrix.props` | ✗ |
| `iteration` | `number` | let/var | `0` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `path._length` | ✗ |
| `currentV` | `any` | let/var | `*not shown*` | ✗ |
| `currentI` | `any` | let/var | `*not shown*` | ✗ |
| `currentO` | `any` | let/var | `*not shown*` | ✗ |
| `closerV` | `any` | let/var | `*not shown*` | ✗ |
| `distance` | `any` | let/var | `*not shown*` | ✗ |
| `newPosPerc` | `any` | let/var | `*not shown*` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `vX` | `any` | let/var | `*not shown*` | ✗ |
| `vY` | `any` | let/var | `*not shown*` | ✗ |
| `oX` | `any` | let/var | `*not shown*` | ✗ |
| `oY` | `any` | let/var | `*not shown*` | ✗ |
| `iX` | `any` | let/var | `*not shown*` | ✗ |
| `iY` | `any` | let/var | `*not shown*` | ✗ |
| `shapePaths` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.shapes.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `rd` | `any` | let/var | `this.rd.v` | ✗ |
| `shapeData` | `any` | let/var | `*not shown*` | ✗ |
| `localShapeCollection` | `any` | let/var | `*not shown*` | ✗ |
| `styles` | `any` | let/var | `fontData.fStyle ? fontData.fStyle.split(' ') : []` | ✗ |
| `fWeight` | `string` | let/var | `'normal'` | ✗ |
| `fStyle` | `string` | let/var | `'normal'` | ✗ |
| `len` | `any` | let/var | `styles.length` | ✗ |
| `styleName` | `any` | let/var | `*not shown*` | ✗ |
| `maxWaitingTime` | `number` | let/var | `5000` | ✗ |
| `emptyChar` | `{ w: number; size: number; shapes: an...` | let/var | `{ w: 0, size: 0, shapes: [], data: { shapes: [], }, }` | ✗ |
| `combinedCharacters` | `any[]` | let/var | `[]` | ✗ |
| `surrogateModifiers` | `string[]` | let/var | `[ 'd83cdffb', 'd83cdffc', 'd83cdffd', 'd83cdffe', 'd83cdfff', ]` | ✗ |
| `zeroWidthJoiner` | `number[]` | let/var | `[65039, 8205]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `familyArray.length` | ✗ |
| `enabledFamilies` | `any[]` | let/var | `[]` | ✗ |
| `width` | `any` | let/var | `node.offsetWidth` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.fonts.length` | ✗ |
| `node` | `any` | let/var | `*not shown*` | ✗ |
| `w` | `any` | let/var | `*not shown*` | ✗ |
| `loadedCount` | `any` | let/var | `len` | ✗ |
| `engine` | `string` | let/var | `(document.body && def) ? 'svg' : 'canvas'` | ✗ |
| `helper` | `any` | let/var | `*not shown*` | ✗ |
| `fontArr` | `any` | let/var | `fontData.list` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `fontArr.length` | ✗ |
| `_pendingFonts` | `any` | let/var | `len` | ✗ |
| `shouldLoadFont` | `boolean` | let/var | `true` | ✗ |
| `loadedSelector` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `chars.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `number` | let/var | `this.chars.length` | ✗ |
| `found` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.chars.length` | ✗ |
| `tHelper` | `any` | let/var | `fontData.helper` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.fonts.length` | ✗ |
| `sum` | `any` | let/var | `firstCharCode.toString(16) + secondCharCode.toString(16)` | ✗ |
| `fontPrototype` | `{ addChars: typeof addChars; addFonts...` | let/var | `{ addChars: addChars, addFonts: addFonts, getCharData: getCharData, getFontBy...` | ✗ |
| `FontManager` | `typeof Font` | let/var | `(function () { var maxWaitingTime = 5000; var emptyChar = { w: 0, size: 0, sh...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.renderableComponents.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `maskManager.viewData.length` | ✗ |
| `MaskManagerInterface` | `(maskManager: any) => (name: any) => any` | let/var | `(function () { function MaskInterface(mask, data) { this._mask = mask; this._...` | ✗ |
| `defaultUnidimensionalValue` | `{ pv: number; v: number; mult: number; }` | let/var | `{ pv: 0, v: 0, mult: 1 }` | ✗ |
| `defaultMultidimensionalValue` | `{ pv: number[]; v: number[]; mult: nu...` | let/var | `{ pv: [0, 0, 0], v: [0, 0, 0], mult: 1 }` | ✗ |
| `value` | `string` | let/var | `''` | ✗ |
| `valueProp` | `string \| Number` | let/var | `type === 'unidimensional' ? new Number(value) : Object.assign({}, value)` | ✗ |
| `mult` | `number` | let/var | `1 / property.mult` | ✗ |
| `val` | `number` | let/var | `property.pv * mult` | ✗ |
| `expressionValue` | `Number` | let/var | `new Number(val)` | ✗ |
| `mult` | `number` | let/var | `1 / property.mult` | ✗ |
| `len` | `any` | let/var | `(property.data && property.data.l) \|\| property.pv.length` | ✗ |
| `ExpressionPropertyInterface` | `(property: any) => (() => Number) \| ...` | let/var | `(function () { var defaultUnidimensionalValue = { pv: 0, v: 0, mult: 1 }; var...` | ✗ |
| `_px` | `any` | let/var | `*not shown*` | ✗ |
| `_py` | `any` | let/var | `*not shown*` | ✗ |
| `_pz` | `any` | let/var | `*not shown*` | ✗ |
| `_transformFactory` | `any` | let/var | `*not shown*` | ✗ |
| `TransformExpressionInterface` | `(transform: any) => { (name: any): an...` | let/var | `(function () { return function (transform) { function _thisFunction(name) { s...` | ✗ |
| `toWorldMat` | `(Anonymous function)` | let/var | `new Matrix()` | ✗ |
| `transformMat` | `any` | let/var | `this._elem.finalTransform.mProp` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this._elem.hierarchy.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this._elem.hierarchy.length` | ✗ |
| `toWorldMat` | `(Anonymous function)` | let/var | `new Matrix()` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this._elem.hierarchy.length` | ✗ |
| `transformInterface` | `any` | let/var | `*not shown*` | ✗ |
| `LayerExpressionInterface` | `(elem: any) => { (name: any): any; ge...` | let/var | `(function () { function getMatrix(time) { var toWorldMat = new Matrix(); if (...` | ✗ |
| `propertyGroupFactory` | `(interfaceFunction: any, parentProper...` | let/var | `(function () { return function (interfaceFunction, parentPropertyGroup) { ret...` | ✗ |
| `interfaceFunction` | `{ _name: any; }` | let/var | `{ _name: propertyName, }` | ✗ |
| `PropertyInterface` | `(propertyName: any, propertyGroup: an...` | let/var | `(function () { return function (propertyName, propertyGroup) { var interfaceF...` | ✗ |
| `ob` | `{ createEffectsInterface: (elem: any,...` | let/var | `{ createEffectsInterface: createEffectsInterface, }` | ✗ |
| `effectElements` | `any[]` | let/var | `[]` | ✗ |
| `effectsData` | `any` | let/var | `elem.data.ef` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `elem.effectsManager.effectElements.length` | ✗ |
| `effects` | `any` | let/var | `elem.data.ef \|\| []` | ✗ |
| `effects` | `any` | let/var | `data.ef` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `effects.length` | ✗ |
| `effectElements` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `data.ef.length` | ✗ |
| `EffectsExpressionInterface` | `{ createEffectsInterface: (elem: any,...` | let/var | `(function () { var ob = { createEffectsInterface: createEffectsInterface, }; ...` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `comp.layers.length` | ✗ |
| `CompExpressionInterface` | `(comp: any) => { (name: any): any; re...` | let/var | `(function () { return function (comp) { function _thisLayerFunction(name) { v...` | ✗ |
| `prop` | `any` | let/var | `view.sh` | ✗ |
| `ShapePathInterface` | `(shape: any, view: any, propertyGroup...` | let/var | `( function () { return function pathInterfaceFactory(shape, view, propertyGro...` | ✗ |
| `arr` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapes ? shapes.length : 0` | ✗ |
| `interfaces` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `interfaces.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shape.d ? shape.d.length : 0` | ✗ |
| `dashOb` | `{}` | let/var | `{}` | ✗ |
| `prop` | `any` | let/var | `view.sh.ty === 'tm' ? view.sh.prop : view.sh` | ✗ |
| `prop` | `any` | let/var | `view.sh.ty === 'tm' ? view.sh.prop : view.sh` | ✗ |
| `prop` | `any` | let/var | `view.sh.ty === 'tm' ? view.sh.prop : view.sh` | ✗ |
| `prop` | `any` | let/var | `view` | ✗ |
| `prop` | `any` | let/var | `view` | ✗ |
| `interfaces` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `interfaces.length` | ✗ |
| `ShapeExpressionInterface` | `(shapes: any, view: any, propertyGrou...` | let/var | `(function () { function iterateElements(shapes, view, propertyGroup) { var ar...` | ✗ |
| `_prevValue` | `any` | let/var | `*not shown*` | ✗ |
| `_sourceText` | `any` | let/var | `*not shown*` | ✗ |
| `stringValue` | `any` | let/var | `elem.textProperty.currentData.t` | ✗ |
| `TextExpressionInterface` | `(elem: any) => { (name: any): any; re...` | let/var | `(function () { return function (elem) { var _prevValue; var _sourceText; func...` | ✗ |
| `blendModeEnums` | `{ 0: string; 1: string; 2: string; 3:...` | let/var | `{ 0: 'source-over', 1: 'multiply', 2: 'screen', 3: 'overlay', 4: 'darken', 5:...` | ✗ |
| `getBlendMode` | `(mode: any) => any` | let/var | `(function () { var blendModeEnums = { 0: 'source-over', 1: 'multiply', 2: 'sc...` | ✗ |
| `effects` | `any` | let/var | `data.ef \|\| []` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `effects.length` | ✗ |
| `effectItem` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.data.ef.length` | ✗ |
| `eff` | `any` | let/var | `*not shown*` | ✗ |
| `effects` | `any` | let/var | `this.data.ef` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.data.masksProperties.length` | ✗ |
| `elem` | `any` | let/var | `this.baseElement \|\| this.layerElement` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.dynamicProperties.length` | ✗ |
| `currentPropertyName` | `string` | let/var | `''` | ✗ |
| `outlineInterfaceFactory` | `(elem: any) => () => (value: any) => any` | let/var | `(function (elem) { var currentPropertyName = ''; var currentProperty = elem.g...` | ✗ |
| `FootageInterface` | `(elem: any) => { (value: any): { (val...` | let/var | `(function () { var outlineInterfaceFactory = (function (elem) { var currentPr...` | ✗ |
| `timeRemapped` | `any` | let/var | `this.tm.v` | ✗ |
| `totalVolume` | `number` | let/var | `this._volume * this._volumeMultiplier` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `newLayers.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `this.layers.length` | ✗ |
| `elements` | `any` | let/var | `this.elements` | ✗ |
| `layers` | `any` | let/var | `this.layers` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `layers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `assets.length` | ✗ |
| `element` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.elements.length` | ✗ |
| `mat` | `any` | let/var | `*not shown*` | ✗ |
| `finalMat` | `any` | let/var | `this.finalTransform.mat` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.hierarchy.length` | ✗ |
| `transforms` | `any[]` | let/var | `[]` | ✗ |
| `flag` | `boolean` | let/var | `true` | ✗ |
| `comp` | `any` | let/var | `this.comp` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `transforms.length` | ✗ |
| `ptNew` | `any` | let/var | `*not shown*` | ✗ |
| `defs` | `any` | let/var | `this.globalData.defs` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.masksProperties ? this.masksProperties.length : 0` | ✗ |
| `path` | `any` | let/var | `*not shown*` | ✗ |
| `properties` | `any` | let/var | `this.masksProperties` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `currentMasks` | `any[]` | let/var | `[]` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `rect` | `any` | let/var | `*not shown*` | ✗ |
| `expansor` | `any` | let/var | `*not shown*` | ✗ |
| `feMorph` | `any` | let/var | `*not shown*` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `maskType` | `string` | let/var | `'clipPath'` | ✗ |
| `maskRef` | `string` | let/var | `'clip-path'` | ✗ |
| `filterID` | `any` | let/var | `*not shown*` | ✗ |
| `finalMat` | `any` | let/var | `this.element.finalTransform.mat` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.masksProperties.length` | ✗ |
| `feMorph` | `any` | let/var | `this.storedData[i].expan` | ✗ |
| `path` | `string` | let/var | `'M0,0 '` | ✗ |
| `pathString` | `string` | let/var | `' M' + pathNodes.v[0][0] + ',' + pathNodes.v[0][1]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `pathShapeValue` | `string` | let/var | `''` | ✗ |
| `ob` | `{ createFilter: (filId: any, skipCoor...` | let/var | `{}` | ✗ |
| `filtersFactory` | `{ createFilter: (filId: any, skipCoor...` | let/var | `(function () { var ob = {}; ob.createFilter = createFilter; ob.createAlphaToL...` | ✗ |
| `ob` | `{ maskType: boolean; }` | let/var | `{ maskType: true, }` | ✗ |
| `featureSupport` | `{ maskType: boolean; }` | let/var | `(function () { var ob = { maskType: true, }; if (/MSIE 10/i.test(navigator.us...` | ✗ |
| `registeredEffects` | `{}` | let/var | `{}` | ✗ |
| `idPrefix` | `string` | let/var | `'filter_result_'` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `source` | `string` | let/var | `'SourceGraphic'` | ✗ |
| `len` | `any` | let/var | `elem.data.ef ? elem.data.ef.length : 0` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `filterManager` | `any` | let/var | `*not shown*` | ✗ |
| `type` | `any` | let/var | `elem.data.ef[i].ty` | ✗ |
| `Effect` | `any` | let/var | `registeredEffects[type].effect` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.filters.length` | ✗ |
| `layerElementParent` | `any` | let/var | `null` | ✗ |
| `filId` | `any` | let/var | `*not shown*` | ✗ |
| `fil` | `any` | let/var | `*not shown*` | ✗ |
| `gg` | `any` | let/var | `*not shown*` | ✗ |
| `elem` | `any` | let/var | `this.baseElement \|\| this.layerElement` | ✗ |
| `elem` | `any` | let/var | `this.baseElement \|\| this.layerElement` | ✗ |
| `_prototype` | `{ initElement: (data: any, globalData...` | let/var | `{ initElement: function (data, globalData, comp) { this.initFrame(); this.ini...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.shapeModifiers.length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.shapeModifiers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.shapes.length` | ✗ |
| `shouldBreakProcess` | `any` | let/var | `*not shown*` | ✗ |
| `elements` | `any` | let/var | `this.processedElements` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `elements.length` | ✗ |
| `elements` | `any` | let/var | `this.processedElements` | ✗ |
| `i` | `any` | let/var | `elements.length` | ✗ |
| `lineCapEnum` | `{ 1: string; 2: string; 3: string; }` | let/var | `{ 1: 'butt', 2: 'round', 3: 'square', }` | ✗ |
| `lineJoinEnum` | `{ 1: string; 2: string; 3: string; }` | let/var | `{ 1: 'miter', 2: 'round', 3: 'bevel', }` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `transformers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `data.length \|\| 0` | ✗ |
| `prop` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.dataProps.length` | ✗ |
| `cLength` | `number` | let/var | `data.k.k[0].s ? (data.k.k[0].s.length - data.p * 4) : data.k.k.length - data....` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `number` | let/var | `this.o.length / 2` | ✗ |
| `diff` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.data.k.k.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.data.p * 4` | ✗ |
| `mult` | `any` | let/var | `*not shown*` | ✗ |
| `val` | `any` | let/var | `*not shown*` | ✗ |
| `stops` | `any[]` | let/var | `[]` | ✗ |
| `stop` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `stop` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `stops` | `any` | let/var | `this.stops` | ✗ |
| `_o` | `any` | let/var | `pathNodes.o` | ✗ |
| `_i` | `any` | let/var | `pathNodes.i` | ✗ |
| `_v` | `any` | let/var | `pathNodes.v` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `shapeString` | `string` | let/var | `' M' + mat.applyToPointStringified(_v[0][0], _v[0][1])` | ✗ |
| `_identityMatrix` | `(Anonymous function)` | let/var | `new Matrix()` | ✗ |
| `_matrixHelper` | `(Anonymous function)` | let/var | `new Matrix()` | ✗ |
| `ob` | `{ createRenderFunction: (data: any) =...` | let/var | `{ createRenderFunction: createRenderFunction, }` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `pathStringTransformed` | `any` | let/var | `*not shown*` | ✗ |
| `redraw` | `any` | let/var | `*not shown*` | ✗ |
| `pathNodes` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `lLen` | `any` | let/var | `itemData.styles.length` | ✗ |
| `lvl` | `any` | let/var | `itemData.lvl` | ✗ |
| `paths` | `any` | let/var | `*not shown*` | ✗ |
| `mat` | `any` | let/var | `*not shown*` | ✗ |
| `props` | `any` | let/var | `*not shown*` | ✗ |
| `iterations` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `styleElem` | `any` | let/var | `itemData.style` | ✗ |
| `gfill` | `any` | let/var | `itemData.gf` | ✗ |
| `hasOpacity` | `any` | let/var | `itemData.g._hasOpacity` | ✗ |
| `pt1` | `any` | let/var | `itemData.s.v` | ✗ |
| `pt2` | `any` | let/var | `itemData.e.v` | ✗ |
| `attr` | `string` | let/var | `styleData.ty === 'gf' ? 'fill-opacity' : 'stroke-opacity'` | ✗ |
| `attr1` | `string` | let/var | `styleData.t === 1 ? 'x1' : 'cx'` | ✗ |
| `attr2` | `string` | let/var | `attr1 === 'x1' ? 'y1' : 'cy'` | ✗ |
| `stops` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `stop` | `any` | let/var | `*not shown*` | ✗ |
| `cValues` | `any` | let/var | `itemData.g.c` | ✗ |
| `oValues` | `any` | let/var | `itemData.g.o` | ✗ |
| `rad` | `any` | let/var | `*not shown*` | ✗ |
| `percent` | `any` | let/var | `itemData.h.v` | ✗ |
| `dist` | `number` | let/var | `rad * percent` | ✗ |
| `x` | `any` | let/var | `Math.cos(ang + itemData.a.v) * dist + pt1[0]` | ✗ |
| `y` | `any` | let/var | `Math.sin(ang + itemData.a.v) * dist + pt1[1]` | ✗ |
| `styleElem` | `any` | let/var | `itemData.style` | ✗ |
| `d` | `any` | let/var | `itemData.d` | ✗ |
| `SVGElementsRenderer` | `{ createRenderFunction: (data: any) =...` | let/var | `(function () { var _identityMatrix = new Matrix(); var _matrixHelper = new Ma...` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.shapes.length` | ✗ |
| `shape` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `number` | let/var | `this.stylesList.length` | ✗ |
| `style` | `any` | let/var | `*not shown*` | ✗ |
| `tempShapes` | `any[]` | let/var | `[]` | ✗ |
| `areAnimated` | `boolean` | let/var | `false` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapes.length` | ✗ |
| `elementData` | `any` | let/var | `*not shown*` | ✗ |
| `styleOb` | `SVGStyleData` | let/var | `new SVGStyleData(data, level)` | ✗ |
| `pathElement` | `any` | let/var | `styleOb.pElem` | ✗ |
| `GradientConstructor` | `typeof SVGGradientFillStyleData \| ty...` | let/var | `data.ty === 'gf' ? SVGGradientFillStyleData : SVGGradientStrokeStyleData` | ✗ |
| `elementData` | `ShapeGroupData` | let/var | `new ShapeGroupData()` | ✗ |
| `elementData` | `SVGTransformData` | let/var | `new SVGTransformData(transformProperty, transformProperty.o, container)` | ✗ |
| `ty` | `number` | let/var | `4` | ✗ |
| `elementData` | `SVGShapeData` | let/var | `new SVGShapeData(ownTransformers, level, shapeProperty)` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `number` | let/var | `this.animatedContents.length` | ✗ |
| `arr` | `any` | let/var | `elementData.styles` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `number` | let/var | `this.stylesList.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.itemsData.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `arr.length - 1` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `ownStyles` | `any[]` | let/var | `[]` | ✗ |
| `ownModifiers` | `any[]` | let/var | `[]` | ✗ |
| `currentTransform` | `any` | let/var | `*not shown*` | ✗ |
| `modifier` | `any` | let/var | `*not shown*` | ✗ |
| `processedPos` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.stylesList.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.animatedContents.length` | ✗ |
| `animatedContent` | `any` | let/var | `*not shown*` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `currentValue` | `{ ascent: number; boxWidth: number[];...` | let/var | `this.currentData` | ✗ |
| `currentIndex` | `number` | let/var | `this.keysIndex` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.effectsSequence.length` | ✗ |
| `finalValue` | `any` | let/var | `_finalValue \|\| this.data.d.k[this.keysIndex].s` | ✗ |
| `textKeys` | `any` | let/var | `this.data.d.k` | ✗ |
| `frameNum` | `any` | let/var | `this.elem.comp.renderedFrame` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `textKeys.length` | ✗ |
| `charactersArray` | `any[]` | let/var | `[]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `text.length` | ✗ |
| `charCode` | `any` | let/var | `*not shown*` | ✗ |
| `secondCharCode` | `any` | let/var | `*not shown*` | ✗ |
| `shouldCombine` | `boolean` | let/var | `false` | ✗ |
| `fontManager` | `any` | let/var | `this.elem.globalData.fontManager` | ✗ |
| `data` | `any` | let/var | `this.data` | ✗ |
| `letters` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `newLineFlag` | `any` | let/var | `*not shown*` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `val` | `any` | let/var | `*not shown*` | ✗ |
| `anchorGrouping` | `any` | let/var | `data.m.g` | ✗ |
| `currentSize` | `number` | let/var | `0` | ✗ |
| `currentPos` | `number` | let/var | `0` | ✗ |
| `currentLine` | `number` | let/var | `0` | ✗ |
| `lineWidths` | `any[]` | let/var | `[]` | ✗ |
| `lineWidth` | `number` | let/var | `0` | ✗ |
| `maxLineWidth` | `number` | let/var | `0` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `charData` | `any` | let/var | `*not shown*` | ✗ |
| `cLength` | `number` | let/var | `0` | ✗ |
| `trackingOffset` | `number` | let/var | `(documentData.tr / 1000) * documentData.finalSize` | ✗ |
| `charCode` | `any` | let/var | `*not shown*` | ✗ |
| `flag` | `boolean` | let/var | `true` | ✗ |
| `boxWidth` | `any` | let/var | `documentData.sz[0]` | ✗ |
| `boxHeight` | `any` | let/var | `documentData.sz[1]` | ✗ |
| `currentHeight` | `any` | let/var | `*not shown*` | ✗ |
| `finalText` | `any` | let/var | `*not shown*` | ✗ |
| `lastSpaceIndex` | `number` | let/var | `-1` | ✗ |
| `uncollapsedSpaces` | `number` | let/var | `0` | ✗ |
| `currentChar` | `any` | let/var | `*not shown*` | ✗ |
| `animators` | `any` | let/var | `data.a` | ✗ |
| `animatorData` | `any` | let/var | `*not shown*` | ✗ |
| `letterData` | `any` | let/var | `*not shown*` | ✗ |
| `based` | `any` | let/var | `*not shown*` | ✗ |
| `ind` | `any` | let/var | `*not shown*` | ✗ |
| `indexes` | `any[]` | let/var | `[]` | ✗ |
| `currentInd` | `number` | let/var | `-1` | ✗ |
| `newInd` | `any` | let/var | `*not shown*` | ✗ |
| `dData` | `any` | let/var | `this.data.d.k[index].s` | ✗ |
| `max` | `(...values: number[]) => number` | let/var | `Math.max` | ✗ |
| `min` | `(...values: number[]) => number` | let/var | `Math.min` | ✗ |
| `floor` | `(x: number) => number` | let/var | `Math.floor` | ✗ |
| `x1` | `number` | let/var | `0` | ✗ |
| `y1` | `number` | let/var | `0` | ✗ |
| `x2` | `number` | let/var | `1` | ✗ |
| `y2` | `number` | let/var | `1` | ✗ |
| `easer` | `any` | let/var | `BezierFactory.getBezierEasing(x1, y1, x2, y2).get` | ✗ |
| `mult` | `number` | let/var | `0` | ✗ |
| `s` | `number` | let/var | `this.finalS` | ✗ |
| `e` | `number` | let/var | `this.finalE` | ✗ |
| `type` | `any` | let/var | `this.data.sh` | ✗ |
| `tot` | `number` | let/var | `e - s` | ✗ |
| `x` | `any` | let/var | `-tot / 2 + ind` | ✗ |
| `a` | `number` | let/var | `tot / 2` | ✗ |
| `smoothness` | `number` | let/var | `this.sm.v * 0.01` | ✗ |
| `threshold` | `number` | let/var | `0.5 - smoothness * 0.5` | ✗ |
| `divisor` | `number` | let/var | `this.data.r === 2 ? 1 : 100 / this.data.totalChars` | ✗ |
| `o` | `number` | let/var | `this.o.v / divisor` | ✗ |
| `s` | `number` | let/var | `this.s.v / divisor + o` | ✗ |
| `e` | `number` | let/var | `(this.e.v / divisor) + o` | ✗ |
| `_s` | `number` | let/var | `s` | ✗ |
| `TextSelectorProp` | `{ getTextSelectorProp: (elem: any, da...` | let/var | `(function () { var max = Math.max; var min = Math.min; var floor = Math.floor...` | ✗ |
| `defaultData` | `{ propType: boolean; }` | let/var | `{ propType: false }` | ✗ |
| `getProp` | `(elem: any, data: any, type: any, mul...` | let/var | `PropertyFactory.getProp` | ✗ |
| `textAnimatorAnimatables` | `any` | let/var | `animatorProps.a` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this._textData.a.length` | ✗ |
| `animatorProps` | `any` | let/var | `*not shown*` | ✗ |
| `getProp` | `(elem: any, data: any, type: any, mul...` | let/var | `PropertyFactory.getProp` | ✗ |
| `alignment` | `any` | let/var | `this._moreOptions.alignment.v` | ✗ |
| `animators` | `any` | let/var | `this._animatorsData` | ✗ |
| `textData` | `any` | let/var | `this._textData` | ✗ |
| `matrixHelper` | `(Anonymous function)` | let/var | `this.mHelper` | ✗ |
| `renderType` | `any` | let/var | `this._renderType` | ✗ |
| `renderedLettersCount` | `number` | let/var | `this.renderedLetters.length` | ✗ |
| `xPos` | `any` | let/var | `*not shown*` | ✗ |
| `yPos` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `letters` | `any` | let/var | `documentData.l` | ✗ |
| `pathInfo` | `any` | let/var | `*not shown*` | ✗ |
| `currentLength` | `any` | let/var | `*not shown*` | ✗ |
| `currentPoint` | `any` | let/var | `*not shown*` | ✗ |
| `segmentLength` | `any` | let/var | `*not shown*` | ✗ |
| `flag` | `any` | let/var | `*not shown*` | ✗ |
| `pointInd` | `any` | let/var | `*not shown*` | ✗ |
| `segmentInd` | `any` | let/var | `*not shown*` | ✗ |
| `prevPoint` | `any` | let/var | `*not shown*` | ✗ |
| `points` | `any` | let/var | `*not shown*` | ✗ |
| `segments` | `any` | let/var | `*not shown*` | ✗ |
| `partialLength` | `any` | let/var | `*not shown*` | ✗ |
| `totalLength` | `any` | let/var | `*not shown*` | ✗ |
| `perc` | `any` | let/var | `*not shown*` | ✗ |
| `tanAngle` | `any` | let/var | `*not shown*` | ✗ |
| `mask` | `any` | let/var | `*not shown*` | ✗ |
| `paths` | `any` | let/var | `mask.v` | ✗ |
| `bezierData` | `any` | let/var | `*not shown*` | ✗ |
| `yOff` | `number` | let/var | `documentData.finalSize * 1.2 * 0.714` | ✗ |
| `firstLine` | `boolean` | let/var | `true` | ✗ |
| `animatorProps` | `any` | let/var | `*not shown*` | ✗ |
| `animatorSelector` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `letterValue` | `any` | let/var | `*not shown*` | ✗ |
| `mult` | `any` | let/var | `*not shown*` | ✗ |
| `ind` | `number` | let/var | `-1` | ✗ |
| `offf` | `any` | let/var | `*not shown*` | ✗ |
| `xPathPos` | `any` | let/var | `*not shown*` | ✗ |
| `yPathPos` | `any` | let/var | `*not shown*` | ✗ |
| `initPathPos` | `any` | let/var | `currentLength` | ✗ |
| `initSegmentInd` | `number` | let/var | `segmentInd` | ✗ |
| `initPointInd` | `number` | let/var | `pointInd` | ✗ |
| `currentLine` | `number` | let/var | `-1` | ✗ |
| `elemOpacity` | `any` | let/var | `*not shown*` | ✗ |
| `sc` | `any` | let/var | `*not shown*` | ✗ |
| `sw` | `any` | let/var | `*not shown*` | ✗ |
| `fc` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `letterSw` | `any` | let/var | `*not shown*` | ✗ |
| `letterSc` | `any` | let/var | `*not shown*` | ✗ |
| `letterFc` | `any` | let/var | `*not shown*` | ✗ |
| `letterM` | `string` | let/var | `''` | ✗ |
| `letterP` | `any[]` | let/var | `this.defaultPropsArray` | ✗ |
| `letterO` | `any` | let/var | `*not shown*` | ✗ |
| `animatorJustifyOffset` | `number` | let/var | `0` | ✗ |
| `animatorFirstCharOffset` | `number` | let/var | `0` | ✗ |
| `justifyOffsetMult` | `number` | let/var | `documentData.j === 2 ? -0.5 : -1` | ✗ |
| `lastIndex` | `number` | let/var | `0` | ✗ |
| `isNewLine` | `boolean` | let/var | `true` | ✗ |
| `animatorOffset` | `number` | let/var | `0` | ✗ |
| `rot` | `number` | let/var | `(Math.atan(tanAngle) * 180) / Math.PI` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `shapes.length` | ✗ |
| `pathNodes` | `any` | let/var | `*not shown*` | ✗ |
| `shapeStr` | `string` | let/var | `''` | ✗ |
| `emptyShapeData` | `{ shapes: any[]; }` | let/var | `{ shapes: [], }` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `textArray.length` | ✗ |
| `textContents` | `any[]` | let/var | `[]` | ✗ |
| `currentTextContent` | `string` | let/var | `''` | ✗ |
| `shape` | `any` | let/var | `data.shapes[0]` | ✗ |
| `shapeItem` | `any` | let/var | `shape.it[shape.it.length - 1]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `documentData` | `any` | let/var | `this.textProperty.currentData` | ✗ |
| `fWeight` | `any` | let/var | `documentData.fWeight` | ✗ |
| `fStyle` | `any` | let/var | `documentData.fStyle` | ✗ |
| `letters` | `any` | let/var | `documentData.l \|\| []` | ✗ |
| `usesGlyphs` | `boolean` | let/var | `!!this.globalData.fontManager.chars` | ✗ |
| `tSpan` | `any` | let/var | `*not shown*` | ✗ |
| `matrixHelper` | `any` | let/var | `this.mHelper` | ✗ |
| `shapeStr` | `string` | let/var | `''` | ✗ |
| `singleShape` | `any` | let/var | `this.data.singleShape` | ✗ |
| `xPos` | `number` | let/var | `0` | ✗ |
| `yPos` | `number` | let/var | `0` | ✗ |
| `firstLine` | `boolean` | let/var | `true` | ✗ |
| `trackingOffset` | `number` | let/var | `documentData.tr * 0.001 * documentData.finalSize` | ✗ |
| `tElement` | `any` | let/var | `this.textContainer` | ✗ |
| `justify` | `string` | let/var | `'start'` | ✗ |
| `cachedSpansLength` | `number` | let/var | `this.textSpans.length` | ✗ |
| `charData` | `any` | let/var | `*not shown*` | ✗ |
| `glyphElement` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `{ shapes: any[]; }` | let/var | `emptyShapeData` | ✗ |
| `glyph` | `any` | let/var | `this.textSpans[i].glyph` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.textSpans.length` | ✗ |
| `glyphElement` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `renderedLetters` | `any` | let/var | `this.textAnimator.renderedLetters` | ✗ |
| `letters` | `any` | let/var | `this.textProperty.currentData.l` | ✗ |
| `renderedLetter` | `any` | let/var | `*not shown*` | ✗ |
| `textSpan` | `any` | let/var | `*not shown*` | ✗ |
| `glyphElement` | `any` | let/var | `*not shown*` | ✗ |
| `defs` | `any` | let/var | `this.globalData.defs` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers ? this.layers.length : 0` | ✗ |
| `elements` | `any` | let/var | `this.elements` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `this.elements.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `nextElement` | `any` | let/var | `*not shown*` | ✗ |
| `timeRemapped` | `any` | let/var | `this.tm.v` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.elements.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `ariaLabel` | `string` | let/var | `''` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `15` | ✗ |
| `newLength` | `number` | let/var | `this._length * 2` | ✗ |
| `currentSavedOp` | `number[] \| Float32Array<any> \| Int1...` | let/var | `this.savedOp` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `transforms.length` | ✗ |
| `key` | `string` | let/var | `'_'` | ✗ |
| `sequence` | `any` | let/var | `this.sequences[key]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `sequence.transforms.length` | ✗ |
| `_mdf` | `any` | let/var | `isFirstFrame` | ✗ |
| `props` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.sequenceList.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.masksProperties.length` | ✗ |
| `hasMasks` | `boolean` | let/var | `false` | ✗ |
| `transform` | `any` | let/var | `this.element.finalTransform.mat` | ✗ |
| `ctx` | `any` | let/var | `this.element.canvasContext` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.masksProperties.length` | ✗ |
| `pt` | `any` | let/var | `*not shown*` | ✗ |
| `pts` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `data._length` | ✗ |
| `globalData` | `any` | let/var | `this.globalData` | ✗ |
| `forceRealStack` | `boolean` | let/var | `this.data.ty === 0` | ✗ |
| `ty` | `number` | let/var | `4` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `styles.length` | ✗ |
| `styledShape` | `any` | let/var | `*not shown*` | ✗ |
| `styleElem` | `{ data: any; type: any; preTransforms...` | let/var | `{ data: data, type: data.ty, preTransforms: this.transformsManager.addTransfo...` | ✗ |
| `elementData` | `{ c: ValueProperty \| MultiDimensiona...` | let/var | `{}` | ✗ |
| `d` | `DashProperty` | let/var | `new DashProperty(this, data.d, 'canvas', this)` | ✗ |
| `elementData` | `{ it: any[]; prevViewData: any[]; }` | let/var | `{ it: [], prevViewData: [], }` | ✗ |
| `elementData` | `{ transform: { opacity: number; _opMd...` | let/var | `{ transform: { opacity: 1, _opMdf: false, key: this.transformsManager.getNewK...` | ✗ |
| `elementData` | `CVShapeData` | let/var | `new CVShapeData(this, data, this.stylesList, this.transformsManager)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.itemsData.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.stylesList.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.stylesList.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `styles.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `arr.length - 1` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `ownStyles` | `any[]` | let/var | `[]` | ✗ |
| `ownModifiers` | `any[]` | let/var | `[]` | ✗ |
| `processedPos` | `any` | let/var | `*not shown*` | ✗ |
| `modifier` | `any` | let/var | `*not shown*` | ✗ |
| `currentTransform` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `this.stylesList.length` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `kLen` | `any` | let/var | `*not shown*` | ✗ |
| `elems` | `any` | let/var | `*not shown*` | ✗ |
| `nodes` | `any` | let/var | `*not shown*` | ✗ |
| `renderer` | `any` | let/var | `this.globalData.renderer` | ✗ |
| `ctx` | `any` | let/var | `this.globalData.canvasContext` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `currentStyle` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `items.length - 1` | ✗ |
| `groupTransform` | `any` | let/var | `*not shown*` | ✗ |
| `shapeNodes` | `any` | let/var | `styledShape.trNodes` | ✗ |
| `paths` | `any` | let/var | `shape.paths` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `paths._length` | ✗ |
| `groupTransformMat` | `any` | let/var | `styledShape.transforms.finalTransform` | ✗ |
| `pathNodes` | `any` | let/var | `paths.shapes[j]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `itemData.styledShapes.length` | ✗ |
| `styleElem` | `any` | let/var | `itemData.style` | ✗ |
| `styleElem` | `any` | let/var | `itemData.style` | ✗ |
| `grd` | `any` | let/var | `*not shown*` | ✗ |
| `ctx` | `any` | let/var | `this.globalData.canvasContext` | ✗ |
| `pt1` | `any` | let/var | `itemData.s.v` | ✗ |
| `pt2` | `any` | let/var | `itemData.e.v` | ✗ |
| `percent` | `any` | let/var | `itemData.h.v` | ✗ |
| `dist` | `number` | let/var | `rad * percent` | ✗ |
| `x` | `any` | let/var | `Math.cos(ang + itemData.a.v) * dist + pt1[0]` | ✗ |
| `y` | `any` | let/var | `Math.sin(ang + itemData.a.v) * dist + pt1[1]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `styleData.g.p` | ✗ |
| `cValues` | `any` | let/var | `itemData.g.c` | ✗ |
| `opacity` | `number` | let/var | `1` | ✗ |
| `styleElem` | `any` | let/var | `itemData.style` | ✗ |
| `d` | `any` | let/var | `itemData.d` | ✗ |
| `documentData` | `any` | let/var | `this.textProperty.currentData` | ✗ |
| `hasFill` | `boolean` | let/var | `false` | ✗ |
| `hasStroke` | `boolean` | let/var | `false` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `letters` | `any` | let/var | `documentData.l` | ✗ |
| `matrixHelper` | `any` | let/var | `this.mHelper` | ✗ |
| `charData` | `any` | let/var | `*not shown*` | ✗ |
| `shapeData` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `kLen` | `any` | let/var | `*not shown*` | ✗ |
| `shapes` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `pathNodes` | `any` | let/var | `*not shown*` | ✗ |
| `commands` | `any` | let/var | `*not shown*` | ✗ |
| `pathArr` | `any` | let/var | `*not shown*` | ✗ |
| `singleShape` | `any` | let/var | `this.data.singleShape` | ✗ |
| `trackingOffset` | `number` | let/var | `documentData.tr * 0.001 * documentData.finalSize` | ✗ |
| `xPos` | `number` | let/var | `0` | ✗ |
| `yPos` | `number` | let/var | `0` | ✗ |
| `firstLine` | `boolean` | let/var | `true` | ✗ |
| `cnt` | `number` | let/var | `0` | ✗ |
| `commandsCounter` | `number` | let/var | `0` | ✗ |
| `ctx` | `any` | let/var | `this.canvasContext` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jLen` | `any` | let/var | `*not shown*` | ✗ |
| `k` | `any` | let/var | `*not shown*` | ✗ |
| `kLen` | `any` | let/var | `*not shown*` | ✗ |
| `renderedLetters` | `any` | let/var | `this.textAnimator.renderedLetters` | ✗ |
| `letters` | `any` | let/var | `this.textProperty.currentData.l` | ✗ |
| `renderedLetter` | `any` | let/var | `*not shown*` | ✗ |
| `lastFill` | `any` | let/var | `null` | ✗ |
| `lastStroke` | `any` | let/var | `null` | ✗ |
| `lastStrokeW` | `any` | let/var | `null` | ✗ |
| `commands` | `any` | let/var | `*not shown*` | ✗ |
| `pathArr` | `any` | let/var | `*not shown*` | ✗ |
| `imgW` | `any` | let/var | `this.img.width` | ✗ |
| `imgH` | `any` | let/var | `this.img.height` | ✗ |
| `imgRel` | `number` | let/var | `imgW / imgH` | ✗ |
| `canvasRel` | `number` | let/var | `this.assetData.w / this.assetData.h` | ✗ |
| `widthCrop` | `any` | let/var | `*not shown*` | ✗ |
| `heightCrop` | `any` | let/var | `*not shown*` | ✗ |
| `par` | `any` | let/var | `this.assetData.pr \|\| this.globalData.renderConfig.imagePreserveAspectRatio` | ✗ |
| `ctx` | `any` | let/var | `this.canvasContext` | ✗ |
| `cProps` | `number[] \| Float32Array<any> \| Int1...` | let/var | `this.contextData.cTr.props` | ✗ |
| `trProps` | `number[] \| Float32Array<any> \| Int1...` | let/var | `this.contextData.cTr.props` | ✗ |
| `props` | `number[] \| Float32Array<any> \| Int1...` | let/var | `this.contextData.cTr.props` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `arr` | `number[] \| Float32Array<any> \| Int1...` | let/var | `this.contextData.saved[this.contextData.cArrPos]` | ✗ |
| `popped` | `number[] \| Float32Array<any> \| Int1...` | let/var | `this.contextData.saved[this.contextData.cArrPos]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `arr` | `number[] \| Float32Array<any> \| Int1...` | let/var | `this.contextData.cTr.props` | ✗ |
| `containerStyle` | `any` | let/var | `this.animationItem.container.style` | ✗ |
| `origin` | `string` | let/var | `'0px 0px 0px'` | ✗ |
| `elementWidth` | `any` | let/var | `*not shown*` | ✗ |
| `elementHeight` | `any` | let/var | `*not shown*` | ✗ |
| `elementRel` | `any` | let/var | `*not shown*` | ✗ |
| `animationRel` | `any` | let/var | `*not shown*` | ✗ |
| `fillType` | `any` | let/var | `par[1] \|\| 'meet'` | ✗ |
| `pos` | `any` | let/var | `par[0] \|\| 'xMidYMid'` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers ? this.layers.length : 0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `elements` | `any[]` | let/var | `this.elements` | ✗ |
| `ctx` | `any` | let/var | `this.canvasContext` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `this.layers.length` | ✗ |
| `ob` | `{ initExpressions: (animation: any) =...` | let/var | `{}` | ✗ |
| `stackCount` | `number` | let/var | `0` | ✗ |
| `registers` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `registers.length` | ✗ |
| `Expressions` | `{ initExpressions: (animation: any) =...` | let/var | `(function () { var ob = {}; ob.initExpressions = initExpressions; function in...` | ✗ |
| `global` | `any` | let/var | `this` | ✗ |
| `width` | `number` | let/var | `256` | ✗ |
| `chunks` | `number` | let/var | `6` | ✗ |
| `digits` | `number` | let/var | `52` | ✗ |
| `rngname` | `string` | let/var | `'random'` | ✗ |
| `overflow` | `number` | let/var | `significance * 2` | ✗ |
| `mask` | `number` | let/var | `width - 1` | ✗ |
| `nodecrypto` | `any` | let/var | `*not shown*` | ✗ |
| `key` | `any[]` | let/var | `[]` | ✗ |
| `arc4` | `ARC4` | let/var | `new ARC4(key)` | ✗ |
| `d` | `any` | let/var | `startdenom` | ✗ |
| `x` | `number` | let/var | `0` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `keylen` | `any` | let/var | `key.length` | ✗ |
| `me` | `this` | let/var | `this` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `j` | `number` | let/var | `me.i = me.j = 0` | ✗ |
| `s` | `any[]` | let/var | `me.S = []` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `r` | `number` | let/var | `0` | ✗ |
| `i` | `number` | let/var | `me.i` | ✗ |
| `j` | `number` | let/var | `me.j` | ✗ |
| `s` | `any[]` | let/var | `me.S` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `typ` | `"string" \| "number" \| "bigint" \| "...` | let/var | `(typeof obj)` | ✗ |
| `prop` | `any` | let/var | `*not shown*` | ✗ |
| `stringseed` | `string` | let/var | `seed + ''` | ✗ |
| `smear` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `number` | let/var | `0` | ✗ |
| `out` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(width)` | ✗ |
| `browser` | `any` | let/var | `global.navigator` | ✗ |
| `plugins` | `any` | let/var | `browser && browser.plugins` | ✗ |
| `propTypes` | `{ SHAPE: string; }` | let/var | `{ SHAPE: 'shape', }` | ✗ |
| `ob` | `{ initiateExpression: (elem: any, dat...` | let/var | `{}` | ✗ |
| `Math` | `{ random: () => number; abs(val: any)...` | let/var | `BMMath` | ✗ |
| `window` | `any` | let/var | `null` | ✗ |
| `document` | `any` | let/var | `null` | ✗ |
| `XMLHttpRequest` | `any` | let/var | `null` | ✗ |
| `fetch` | `any` | let/var | `null` | ✗ |
| `frames` | `any` | let/var | `null` | ✗ |
| `tOfA` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof a` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `lenA` | `any` | let/var | `a.length` | ✗ |
| `retArr` | `any[]` | let/var | `[]` | ✗ |
| `easeInBez` | `any` | let/var | `BezierFactory.getBezierEasing(0.333, 0, 0.833, 0.833, 'easeIn').get` | ✗ |
| `easeOutBez` | `any` | let/var | `BezierFactory.getBezierEasing(0.167, 0.167, 0.667, 1, 'easeOut').get` | ✗ |
| `easeInOutBez` | `any` | let/var | `BezierFactory.getBezierEasing(0.33, 0, 0.667, 1, 'easeInOut').get` | ✗ |
| `tOfA` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof a` | ✗ |
| `tOfB` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof b` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `lenA` | `any` | let/var | `a.length` | ✗ |
| `lenB` | `any` | let/var | `b.length` | ✗ |
| `retArr` | `any[]` | let/var | `[]` | ✗ |
| `add` | `(a: any, b: any) => any` | let/var | `sum` | ✗ |
| `tOfA` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof a` | ✗ |
| `tOfB` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof b` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `lenA` | `any` | let/var | `a.length` | ✗ |
| `lenB` | `any` | let/var | `b.length` | ✗ |
| `retArr` | `any[]` | let/var | `[]` | ✗ |
| `tOfA` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof a` | ✗ |
| `tOfB` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof b` | ✗ |
| `arr` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `tOfA` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof a` | ✗ |
| `tOfB` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof b` | ✗ |
| `arr` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `$bm_sum` | `(a: any, b: any) => any` | let/var | `sum` | ✗ |
| `$bm_sub` | `(a: any, b: any) => any` | let/var | `sub` | ✗ |
| `$bm_mul` | `(a: any, b: any) => number \| number[...` | let/var | `mul` | ✗ |
| `$bm_div` | `(a: any, b: any) => number \| number[...` | let/var | `div` | ✗ |
| `$bm_mod` | `(a: any, b: any) => number` | let/var | `mod` | ✗ |
| `mm` | `any` | let/var | `max` | ✗ |
| `radians_to_degrees` | `(val: any) => number` | let/var | `radiansToDegrees` | ✗ |
| `degrees_to_radians` | `(val: any) => number` | let/var | `radiansToDegrees` | ✗ |
| `helperLengthArray` | `number[]` | let/var | `[0, 0, 0, 0, 0, 0]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `addedLength` | `number` | let/var | `0` | ✗ |
| `r` | `any` | let/var | `val[0]` | ✗ |
| `g` | `any` | let/var | `val[1]` | ✗ |
| `b` | `any` | let/var | `val[2]` | ✗ |
| `h` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `number` | let/var | `(max + min) / 2` | ✗ |
| `d` | `number` | let/var | `max - min` | ✗ |
| `h` | `any` | let/var | `val[0]` | ✗ |
| `s` | `any` | let/var | `val[1]` | ✗ |
| `l` | `any` | let/var | `val[2]` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `g` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `any` | let/var | `*not shown*` | ✗ |
| `q` | `number` | let/var | `l < 0.5 ? l * (1 + s) : l + s - l * s` | ✗ |
| `p` | `number` | let/var | `2 * l - q` | ✗ |
| `_tMin` | `any` | let/var | `tMax` | ✗ |
| `perc` | `number` | let/var | `tMax === tMin ? 0 : (t - tMin) / (tMax - tMin)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `value1.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `max.length` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `points.length` | ✗ |
| `arrPlaceholder` | `number[]` | let/var | `[0, 0]` | ✗ |
| `inVertexPoint` | `any` | let/var | `*not shown*` | ✗ |
| `outVertexPoint` | `any` | let/var | `*not shown*` | ✗ |
| `val` | `any` | let/var | `data.x` | ✗ |
| `_needsRandom` | `boolean` | let/var | `val.indexOf('random') !== -1` | ✗ |
| `elemType` | `any` | let/var | `elem.data.ty` | ✗ |
| `transform` | `any` | let/var | `*not shown*` | ✗ |
| `$bm_transform` | `any` | let/var | `*not shown*` | ✗ |
| `content` | `any` | let/var | `*not shown*` | ✗ |
| `effect` | `any` | let/var | `*not shown*` | ✗ |
| `thisProperty` | `any` | let/var | `property` | ✗ |
| `inPoint` | `number` | let/var | `elem.data.ip / elem.comp.globalData.frameRate` | ✗ |
| `outPoint` | `number` | let/var | `elem.data.op / elem.comp.globalData.frameRate` | ✗ |
| `width` | `any` | let/var | `elem.data.sw ? elem.data.sw : 0` | ✗ |
| `height` | `any` | let/var | `elem.data.sh ? elem.data.sh : 0` | ✗ |
| `name` | `any` | let/var | `elem.data.nm` | ✗ |
| `loopIn` | `any` | let/var | `*not shown*` | ✗ |
| `loop_in` | `any` | let/var | `*not shown*` | ✗ |
| `loopOut` | `any` | let/var | `*not shown*` | ✗ |
| `loop_out` | `any` | let/var | `*not shown*` | ✗ |
| `smooth` | `any` | let/var | `*not shown*` | ✗ |
| `toWorld` | `any` | let/var | `*not shown*` | ✗ |
| `fromWorld` | `any` | let/var | `*not shown*` | ✗ |
| `fromComp` | `any` | let/var | `*not shown*` | ✗ |
| `toComp` | `any` | let/var | `*not shown*` | ✗ |
| `fromCompToSurface` | `any` | let/var | `*not shown*` | ✗ |
| `position` | `any` | let/var | `*not shown*` | ✗ |
| `rotation` | `any` | let/var | `*not shown*` | ✗ |
| `anchorPoint` | `any` | let/var | `*not shown*` | ✗ |
| `scale` | `any` | let/var | `*not shown*` | ✗ |
| `thisLayer` | `any` | let/var | `*not shown*` | ✗ |
| `thisComp` | `any` | let/var | `*not shown*` | ✗ |
| `mask` | `any` | let/var | `*not shown*` | ✗ |
| `valueAtTime` | `any` | let/var | `*not shown*` | ✗ |
| `velocityAtTime` | `any` | let/var | `*not shown*` | ✗ |
| `scoped_bm_rt` | `any` | let/var | `*not shown*` | ✗ |
| `expression_function` | `any` | let/var | `eval('[function _expression_function(){' + val + ';scoped_bm_rt=$bm_rt}]')[0]` | ✗ |
| `numKeys` | `any` | let/var | `property.kf ? data.k.length : 0` | ✗ |
| `active` | `boolean` | let/var | `!this.data \|\| this.data.hd !== true` | ✗ |
| `iWiggle` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `lenWiggle` | `any` | let/var | `this.pv.length ? this.pv.length : 1` | ✗ |
| `periods` | `number` | let/var | `time * freq` | ✗ |
| `perc` | `number` | let/var | `periods - Math.floor(periods)` | ✗ |
| `fVec` | `number[]` | let/var | `[elem2[0] - elem1[0], elem2[1] - elem1[1], elem2[2] - elem1[2]]` | ✗ |
| `pitch` | `number` | let/var | `Math.atan2(fVec[0], Math.sqrt(fVec[1] * fVec[1] + fVec[2] * fVec[2])) / degTo...` | ✗ |
| `yaw` | `number` | let/var | `-Math.atan2(fVec[1], fVec[2]) / degToRads` | ✗ |
| `iKey` | `any` | let/var | `*not shown*` | ✗ |
| `lenKey` | `any` | let/var | `val1.length` | ✗ |
| `iKey` | `any` | let/var | `*not shown*` | ✗ |
| `lenKey` | `any` | let/var | `data.k.length` | ✗ |
| `index` | `any` | let/var | `*not shown*` | ✗ |
| `keyTime` | `any` | let/var | `*not shown*` | ✗ |
| `obKey` | `{ index: number; time: number; }` | let/var | `{}` | ✗ |
| `obKey` | `any` | let/var | `*not shown*` | ✗ |
| `iKey` | `any` | let/var | `*not shown*` | ✗ |
| `lenKey` | `any` | let/var | `*not shown*` | ✗ |
| `arr` | `any` | let/var | `Object.prototype.hasOwnProperty.call(data.k[ind], 's') ? data.k[ind].s : data...` | ✗ |
| `time` | `any` | let/var | `*not shown*` | ✗ |
| `velocity` | `any` | let/var | `*not shown*` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `text` | `any` | let/var | `*not shown*` | ✗ |
| `textIndex` | `any` | let/var | `*not shown*` | ✗ |
| `textTotal` | `any` | let/var | `*not shown*` | ✗ |
| `selectorValue` | `any` | let/var | `*not shown*` | ✗ |
| `index` | `any` | let/var | `elem.data.ind` | ✗ |
| `hasParent` | `boolean` | let/var | `!!(elem.hierarchy && elem.hierarchy.length)` | ✗ |
| `parent` | `any` | let/var | `*not shown*` | ✗ |
| `globalData` | `any` | let/var | `elem.globalData` | ✗ |
| `ExpressionManager` | `{ initiateExpression: (elem: any, dat...` | let/var | `(function () { 'use strict'; var ob = {}; var Math = BMMath; var window = nul...` | ✗ |
| `delta` | `number` | let/var | `-0.01` | ✗ |
| `speed` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `delta` | `number` | let/var | `-0.001` | ✗ |
| `velocity` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `expressionHelpers` | `{ searchExpressions: (elem: any, data...` | let/var | `(function () { function searchExpressions(elem, data, prop) { if (data.x) { p...` | ✗ |
| `currentFrame` | `any` | let/var | `this.comp.renderedFrame` | ✗ |
| `keyframes` | `any` | let/var | `this.keyframes` | ✗ |
| `lastKeyFrame` | `any` | let/var | `keyframes[keyframes.length - 1].t` | ✗ |
| `cycleDuration` | `any` | let/var | `*not shown*` | ✗ |
| `firstKeyFrame` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `ret` | `any` | let/var | `*not shown*` | ✗ |
| `currentFrame` | `any` | let/var | `this.comp.renderedFrame` | ✗ |
| `keyframes` | `any` | let/var | `this.keyframes` | ✗ |
| `firstKeyFrame` | `any` | let/var | `keyframes[0].t` | ✗ |
| `cycleDuration` | `any` | let/var | `*not shown*` | ✗ |
| `lastKeyFrame` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `ret` | `any` | let/var | `*not shown*` | ✗ |
| `repeats` | `number` | let/var | `Math.floor((firstKeyFrame - currentFrame) / cycleDuration) + 1` | ✗ |
| `currentTime` | `number` | let/var | `this.comp.renderedFrame / this.comp.globalData.frameRate` | ✗ |
| `initFrame` | `number` | let/var | `currentTime - width` | ✗ |
| `endFrame` | `any` | let/var | `currentTime + width` | ✗ |
| `sampleFrequency` | `number` | let/var | `samples > 1 ? (endFrame - initFrame) / (samples - 1) : 1` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `j` | `number` | let/var | `0` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `sampleValue` | `any` | let/var | `*not shown*` | ✗ |
| `matrix` | `(Anonymous function)` | let/var | `this._transformCachingAtTime.v` | ✗ |
| `getTransformProperty` | `(elem: any, data: any, container: any...` | let/var | `TransformPropertyFactory.getTransformProperty` | ✗ |
| `propertyGetProp` | `(elem: any, data: any, type: any, mul...` | let/var | `PropertyFactory.getProp` | ✗ |
| `value` | `number` | let/var | `0` | ✗ |
| `shapePath` | `any` | let/var | `this.v` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `shapePath._length` | ✗ |
| `vertices` | `any` | let/var | `shapePath[prop]` | ✗ |
| `points` | `any` | let/var | `shapePath.v` | ✗ |
| `shapePath` | `any` | let/var | `this.v` | ✗ |
| `segmentsLength` | `any` | let/var | `this._segmentsLength` | ✗ |
| `lengths` | `any` | let/var | `segmentsLength.lengths` | ✗ |
| `lengthPos` | `number` | let/var | `segmentsLength.totalLength * perc` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `lengths.length` | ✗ |
| `accumulatedLength` | `number` | let/var | `0` | ✗ |
| `pt` | `any` | let/var | `*not shown*` | ✗ |
| `initIndex` | `number` | let/var | `i` | ✗ |
| `endIndex` | `number` | let/var | `(shapePath.c && i === len - 1) ? 0 : i + 1` | ✗ |
| `segmentPerc` | `number` | let/var | `(lengthPos - accumulatedLength) / lengths[i].addedLength` | ✗ |
| `xLength` | `number` | let/var | `pt2[0] - pt1[0]` | ✗ |
| `yLength` | `number` | let/var | `pt2[1] - pt1[1]` | ✗ |
| `unitVector` | `number[]` | let/var | `vectorType === 'tangent' ? [xLength / magnitude, yLength / magnitude] : [-yLe...` | ✗ |
| `propertyGetShapeProp` | `(elem: any, data: any, type: any) => ...` | let/var | `ShapePropertyFactory.getShapeProp` | ✗ |
| `newData` | `{ t: any; __complete: boolean; }` | let/var | `{}` | ✗ |


---

## Functions

### `setWebWorker(flag: any): void`

**Parameters:**

- **`flag`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(flag) => { _useWebWorker = !!flag; }
```
</details>

### `getWebWorker(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
() => _useWebWorker
```
</details>

### `setLocationHref(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(value) => { locationHref = value; }
```
</details>

### `getLocationHref(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
() => locationHref
```
</details>

### `createTag(type: any): any`

**Parameters:**

- **`type`** `any`

**Returns:** `any`

**Calls:**

- `document.createElement`

**Internal Comments:**
```
// return {appendChild:function(){},setAttribute:function(){},style:{}}
```

<details><summary>Code</summary>

```typescript
function createTag(type) {
  // return {appendChild:function(){},setAttribute:function(){},style:{}}
  return document.createElement(type);
}
```
</details>

### `extendPrototype(sources: any, destination: any): void`

**Parameters:**

- **`sources`** `any`
- **`destination`** `any`

**Returns:** `void`

**Calls:**

- `Object.prototype.hasOwnProperty.call`

<details><summary>Code</summary>

```typescript
function extendPrototype(sources, destination) {
  var i;
  var len = sources.length;
  var sourcePrototype;
  for (i = 0; i < len; i += 1) {
    sourcePrototype = sources[i].prototype;
    for (var attr in sourcePrototype) {
      if (Object.prototype.hasOwnProperty.call(sourcePrototype, attr)) destination.prototype[attr] = sourcePrototype[attr];
    }
  }
}
```
</details>

### `getDescriptor(object: any, prop: any): PropertyDescriptor`

**Parameters:**

- **`object`** `any`
- **`prop`** `any`

**Returns:** `PropertyDescriptor`

**Calls:**

- `Object.getOwnPropertyDescriptor`

<details><summary>Code</summary>

```typescript
function getDescriptor(object, prop) {
  return Object.getOwnPropertyDescriptor(object, prop);
}
```
</details>

### `createProxyFunction(prototype: any): { (): void; prototype: any; }`

**Parameters:**

- **`prototype`** `any`

**Returns:** `{ (): void; prototype: any; }`

<details><summary>Code</summary>

```typescript
function createProxyFunction(prototype) {
  function ProxyFunction() {}
  ProxyFunction.prototype = prototype;
  return ProxyFunction;
}
```
</details>

### `ProxyFunction(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ProxyFunction() {}
```
</details>

### `AudioController(audioFactory: any): void`

**Parameters:**

- **`audioFactory`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function AudioController(audioFactory) {
    this.audios = [];
    this.audioFactory = audioFactory;
    this._volume = 1;
    this._isMuted = false;
  }
```
</details>

### `addAudio(audio: any): void`

**Parameters:**

- **`audio`** `any`

**Returns:** `void`

**Calls:**

- `this.audios.push`

<details><summary>Code</summary>

```typescript
function (audio) {
      this.audios.push(audio);
    }
```
</details>

### `pause(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].pause`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].pause();
      }
    }
```
</details>

### `resume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].resume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].resume();
      }
    }
```
</details>

### `setRate(rateValue: any): void`

**Parameters:**

- **`rateValue`** `any`

**Returns:** `void`

**Calls:**

- `this.audios[i].setRate`

<details><summary>Code</summary>

```typescript
function (rateValue) {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].setRate(rateValue);
      }
    }
```
</details>

### `createAudio(assetPath: any): any`

**Parameters:**

- **`assetPath`** `any`

**Returns:** `any`

**Calls:**

- `this.audioFactory`

<details><summary>Code</summary>

```typescript
function (assetPath) {
      if (this.audioFactory) {
        return this.audioFactory(assetPath);
      } if (window.Howl) {
        return new window.Howl({
          src: [assetPath],
        });
      }
      return {
        isPlaying: false,
        play: function () { this.isPlaying = true; },
        seek: function () { this.isPlaying = false; },
        playing: function () {},
        rate: function () {},
        setVolume: function () {},
      };
    }
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setAudioFactory(audioFactory: any): void`

**Parameters:**

- **`audioFactory`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (audioFactory) {
      this.audioFactory = audioFactory;
    }
```
</details>

### `setVolume(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function (value) {
      this._volume = value;
      this._updateVolume();
    }
```
</details>

### `mute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = true;
      this._updateVolume();
    }
```
</details>

### `unmute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = false;
      this._updateVolume();
    }
```
</details>

### `getVolume(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
      return this._volume;
    }
```
</details>

### `_updateVolume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].volume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].volume(this._volume * (this._isMuted ? 0 : 1));
      }
    }
```
</details>

### `addAudio(audio: any): void`

**Parameters:**

- **`audio`** `any`

**Returns:** `void`

**Calls:**

- `this.audios.push`

<details><summary>Code</summary>

```typescript
function (audio) {
      this.audios.push(audio);
    }
```
</details>

### `pause(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].pause`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].pause();
      }
    }
```
</details>

### `resume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].resume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].resume();
      }
    }
```
</details>

### `setRate(rateValue: any): void`

**Parameters:**

- **`rateValue`** `any`

**Returns:** `void`

**Calls:**

- `this.audios[i].setRate`

<details><summary>Code</summary>

```typescript
function (rateValue) {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].setRate(rateValue);
      }
    }
```
</details>

### `createAudio(assetPath: any): any`

**Parameters:**

- **`assetPath`** `any`

**Returns:** `any`

**Calls:**

- `this.audioFactory`

<details><summary>Code</summary>

```typescript
function (assetPath) {
      if (this.audioFactory) {
        return this.audioFactory(assetPath);
      } if (window.Howl) {
        return new window.Howl({
          src: [assetPath],
        });
      }
      return {
        isPlaying: false,
        play: function () { this.isPlaying = true; },
        seek: function () { this.isPlaying = false; },
        playing: function () {},
        rate: function () {},
        setVolume: function () {},
      };
    }
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setAudioFactory(audioFactory: any): void`

**Parameters:**

- **`audioFactory`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (audioFactory) {
      this.audioFactory = audioFactory;
    }
```
</details>

### `setVolume(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function (value) {
      this._volume = value;
      this._updateVolume();
    }
```
</details>

### `mute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = true;
      this._updateVolume();
    }
```
</details>

### `unmute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = false;
      this._updateVolume();
    }
```
</details>

### `getVolume(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
      return this._volume;
    }
```
</details>

### `_updateVolume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].volume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].volume(this._volume * (this._isMuted ? 0 : 1));
      }
    }
```
</details>

### `AudioController(audioFactory: any): void`

**Parameters:**

- **`audioFactory`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function AudioController(audioFactory) {
    this.audios = [];
    this.audioFactory = audioFactory;
    this._volume = 1;
    this._isMuted = false;
  }
```
</details>

### `addAudio(audio: any): void`

**Parameters:**

- **`audio`** `any`

**Returns:** `void`

**Calls:**

- `this.audios.push`

<details><summary>Code</summary>

```typescript
function (audio) {
      this.audios.push(audio);
    }
```
</details>

### `pause(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].pause`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].pause();
      }
    }
```
</details>

### `resume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].resume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].resume();
      }
    }
```
</details>

### `setRate(rateValue: any): void`

**Parameters:**

- **`rateValue`** `any`

**Returns:** `void`

**Calls:**

- `this.audios[i].setRate`

<details><summary>Code</summary>

```typescript
function (rateValue) {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].setRate(rateValue);
      }
    }
```
</details>

### `createAudio(assetPath: any): any`

**Parameters:**

- **`assetPath`** `any`

**Returns:** `any`

**Calls:**

- `this.audioFactory`

<details><summary>Code</summary>

```typescript
function (assetPath) {
      if (this.audioFactory) {
        return this.audioFactory(assetPath);
      } if (window.Howl) {
        return new window.Howl({
          src: [assetPath],
        });
      }
      return {
        isPlaying: false,
        play: function () { this.isPlaying = true; },
        seek: function () { this.isPlaying = false; },
        playing: function () {},
        rate: function () {},
        setVolume: function () {},
      };
    }
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setAudioFactory(audioFactory: any): void`

**Parameters:**

- **`audioFactory`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (audioFactory) {
      this.audioFactory = audioFactory;
    }
```
</details>

### `setVolume(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function (value) {
      this._volume = value;
      this._updateVolume();
    }
```
</details>

### `mute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = true;
      this._updateVolume();
    }
```
</details>

### `unmute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = false;
      this._updateVolume();
    }
```
</details>

### `getVolume(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
      return this._volume;
    }
```
</details>

### `_updateVolume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].volume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].volume(this._volume * (this._isMuted ? 0 : 1));
      }
    }
```
</details>

### `addAudio(audio: any): void`

**Parameters:**

- **`audio`** `any`

**Returns:** `void`

**Calls:**

- `this.audios.push`

<details><summary>Code</summary>

```typescript
function (audio) {
      this.audios.push(audio);
    }
```
</details>

### `pause(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].pause`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].pause();
      }
    }
```
</details>

### `resume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].resume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].resume();
      }
    }
```
</details>

### `setRate(rateValue: any): void`

**Parameters:**

- **`rateValue`** `any`

**Returns:** `void`

**Calls:**

- `this.audios[i].setRate`

<details><summary>Code</summary>

```typescript
function (rateValue) {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].setRate(rateValue);
      }
    }
```
</details>

### `createAudio(assetPath: any): any`

**Parameters:**

- **`assetPath`** `any`

**Returns:** `any`

**Calls:**

- `this.audioFactory`

<details><summary>Code</summary>

```typescript
function (assetPath) {
      if (this.audioFactory) {
        return this.audioFactory(assetPath);
      } if (window.Howl) {
        return new window.Howl({
          src: [assetPath],
        });
      }
      return {
        isPlaying: false,
        play: function () { this.isPlaying = true; },
        seek: function () { this.isPlaying = false; },
        playing: function () {},
        rate: function () {},
        setVolume: function () {},
      };
    }
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = true; }
```
</details>

### `seek(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { this.isPlaying = false; }
```
</details>

### `playing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `rate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setVolume(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setAudioFactory(audioFactory: any): void`

**Parameters:**

- **`audioFactory`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (audioFactory) {
      this.audioFactory = audioFactory;
    }
```
</details>

### `setVolume(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function (value) {
      this._volume = value;
      this._updateVolume();
    }
```
</details>

### `mute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = true;
      this._updateVolume();
    }
```
</details>

### `unmute(): void`

**Returns:** `void`

**Calls:**

- `this._updateVolume`

<details><summary>Code</summary>

```typescript
function () {
      this._isMuted = false;
      this._updateVolume();
    }
```
</details>

### `getVolume(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
      return this._volume;
    }
```
</details>

### `_updateVolume(): void`

**Returns:** `void`

**Calls:**

- `this.audios[i].volume`

<details><summary>Code</summary>

```typescript
function () {
      var i;
      var len = this.audios.length;
      for (i = 0; i < len; i += 1) {
        this.audios[i].volume(this._volume * (this._isMuted ? 0 : 1));
      }
    }
```
</details>

### `createRegularArray(type: any, len: any): number[]`

**Parameters:**

- **`type`** `any`
- **`len`** `any`

**Returns:** `number[]`

**Calls:**

- `arr.push`

<details><summary>Code</summary>

```typescript
function createRegularArray(type, len) {
    var i = 0;
    var arr = [];
    var value;
    switch (type) {
      case 'int16':
      case 'uint8c':
        value = 1;
        break;
      default:
        value = 1.1;
        break;
    }
    for (i = 0; i < len; i += 1) {
      arr.push(value);
    }
    return arr;
  }
```
</details>

### `createTypedArrayFactory(type: any, len: any): number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Parameters:**

- **`type`** `any`
- **`len`** `any`

**Returns:** `number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `createRegularArray`

<details><summary>Code</summary>

```typescript
function createTypedArrayFactory(type, len) {
    if (type === 'float32') {
      return new Float32Array(len);
    } if (type === 'int16') {
      return new Int16Array(len);
    } if (type === 'uint8c') {
      return new Uint8ClampedArray(len);
    }
    return createRegularArray(type, len);
  }
```
</details>

### `createSizedArray(len: any): any`

**Parameters:**

- **`len`** `any`

**Returns:** `any`

**Calls:**

- `Array.apply`

<details><summary>Code</summary>

```typescript
function createSizedArray(len) {
  return Array.apply(null, { length: len });
}
```
</details>

### `ProjectInterface$1(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function ProjectInterface$1() { return {}; }
```
</details>

### `roundValues(flag: any): void`

**Parameters:**

- **`flag`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function roundValues(flag) {
  _shouldRoundValues = !!flag;
}
```
</details>

### `bmRnd(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Math.round`

<details><summary>Code</summary>

```typescript
function bmRnd(value) {
  if (_shouldRoundValues) {
    return Math.round(value);
  }
  return value;
}
```
</details>

### `styleDiv(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function styleDiv(element) {
  element.style.position = 'absolute';
  element.style.top = 0;
  element.style.left = 0;
  element.style.display = 'block';
  element.style.transformOrigin = '0 0';
  element.style.webkitTransformOrigin = '0 0';
  element.style.backfaceVisibility = 'visible';
  element.style.webkitBackfaceVisibility = 'visible';
  element.style.transformStyle = 'preserve-3d';
  element.style.webkitTransformStyle = 'preserve-3d';
  element.style.mozTransformStyle = 'preserve-3d';
}
```
</details>

### `BMEnterFrameEvent(type: any, currentTime: any, totalTime: any, frameMultiplier: any): void`

**Parameters:**

- **`type`** `any`
- **`currentTime`** `any`
- **`totalTime`** `any`
- **`frameMultiplier`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMEnterFrameEvent(type, currentTime, totalTime, frameMultiplier) {
  this.type = type;
  this.currentTime = currentTime;
  this.totalTime = totalTime;
  this.direction = frameMultiplier < 0 ? -1 : 1;
}
```
</details>

### `BMCompleteEvent(type: any, frameMultiplier: any): void`

**Parameters:**

- **`type`** `any`
- **`frameMultiplier`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMCompleteEvent(type, frameMultiplier) {
  this.type = type;
  this.direction = frameMultiplier < 0 ? -1 : 1;
}
```
</details>

### `BMCompleteLoopEvent(type: any, totalLoops: any, currentLoop: any, frameMultiplier: any): void`

**Parameters:**

- **`type`** `any`
- **`totalLoops`** `any`
- **`currentLoop`** `any`
- **`frameMultiplier`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMCompleteLoopEvent(type, totalLoops, currentLoop, frameMultiplier) {
  this.type = type;
  this.currentLoop = currentLoop;
  this.totalLoops = totalLoops;
  this.direction = frameMultiplier < 0 ? -1 : 1;
}
```
</details>

### `BMSegmentStartEvent(type: any, firstFrame: any, totalFrames: any): void`

**Parameters:**

- **`type`** `any`
- **`firstFrame`** `any`
- **`totalFrames`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMSegmentStartEvent(type, firstFrame, totalFrames) {
  this.type = type;
  this.firstFrame = firstFrame;
  this.totalFrames = totalFrames;
}
```
</details>

### `BMDestroyEvent(type: any, target: any): void`

**Parameters:**

- **`type`** `any`
- **`target`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMDestroyEvent(type, target) {
  this.type = type;
  this.target = target;
}
```
</details>

### `BMRenderFrameErrorEvent(nativeError: any, currentTime: any): void`

**Parameters:**

- **`nativeError`** `any`
- **`currentTime`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMRenderFrameErrorEvent(nativeError, currentTime) {
  this.type = 'renderFrameError';
  this.nativeError = nativeError;
  this.currentTime = currentTime;
}
```
</details>

### `BMConfigErrorEvent(nativeError: any): void`

**Parameters:**

- **`nativeError`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMConfigErrorEvent(nativeError) {
  this.type = 'configError';
  this.nativeError = nativeError;
}
```
</details>

### `BMAnimationConfigErrorEvent(type: any, nativeError: any): void`

**Parameters:**

- **`type`** `any`
- **`nativeError`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BMAnimationConfigErrorEvent(type, nativeError) {
  this.type = type;
  this.nativeError = nativeError;
}
```
</details>

### `HSVtoRGB(h: any, s: any, v: any): any[]`

**Parameters:**

- **`h`** `any`
- **`s`** `any`
- **`v`** `any`

**Returns:** `any[]`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
function HSVtoRGB(h, s, v) {
  var r;
  var g;
  var b;
  var i;
  var f;
  var p;
  var q;
  var t;
  i = Math.floor(h * 6);
  f = h * 6 - i;
  p = v * (1 - s);
  q = v * (1 - f * s);
  t = v * (1 - (1 - f) * s);
  switch (i % 6) {
    case 0: r = v; g = t; b = p; break;
    case 1: r = q; g = v; b = p; break;
    case 2: r = p; g = v; b = t; break;
    case 3: r = p; g = q; b = v; break;
    case 4: r = t; g = p; b = v; break;
    case 5: r = v; g = p; b = q; break;
    default: break;
  }
  return [r,
    g,
    b];
}
```
</details>

### `RGBtoHSV(r: any, g: any, b: any): number[]`

**Parameters:**

- **`r`** `any`
- **`g`** `any`
- **`b`** `any`

**Returns:** `number[]`

**Calls:**

- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function RGBtoHSV(r, g, b) {
  var max = Math.max(r, g, b);
  var min = Math.min(r, g, b);
  var d = max - min;
  var h;
  var s = (max === 0 ? 0 : d / max);
  var v = max / 255;

  switch (max) {
    case min: h = 0; break;
    case r: h = (g - b) + d * (g < b ? 6 : 0); h /= 6 * d; break;
    case g: h = (b - r) + d * 2; h /= 6 * d; break;
    case b: h = (r - g) + d * 4; h /= 6 * d; break;
    default: break;
  }

  return [
    h,
    s,
    v,
  ];
}
```
</details>

### `addSaturationToRGB(color: any, offset: any): any[]`

**Parameters:**

- **`color`** `any`
- **`offset`** `any`

**Returns:** `any[]`

**Calls:**

- `RGBtoHSV`
- `HSVtoRGB`

<details><summary>Code</summary>

```typescript
function addSaturationToRGB(color, offset) {
  var hsv = RGBtoHSV(color[0] * 255, color[1] * 255, color[2] * 255);
  hsv[1] += offset;
  if (hsv[1] > 1) {
    hsv[1] = 1;
  } else if (hsv[1] <= 0) {
    hsv[1] = 0;
  }
  return HSVtoRGB(hsv[0], hsv[1], hsv[2]);
}
```
</details>

### `addBrightnessToRGB(color: any, offset: any): any[]`

**Parameters:**

- **`color`** `any`
- **`offset`** `any`

**Returns:** `any[]`

**Calls:**

- `RGBtoHSV`
- `HSVtoRGB`

<details><summary>Code</summary>

```typescript
function addBrightnessToRGB(color, offset) {
  var hsv = RGBtoHSV(color[0] * 255, color[1] * 255, color[2] * 255);
  hsv[2] += offset;
  if (hsv[2] > 1) {
    hsv[2] = 1;
  } else if (hsv[2] < 0) {
    hsv[2] = 0;
  }
  return HSVtoRGB(hsv[0], hsv[1], hsv[2]);
}
```
</details>

### `addHueToRGB(color: any, offset: any): any[]`

**Parameters:**

- **`color`** `any`
- **`offset`** `any`

**Returns:** `any[]`

**Calls:**

- `RGBtoHSV`
- `HSVtoRGB`

<details><summary>Code</summary>

```typescript
function addHueToRGB(color, offset) {
  var hsv = RGBtoHSV(color[0] * 255, color[1] * 255, color[2] * 255);
  hsv[0] += offset / 360;
  if (hsv[0] > 1) {
    hsv[0] -= 1;
  } else if (hsv[0] < 0) {
    hsv[0] += 1;
  }
  return HSVtoRGB(hsv[0], hsv[1], hsv[2]);
}
```
</details>

### `setSubframeEnabled(flag: any): void`

**Parameters:**

- **`flag`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(flag) => { subframeEnabled = !!flag; }
```
</details>

### `getSubframeEnabled(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
() => subframeEnabled
```
</details>

### `setExpressionsPlugin(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(value) => { expressionsPlugin = value; }
```
</details>

### `getExpressionsPlugin(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => expressionsPlugin
```
</details>

### `setDefaultCurveSegments(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(value) => { defaultCurveSegments = value; }
```
</details>

### `getDefaultCurveSegments(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
() => defaultCurveSegments
```
</details>

### `setIdPrefix(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(value) => { idPrefix$1 = value; }
```
</details>

### `getIdPrefix(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
() => idPrefix$1
```
</details>

### `createNS(type: any): any`

**Parameters:**

- **`type`** `any`

**Returns:** `any`

**Calls:**

- `document.createElementNS`

**Internal Comments:**
```
// return {appendChild:function(){},setAttribute:function(){},style:{}}
```

<details><summary>Code</summary>

```typescript
function createNS(type) {
  // return {appendChild:function(){},setAttribute:function(){},style:{}}
  return document.createElementNS(svgNS, type);
}
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `createWorker(fn: any): Worker | { onmessage: () => void; postMessage: (path: any) => void; }`

**Parameters:**

- **`fn`** `any`

**Returns:** `Worker | { onmessage: () => void; postMessage: (path: any) => void; }`

**Calls:**

- `getWebWorker`
- `fn.toString`
- `URL.createObjectURL`

**Internal Comments:**
```
// var blob = new Blob(['self.onmessage = ', fn.toString()], { type: 'text/javascript' }); (x2)
```

<details><summary>Code</summary>

```typescript
function createWorker(fn) {
    if (window.Worker && window.Blob && getWebWorker()) {
      var blob = new Blob(['var _workerSelf = self; self.onmessage = ', fn.toString()], { type: 'text/javascript' });
      // var blob = new Blob(['self.onmessage = ', fn.toString()], { type: 'text/javascript' });
      var url = URL.createObjectURL(blob);
      return new Worker(url);
    }
    workerFn = fn;
    return workerProxy;
  }
```
</details>

### `setupWorker(): void`

**Returns:** `void`

**Calls:**

- `createWorker`
- `convertPathsToAbsoluteValues`
- `findCompLayers`
- `completeLayers`
- `completeShapes`
- `completeText`
- `findComp`
- `JSON.parse`
- `JSON.stringify`
- `animVersionString.split`
- `complex_call_16741`
- `updateTextLayer`
- `checkVersion`
- `iterateLayers`
- `complex_call_17998`
- `charData.data.shapes.push`
- `charData.data.shapes[0].it.push`
- `complex_call_19824`
- `complex_call_21410`
- `iterateShapes`
- `complex_call_23766`
- `completeClosingShapes`
- `checkColors`
- `checkText`
- `checkChars`
- `checkPathProperties`
- `checkShapes`
- `completeChars`
- `dataFunctionManager`
- `complex_call_27867`
- `xhr.getResponseHeader`
- `contentTypeHeader.indexOf`
- `formatResponse`
- `callback`
- `errorCallback`
- `xhr.open`
- `xhr.send`
- `_workerSelf.assetLoader.load`
- `_workerSelf.dataManager.completeData`
- `_workerSelf.postMessage`
- `process.onComplete`
- `process.onError`

**Internal Comments:**
```
// var compData = findComp(chars[i].data.refId, assets); (x6)
// chars[i].data.ip = 0; (x3)
// chars[i].data.op = 99999; (x3)
// chars[i].data.st = 0; (x3)
// chars[i].data.sr = 1; (x3)
// chars[i].w = compData.w; (x3)
// chars[i].data.ks = { (x3)
//   a: { k: [0, 0, 0], a: 0 }, (x3)
//   p: { k: [0, -compData.h, 0], a: 0 }, (x3)
//   r: { k: 0, a: 0 }, (x3)
//   s: { k: [100, 100], a: 0 }, (x3)
//   o: { k: 100, a: 0 }, (x3)
// }; (x3)
// using typeof doubles the time of execution of this method, (x2)
// so if available, it's better to use the header to validate the type (x2)
// set responseType after calling open or IE will break.
// This crashes on Android WebView prior to KitKat (x4)
```

<details><summary>Code</summary>

```typescript
function setupWorker() {
    if (!workerInstance) {
      workerInstance = createWorker(function workerStart(e) {
        function dataFunctionManager() {
          function completeLayers(layers, comps) {
            var layerData;
            var i;
            var len = layers.length;
            var j;
            var jLen;
            var k;
            var kLen;
            for (i = 0; i < len; i += 1) {
              layerData = layers[i];
              if (('ks' in layerData) && !layerData.completed) {
                layerData.completed = true;
                if (layerData.tt) {
                  layers[i - 1].td = layerData.tt;
                }
                if (layerData.hasMask) {
                  var maskProps = layerData.masksProperties;
                  jLen = maskProps.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (maskProps[j].pt.k.i) {
                      convertPathsToAbsoluteValues(maskProps[j].pt.k);
                    } else {
                      kLen = maskProps[j].pt.k.length;
                      for (k = 0; k < kLen; k += 1) {
                        if (maskProps[j].pt.k[k].s) {
                          convertPathsToAbsoluteValues(maskProps[j].pt.k[k].s[0]);
                        }
                        if (maskProps[j].pt.k[k].e) {
                          convertPathsToAbsoluteValues(maskProps[j].pt.k[k].e[0]);
                        }
                      }
                    }
                  }
                }
                if (layerData.ty === 0) {
                  layerData.layers = findCompLayers(layerData.refId, comps);
                  completeLayers(layerData.layers, comps);
                } else if (layerData.ty === 4) {
                  completeShapes(layerData.shapes);
                } else if (layerData.ty === 5) {
                  completeText(layerData);
                }
              }
            }
          }

          function completeChars(chars, assets) {
            if (chars) {
              var i = 0;
              var len = chars.length;
              for (i = 0; i < len; i += 1) {
                if (chars[i].t === 1) {
                  // var compData = findComp(chars[i].data.refId, assets);
                  chars[i].data.layers = findCompLayers(chars[i].data.refId, assets);
                  // chars[i].data.ip = 0;
                  // chars[i].data.op = 99999;
                  // chars[i].data.st = 0;
                  // chars[i].data.sr = 1;
                  // chars[i].w = compData.w;
                  // chars[i].data.ks = {
                  //   a: { k: [0, 0, 0], a: 0 },
                  //   p: { k: [0, -compData.h, 0], a: 0 },
                  //   r: { k: 0, a: 0 },
                  //   s: { k: [100, 100], a: 0 },
                  //   o: { k: 100, a: 0 },
                  // };
                  completeLayers(chars[i].data.layers, assets);
                }
              }
            }
          }

          function findComp(id, comps) {
            var i = 0;
            var len = comps.length;
            while (i < len) {
              if (comps[i].id === id) {
                return comps[i];
              }
              i += 1;
            }
            return null;
          }

          function findCompLayers(id, comps) {
            var comp = findComp(id, comps);
            if (comp) {
              if (!comp.layers.__used) {
                comp.layers.__used = true;
                return comp.layers;
              }
              return JSON.parse(JSON.stringify(comp.layers));
            }
            return null;
          }

          function completeShapes(arr) {
            var i;
            var len = arr.length;
            var j;
            var jLen;
            for (i = len - 1; i >= 0; i -= 1) {
              if (arr[i].ty === 'sh') {
                if (arr[i].ks.k.i) {
                  convertPathsToAbsoluteValues(arr[i].ks.k);
                } else {
                  jLen = arr[i].ks.k.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (arr[i].ks.k[j].s) {
                      convertPathsToAbsoluteValues(arr[i].ks.k[j].s[0]);
                    }
                    if (arr[i].ks.k[j].e) {
                      convertPathsToAbsoluteValues(arr[i].ks.k[j].e[0]);
                    }
                  }
                }
              } else if (arr[i].ty === 'gr') {
                completeShapes(arr[i].it);
              }
            }
          }

          function convertPathsToAbsoluteValues(path) {
            var i;
            var len = path.i.length;
            for (i = 0; i < len; i += 1) {
              path.i[i][0] += path.v[i][0];
              path.i[i][1] += path.v[i][1];
              path.o[i][0] += path.v[i][0];
              path.o[i][1] += path.v[i][1];
            }
          }

          function checkVersion(minimum, animVersionString) {
            var animVersion = animVersionString ? animVersionString.split('.') : [100, 100, 100];
            if (minimum[0] > animVersion[0]) {
              return true;
            } if (animVersion[0] > minimum[0]) {
              return false;
            }
            if (minimum[1] > animVersion[1]) {
              return true;
            } if (animVersion[1] > minimum[1]) {
              return false;
            }
            if (minimum[2] > animVersion[2]) {
              return true;
            } if (animVersion[2] > minimum[2]) {
              return false;
            }
            return null;
          }

          var checkText = (function () {
            var minimumVersion = [4, 4, 14];

            function updateTextLayer(textLayer) {
              var documentData = textLayer.t.d;
              textLayer.t.d = {
                k: [
                  {
                    s: documentData,
                    t: 0,
                  },
                ],
              };
            }

            function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 5) {
                  updateTextLayer(layers[i]);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          var checkChars = (function () {
            var minimumVersion = [4, 7, 99];
            return function (animationData) {
              if (animationData.chars && !checkVersion(minimumVersion, animationData.v)) {
                var i;
                var len = animationData.chars.length;
                for (i = 0; i < len; i += 1) {
                  var charData = animationData.chars[i];
                  if (charData.data && charData.data.shapes) {
                    completeShapes(charData.data.shapes);
                    charData.data.ip = 0;
                    charData.data.op = 99999;
                    charData.data.st = 0;
                    charData.data.sr = 1;
                    charData.data.ks = {
                      p: { k: [0, 0], a: 0 },
                      s: { k: [100, 100], a: 0 },
                      a: { k: [0, 0], a: 0 },
                      r: { k: 0, a: 0 },
                      o: { k: 100, a: 0 },
                    };
                    if (!animationData.chars[i].t) {
                      charData.data.shapes.push(
                        {
                          ty: 'no',
                        }
                      );
                      charData.data.shapes[0].it.push(
                        {
                          p: { k: [0, 0], a: 0 },
                          s: { k: [100, 100], a: 0 },
                          a: { k: [0, 0], a: 0 },
                          r: { k: 0, a: 0 },
                          o: { k: 100, a: 0 },
                          sk: { k: 0, a: 0 },
                          sa: { k: 0, a: 0 },
                          ty: 'tr',
                        }
                      );
                    }
                  }
                }
              }
            };
          }());

          var checkPathProperties = (function () {
            var minimumVersion = [5, 7, 15];

            function updateTextLayer(textLayer) {
              var pathData = textLayer.t.p;
              if (typeof pathData.a === 'number') {
                pathData.a = {
                  a: 0,
                  k: pathData.a,
                };
              }
              if (typeof pathData.p === 'number') {
                pathData.p = {
                  a: 0,
                  k: pathData.p,
                };
              }
              if (typeof pathData.r === 'number') {
                pathData.r = {
                  a: 0,
                  k: pathData.r,
                };
              }
            }

            function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 5) {
                  updateTextLayer(layers[i]);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          var checkColors = (function () {
            var minimumVersion = [4, 1, 9];

            function iterateShapes(shapes) {
              var i;
              var len = shapes.length;
              var j;
              var jLen;
              for (i = 0; i < len; i += 1) {
                if (shapes[i].ty === 'gr') {
                  iterateShapes(shapes[i].it);
                } else if (shapes[i].ty === 'fl' || shapes[i].ty === 'st') {
                  if (shapes[i].c.k && shapes[i].c.k[0].i) {
                    jLen = shapes[i].c.k.length;
                    for (j = 0; j < jLen; j += 1) {
                      if (shapes[i].c.k[j].s) {
                        shapes[i].c.k[j].s[0] /= 255;
                        shapes[i].c.k[j].s[1] /= 255;
                        shapes[i].c.k[j].s[2] /= 255;
                        shapes[i].c.k[j].s[3] /= 255;
                      }
                      if (shapes[i].c.k[j].e) {
                        shapes[i].c.k[j].e[0] /= 255;
                        shapes[i].c.k[j].e[1] /= 255;
                        shapes[i].c.k[j].e[2] /= 255;
                        shapes[i].c.k[j].e[3] /= 255;
                      }
                    }
                  } else {
                    shapes[i].c.k[0] /= 255;
                    shapes[i].c.k[1] /= 255;
                    shapes[i].c.k[2] /= 255;
                    shapes[i].c.k[3] /= 255;
                  }
                }
              }
            }

            function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 4) {
                  iterateShapes(layers[i].shapes);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          var checkShapes = (function () {
            var minimumVersion = [4, 4, 18];

            function completeClosingShapes(arr) {
              var i;
              var len = arr.length;
              var j;
              var jLen;
              for (i = len - 1; i >= 0; i -= 1) {
                if (arr[i].ty === 'sh') {
                  if (arr[i].ks.k.i) {
                    arr[i].ks.k.c = arr[i].closed;
                  } else {
                    jLen = arr[i].ks.k.length;
                    for (j = 0; j < jLen; j += 1) {
                      if (arr[i].ks.k[j].s) {
                        arr[i].ks.k[j].s[0].c = arr[i].closed;
                      }
                      if (arr[i].ks.k[j].e) {
                        arr[i].ks.k[j].e[0].c = arr[i].closed;
                      }
                    }
                  }
                } else if (arr[i].ty === 'gr') {
                  completeClosingShapes(arr[i].it);
                }
              }
            }

            function iterateLayers(layers) {
              var layerData;
              var i;
              var len = layers.length;
              var j;
              var jLen;
              var k;
              var kLen;
              for (i = 0; i < len; i += 1) {
                layerData = layers[i];
                if (layerData.hasMask) {
                  var maskProps = layerData.masksProperties;
                  jLen = maskProps.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (maskProps[j].pt.k.i) {
                      maskProps[j].pt.k.c = maskProps[j].cl;
                    } else {
                      kLen = maskProps[j].pt.k.length;
                      for (k = 0; k < kLen; k += 1) {
                        if (maskProps[j].pt.k[k].s) {
                          maskProps[j].pt.k[k].s[0].c = maskProps[j].cl;
                        }
                        if (maskProps[j].pt.k[k].e) {
                          maskProps[j].pt.k[k].e[0].c = maskProps[j].cl;
                        }
                      }
                    }
                  }
                }
                if (layerData.ty === 4) {
                  completeClosingShapes(layerData.shapes);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          function completeData(animationData) {
            if (animationData.__complete) {
              return;
            }
            checkColors(animationData);
            checkText(animationData);
            checkChars(animationData);
            checkPathProperties(animationData);
            checkShapes(animationData);
            completeLayers(animationData.layers, animationData.assets);
            completeChars(animationData.chars, animationData.assets);
            animationData.__complete = true;
          }

          function completeText(data) {
            if (data.t.a.length === 0 && !('m' in data.t.p)) {
              // data.singleShape = true;
            }
          }

          var moduleOb = {};
          moduleOb.completeData = completeData;
          moduleOb.checkColors = checkColors;
          moduleOb.checkChars = checkChars;
          moduleOb.checkPathProperties = checkPathProperties;
          moduleOb.checkShapes = checkShapes;
          moduleOb.completeLayers = completeLayers;

          return moduleOb;
        }
        if (!_workerSelf.dataManager) {
          _workerSelf.dataManager = dataFunctionManager();
        }

        if (!_workerSelf.assetLoader) {
          _workerSelf.assetLoader = (function () {
            function formatResponse(xhr) {
              // using typeof doubles the time of execution of this method,
              // so if available, it's better to use the header to validate the type
              var contentTypeHeader = xhr.getResponseHeader('content-type');
              if (contentTypeHeader && xhr.responseType === 'json' && contentTypeHeader.indexOf('json') !== -1) {
                return xhr.response;
              }
              if (xhr.response && typeof xhr.response === 'object') {
                return xhr.response;
              } if (xhr.response && typeof xhr.response === 'string') {
                return JSON.parse(xhr.response);
              } if (xhr.responseText) {
                return JSON.parse(xhr.responseText);
              }
              return null;
            }

            function loadAsset(path, fullPath, callback, errorCallback) {
              var response;
              var xhr = new XMLHttpRequest();
              // set responseType after calling open or IE will break.
              try {
                // This crashes on Android WebView prior to KitKat
                xhr.responseType = 'json';
              } catch (err) {} // eslint-disable-line no-empty
              xhr.onreadystatechange = function () {
                if (xhr.readyState === 4) {
                  if (xhr.status === 200) {
                    response = formatResponse(xhr);
                    callback(response);
                  } else {
                    try {
                      response = formatResponse(xhr);
                      callback(response);
                    } catch (err) {
                      if (errorCallback) {
                        errorCallback(err);
                      }
                    }
                  }
                }
              };
              try {
                xhr.open('GET', path, true);
              } catch (error) {
                xhr.open('GET', fullPath + '/' + path, true);
              }
              xhr.send();
            }
            return {
              load: loadAsset,
            };
          }());
        }

        if (e.data.type === 'loadAnimation') {
          _workerSelf.assetLoader.load(
            e.data.path,
            e.data.fullPath,
            function (data) {
              _workerSelf.dataManager.completeData(data);
              _workerSelf.postMessage({
                id: e.data.id,
                payload: data,
                status: 'success',
              });
            },
            function () {
              _workerSelf.postMessage({
                id: e.data.id,
                status: 'error',
              });
            }
          );
        } else if (e.data.type === 'complete') {
          var animation = e.data.animation;
          _workerSelf.dataManager.completeData(animation);
          _workerSelf.postMessage({
            id: e.data.id,
            payload: animation,
            status: 'success',
          });
        } else if (e.data.type === 'loadData') {
          _workerSelf.assetLoader.load(
            e.data.path,
            e.data.fullPath,
            function (data) {
              _workerSelf.postMessage({
                id: e.data.id,
                payload: data,
                status: 'success',
              });
            },
            function () {
              _workerSelf.postMessage({
                id: e.data.id,
                status: 'error',
              });
            }
          );
        }
      });

      workerInstance.onmessage = function (event) {
        var data = event.data;
        var id = data.id;
        var process = processes[id];
        processes[id] = null;
        if (data.status === 'success') {
          process.onComplete(data.payload);
        } else if (process.onError) {
          process.onError();
        }
      };
    }
  }
```
</details>

### `dataFunctionManager(): { completeData: (animationData: any) => void; checkColors: (animationData: any) => void; checkChars: (animationData: any) => void; checkPathProperties: (animationData: any) => void; checkShapes: (animationData: any) => void; completeLayers: (layers: any, comps: any) => void; }`

**Returns:** `{ completeData: (animationData: any) => void; checkColors: (animationData: any) => void; checkChars: (animationData: any) => void; checkPathProperties: (animationData: any) => void; checkShapes: (animationData: any) => void; completeLayers: (layers: any, comps: any) => void; }`

**Calls:**

- `convertPathsToAbsoluteValues`
- `findCompLayers`
- `completeLayers`
- `completeShapes`
- `completeText`
- `findComp`
- `JSON.parse`
- `JSON.stringify`
- `animVersionString.split`
- `complex_call_16741`
- `updateTextLayer`
- `checkVersion`
- `iterateLayers`
- `complex_call_17998`
- `charData.data.shapes.push`
- `charData.data.shapes[0].it.push`
- `complex_call_19824`
- `complex_call_21410`
- `iterateShapes`
- `complex_call_23766`
- `completeClosingShapes`
- `checkColors`
- `checkText`
- `checkChars`
- `checkPathProperties`
- `checkShapes`
- `completeChars`

**Internal Comments:**
```
// var compData = findComp(chars[i].data.refId, assets); (x6)
// chars[i].data.ip = 0; (x3)
// chars[i].data.op = 99999; (x3)
// chars[i].data.st = 0; (x3)
// chars[i].data.sr = 1; (x3)
// chars[i].w = compData.w; (x3)
// chars[i].data.ks = { (x3)
//   a: { k: [0, 0, 0], a: 0 }, (x3)
//   p: { k: [0, -compData.h, 0], a: 0 }, (x3)
//   r: { k: 0, a: 0 }, (x3)
//   s: { k: [100, 100], a: 0 }, (x3)
//   o: { k: 100, a: 0 }, (x3)
// }; (x3)
```

<details><summary>Code</summary>

```typescript
function dataFunctionManager() {
          function completeLayers(layers, comps) {
            var layerData;
            var i;
            var len = layers.length;
            var j;
            var jLen;
            var k;
            var kLen;
            for (i = 0; i < len; i += 1) {
              layerData = layers[i];
              if (('ks' in layerData) && !layerData.completed) {
                layerData.completed = true;
                if (layerData.tt) {
                  layers[i - 1].td = layerData.tt;
                }
                if (layerData.hasMask) {
                  var maskProps = layerData.masksProperties;
                  jLen = maskProps.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (maskProps[j].pt.k.i) {
                      convertPathsToAbsoluteValues(maskProps[j].pt.k);
                    } else {
                      kLen = maskProps[j].pt.k.length;
                      for (k = 0; k < kLen; k += 1) {
                        if (maskProps[j].pt.k[k].s) {
                          convertPathsToAbsoluteValues(maskProps[j].pt.k[k].s[0]);
                        }
                        if (maskProps[j].pt.k[k].e) {
                          convertPathsToAbsoluteValues(maskProps[j].pt.k[k].e[0]);
                        }
                      }
                    }
                  }
                }
                if (layerData.ty === 0) {
                  layerData.layers = findCompLayers(layerData.refId, comps);
                  completeLayers(layerData.layers, comps);
                } else if (layerData.ty === 4) {
                  completeShapes(layerData.shapes);
                } else if (layerData.ty === 5) {
                  completeText(layerData);
                }
              }
            }
          }

          function completeChars(chars, assets) {
            if (chars) {
              var i = 0;
              var len = chars.length;
              for (i = 0; i < len; i += 1) {
                if (chars[i].t === 1) {
                  // var compData = findComp(chars[i].data.refId, assets);
                  chars[i].data.layers = findCompLayers(chars[i].data.refId, assets);
                  // chars[i].data.ip = 0;
                  // chars[i].data.op = 99999;
                  // chars[i].data.st = 0;
                  // chars[i].data.sr = 1;
                  // chars[i].w = compData.w;
                  // chars[i].data.ks = {
                  //   a: { k: [0, 0, 0], a: 0 },
                  //   p: { k: [0, -compData.h, 0], a: 0 },
                  //   r: { k: 0, a: 0 },
                  //   s: { k: [100, 100], a: 0 },
                  //   o: { k: 100, a: 0 },
                  // };
                  completeLayers(chars[i].data.layers, assets);
                }
              }
            }
          }

          function findComp(id, comps) {
            var i = 0;
            var len = comps.length;
            while (i < len) {
              if (comps[i].id === id) {
                return comps[i];
              }
              i += 1;
            }
            return null;
          }

          function findCompLayers(id, comps) {
            var comp = findComp(id, comps);
            if (comp) {
              if (!comp.layers.__used) {
                comp.layers.__used = true;
                return comp.layers;
              }
              return JSON.parse(JSON.stringify(comp.layers));
            }
            return null;
          }

          function completeShapes(arr) {
            var i;
            var len = arr.length;
            var j;
            var jLen;
            for (i = len - 1; i >= 0; i -= 1) {
              if (arr[i].ty === 'sh') {
                if (arr[i].ks.k.i) {
                  convertPathsToAbsoluteValues(arr[i].ks.k);
                } else {
                  jLen = arr[i].ks.k.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (arr[i].ks.k[j].s) {
                      convertPathsToAbsoluteValues(arr[i].ks.k[j].s[0]);
                    }
                    if (arr[i].ks.k[j].e) {
                      convertPathsToAbsoluteValues(arr[i].ks.k[j].e[0]);
                    }
                  }
                }
              } else if (arr[i].ty === 'gr') {
                completeShapes(arr[i].it);
              }
            }
          }

          function convertPathsToAbsoluteValues(path) {
            var i;
            var len = path.i.length;
            for (i = 0; i < len; i += 1) {
              path.i[i][0] += path.v[i][0];
              path.i[i][1] += path.v[i][1];
              path.o[i][0] += path.v[i][0];
              path.o[i][1] += path.v[i][1];
            }
          }

          function checkVersion(minimum, animVersionString) {
            var animVersion = animVersionString ? animVersionString.split('.') : [100, 100, 100];
            if (minimum[0] > animVersion[0]) {
              return true;
            } if (animVersion[0] > minimum[0]) {
              return false;
            }
            if (minimum[1] > animVersion[1]) {
              return true;
            } if (animVersion[1] > minimum[1]) {
              return false;
            }
            if (minimum[2] > animVersion[2]) {
              return true;
            } if (animVersion[2] > minimum[2]) {
              return false;
            }
            return null;
          }

          var checkText = (function () {
            var minimumVersion = [4, 4, 14];

            function updateTextLayer(textLayer) {
              var documentData = textLayer.t.d;
              textLayer.t.d = {
                k: [
                  {
                    s: documentData,
                    t: 0,
                  },
                ],
              };
            }

            function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 5) {
                  updateTextLayer(layers[i]);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          var checkChars = (function () {
            var minimumVersion = [4, 7, 99];
            return function (animationData) {
              if (animationData.chars && !checkVersion(minimumVersion, animationData.v)) {
                var i;
                var len = animationData.chars.length;
                for (i = 0; i < len; i += 1) {
                  var charData = animationData.chars[i];
                  if (charData.data && charData.data.shapes) {
                    completeShapes(charData.data.shapes);
                    charData.data.ip = 0;
                    charData.data.op = 99999;
                    charData.data.st = 0;
                    charData.data.sr = 1;
                    charData.data.ks = {
                      p: { k: [0, 0], a: 0 },
                      s: { k: [100, 100], a: 0 },
                      a: { k: [0, 0], a: 0 },
                      r: { k: 0, a: 0 },
                      o: { k: 100, a: 0 },
                    };
                    if (!animationData.chars[i].t) {
                      charData.data.shapes.push(
                        {
                          ty: 'no',
                        }
                      );
                      charData.data.shapes[0].it.push(
                        {
                          p: { k: [0, 0], a: 0 },
                          s: { k: [100, 100], a: 0 },
                          a: { k: [0, 0], a: 0 },
                          r: { k: 0, a: 0 },
                          o: { k: 100, a: 0 },
                          sk: { k: 0, a: 0 },
                          sa: { k: 0, a: 0 },
                          ty: 'tr',
                        }
                      );
                    }
                  }
                }
              }
            };
          }());

          var checkPathProperties = (function () {
            var minimumVersion = [5, 7, 15];

            function updateTextLayer(textLayer) {
              var pathData = textLayer.t.p;
              if (typeof pathData.a === 'number') {
                pathData.a = {
                  a: 0,
                  k: pathData.a,
                };
              }
              if (typeof pathData.p === 'number') {
                pathData.p = {
                  a: 0,
                  k: pathData.p,
                };
              }
              if (typeof pathData.r === 'number') {
                pathData.r = {
                  a: 0,
                  k: pathData.r,
                };
              }
            }

            function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 5) {
                  updateTextLayer(layers[i]);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          var checkColors = (function () {
            var minimumVersion = [4, 1, 9];

            function iterateShapes(shapes) {
              var i;
              var len = shapes.length;
              var j;
              var jLen;
              for (i = 0; i < len; i += 1) {
                if (shapes[i].ty === 'gr') {
                  iterateShapes(shapes[i].it);
                } else if (shapes[i].ty === 'fl' || shapes[i].ty === 'st') {
                  if (shapes[i].c.k && shapes[i].c.k[0].i) {
                    jLen = shapes[i].c.k.length;
                    for (j = 0; j < jLen; j += 1) {
                      if (shapes[i].c.k[j].s) {
                        shapes[i].c.k[j].s[0] /= 255;
                        shapes[i].c.k[j].s[1] /= 255;
                        shapes[i].c.k[j].s[2] /= 255;
                        shapes[i].c.k[j].s[3] /= 255;
                      }
                      if (shapes[i].c.k[j].e) {
                        shapes[i].c.k[j].e[0] /= 255;
                        shapes[i].c.k[j].e[1] /= 255;
                        shapes[i].c.k[j].e[2] /= 255;
                        shapes[i].c.k[j].e[3] /= 255;
                      }
                    }
                  } else {
                    shapes[i].c.k[0] /= 255;
                    shapes[i].c.k[1] /= 255;
                    shapes[i].c.k[2] /= 255;
                    shapes[i].c.k[3] /= 255;
                  }
                }
              }
            }

            function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 4) {
                  iterateShapes(layers[i].shapes);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          var checkShapes = (function () {
            var minimumVersion = [4, 4, 18];

            function completeClosingShapes(arr) {
              var i;
              var len = arr.length;
              var j;
              var jLen;
              for (i = len - 1; i >= 0; i -= 1) {
                if (arr[i].ty === 'sh') {
                  if (arr[i].ks.k.i) {
                    arr[i].ks.k.c = arr[i].closed;
                  } else {
                    jLen = arr[i].ks.k.length;
                    for (j = 0; j < jLen; j += 1) {
                      if (arr[i].ks.k[j].s) {
                        arr[i].ks.k[j].s[0].c = arr[i].closed;
                      }
                      if (arr[i].ks.k[j].e) {
                        arr[i].ks.k[j].e[0].c = arr[i].closed;
                      }
                    }
                  }
                } else if (arr[i].ty === 'gr') {
                  completeClosingShapes(arr[i].it);
                }
              }
            }

            function iterateLayers(layers) {
              var layerData;
              var i;
              var len = layers.length;
              var j;
              var jLen;
              var k;
              var kLen;
              for (i = 0; i < len; i += 1) {
                layerData = layers[i];
                if (layerData.hasMask) {
                  var maskProps = layerData.masksProperties;
                  jLen = maskProps.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (maskProps[j].pt.k.i) {
                      maskProps[j].pt.k.c = maskProps[j].cl;
                    } else {
                      kLen = maskProps[j].pt.k.length;
                      for (k = 0; k < kLen; k += 1) {
                        if (maskProps[j].pt.k[k].s) {
                          maskProps[j].pt.k[k].s[0].c = maskProps[j].cl;
                        }
                        if (maskProps[j].pt.k[k].e) {
                          maskProps[j].pt.k[k].e[0].c = maskProps[j].cl;
                        }
                      }
                    }
                  }
                }
                if (layerData.ty === 4) {
                  completeClosingShapes(layerData.shapes);
                }
              }
            }

            return function (animationData) {
              if (checkVersion(minimumVersion, animationData.v)) {
                iterateLayers(animationData.layers);
                if (animationData.assets) {
                  var i;
                  var len = animationData.assets.length;
                  for (i = 0; i < len; i += 1) {
                    if (animationData.assets[i].layers) {
                      iterateLayers(animationData.assets[i].layers);
                    }
                  }
                }
              }
            };
          }());

          function completeData(animationData) {
            if (animationData.__complete) {
              return;
            }
            checkColors(animationData);
            checkText(animationData);
            checkChars(animationData);
            checkPathProperties(animationData);
            checkShapes(animationData);
            completeLayers(animationData.layers, animationData.assets);
            completeChars(animationData.chars, animationData.assets);
            animationData.__complete = true;
          }

          function completeText(data) {
            if (data.t.a.length === 0 && !('m' in data.t.p)) {
              // data.singleShape = true;
            }
          }

          var moduleOb = {};
          moduleOb.completeData = completeData;
          moduleOb.checkColors = checkColors;
          moduleOb.checkChars = checkChars;
          moduleOb.checkPathProperties = checkPathProperties;
          moduleOb.checkShapes = checkShapes;
          moduleOb.completeLayers = completeLayers;

          return moduleOb;
        }
```
</details>

### `completeLayers(layers: any, comps: any): void`

**Parameters:**

- **`layers`** `any`
- **`comps`** `any`

**Returns:** `void`

**Calls:**

- `convertPathsToAbsoluteValues`
- `findCompLayers`
- `completeLayers`
- `completeShapes`
- `completeText`

<details><summary>Code</summary>

```typescript
function completeLayers(layers, comps) {
            var layerData;
            var i;
            var len = layers.length;
            var j;
            var jLen;
            var k;
            var kLen;
            for (i = 0; i < len; i += 1) {
              layerData = layers[i];
              if (('ks' in layerData) && !layerData.completed) {
                layerData.completed = true;
                if (layerData.tt) {
                  layers[i - 1].td = layerData.tt;
                }
                if (layerData.hasMask) {
                  var maskProps = layerData.masksProperties;
                  jLen = maskProps.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (maskProps[j].pt.k.i) {
                      convertPathsToAbsoluteValues(maskProps[j].pt.k);
                    } else {
                      kLen = maskProps[j].pt.k.length;
                      for (k = 0; k < kLen; k += 1) {
                        if (maskProps[j].pt.k[k].s) {
                          convertPathsToAbsoluteValues(maskProps[j].pt.k[k].s[0]);
                        }
                        if (maskProps[j].pt.k[k].e) {
                          convertPathsToAbsoluteValues(maskProps[j].pt.k[k].e[0]);
                        }
                      }
                    }
                  }
                }
                if (layerData.ty === 0) {
                  layerData.layers = findCompLayers(layerData.refId, comps);
                  completeLayers(layerData.layers, comps);
                } else if (layerData.ty === 4) {
                  completeShapes(layerData.shapes);
                } else if (layerData.ty === 5) {
                  completeText(layerData);
                }
              }
            }
          }
```
</details>

### `completeChars(chars: any, assets: any): void`

**Parameters:**

- **`chars`** `any`
- **`assets`** `any`

**Returns:** `void`

**Calls:**

- `findCompLayers`
- `completeLayers`

**Internal Comments:**
```
// var compData = findComp(chars[i].data.refId, assets); (x6)
// chars[i].data.ip = 0; (x3)
// chars[i].data.op = 99999; (x3)
// chars[i].data.st = 0; (x3)
// chars[i].data.sr = 1; (x3)
// chars[i].w = compData.w; (x3)
// chars[i].data.ks = { (x3)
//   a: { k: [0, 0, 0], a: 0 }, (x3)
//   p: { k: [0, -compData.h, 0], a: 0 }, (x3)
//   r: { k: 0, a: 0 }, (x3)
//   s: { k: [100, 100], a: 0 }, (x3)
//   o: { k: 100, a: 0 }, (x3)
// }; (x3)
```

<details><summary>Code</summary>

```typescript
function completeChars(chars, assets) {
            if (chars) {
              var i = 0;
              var len = chars.length;
              for (i = 0; i < len; i += 1) {
                if (chars[i].t === 1) {
                  // var compData = findComp(chars[i].data.refId, assets);
                  chars[i].data.layers = findCompLayers(chars[i].data.refId, assets);
                  // chars[i].data.ip = 0;
                  // chars[i].data.op = 99999;
                  // chars[i].data.st = 0;
                  // chars[i].data.sr = 1;
                  // chars[i].w = compData.w;
                  // chars[i].data.ks = {
                  //   a: { k: [0, 0, 0], a: 0 },
                  //   p: { k: [0, -compData.h, 0], a: 0 },
                  //   r: { k: 0, a: 0 },
                  //   s: { k: [100, 100], a: 0 },
                  //   o: { k: 100, a: 0 },
                  // };
                  completeLayers(chars[i].data.layers, assets);
                }
              }
            }
          }
```
</details>

### `findComp(id: any, comps: any): any`

**Parameters:**

- **`id`** `any`
- **`comps`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function findComp(id, comps) {
            var i = 0;
            var len = comps.length;
            while (i < len) {
              if (comps[i].id === id) {
                return comps[i];
              }
              i += 1;
            }
            return null;
          }
```
</details>

### `findCompLayers(id: any, comps: any): any`

**Parameters:**

- **`id`** `any`
- **`comps`** `any`

**Returns:** `any`

**Calls:**

- `findComp`
- `JSON.parse`
- `JSON.stringify`

<details><summary>Code</summary>

```typescript
function findCompLayers(id, comps) {
            var comp = findComp(id, comps);
            if (comp) {
              if (!comp.layers.__used) {
                comp.layers.__used = true;
                return comp.layers;
              }
              return JSON.parse(JSON.stringify(comp.layers));
            }
            return null;
          }
```
</details>

### `completeShapes(arr: any): void`

**Parameters:**

- **`arr`** `any`

**Returns:** `void`

**Calls:**

- `convertPathsToAbsoluteValues`
- `completeShapes`

<details><summary>Code</summary>

```typescript
function completeShapes(arr) {
            var i;
            var len = arr.length;
            var j;
            var jLen;
            for (i = len - 1; i >= 0; i -= 1) {
              if (arr[i].ty === 'sh') {
                if (arr[i].ks.k.i) {
                  convertPathsToAbsoluteValues(arr[i].ks.k);
                } else {
                  jLen = arr[i].ks.k.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (arr[i].ks.k[j].s) {
                      convertPathsToAbsoluteValues(arr[i].ks.k[j].s[0]);
                    }
                    if (arr[i].ks.k[j].e) {
                      convertPathsToAbsoluteValues(arr[i].ks.k[j].e[0]);
                    }
                  }
                }
              } else if (arr[i].ty === 'gr') {
                completeShapes(arr[i].it);
              }
            }
          }
```
</details>

### `convertPathsToAbsoluteValues(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function convertPathsToAbsoluteValues(path) {
            var i;
            var len = path.i.length;
            for (i = 0; i < len; i += 1) {
              path.i[i][0] += path.v[i][0];
              path.i[i][1] += path.v[i][1];
              path.o[i][0] += path.v[i][0];
              path.o[i][1] += path.v[i][1];
            }
          }
```
</details>

### `checkVersion(minimum: any, animVersionString: any): boolean`

**Parameters:**

- **`minimum`** `any`
- **`animVersionString`** `any`

**Returns:** `boolean`

**Calls:**

- `animVersionString.split`

<details><summary>Code</summary>

```typescript
function checkVersion(minimum, animVersionString) {
            var animVersion = animVersionString ? animVersionString.split('.') : [100, 100, 100];
            if (minimum[0] > animVersion[0]) {
              return true;
            } if (animVersion[0] > minimum[0]) {
              return false;
            }
            if (minimum[1] > animVersion[1]) {
              return true;
            } if (animVersion[1] > minimum[1]) {
              return false;
            }
            if (minimum[2] > animVersion[2]) {
              return true;
            } if (animVersion[2] > minimum[2]) {
              return false;
            }
            return null;
          }
```
</details>

### `updateTextLayer(textLayer: any): void`

**Parameters:**

- **`textLayer`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function updateTextLayer(textLayer) {
              var documentData = textLayer.t.d;
              textLayer.t.d = {
                k: [
                  {
                    s: documentData,
                    t: 0,
                  },
                ],
              };
            }
```
</details>

### `iterateLayers(layers: any): void`

**Parameters:**

- **`layers`** `any`

**Returns:** `void`

**Calls:**

- `updateTextLayer`

<details><summary>Code</summary>

```typescript
function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 5) {
                  updateTextLayer(layers[i]);
                }
              }
            }
```
</details>

### `updateTextLayer(textLayer: any): void`

**Parameters:**

- **`textLayer`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function updateTextLayer(textLayer) {
              var pathData = textLayer.t.p;
              if (typeof pathData.a === 'number') {
                pathData.a = {
                  a: 0,
                  k: pathData.a,
                };
              }
              if (typeof pathData.p === 'number') {
                pathData.p = {
                  a: 0,
                  k: pathData.p,
                };
              }
              if (typeof pathData.r === 'number') {
                pathData.r = {
                  a: 0,
                  k: pathData.r,
                };
              }
            }
```
</details>

### `iterateLayers(layers: any): void`

**Parameters:**

- **`layers`** `any`

**Returns:** `void`

**Calls:**

- `updateTextLayer`

<details><summary>Code</summary>

```typescript
function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 5) {
                  updateTextLayer(layers[i]);
                }
              }
            }
```
</details>

### `iterateShapes(shapes: any): void`

**Parameters:**

- **`shapes`** `any`

**Returns:** `void`

**Calls:**

- `iterateShapes`

<details><summary>Code</summary>

```typescript
function iterateShapes(shapes) {
              var i;
              var len = shapes.length;
              var j;
              var jLen;
              for (i = 0; i < len; i += 1) {
                if (shapes[i].ty === 'gr') {
                  iterateShapes(shapes[i].it);
                } else if (shapes[i].ty === 'fl' || shapes[i].ty === 'st') {
                  if (shapes[i].c.k && shapes[i].c.k[0].i) {
                    jLen = shapes[i].c.k.length;
                    for (j = 0; j < jLen; j += 1) {
                      if (shapes[i].c.k[j].s) {
                        shapes[i].c.k[j].s[0] /= 255;
                        shapes[i].c.k[j].s[1] /= 255;
                        shapes[i].c.k[j].s[2] /= 255;
                        shapes[i].c.k[j].s[3] /= 255;
                      }
                      if (shapes[i].c.k[j].e) {
                        shapes[i].c.k[j].e[0] /= 255;
                        shapes[i].c.k[j].e[1] /= 255;
                        shapes[i].c.k[j].e[2] /= 255;
                        shapes[i].c.k[j].e[3] /= 255;
                      }
                    }
                  } else {
                    shapes[i].c.k[0] /= 255;
                    shapes[i].c.k[1] /= 255;
                    shapes[i].c.k[2] /= 255;
                    shapes[i].c.k[3] /= 255;
                  }
                }
              }
            }
```
</details>

### `iterateLayers(layers: any): void`

**Parameters:**

- **`layers`** `any`

**Returns:** `void`

**Calls:**

- `iterateShapes`

<details><summary>Code</summary>

```typescript
function iterateLayers(layers) {
              var i;
              var len = layers.length;
              for (i = 0; i < len; i += 1) {
                if (layers[i].ty === 4) {
                  iterateShapes(layers[i].shapes);
                }
              }
            }
```
</details>

### `completeClosingShapes(arr: any): void`

**Parameters:**

- **`arr`** `any`

**Returns:** `void`

**Calls:**

- `completeClosingShapes`

<details><summary>Code</summary>

```typescript
function completeClosingShapes(arr) {
              var i;
              var len = arr.length;
              var j;
              var jLen;
              for (i = len - 1; i >= 0; i -= 1) {
                if (arr[i].ty === 'sh') {
                  if (arr[i].ks.k.i) {
                    arr[i].ks.k.c = arr[i].closed;
                  } else {
                    jLen = arr[i].ks.k.length;
                    for (j = 0; j < jLen; j += 1) {
                      if (arr[i].ks.k[j].s) {
                        arr[i].ks.k[j].s[0].c = arr[i].closed;
                      }
                      if (arr[i].ks.k[j].e) {
                        arr[i].ks.k[j].e[0].c = arr[i].closed;
                      }
                    }
                  }
                } else if (arr[i].ty === 'gr') {
                  completeClosingShapes(arr[i].it);
                }
              }
            }
```
</details>

### `iterateLayers(layers: any): void`

**Parameters:**

- **`layers`** `any`

**Returns:** `void`

**Calls:**

- `completeClosingShapes`

<details><summary>Code</summary>

```typescript
function iterateLayers(layers) {
              var layerData;
              var i;
              var len = layers.length;
              var j;
              var jLen;
              var k;
              var kLen;
              for (i = 0; i < len; i += 1) {
                layerData = layers[i];
                if (layerData.hasMask) {
                  var maskProps = layerData.masksProperties;
                  jLen = maskProps.length;
                  for (j = 0; j < jLen; j += 1) {
                    if (maskProps[j].pt.k.i) {
                      maskProps[j].pt.k.c = maskProps[j].cl;
                    } else {
                      kLen = maskProps[j].pt.k.length;
                      for (k = 0; k < kLen; k += 1) {
                        if (maskProps[j].pt.k[k].s) {
                          maskProps[j].pt.k[k].s[0].c = maskProps[j].cl;
                        }
                        if (maskProps[j].pt.k[k].e) {
                          maskProps[j].pt.k[k].e[0].c = maskProps[j].cl;
                        }
                      }
                    }
                  }
                }
                if (layerData.ty === 4) {
                  completeClosingShapes(layerData.shapes);
                }
              }
            }
```
</details>

### `completeData(animationData: any): void`

**Parameters:**

- **`animationData`** `any`

**Returns:** `void`

**Calls:**

- `checkColors`
- `checkText`
- `checkChars`
- `checkPathProperties`
- `checkShapes`
- `completeLayers`
- `completeChars`

<details><summary>Code</summary>

```typescript
function completeData(animationData) {
            if (animationData.__complete) {
              return;
            }
            checkColors(animationData);
            checkText(animationData);
            checkChars(animationData);
            checkPathProperties(animationData);
            checkShapes(animationData);
            completeLayers(animationData.layers, animationData.assets);
            completeChars(animationData.chars, animationData.assets);
            animationData.__complete = true;
          }
```
</details>

### `completeText(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function completeText(data) {
            if (data.t.a.length === 0 && !('m' in data.t.p)) {
              // data.singleShape = true;
            }
          }
```
</details>

### `formatResponse(xhr: any): any`

**Parameters:**

- **`xhr`** `any`

**Returns:** `any`

**Calls:**

- `xhr.getResponseHeader`
- `contentTypeHeader.indexOf`
- `JSON.parse`

**Internal Comments:**
```
// using typeof doubles the time of execution of this method, (x2)
// so if available, it's better to use the header to validate the type (x2)
```

<details><summary>Code</summary>

```typescript
function formatResponse(xhr) {
              // using typeof doubles the time of execution of this method,
              // so if available, it's better to use the header to validate the type
              var contentTypeHeader = xhr.getResponseHeader('content-type');
              if (contentTypeHeader && xhr.responseType === 'json' && contentTypeHeader.indexOf('json') !== -1) {
                return xhr.response;
              }
              if (xhr.response && typeof xhr.response === 'object') {
                return xhr.response;
              } if (xhr.response && typeof xhr.response === 'string') {
                return JSON.parse(xhr.response);
              } if (xhr.responseText) {
                return JSON.parse(xhr.responseText);
              }
              return null;
            }
```
</details>

### `loadAsset(path: any, fullPath: any, callback: any, errorCallback: any): void`

**Parameters:**

- **`path`** `any`
- **`fullPath`** `any`
- **`callback`** `any`
- **`errorCallback`** `any`

**Returns:** `void`

**Calls:**

- `formatResponse`
- `callback`
- `errorCallback`
- `xhr.open`
- `xhr.send`

**Internal Comments:**
```
// set responseType after calling open or IE will break.
// This crashes on Android WebView prior to KitKat (x4)
```

<details><summary>Code</summary>

```typescript
function loadAsset(path, fullPath, callback, errorCallback) {
              var response;
              var xhr = new XMLHttpRequest();
              // set responseType after calling open or IE will break.
              try {
                // This crashes on Android WebView prior to KitKat
                xhr.responseType = 'json';
              } catch (err) {} // eslint-disable-line no-empty
              xhr.onreadystatechange = function () {
                if (xhr.readyState === 4) {
                  if (xhr.status === 200) {
                    response = formatResponse(xhr);
                    callback(response);
                  } else {
                    try {
                      response = formatResponse(xhr);
                      callback(response);
                    } catch (err) {
                      if (errorCallback) {
                        errorCallback(err);
                      }
                    }
                  }
                }
              };
              try {
                xhr.open('GET', path, true);
              } catch (error) {
                xhr.open('GET', fullPath + '/' + path, true);
              }
              xhr.send();
            }
```
</details>

### `createProcess(onComplete: any, onError: any): string`

**Parameters:**

- **`onComplete`** `any`
- **`onError`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function createProcess(onComplete, onError) {
    _counterId += 1;
    var id = 'processId_' + _counterId;
    processes[id] = {
      onComplete: onComplete,
      onError: onError,
    };
    return id;
  }
```
</details>

### `loadAnimation(path: any, onComplete: any, onError: any): void`

**Parameters:**

- **`path`** `any`
- **`onComplete`** `any`
- **`onError`** `any`

**Returns:** `void`

**Calls:**

- `setupWorker`
- `createProcess`
- `workerInstance.postMessage`

<details><summary>Code</summary>

```typescript
function loadAnimation(path, onComplete, onError) {
    setupWorker();
    var processId = createProcess(onComplete, onError);
    workerInstance.postMessage({
      type: 'loadAnimation',
      path: path,
      fullPath: window.location.origin + window.location.pathname,
      id: processId,
    });
  }
```
</details>

### `loadData(path: any, onComplete: any, onError: any): void`

**Parameters:**

- **`path`** `any`
- **`onComplete`** `any`
- **`onError`** `any`

**Returns:** `void`

**Calls:**

- `setupWorker`
- `createProcess`
- `workerInstance.postMessage`

<details><summary>Code</summary>

```typescript
function loadData(path, onComplete, onError) {
    setupWorker();
    var processId = createProcess(onComplete, onError);
    workerInstance.postMessage({
      type: 'loadData',
      path: path,
      fullPath: window.location.origin + window.location.pathname,
      id: processId,
    });
  }
```
</details>

### `completeAnimation(anim: any, onComplete: any, onError: any): void`

**Parameters:**

- **`anim`** `any`
- **`onComplete`** `any`
- **`onError`** `any`

**Returns:** `void`

**Calls:**

- `setupWorker`
- `createProcess`
- `workerInstance.postMessage`

<details><summary>Code</summary>

```typescript
function completeAnimation(anim, onComplete, onError) {
    setupWorker();
    var processId = createProcess(onComplete, onError);
    workerInstance.postMessage({
      type: 'complete',
      animation: anim,
      id: processId,
    });
  }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `onmessage(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

    }
```
</details>

### `postMessage(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

**Calls:**

- `workerFn`

<details><summary>Code</summary>

```typescript
function (path) {
      workerFn({
        data: path,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `postMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `workerProxy.onmessage`

<details><summary>Code</summary>

```typescript
function (data) {
      workerProxy.onmessage({
        data: data,
      });
    }
```
</details>

### `imageLoaded(): void`

**Returns:** `void`

**Calls:**

- `this.imagesLoadedCb`

<details><summary>Code</summary>

```typescript
function imageLoaded() {
    this.loadedAssets += 1;
    if (this.loadedAssets === this.totalImages && this.loadedFootagesCount === this.totalFootages) {
      if (this.imagesLoadedCb) {
        this.imagesLoadedCb(null);
      }
    }
  }
```
</details>

### `footageLoaded(): void`

**Returns:** `void`

**Calls:**

- `this.imagesLoadedCb`

<details><summary>Code</summary>

```typescript
function footageLoaded() {
    this.loadedFootagesCount += 1;
    if (this.loadedAssets === this.totalImages && this.loadedFootagesCount === this.totalFootages) {
      if (this.imagesLoadedCb) {
        this.imagesLoadedCb(null);
      }
    }
  }
```
</details>

### `getAssetsPath(assetData: any, assetsPath: any, originalPath: any): string`

**Parameters:**

- **`assetData`** `any`
- **`assetsPath`** `any`
- **`originalPath`** `any`

**Returns:** `string`

**Calls:**

- `imagePath.indexOf`
- `imagePath.split`

<details><summary>Code</summary>

```typescript
function getAssetsPath(assetData, assetsPath, originalPath) {
    var path = '';
    if (assetData.e) {
      path = assetData.p;
    } else if (assetsPath) {
      var imagePath = assetData.p;
      if (imagePath.indexOf('images/') !== -1) {
        imagePath = imagePath.split('/')[1];
      }
      path = assetsPath + imagePath;
    } else {
      path = originalPath;
      path += assetData.u ? assetData.u : '';
      path += assetData.p;
    }
    return path;
  }
```
</details>

### `testImageLoaded(img: any): void`

**Parameters:**

- **`img`** `any`

**Returns:** `void`

**Calls:**

- `setInterval`
- `function () {
      var box = img.getBBox();
      if (box.width || _count > 500) {
        this._imageLoaded();
        clearInterval(intervalId);
      }
      _count += 1;
    }.bind`
- `img.getBBox`
- `this._imageLoaded`
- `clearInterval`

<details><summary>Code</summary>

```typescript
function testImageLoaded(img) {
    var _count = 0;
    var intervalId = setInterval(function () {
      var box = img.getBBox();
      if (box.width || _count > 500) {
        this._imageLoaded();
        clearInterval(intervalId);
      }
      _count += 1;
    }.bind(this), 50);
  }
```
</details>

### `createImageData(assetData: any): { img: any; assetData: any; }`

**Parameters:**

- **`assetData`** `any`

**Returns:** `{ img: any; assetData: any; }`

**Calls:**

- `getAssetsPath`
- `createNS`
- `this.testImageLoaded`
- `img.addEventListener`
- `function () {
      ob.img = proxyImage;
      this._imageLoaded();
    }.bind`
- `this._imageLoaded`
- `img.setAttributeNS`
- `this._elementHelper.append`
- `this._elementHelper.appendChild`

<details><summary>Code</summary>

```typescript
function createImageData(assetData) {
    var path = getAssetsPath(assetData, this.assetsPath, this.path);
    var img = createNS('image');
    if (isSafari) {
      this.testImageLoaded(img);
    } else {
      img.addEventListener('load', this._imageLoaded, false);
    }
    img.addEventListener('error', function () {
      ob.img = proxyImage;
      this._imageLoaded();
    }.bind(this), false);
    img.setAttributeNS('http://www.w3.org/1999/xlink', 'href', path);
    if (this._elementHelper.append) {
      this._elementHelper.append(img);
    } else {
      this._elementHelper.appendChild(img);
    }
    var ob = {
      img: img,
      assetData: assetData,
    };
    return ob;
  }
```
</details>

### `createImgData(assetData: any): { img: any; assetData: any; }`

**Parameters:**

- **`assetData`** `any`

**Returns:** `{ img: any; assetData: any; }`

**Calls:**

- `getAssetsPath`
- `createTag`
- `img.addEventListener`
- `function () {
      ob.img = proxyImage;
      this._imageLoaded();
    }.bind`
- `this._imageLoaded`

<details><summary>Code</summary>

```typescript
function createImgData(assetData) {
    var path = getAssetsPath(assetData, this.assetsPath, this.path);
    var img = createTag('img');
    img.crossOrigin = 'anonymous';
    img.addEventListener('load', this._imageLoaded, false);
    img.addEventListener('error', function () {
      ob.img = proxyImage;
      this._imageLoaded();
    }.bind(this), false);
    img.src = path;
    var ob = {
      img: img,
      assetData: assetData,
    };
    return ob;
  }
```
</details>

### `createFootageData(data: any): { assetData: any; }`

**Parameters:**

- **`data`** `any`

**Returns:** `{ assetData: any; }`

**Calls:**

- `getAssetsPath`
- `dataManager.loadData`
- `function (footageData) {
      ob.img = footageData;
      this._footageLoaded();
    }.bind`
- `this._footageLoaded`
- `function () {
      ob.img = {};
      this._footageLoaded();
    }.bind`

<details><summary>Code</summary>

```typescript
function createFootageData(data) {
    var ob = {
      assetData: data,
    };
    var path = getAssetsPath(data, this.assetsPath, this.path);
    dataManager.loadData(path, function (footageData) {
      ob.img = footageData;
      this._footageLoaded();
    }.bind(this), function () {
      ob.img = {};
      this._footageLoaded();
    }.bind(this));
    return ob;
  }
```
</details>

### `loadAssets(assets: any, cb: any): void`

**Parameters:**

- **`assets`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `this.images.push`
- `this._createImageData`
- `this.createFootageData`

<details><summary>Code</summary>

```typescript
function loadAssets(assets, cb) {
    this.imagesLoadedCb = cb;
    var i;
    var len = assets.length;
    for (i = 0; i < len; i += 1) {
      if (!assets[i].layers) {
        if (!assets[i].t || assets[i].t === 'seq') {
          this.totalImages += 1;
          this.images.push(this._createImageData(assets[i]));
        } else if (assets[i].t === 3) {
          this.totalFootages += 1;
          this.images.push(this.createFootageData(assets[i]));
        }
      }
    }
  }
```
</details>

### `setPath(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setPath(path) {
    this.path = path || '';
  }
```
</details>

### `setAssetsPath(path: any): void`

**Parameters:**

- **`path`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setAssetsPath(path) {
    this.assetsPath = path || '';
  }
```
</details>

### `getAsset(assetData: any): any`

**Parameters:**

- **`assetData`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getAsset(assetData) {
    var i = 0;
    var len = this.images.length;
    while (i < len) {
      if (this.images[i].assetData === assetData) {
        return this.images[i].img;
      }
      i += 1;
    }
    return null;
  }
```
</details>

### `destroy(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function destroy() {
    this.imagesLoadedCb = null;
    this.images.length = 0;
  }
```
</details>

### `loadedImages(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function loadedImages() {
    return this.totalImages === this.loadedAssets;
  }
```
</details>

### `loadedFootages(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function loadedFootages() {
    return this.totalFootages === this.loadedFootagesCount;
  }
```
</details>

### `setCacheType(type: any, elementHelper: any): void`

**Parameters:**

- **`type`** `any`
- **`elementHelper`** `any`

**Returns:** `void`

**Calls:**

- `this.createImageData.bind`
- `this.createImgData.bind`

<details><summary>Code</summary>

```typescript
function setCacheType(type, elementHelper) {
    if (type === 'svg') {
      this._elementHelper = elementHelper;
      this._createImageData = this.createImageData.bind(this);
    } else {
      this._createImageData = this.createImgData.bind(this);
    }
  }
```
</details>

### `ImagePreloaderFactory(): void`

**Returns:** `void`

**Calls:**

- `imageLoaded.bind`
- `footageLoaded.bind`
- `testImageLoaded.bind`
- `createFootageData.bind`

<details><summary>Code</summary>

```typescript
function ImagePreloaderFactory() {
    this._imageLoaded = imageLoaded.bind(this);
    this._footageLoaded = footageLoaded.bind(this);
    this.testImageLoaded = testImageLoaded.bind(this);
    this.createFootageData = createFootageData.bind(this);
    this.assetsPath = '';
    this.path = '';
    this.totalImages = 0;
    this.totalFootages = 0;
    this.loadedAssets = 0;
    this.loadedFootagesCount = 0;
    this.imagesLoadedCb = null;
    this.images = [];
  }
```
</details>

### `ImagePreloaderFactory(): void`

**Returns:** `void`

**Calls:**

- `imageLoaded.bind`
- `footageLoaded.bind`
- `testImageLoaded.bind`
- `createFootageData.bind`

<details><summary>Code</summary>

```typescript
function ImagePreloaderFactory() {
    this._imageLoaded = imageLoaded.bind(this);
    this._footageLoaded = footageLoaded.bind(this);
    this.testImageLoaded = testImageLoaded.bind(this);
    this.createFootageData = createFootageData.bind(this);
    this.assetsPath = '';
    this.path = '';
    this.totalImages = 0;
    this.totalFootages = 0;
    this.loadedAssets = 0;
    this.loadedFootagesCount = 0;
    this.imagesLoadedCb = null;
    this.images = [];
  }
```
</details>

### `BaseEvent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BaseEvent() {}
```
</details>

### `triggerEvent(eventName: any, args: any): void`

**Parameters:**

- **`eventName`** `any`
- **`args`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_38627`

<details><summary>Code</summary>

```typescript
function (eventName, args) {
    if (this._cbs[eventName]) {
      var callbacks = this._cbs[eventName];
      for (var i = 0; i < callbacks.length; i += 1) {
        callbacks[i](args);
      }
    }
  }
```
</details>

### `addEventListener(eventName: any, callback: any): any`

**Parameters:**

- **`eventName`** `any`
- **`callback`** `any`

**Returns:** `any`

**Calls:**

- `this._cbs[eventName].push`
- `function () {
      this.removeEventListener(eventName, callback);
    }.bind`
- `this.removeEventListener`

<details><summary>Code</summary>

```typescript
function (eventName, callback) {
    if (!this._cbs[eventName]) {
      this._cbs[eventName] = [];
    }
    this._cbs[eventName].push(callback);

    return function () {
      this.removeEventListener(eventName, callback);
    }.bind(this);
  }
```
</details>

### `removeEventListener(eventName: any, callback: any): void`

**Parameters:**

- **`eventName`** `any`
- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `this._cbs[eventName].splice`

<details><summary>Code</summary>

```typescript
function (eventName, callback) {
    if (!callback) {
      this._cbs[eventName] = null;
    } else if (this._cbs[eventName]) {
      var i = 0;
      var len = this._cbs[eventName].length;
      while (i < len) {
        if (this._cbs[eventName][i] === callback) {
          this._cbs[eventName].splice(i, 1);
          i -= 1;
          len -= 1;
        }
        i += 1;
      }
      if (!this._cbs[eventName].length) {
        this._cbs[eventName] = null;
      }
    }
  }
```
</details>

### `triggerEvent(eventName: any, args: any): void`

**Parameters:**

- **`eventName`** `any`
- **`args`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_38627`

<details><summary>Code</summary>

```typescript
function (eventName, args) {
    if (this._cbs[eventName]) {
      var callbacks = this._cbs[eventName];
      for (var i = 0; i < callbacks.length; i += 1) {
        callbacks[i](args);
      }
    }
  }
```
</details>

### `addEventListener(eventName: any, callback: any): any`

**Parameters:**

- **`eventName`** `any`
- **`callback`** `any`

**Returns:** `any`

**Calls:**

- `this._cbs[eventName].push`
- `function () {
      this.removeEventListener(eventName, callback);
    }.bind`
- `this.removeEventListener`

<details><summary>Code</summary>

```typescript
function (eventName, callback) {
    if (!this._cbs[eventName]) {
      this._cbs[eventName] = [];
    }
    this._cbs[eventName].push(callback);

    return function () {
      this.removeEventListener(eventName, callback);
    }.bind(this);
  }
```
</details>

### `removeEventListener(eventName: any, callback: any): void`

**Parameters:**

- **`eventName`** `any`
- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `this._cbs[eventName].splice`

<details><summary>Code</summary>

```typescript
function (eventName, callback) {
    if (!callback) {
      this._cbs[eventName] = null;
    } else if (this._cbs[eventName]) {
      var i = 0;
      var len = this._cbs[eventName].length;
      while (i < len) {
        if (this._cbs[eventName][i] === callback) {
          this._cbs[eventName].splice(i, 1);
          i -= 1;
          len -= 1;
        }
        i += 1;
      }
      if (!this._cbs[eventName].length) {
        this._cbs[eventName] = null;
      }
    }
  }
```
</details>

### `parsePayloadLines(payload: any): {}`

**Parameters:**

- **`payload`** `any`

**Returns:** `{}`

**Calls:**

- `payload.split`
- `lines[i].split`
- `line[1].trim`

<details><summary>Code</summary>

```typescript
function parsePayloadLines(payload) {
      var lines = payload.split('\r\n');
      var keys = {};
      var line;
      var keysCount = 0;
      for (var i = 0; i < lines.length; i += 1) {
        line = lines[i].split(':');
        if (line.length === 2) {
          keys[line[0]] = line[1].trim();
          keysCount += 1;
        }
      }
      if (keysCount === 0) {
        throw new Error();
      }
      return keys;
    }
```
</details>

### `registerComposition(comp: any): void`

**Parameters:**

- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.compositions.push`

<details><summary>Code</summary>

```typescript
function registerComposition(comp) {
    this.compositions.push(comp);
  }
```
</details>

### `_thisProjectFunction(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.compositions[i].prepareFrame`

<details><summary>Code</summary>

```typescript
function _thisProjectFunction(name) {
      var i = 0;
      var len = this.compositions.length;
      while (i < len) {
        if (this.compositions[i].data && this.compositions[i].data.nm === name) {
          if (this.compositions[i].prepareFrame && this.compositions[i].data.xt) {
            this.compositions[i].prepareFrame(this.currentFrame);
          }
          return this.compositions[i].compInterface;
        }
        i += 1;
      }
      return null;
    }
```
</details>

### `registerRenderer(key: any, value: any): void`

**Parameters:**

- **`key`** `any`
- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(key, value) => {
  renderers[key] = value;
}
```
</details>

### `getRenderer(key: any): any`

**Parameters:**

- **`key`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getRenderer(key) {
  return renderers[key];
}
```
</details>

### `AnimationItem(): void`

**Returns:** `void`

**Calls:**

- `createElementID`
- `getSubframeEnabled`
- `ProjectInterface`
- `audioControllerFactory`
- `this.configAnimation.bind`
- `this.onSetupError.bind`
- `this.onSegmentComplete.bind`

<details><summary>Code</summary>

```typescript
function () {
  this._cbs = [];
  this.name = '';
  this.path = '';
  this.isLoaded = false;
  this.currentFrame = 0;
  this.currentRawFrame = 0;
  this.firstFrame = 0;
  this.totalFrames = 0;
  this.frameRate = 0;
  this.frameMult = 0;
  this.playSpeed = 1;
  this.playDirection = 1;
  this.playCount = 0;
  this.animationData = {};
  this.assets = [];
  this.isPaused = true;
  this.autoplay = false;
  this.loop = true;
  this.renderer = null;
  this.animationID = createElementID();
  this.assetsPath = '';
  this.timeCompleted = 0;
  this.segmentPos = 0;
  this.isSubframeEnabled = getSubframeEnabled();
  this.segments = [];
  this._idle = true;
  this._completedLoop = false;
  this.projectInterface = ProjectInterface();
  this.imagePreloader = new ImagePreloader();
  this.audioController = audioControllerFactory();
  this.markers = [];
  this.configAnimation = this.configAnimation.bind(this);
  this.onSetupError = this.onSetupError.bind(this);
  this.onSegmentComplete = this.onSegmentComplete.bind(this);
  this.drawnFrameEvent = new BMEnterFrameEvent('drawnFrame', 0, 0, 0);
}
```
</details>

### `removeElement(ev: any): void`

**Parameters:**

- **`ev`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations.splice`
- `subtractPlayingCount`

<details><summary>Code</summary>

```typescript
function removeElement(ev) {
    var i = 0;
    var animItem = ev.target;
    while (i < len) {
      if (registeredAnimations[i].animation === animItem) {
        registeredAnimations.splice(i, 1);
        i -= 1;
        len -= 1;
        if (!animItem.isPaused) {
          subtractPlayingCount();
        }
      }
      i += 1;
    }
  }
```
</details>

### `registerAnimation(element: any, animationData: any): any`

**Parameters:**

- **`element`** `any`
- **`animationData`** `any`

**Returns:** `any`

**Calls:**

- `setupAnimation`
- `animItem.setData`

<details><summary>Code</summary>

```typescript
function registerAnimation(element, animationData) {
    if (!element) {
      return null;
    }
    var i = 0;
    while (i < len) {
      if (registeredAnimations[i].elem === element && registeredAnimations[i].elem !== null) {
        return registeredAnimations[i].animation;
      }
      i += 1;
    }
    var animItem = new AnimationItem();
    setupAnimation(animItem, element);
    animItem.setData(element, animationData);
    return animItem;
  }
```
</details>

### `getRegisteredAnimations(): any[]`

**Returns:** `any[]`

**Calls:**

- `animations.push`

<details><summary>Code</summary>

```typescript
function getRegisteredAnimations() {
    var i;
    var lenAnims = registeredAnimations.length;
    var animations = [];
    for (i = 0; i < lenAnims; i += 1) {
      animations.push(registeredAnimations[i].animation);
    }
    return animations;
  }
```
</details>

### `addPlayingCount(): void`

**Returns:** `void`

**Calls:**

- `activate`

<details><summary>Code</summary>

```typescript
function addPlayingCount() {
    playingAnimationsNum += 1;
    activate();
  }
```
</details>

### `subtractPlayingCount(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function subtractPlayingCount() {
    playingAnimationsNum -= 1;
  }
```
</details>

### `setupAnimation(animItem: any, element: any): void`

**Parameters:**

- **`animItem`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `animItem.addEventListener`
- `registeredAnimations.push`

<details><summary>Code</summary>

```typescript
function setupAnimation(animItem, element) {
    animItem.addEventListener('destroy', removeElement);
    animItem.addEventListener('_active', addPlayingCount);
    animItem.addEventListener('_idle', subtractPlayingCount);
    registeredAnimations.push({ elem: element, animation: animItem });
    len += 1;
  }
```
</details>

### `loadAnimation(params: any): AnimationItem`

**Parameters:**

- **`params`** `any`

**Returns:** `AnimationItem`

**Calls:**

- `setupAnimation`
- `animItem.setParams`

<details><summary>Code</summary>

```typescript
function loadAnimation(params) {
    var animItem = new AnimationItem();
    setupAnimation(animItem, null);
    animItem.setParams(params);
    return animItem;
  }
```
</details>

### `setSpeed(val: any, animation: any): void`

**Parameters:**

- **`val`** `any`
- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.setSpeed`

<details><summary>Code</summary>

```typescript
function setSpeed(val, animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.setSpeed(val, animation);
    }
  }
```
</details>

### `setDirection(val: any, animation: any): void`

**Parameters:**

- **`val`** `any`
- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.setDirection`

<details><summary>Code</summary>

```typescript
function setDirection(val, animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.setDirection(val, animation);
    }
  }
```
</details>

### `play(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.play`

<details><summary>Code</summary>

```typescript
function play(animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.play(animation);
    }
  }
```
</details>

### `resume(nowTime: any): void`

**Parameters:**

- **`nowTime`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.advanceTime`
- `window.requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function resume(nowTime) {
    var elapsedTime = nowTime - initTime;
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.advanceTime(elapsedTime);
    }
    initTime = nowTime;
    if (playingAnimationsNum && !_isFrozen) {
      window.requestAnimationFrame(resume);
    } else {
      _stopped = true;
    }
  }
```
</details>

### `first(nowTime: any): void`

**Parameters:**

- **`nowTime`** `any`

**Returns:** `void`

**Calls:**

- `window.requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function first(nowTime) {
    initTime = nowTime;
    window.requestAnimationFrame(resume);
  }
```
</details>

### `pause(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.pause`

<details><summary>Code</summary>

```typescript
function pause(animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.pause(animation);
    }
  }
```
</details>

### `goToAndStop(value: any, isFrame: any, animation: any): void`

**Parameters:**

- **`value`** `any`
- **`isFrame`** `any`
- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.goToAndStop`

<details><summary>Code</summary>

```typescript
function goToAndStop(value, isFrame, animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.goToAndStop(value, isFrame, animation);
    }
  }
```
</details>

### `stop(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.stop`

<details><summary>Code</summary>

```typescript
function stop(animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.stop(animation);
    }
  }
```
</details>

### `togglePause(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.togglePause`

<details><summary>Code</summary>

```typescript
function togglePause(animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.togglePause(animation);
    }
  }
```
</details>

### `destroy(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.destroy`

<details><summary>Code</summary>

```typescript
function destroy(animation) {
    var i;
    for (i = (len - 1); i >= 0; i -= 1) {
      registeredAnimations[i].animation.destroy(animation);
    }
  }
```
</details>

### `searchAnimations(animationData: any, standalone: any, renderer: any): void`

**Parameters:**

- **`animationData`** `any`
- **`standalone`** `any`
- **`renderer`** `any`

**Returns:** `void`

**Calls:**

- `[].concat`
- `[].slice.call`
- `document.getElementsByClassName`
- `animElements[i].setAttribute`
- `registerAnimation`
- `document.getElementsByTagName`
- `createTag`
- `div.setAttribute`
- `body.appendChild`

<details><summary>Code</summary>

```typescript
function searchAnimations(animationData, standalone, renderer) {
    var animElements = [].concat([].slice.call(document.getElementsByClassName('lottie')),
      [].slice.call(document.getElementsByClassName('bodymovin')));
    var i;
    var lenAnims = animElements.length;
    for (i = 0; i < lenAnims; i += 1) {
      if (renderer) {
        animElements[i].setAttribute('data-bm-type', renderer);
      }
      registerAnimation(animElements[i], animationData);
    }
    if (standalone && lenAnims === 0) {
      if (!renderer) {
        renderer = 'svg';
      }
      var body = document.getElementsByTagName('body')[0];
      body.innerText = '';
      var div = createTag('div');
      div.style.width = '100%';
      div.style.height = '100%';
      div.setAttribute('data-bm-type', renderer);
      body.appendChild(div);
      registerAnimation(div, animationData);
    }
  }
```
</details>

### `resize(): void`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.resize`

<details><summary>Code</summary>

```typescript
function resize() {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.resize();
    }
  }
```
</details>

### `activate(): void`

**Returns:** `void`

**Calls:**

- `window.requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function activate() {
    if (!_isFrozen && playingAnimationsNum) {
      if (_stopped) {
        window.requestAnimationFrame(first);
        _stopped = false;
      }
    }
  }
```
</details>

### `freeze(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function freeze() {
    _isFrozen = true;
  }
```
</details>

### `unfreeze(): void`

**Returns:** `void`

**Calls:**

- `activate`

<details><summary>Code</summary>

```typescript
function unfreeze() {
    _isFrozen = false;
    activate();
  }
```
</details>

### `setVolume(val: any, animation: any): void`

**Parameters:**

- **`val`** `any`
- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.setVolume`

<details><summary>Code</summary>

```typescript
function setVolume(val, animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.setVolume(val, animation);
    }
  }
```
</details>

### `mute(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.mute`

<details><summary>Code</summary>

```typescript
function mute(animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.mute(animation);
    }
  }
```
</details>

### `unmute(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `registeredAnimations[i].animation.unmute`

<details><summary>Code</summary>

```typescript
function unmute(animation) {
    var i;
    for (i = 0; i < len; i += 1) {
      registeredAnimations[i].animation.unmute(animation);
    }
  }
```
</details>

### `getBezierEasing(a: any, b: any, c: any, d: any, nm: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`d`** `any`
- **`nm`** `any`

**Returns:** `any`

**Calls:**

- `('bez_' + a + '_' + b + '_' + c + '_' + d).replace`

<details><summary>Code</summary>

```typescript
function getBezierEasing(a, b, c, d, nm) {
    var str = nm || ('bez_' + a + '_' + b + '_' + c + '_' + d).replace(/\./g, 'p');
    if (beziers[str]) {
      return beziers[str];
    }
    var bezEasing = new BezierEasing([a, b, c, d]);
    beziers[str] = bezEasing;
    return bezEasing;
  }
```
</details>

### `A(aA1: any, aA2: any): number`

**Parameters:**

- **`aA1`** `any`
- **`aA2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function A(aA1, aA2) { return 1.0 - 3.0 * aA2 + 3.0 * aA1; }
```
</details>

### `B(aA1: any, aA2: any): number`

**Parameters:**

- **`aA1`** `any`
- **`aA2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function B(aA1, aA2) { return 3.0 * aA2 - 6.0 * aA1; }
```
</details>

### `C(aA1: any): number`

**Parameters:**

- **`aA1`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function C(aA1) { return 3.0 * aA1; }
```
</details>

### `calcBezier(aT: any, aA1: any, aA2: any): number`

**Parameters:**

- **`aT`** `any`
- **`aA1`** `any`
- **`aA2`** `any`

**Returns:** `number`

**Calls:**

- `A`
- `B`
- `C`

<details><summary>Code</summary>

```typescript
function calcBezier(aT, aA1, aA2) {
    return ((A(aA1, aA2) * aT + B(aA1, aA2)) * aT + C(aA1)) * aT;
  }
```
</details>

### `getSlope(aT: any, aA1: any, aA2: any): number`

**Parameters:**

- **`aT`** `any`
- **`aA1`** `any`
- **`aA2`** `any`

**Returns:** `number`

**Calls:**

- `A`
- `B`
- `C`

<details><summary>Code</summary>

```typescript
function getSlope(aT, aA1, aA2) {
    return 3.0 * A(aA1, aA2) * aT * aT + 2.0 * B(aA1, aA2) * aT + C(aA1);
  }
```
</details>

### `binarySubdivide(aX: any, aA: any, aB: any, mX1: any, mX2: any): any`

**Parameters:**

- **`aX`** `any`
- **`aA`** `any`
- **`aB`** `any`
- **`mX1`** `any`
- **`mX2`** `any`

**Returns:** `any`

**Calls:**

- `calcBezier`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function binarySubdivide(aX, aA, aB, mX1, mX2) {
    var currentX,
      currentT,
      i = 0;
    do {
      currentT = aA + (aB - aA) / 2.0;
      currentX = calcBezier(currentT, mX1, mX2) - aX;
      if (currentX > 0.0) {
        aB = currentT;
      } else {
        aA = currentT;
      }
    } while (Math.abs(currentX) > SUBDIVISION_PRECISION && ++i < SUBDIVISION_MAX_ITERATIONS);
    return currentT;
  }
```
</details>

### `newtonRaphsonIterate(aX: any, aGuessT: any, mX1: any, mX2: any): any`

**Parameters:**

- **`aX`** `any`
- **`aGuessT`** `any`
- **`mX1`** `any`
- **`mX2`** `any`

**Returns:** `any`

**Calls:**

- `getSlope`
- `calcBezier`

<details><summary>Code</summary>

```typescript
function newtonRaphsonIterate(aX, aGuessT, mX1, mX2) {
    for (var i = 0; i < NEWTON_ITERATIONS; ++i) {
      var currentSlope = getSlope(aGuessT, mX1, mX2);
      if (currentSlope === 0.0) return aGuessT;
      var currentX = calcBezier(aGuessT, mX1, mX2) - aX;
      aGuessT -= currentX / currentSlope;
    }
    return aGuessT;
  }
```
</details>

### `BezierEasing(points: any): void`

**JSDoc:**
```typescript
/**
     * points is an array of [ mX1, mY1, mX2, mY2 ]
     */
```

**Parameters:**

- **`points`** `any`

**Returns:** `void`

**Calls:**

- `this.get.bind`

<details><summary>Code</summary>

```typescript
function BezierEasing(points) {
    this._p = points;
    this._mSampleValues = float32ArraySupported ? new Float32Array(kSplineTableSize) : new Array(kSplineTableSize);
    this._precomputed = false;

    this.get = this.get.bind(this);
  }
```
</details>

### `get(x: any): any`

**Parameters:**

- **`x`** `any`

**Returns:** `any`

**Calls:**

- `this._precompute`
- `calcBezier`
- `this._getTForX`

**Internal Comments:**
```
// Because JavaScript number are imprecise, we should guarantee the extremes are right.
```

<details><summary>Code</summary>

```typescript
function (x) {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      if (!this._precomputed) this._precompute();
      if (mX1 === mY1 && mX2 === mY2) return x; // linear
      // Because JavaScript number are imprecise, we should guarantee the extremes are right.
      if (x === 0) return 0;
      if (x === 1) return 1;
      return calcBezier(this._getTForX(x), mY1, mY2);
    }
```
</details>

### `_precompute(): void`

**Returns:** `void`

**Calls:**

- `this._calcSampleValues`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      this._precomputed = true;
      if (mX1 !== mY1 || mX2 !== mY2) { this._calcSampleValues(); }
    }
```
</details>

### `_calcSampleValues(): void`

**Returns:** `void`

**Calls:**

- `calcBezier`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mX2 = this._p[2];
      for (var i = 0; i < kSplineTableSize; ++i) {
        this._mSampleValues[i] = calcBezier(i * kSampleStepSize, mX1, mX2);
      }
    }
```
</details>

### `_getTForX(aX: any): any`

**Parameters:**

- **`aX`** `any`

**Returns:** `any`

**Calls:**

- `getSlope`
- `newtonRaphsonIterate`
- `binarySubdivide`

**Internal Comments:**
```
// Interpolate to provide an initial guess for t (x2)
```

<details><summary>Code</summary>

```typescript
function (aX) {
      var mX1 = this._p[0],
        mX2 = this._p[2],
        mSampleValues = this._mSampleValues;

      var intervalStart = 0.0;
      var currentSample = 1;
      var lastSample = kSplineTableSize - 1;

      for (; currentSample !== lastSample && mSampleValues[currentSample] <= aX; ++currentSample) {
        intervalStart += kSampleStepSize;
      }
      --currentSample;

      // Interpolate to provide an initial guess for t
      var dist = (aX - mSampleValues[currentSample]) / (mSampleValues[currentSample + 1] - mSampleValues[currentSample]);
      var guessForT = intervalStart + dist * kSampleStepSize;

      var initialSlope = getSlope(guessForT, mX1, mX2);
      if (initialSlope >= NEWTON_MIN_SLOPE) {
        return newtonRaphsonIterate(aX, guessForT, mX1, mX2);
      } if (initialSlope === 0.0) {
        return guessForT;
      }
      return binarySubdivide(aX, intervalStart, intervalStart + kSampleStepSize, mX1, mX2);
    }
```
</details>

### `get(x: any): any`

**Parameters:**

- **`x`** `any`

**Returns:** `any`

**Calls:**

- `this._precompute`
- `calcBezier`
- `this._getTForX`

**Internal Comments:**
```
// Because JavaScript number are imprecise, we should guarantee the extremes are right.
```

<details><summary>Code</summary>

```typescript
function (x) {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      if (!this._precomputed) this._precompute();
      if (mX1 === mY1 && mX2 === mY2) return x; // linear
      // Because JavaScript number are imprecise, we should guarantee the extremes are right.
      if (x === 0) return 0;
      if (x === 1) return 1;
      return calcBezier(this._getTForX(x), mY1, mY2);
    }
```
</details>

### `_precompute(): void`

**Returns:** `void`

**Calls:**

- `this._calcSampleValues`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      this._precomputed = true;
      if (mX1 !== mY1 || mX2 !== mY2) { this._calcSampleValues(); }
    }
```
</details>

### `_calcSampleValues(): void`

**Returns:** `void`

**Calls:**

- `calcBezier`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mX2 = this._p[2];
      for (var i = 0; i < kSplineTableSize; ++i) {
        this._mSampleValues[i] = calcBezier(i * kSampleStepSize, mX1, mX2);
      }
    }
```
</details>

### `_getTForX(aX: any): any`

**Parameters:**

- **`aX`** `any`

**Returns:** `any`

**Calls:**

- `getSlope`
- `newtonRaphsonIterate`
- `binarySubdivide`

**Internal Comments:**
```
// Interpolate to provide an initial guess for t (x2)
```

<details><summary>Code</summary>

```typescript
function (aX) {
      var mX1 = this._p[0],
        mX2 = this._p[2],
        mSampleValues = this._mSampleValues;

      var intervalStart = 0.0;
      var currentSample = 1;
      var lastSample = kSplineTableSize - 1;

      for (; currentSample !== lastSample && mSampleValues[currentSample] <= aX; ++currentSample) {
        intervalStart += kSampleStepSize;
      }
      --currentSample;

      // Interpolate to provide an initial guess for t
      var dist = (aX - mSampleValues[currentSample]) / (mSampleValues[currentSample + 1] - mSampleValues[currentSample]);
      var guessForT = intervalStart + dist * kSampleStepSize;

      var initialSlope = getSlope(guessForT, mX1, mX2);
      if (initialSlope >= NEWTON_MIN_SLOPE) {
        return newtonRaphsonIterate(aX, guessForT, mX1, mX2);
      } if (initialSlope === 0.0) {
        return guessForT;
      }
      return binarySubdivide(aX, intervalStart, intervalStart + kSampleStepSize, mX1, mX2);
    }
```
</details>

### `get(x: any): any`

**Parameters:**

- **`x`** `any`

**Returns:** `any`

**Calls:**

- `this._precompute`
- `calcBezier`
- `this._getTForX`

**Internal Comments:**
```
// Because JavaScript number are imprecise, we should guarantee the extremes are right.
```

<details><summary>Code</summary>

```typescript
function (x) {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      if (!this._precomputed) this._precompute();
      if (mX1 === mY1 && mX2 === mY2) return x; // linear
      // Because JavaScript number are imprecise, we should guarantee the extremes are right.
      if (x === 0) return 0;
      if (x === 1) return 1;
      return calcBezier(this._getTForX(x), mY1, mY2);
    }
```
</details>

### `_precompute(): void`

**Returns:** `void`

**Calls:**

- `this._calcSampleValues`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      this._precomputed = true;
      if (mX1 !== mY1 || mX2 !== mY2) { this._calcSampleValues(); }
    }
```
</details>

### `_calcSampleValues(): void`

**Returns:** `void`

**Calls:**

- `calcBezier`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mX2 = this._p[2];
      for (var i = 0; i < kSplineTableSize; ++i) {
        this._mSampleValues[i] = calcBezier(i * kSampleStepSize, mX1, mX2);
      }
    }
```
</details>

### `_getTForX(aX: any): any`

**Parameters:**

- **`aX`** `any`

**Returns:** `any`

**Calls:**

- `getSlope`
- `newtonRaphsonIterate`
- `binarySubdivide`

**Internal Comments:**
```
// Interpolate to provide an initial guess for t (x2)
```

<details><summary>Code</summary>

```typescript
function (aX) {
      var mX1 = this._p[0],
        mX2 = this._p[2],
        mSampleValues = this._mSampleValues;

      var intervalStart = 0.0;
      var currentSample = 1;
      var lastSample = kSplineTableSize - 1;

      for (; currentSample !== lastSample && mSampleValues[currentSample] <= aX; ++currentSample) {
        intervalStart += kSampleStepSize;
      }
      --currentSample;

      // Interpolate to provide an initial guess for t
      var dist = (aX - mSampleValues[currentSample]) / (mSampleValues[currentSample + 1] - mSampleValues[currentSample]);
      var guessForT = intervalStart + dist * kSampleStepSize;

      var initialSlope = getSlope(guessForT, mX1, mX2);
      if (initialSlope >= NEWTON_MIN_SLOPE) {
        return newtonRaphsonIterate(aX, guessForT, mX1, mX2);
      } if (initialSlope === 0.0) {
        return guessForT;
      }
      return binarySubdivide(aX, intervalStart, intervalStart + kSampleStepSize, mX1, mX2);
    }
```
</details>

### `get(x: any): any`

**Parameters:**

- **`x`** `any`

**Returns:** `any`

**Calls:**

- `this._precompute`
- `calcBezier`
- `this._getTForX`

**Internal Comments:**
```
// Because JavaScript number are imprecise, we should guarantee the extremes are right.
```

<details><summary>Code</summary>

```typescript
function (x) {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      if (!this._precomputed) this._precompute();
      if (mX1 === mY1 && mX2 === mY2) return x; // linear
      // Because JavaScript number are imprecise, we should guarantee the extremes are right.
      if (x === 0) return 0;
      if (x === 1) return 1;
      return calcBezier(this._getTForX(x), mY1, mY2);
    }
```
</details>

### `_precompute(): void`

**Returns:** `void`

**Calls:**

- `this._calcSampleValues`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mY1 = this._p[1],
        mX2 = this._p[2],
        mY2 = this._p[3];
      this._precomputed = true;
      if (mX1 !== mY1 || mX2 !== mY2) { this._calcSampleValues(); }
    }
```
</details>

### `_calcSampleValues(): void`

**Returns:** `void`

**Calls:**

- `calcBezier`

<details><summary>Code</summary>

```typescript
function () {
      var mX1 = this._p[0],
        mX2 = this._p[2];
      for (var i = 0; i < kSplineTableSize; ++i) {
        this._mSampleValues[i] = calcBezier(i * kSampleStepSize, mX1, mX2);
      }
    }
```
</details>

### `_getTForX(aX: any): any`

**Parameters:**

- **`aX`** `any`

**Returns:** `any`

**Calls:**

- `getSlope`
- `newtonRaphsonIterate`
- `binarySubdivide`

**Internal Comments:**
```
// Interpolate to provide an initial guess for t (x2)
```

<details><summary>Code</summary>

```typescript
function (aX) {
      var mX1 = this._p[0],
        mX2 = this._p[2],
        mSampleValues = this._mSampleValues;

      var intervalStart = 0.0;
      var currentSample = 1;
      var lastSample = kSplineTableSize - 1;

      for (; currentSample !== lastSample && mSampleValues[currentSample] <= aX; ++currentSample) {
        intervalStart += kSampleStepSize;
      }
      --currentSample;

      // Interpolate to provide an initial guess for t
      var dist = (aX - mSampleValues[currentSample]) / (mSampleValues[currentSample + 1] - mSampleValues[currentSample]);
      var guessForT = intervalStart + dist * kSampleStepSize;

      var initialSlope = getSlope(guessForT, mX1, mX2);
      if (initialSlope >= NEWTON_MIN_SLOPE) {
        return newtonRaphsonIterate(aX, guessForT, mX1, mX2);
      } if (initialSlope === 0.0) {
        return guessForT;
      }
      return binarySubdivide(aX, intervalStart, intervalStart + kSampleStepSize, mX1, mX2);
    }
```
</details>

### `double(arr: any): any`

**Parameters:**

- **`arr`** `any`

**Returns:** `any`

**Calls:**

- `arr.concat`
- `createSizedArray`

<details><summary>Code</summary>

```typescript
function double(arr) {
    return arr.concat(createSizedArray(arr.length));
  }
```
</details>

### `newElement(): any`

**Returns:** `any`

**Calls:**

- `_create`

<details><summary>Code</summary>

```typescript
function newElement() {
      var element;
      if (_length) {
        _length -= 1;
        element = pool[_length];
      } else {
        element = _create();
      }
      return element;
    }
```
</details>

### `release(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

**Calls:**

- `pooling.double`
- `_release`

<details><summary>Code</summary>

```typescript
function release(element) {
      if (_length === _maxLength) {
        pool = pooling.double(pool);
        _maxLength *= 2;
      }
      if (_release) {
        _release(element);
      }
      pool[_length] = element;
      _length += 1;
    }
```
</details>

### `create(): { addedLength: number; percents: number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>; lengths: number[] | Float32Array<any> | Int16Array<...> | Uint8ClampedArray<...>; }`

**Returns:** `{ addedLength: number; percents: number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>; lengths: number[] | Float32Array<any> | Int16Array<...> | Uint8ClampedArray<...>; }`

**Calls:**

- `createTypedArray`
- `getDefaultCurveSegments`

<details><summary>Code</summary>

```typescript
function create() {
    return {
      addedLength: 0,
      percents: createTypedArray('float32', getDefaultCurveSegments()),
      lengths: createTypedArray('float32', getDefaultCurveSegments()),
    };
  }
```
</details>

### `create(): { lengths: any[]; totalLength: number; }`

**Returns:** `{ lengths: any[]; totalLength: number; }`

<details><summary>Code</summary>

```typescript
function create() {
    return {
      lengths: [],
      totalLength: 0,
    };
  }
```
</details>

### `release(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

**Calls:**

- `bezierLengthPool.release`

<details><summary>Code</summary>

```typescript
function release(element) {
    var i;
    var len = element.lengths.length;
    for (i = 0; i < len; i += 1) {
      bezierLengthPool.release(element.lengths[i]);
    }
    element.lengths.length = 0;
  }
```
</details>

### `bezFunction(): { getSegmentsLength: (shapeData: any) => any; getNewSegment: (pt1: any, pt2: any, pt3: any, pt4: any, startPerc: any, endPerc: any, bezierData: any) => number[] | Float32Array<any> | Int16Array<...> | Uint8ClampedArray<...>; getPointInSegment: (pt1: any, pt2: any, pt3: any, pt4: any, percent: any, bezierData: any) =...`

**Returns:** `{ getSegmentsLength: (shapeData: any) => any; getNewSegment: (pt1: any, pt2: any, pt3: any, pt4: any, startPerc: any, endPerc: any, bezierData: any) => number[] | Float32Array<any> | Int16Array<...> | Uint8ClampedArray<...>; getPointInSegment: (pt1: any, pt2: any, pt3: any, pt4: any, percent: any, bezierData: any) =...`

**Calls:**

- `pointOnLine2D`
- `math.sqrt`
- `math.pow`
- `complex_call_78891`
- `getDefaultCurveSegments`
- `bezierLengthPool.newElement`
- `bmPow`
- `bmSqrt`
- `segmentsLengthPool.newElement`
- `getBezierLength`
- `complex_call_81002`
- `(pt1[0] + '_' + pt1[1] + '_' + pt2[0] + '_' + pt2[1] + '_' + pt3[0] + '_' + pt3[1] + '_' + pt4[0] + '_' + pt4[1]).replace`
- `createSizedArray`
- `bmFloor`
- `getDistancePerc`
- `math.round`
- `createTypedArray`

**Internal Comments:**
```
// FIX for TypedArrays that don't store floating point values with enough accuracy
// (x6)
```

<details><summary>Code</summary>

```typescript
function bezFunction() {
  var math = Math;

  function pointOnLine2D(x1, y1, x2, y2, x3, y3) {
    var det1 = (x1 * y2) + (y1 * x3) + (x2 * y3) - (x3 * y2) - (y3 * x1) - (x2 * y1);
    return det1 > -0.001 && det1 < 0.001;
  }

  function pointOnLine3D(x1, y1, z1, x2, y2, z2, x3, y3, z3) {
    if (z1 === 0 && z2 === 0 && z3 === 0) {
      return pointOnLine2D(x1, y1, x2, y2, x3, y3);
    }
    var dist1 = math.sqrt(math.pow(x2 - x1, 2) + math.pow(y2 - y1, 2) + math.pow(z2 - z1, 2));
    var dist2 = math.sqrt(math.pow(x3 - x1, 2) + math.pow(y3 - y1, 2) + math.pow(z3 - z1, 2));
    var dist3 = math.sqrt(math.pow(x3 - x2, 2) + math.pow(y3 - y2, 2) + math.pow(z3 - z2, 2));
    var diffDist;
    if (dist1 > dist2) {
      if (dist1 > dist3) {
        diffDist = dist1 - dist2 - dist3;
      } else {
        diffDist = dist3 - dist2 - dist1;
      }
    } else if (dist3 > dist2) {
      diffDist = dist3 - dist2 - dist1;
    } else {
      diffDist = dist2 - dist1 - dist3;
    }
    return diffDist > -0.0001 && diffDist < 0.0001;
  }

  var getBezierLength = (function () {
    return function (pt1, pt2, pt3, pt4) {
      var curveSegments = getDefaultCurveSegments();
      var k;
      var i;
      var len;
      var ptCoord;
      var perc;
      var addedLength = 0;
      var ptDistance;
      var point = [];
      var lastPoint = [];
      var lengthData = bezierLengthPool.newElement();
      len = pt3.length;
      for (k = 0; k < curveSegments; k += 1) {
        perc = k / (curveSegments - 1);
        ptDistance = 0;
        for (i = 0; i < len; i += 1) {
          ptCoord = bmPow(1 - perc, 3) * pt1[i] + 3 * bmPow(1 - perc, 2) * perc * pt3[i] + 3 * (1 - perc) * bmPow(perc, 2) * pt4[i] + bmPow(perc, 3) * pt2[i];
          point[i] = ptCoord;
          if (lastPoint[i] !== null) {
            ptDistance += bmPow(point[i] - lastPoint[i], 2);
          }
          lastPoint[i] = point[i];
        }
        if (ptDistance) {
          ptDistance = bmSqrt(ptDistance);
          addedLength += ptDistance;
        }
        lengthData.percents[k] = perc;
        lengthData.lengths[k] = addedLength;
      }
      lengthData.addedLength = addedLength;
      return lengthData;
    };
  }());

  function getSegmentsLength(shapeData) {
    var segmentsLength = segmentsLengthPool.newElement();
    var closed = shapeData.c;
    var pathV = shapeData.v;
    var pathO = shapeData.o;
    var pathI = shapeData.i;
    var i;
    var len = shapeData._length;
    var lengths = segmentsLength.lengths;
    var totalLength = 0;
    for (i = 0; i < len - 1; i += 1) {
      lengths[i] = getBezierLength(pathV[i], pathV[i + 1], pathO[i], pathI[i + 1]);
      totalLength += lengths[i].addedLength;
    }
    if (closed && len) {
      lengths[i] = getBezierLength(pathV[i], pathV[0], pathO[i], pathI[0]);
      totalLength += lengths[i].addedLength;
    }
    segmentsLength.totalLength = totalLength;
    return segmentsLength;
  }

  function BezierData(length) {
    this.segmentLength = 0;
    this.points = new Array(length);
  }

  function PointData(partial, point) {
    this.partialLength = partial;
    this.point = point;
  }

  var buildBezierData = (function () {
    var storedData = {};

    return function (pt1, pt2, pt3, pt4) {
      var bezierName = (pt1[0] + '_' + pt1[1] + '_' + pt2[0] + '_' + pt2[1] + '_' + pt3[0] + '_' + pt3[1] + '_' + pt4[0] + '_' + pt4[1]).replace(/\./g, 'p');
      if (!storedData[bezierName]) {
        var curveSegments = getDefaultCurveSegments();
        var k;
        var i;
        var len;
        var ptCoord;
        var perc;
        var addedLength = 0;
        var ptDistance;
        var point;
        var lastPoint = null;
        if (pt1.length === 2 && (pt1[0] !== pt2[0] || pt1[1] !== pt2[1]) && pointOnLine2D(pt1[0], pt1[1], pt2[0], pt2[1], pt1[0] + pt3[0], pt1[1] + pt3[1]) && pointOnLine2D(pt1[0], pt1[1], pt2[0], pt2[1], pt2[0] + pt4[0], pt2[1] + pt4[1])) {
          curveSegments = 2;
        }
        var bezierData = new BezierData(curveSegments);
        len = pt3.length;
        for (k = 0; k < curveSegments; k += 1) {
          point = createSizedArray(len);
          perc = k / (curveSegments - 1);
          ptDistance = 0;
          for (i = 0; i < len; i += 1) {
            ptCoord = bmPow(1 - perc, 3) * pt1[i] + 3 * bmPow(1 - perc, 2) * perc * (pt1[i] + pt3[i]) + 3 * (1 - perc) * bmPow(perc, 2) * (pt2[i] + pt4[i]) + bmPow(perc, 3) * pt2[i];
            point[i] = ptCoord;
            if (lastPoint !== null) {
              ptDistance += bmPow(point[i] - lastPoint[i], 2);
            }
          }
          ptDistance = bmSqrt(ptDistance);
          addedLength += ptDistance;
          bezierData.points[k] = new PointData(ptDistance, point);
          lastPoint = point;
        }
        bezierData.segmentLength = addedLength;
        storedData[bezierName] = bezierData;
      }
      return storedData[bezierName];
    };
  }());

  function getDistancePerc(perc, bezierData) {
    var percents = bezierData.percents;
    var lengths = bezierData.lengths;
    var len = percents.length;
    var initPos = bmFloor((len - 1) * perc);
    var lengthPos = perc * bezierData.addedLength;
    var lPerc = 0;
    if (initPos === len - 1 || initPos === 0 || lengthPos === lengths[initPos]) {
      return percents[initPos];
    }
    var dir = lengths[initPos] > lengthPos ? -1 : 1;
    var flag = true;
    while (flag) {
      if (lengths[initPos] <= lengthPos && lengths[initPos + 1] > lengthPos) {
        lPerc = (lengthPos - lengths[initPos]) / (lengths[initPos + 1] - lengths[initPos]);
        flag = false;
      } else {
        initPos += dir;
      }
      if (initPos < 0 || initPos >= len - 1) {
        // FIX for TypedArrays that don't store floating point values with enough accuracy
        if (initPos === len - 1) {
          return percents[initPos];
        }
        flag = false;
      }
    }
    return percents[initPos] + (percents[initPos + 1] - percents[initPos]) * lPerc;
  }

  function getPointInSegment(pt1, pt2, pt3, pt4, percent, bezierData) {
    var t1 = getDistancePerc(percent, bezierData);
    var u1 = 1 - t1;
    var ptX = math.round((u1 * u1 * u1 * pt1[0] + (t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * t1) * pt3[0] + (t1 * t1 * u1 + u1 * t1 * t1 + t1 * u1 * t1) * pt4[0] + t1 * t1 * t1 * pt2[0]) * 1000) / 1000;
    var ptY = math.round((u1 * u1 * u1 * pt1[1] + (t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * t1) * pt3[1] + (t1 * t1 * u1 + u1 * t1 * t1 + t1 * u1 * t1) * pt4[1] + t1 * t1 * t1 * pt2[1]) * 1000) / 1000;
    return [ptX, ptY];
  }

  var bezierSegmentPoints = createTypedArray('float32', 8);

  function getNewSegment(pt1, pt2, pt3, pt4, startPerc, endPerc, bezierData) {
    if (startPerc < 0) {
      startPerc = 0;
    } else if (startPerc > 1) {
      startPerc = 1;
    }
    var t0 = getDistancePerc(startPerc, bezierData);
    endPerc = endPerc > 1 ? 1 : endPerc;
    var t1 = getDistancePerc(endPerc, bezierData);
    var i;
    var len = pt1.length;
    var u0 = 1 - t0;
    var u1 = 1 - t1;
    var u0u0u0 = u0 * u0 * u0;
    var t0u0u0_3 = t0 * u0 * u0 * 3; // eslint-disable-line camelcase
    var t0t0u0_3 = t0 * t0 * u0 * 3; // eslint-disable-line camelcase
    var t0t0t0 = t0 * t0 * t0;
    //
    var u0u0u1 = u0 * u0 * u1;
    var t0u0u1_3 = t0 * u0 * u1 + u0 * t0 * u1 + u0 * u0 * t1; // eslint-disable-line camelcase
    var t0t0u1_3 = t0 * t0 * u1 + u0 * t0 * t1 + t0 * u0 * t1; // eslint-disable-line camelcase
    var t0t0t1 = t0 * t0 * t1;
    //
    var u0u1u1 = u0 * u1 * u1;
    var t0u1u1_3 = t0 * u1 * u1 + u0 * t1 * u1 + u0 * u1 * t1; // eslint-disable-line camelcase
    var t0t1u1_3 = t0 * t1 * u1 + u0 * t1 * t1 + t0 * u1 * t1; // eslint-disable-line camelcase
    var t0t1t1 = t0 * t1 * t1;
    //
    var u1u1u1 = u1 * u1 * u1;
    var t1u1u1_3 = t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * t1; // eslint-disable-line camelcase
    var t1t1u1_3 = t1 * t1 * u1 + u1 * t1 * t1 + t1 * u1 * t1; // eslint-disable-line camelcase
    var t1t1t1 = t1 * t1 * t1;
    for (i = 0; i < len; i += 1) {
      bezierSegmentPoints[i * 4] = math.round((u0u0u0 * pt1[i] + t0u0u0_3 * pt3[i] + t0t0u0_3 * pt4[i] + t0t0t0 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
      bezierSegmentPoints[i * 4 + 1] = math.round((u0u0u1 * pt1[i] + t0u0u1_3 * pt3[i] + t0t0u1_3 * pt4[i] + t0t0t1 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
      bezierSegmentPoints[i * 4 + 2] = math.round((u0u1u1 * pt1[i] + t0u1u1_3 * pt3[i] + t0t1u1_3 * pt4[i] + t0t1t1 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
      bezierSegmentPoints[i * 4 + 3] = math.round((u1u1u1 * pt1[i] + t1u1u1_3 * pt3[i] + t1t1u1_3 * pt4[i] + t1t1t1 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
    }

    return bezierSegmentPoints;
  }

  return {
    getSegmentsLength: getSegmentsLength,
    getNewSegment: getNewSegment,
    getPointInSegment: getPointInSegment,
    buildBezierData: buildBezierData,
    pointOnLine2D: pointOnLine2D,
    pointOnLine3D: pointOnLine3D,
  };
}
```
</details>

### `pointOnLine2D(x1: any, y1: any, x2: any, y2: any, x3: any, y3: any): boolean`

**Parameters:**

- **`x1`** `any`
- **`y1`** `any`
- **`x2`** `any`
- **`y2`** `any`
- **`x3`** `any`
- **`y3`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function pointOnLine2D(x1, y1, x2, y2, x3, y3) {
    var det1 = (x1 * y2) + (y1 * x3) + (x2 * y3) - (x3 * y2) - (y3 * x1) - (x2 * y1);
    return det1 > -0.001 && det1 < 0.001;
  }
```
</details>

### `pointOnLine3D(x1: any, y1: any, z1: any, x2: any, y2: any, z2: any, x3: any, y3: any, z3: any): boolean`

**Parameters:**

- **`x1`** `any`
- **`y1`** `any`
- **`z1`** `any`
- **`x2`** `any`
- **`y2`** `any`
- **`z2`** `any`
- **`x3`** `any`
- **`y3`** `any`
- **`z3`** `any`

**Returns:** `boolean`

**Calls:**

- `pointOnLine2D`
- `math.sqrt`
- `math.pow`

<details><summary>Code</summary>

```typescript
function pointOnLine3D(x1, y1, z1, x2, y2, z2, x3, y3, z3) {
    if (z1 === 0 && z2 === 0 && z3 === 0) {
      return pointOnLine2D(x1, y1, x2, y2, x3, y3);
    }
    var dist1 = math.sqrt(math.pow(x2 - x1, 2) + math.pow(y2 - y1, 2) + math.pow(z2 - z1, 2));
    var dist2 = math.sqrt(math.pow(x3 - x1, 2) + math.pow(y3 - y1, 2) + math.pow(z3 - z1, 2));
    var dist3 = math.sqrt(math.pow(x3 - x2, 2) + math.pow(y3 - y2, 2) + math.pow(z3 - z2, 2));
    var diffDist;
    if (dist1 > dist2) {
      if (dist1 > dist3) {
        diffDist = dist1 - dist2 - dist3;
      } else {
        diffDist = dist3 - dist2 - dist1;
      }
    } else if (dist3 > dist2) {
      diffDist = dist3 - dist2 - dist1;
    } else {
      diffDist = dist2 - dist1 - dist3;
    }
    return diffDist > -0.0001 && diffDist < 0.0001;
  }
```
</details>

### `getSegmentsLength(shapeData: any): any`

**Parameters:**

- **`shapeData`** `any`

**Returns:** `any`

**Calls:**

- `segmentsLengthPool.newElement`
- `getBezierLength`

<details><summary>Code</summary>

```typescript
function getSegmentsLength(shapeData) {
    var segmentsLength = segmentsLengthPool.newElement();
    var closed = shapeData.c;
    var pathV = shapeData.v;
    var pathO = shapeData.o;
    var pathI = shapeData.i;
    var i;
    var len = shapeData._length;
    var lengths = segmentsLength.lengths;
    var totalLength = 0;
    for (i = 0; i < len - 1; i += 1) {
      lengths[i] = getBezierLength(pathV[i], pathV[i + 1], pathO[i], pathI[i + 1]);
      totalLength += lengths[i].addedLength;
    }
    if (closed && len) {
      lengths[i] = getBezierLength(pathV[i], pathV[0], pathO[i], pathI[0]);
      totalLength += lengths[i].addedLength;
    }
    segmentsLength.totalLength = totalLength;
    return segmentsLength;
  }
```
</details>

### `BezierData(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BezierData(length) {
    this.segmentLength = 0;
    this.points = new Array(length);
  }
```
</details>

### `PointData(partial: any, point: any): void`

**Parameters:**

- **`partial`** `any`
- **`point`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function PointData(partial, point) {
    this.partialLength = partial;
    this.point = point;
  }
```
</details>

### `getDistancePerc(perc: any, bezierData: any): any`

**Parameters:**

- **`perc`** `any`
- **`bezierData`** `any`

**Returns:** `any`

**Calls:**

- `bmFloor`

**Internal Comments:**
```
// FIX for TypedArrays that don't store floating point values with enough accuracy
```

<details><summary>Code</summary>

```typescript
function getDistancePerc(perc, bezierData) {
    var percents = bezierData.percents;
    var lengths = bezierData.lengths;
    var len = percents.length;
    var initPos = bmFloor((len - 1) * perc);
    var lengthPos = perc * bezierData.addedLength;
    var lPerc = 0;
    if (initPos === len - 1 || initPos === 0 || lengthPos === lengths[initPos]) {
      return percents[initPos];
    }
    var dir = lengths[initPos] > lengthPos ? -1 : 1;
    var flag = true;
    while (flag) {
      if (lengths[initPos] <= lengthPos && lengths[initPos + 1] > lengthPos) {
        lPerc = (lengthPos - lengths[initPos]) / (lengths[initPos + 1] - lengths[initPos]);
        flag = false;
      } else {
        initPos += dir;
      }
      if (initPos < 0 || initPos >= len - 1) {
        // FIX for TypedArrays that don't store floating point values with enough accuracy
        if (initPos === len - 1) {
          return percents[initPos];
        }
        flag = false;
      }
    }
    return percents[initPos] + (percents[initPos + 1] - percents[initPos]) * lPerc;
  }
```
</details>

### `getPointInSegment(pt1: any, pt2: any, pt3: any, pt4: any, percent: any, bezierData: any): number[]`

**Parameters:**

- **`pt1`** `any`
- **`pt2`** `any`
- **`pt3`** `any`
- **`pt4`** `any`
- **`percent`** `any`
- **`bezierData`** `any`

**Returns:** `number[]`

**Calls:**

- `getDistancePerc`
- `math.round`

<details><summary>Code</summary>

```typescript
function getPointInSegment(pt1, pt2, pt3, pt4, percent, bezierData) {
    var t1 = getDistancePerc(percent, bezierData);
    var u1 = 1 - t1;
    var ptX = math.round((u1 * u1 * u1 * pt1[0] + (t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * t1) * pt3[0] + (t1 * t1 * u1 + u1 * t1 * t1 + t1 * u1 * t1) * pt4[0] + t1 * t1 * t1 * pt2[0]) * 1000) / 1000;
    var ptY = math.round((u1 * u1 * u1 * pt1[1] + (t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * t1) * pt3[1] + (t1 * t1 * u1 + u1 * t1 * t1 + t1 * u1 * t1) * pt4[1] + t1 * t1 * t1 * pt2[1]) * 1000) / 1000;
    return [ptX, ptY];
  }
```
</details>

### `getNewSegment(pt1: any, pt2: any, pt3: any, pt4: any, startPerc: any, endPerc: any, bezierData: any): number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Parameters:**

- **`pt1`** `any`
- **`pt2`** `any`
- **`pt3`** `any`
- **`pt4`** `any`
- **`startPerc`** `any`
- **`endPerc`** `any`
- **`bezierData`** `any`

**Returns:** `number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `getDistancePerc`
- `math.round`

**Internal Comments:**
```
// (x6)
```

<details><summary>Code</summary>

```typescript
function getNewSegment(pt1, pt2, pt3, pt4, startPerc, endPerc, bezierData) {
    if (startPerc < 0) {
      startPerc = 0;
    } else if (startPerc > 1) {
      startPerc = 1;
    }
    var t0 = getDistancePerc(startPerc, bezierData);
    endPerc = endPerc > 1 ? 1 : endPerc;
    var t1 = getDistancePerc(endPerc, bezierData);
    var i;
    var len = pt1.length;
    var u0 = 1 - t0;
    var u1 = 1 - t1;
    var u0u0u0 = u0 * u0 * u0;
    var t0u0u0_3 = t0 * u0 * u0 * 3; // eslint-disable-line camelcase
    var t0t0u0_3 = t0 * t0 * u0 * 3; // eslint-disable-line camelcase
    var t0t0t0 = t0 * t0 * t0;
    //
    var u0u0u1 = u0 * u0 * u1;
    var t0u0u1_3 = t0 * u0 * u1 + u0 * t0 * u1 + u0 * u0 * t1; // eslint-disable-line camelcase
    var t0t0u1_3 = t0 * t0 * u1 + u0 * t0 * t1 + t0 * u0 * t1; // eslint-disable-line camelcase
    var t0t0t1 = t0 * t0 * t1;
    //
    var u0u1u1 = u0 * u1 * u1;
    var t0u1u1_3 = t0 * u1 * u1 + u0 * t1 * u1 + u0 * u1 * t1; // eslint-disable-line camelcase
    var t0t1u1_3 = t0 * t1 * u1 + u0 * t1 * t1 + t0 * u1 * t1; // eslint-disable-line camelcase
    var t0t1t1 = t0 * t1 * t1;
    //
    var u1u1u1 = u1 * u1 * u1;
    var t1u1u1_3 = t1 * u1 * u1 + u1 * t1 * u1 + u1 * u1 * t1; // eslint-disable-line camelcase
    var t1t1u1_3 = t1 * t1 * u1 + u1 * t1 * t1 + t1 * u1 * t1; // eslint-disable-line camelcase
    var t1t1t1 = t1 * t1 * t1;
    for (i = 0; i < len; i += 1) {
      bezierSegmentPoints[i * 4] = math.round((u0u0u0 * pt1[i] + t0u0u0_3 * pt3[i] + t0t0u0_3 * pt4[i] + t0t0t0 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
      bezierSegmentPoints[i * 4 + 1] = math.round((u0u0u1 * pt1[i] + t0u0u1_3 * pt3[i] + t0t0u1_3 * pt4[i] + t0t0t1 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
      bezierSegmentPoints[i * 4 + 2] = math.round((u0u1u1 * pt1[i] + t0u1u1_3 * pt3[i] + t0t1u1_3 * pt4[i] + t0t1t1 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
      bezierSegmentPoints[i * 4 + 3] = math.round((u1u1u1 * pt1[i] + t1u1u1_3 * pt3[i] + t1t1u1_3 * pt4[i] + t1t1t1 * pt2[i]) * 1000) / 1000; // eslint-disable-line camelcase
    }

    return bezierSegmentPoints;
  }
```
</details>

### `interpolateValue(frameNum: any, caching: any): any`

**Parameters:**

- **`frameNum`** `any`
- **`caching`** `any`

**Returns:** `any`

**Calls:**

- `createTypedArray`
- `bez.buildBezierData`
- `BezierFactory.getBezierEasing`
- `fnc`
- `createQuaternion`
- `quaternionToEuler`
- `slerp`

<details><summary>Code</summary>

```typescript
function interpolateValue(frameNum, caching) {
    var offsetTime = this.offsetTime;
    var newValue;
    if (this.propType === 'multidimensional') {
      newValue = createTypedArray('float32', this.pv.length);
    }
    var iterationIndex = caching.lastIndex;
    var i = iterationIndex;
    var len = this.keyframes.length - 1;
    var flag = true;
    var keyData;
    var nextKeyData;
    var keyframeMetadata;

    while (flag) {
      keyData = this.keyframes[i];
      nextKeyData = this.keyframes[i + 1];
      if (i === len - 1 && frameNum >= nextKeyData.t - offsetTime) {
        if (keyData.h) {
          keyData = nextKeyData;
        }
        iterationIndex = 0;
        break;
      }
      if ((nextKeyData.t - offsetTime) > frameNum) {
        iterationIndex = i;
        break;
      }
      if (i < len - 1) {
        i += 1;
      } else {
        iterationIndex = 0;
        flag = false;
      }
    }
    keyframeMetadata = this.keyframesMetadata[i] || {};

    var k;
    var kLen;
    var perc;
    var jLen;
    var j;
    var fnc;
    var nextKeyTime = nextKeyData.t - offsetTime;
    var keyTime = keyData.t - offsetTime;
    var endValue;
    if (keyData.to) {
      if (!keyframeMetadata.bezierData) {
        keyframeMetadata.bezierData = bez.buildBezierData(keyData.s, nextKeyData.s || keyData.e, keyData.to, keyData.ti);
      }
      var bezierData = keyframeMetadata.bezierData;
      if (frameNum >= nextKeyTime || frameNum < keyTime) {
        var ind = frameNum >= nextKeyTime ? bezierData.points.length - 1 : 0;
        kLen = bezierData.points[ind].point.length;
        for (k = 0; k < kLen; k += 1) {
          newValue[k] = bezierData.points[ind].point[k];
        }
        // caching._lastKeyframeIndex = -1;
      } else {
        if (keyframeMetadata.__fnct) {
          fnc = keyframeMetadata.__fnct;
        } else {
          fnc = BezierFactory.getBezierEasing(keyData.o.x, keyData.o.y, keyData.i.x, keyData.i.y, keyData.n).get;
          keyframeMetadata.__fnct = fnc;
        }
        perc = fnc((frameNum - keyTime) / (nextKeyTime - keyTime));
        var distanceInLine = bezierData.segmentLength * perc;

        var segmentPerc;
        var addedLength = (caching.lastFrame < frameNum && caching._lastKeyframeIndex === i) ? caching._lastAddedLength : 0;
        j = (caching.lastFrame < frameNum && caching._lastKeyframeIndex === i) ? caching._lastPoint : 0;
        flag = true;
        jLen = bezierData.points.length;
        while (flag) {
          addedLength += bezierData.points[j].partialLength;
          if (distanceInLine === 0 || perc === 0 || j === bezierData.points.length - 1) {
            kLen = bezierData.points[j].point.length;
            for (k = 0; k < kLen; k += 1) {
              newValue[k] = bezierData.points[j].point[k];
            }
            break;
          } else if (distanceInLine >= addedLength && distanceInLine < addedLength + bezierData.points[j + 1].partialLength) {
            segmentPerc = (distanceInLine - addedLength) / bezierData.points[j + 1].partialLength;
            kLen = bezierData.points[j].point.length;
            for (k = 0; k < kLen; k += 1) {
              newValue[k] = bezierData.points[j].point[k] + (bezierData.points[j + 1].point[k] - bezierData.points[j].point[k]) * segmentPerc;
            }
            break;
          }
          if (j < jLen - 1) {
            j += 1;
          } else {
            flag = false;
          }
        }
        caching._lastPoint = j;
        caching._lastAddedLength = addedLength - bezierData.points[j].partialLength;
        caching._lastKeyframeIndex = i;
      }
    } else {
      var outX;
      var outY;
      var inX;
      var inY;
      var keyValue;
      len = keyData.s.length;
      endValue = nextKeyData.s || keyData.e;
      if (this.sh && keyData.h !== 1) {
        if (frameNum >= nextKeyTime) {
          newValue[0] = endValue[0];
          newValue[1] = endValue[1];
          newValue[2] = endValue[2];
        } else if (frameNum <= keyTime) {
          newValue[0] = keyData.s[0];
          newValue[1] = keyData.s[1];
          newValue[2] = keyData.s[2];
        } else {
          var quatStart = createQuaternion(keyData.s);
          var quatEnd = createQuaternion(endValue);
          var time = (frameNum - keyTime) / (nextKeyTime - keyTime);
          quaternionToEuler(newValue, slerp(quatStart, quatEnd, time));
        }
      } else {
        for (i = 0; i < len; i += 1) {
          if (keyData.h !== 1) {
            if (frameNum >= nextKeyTime) {
              perc = 1;
            } else if (frameNum < keyTime) {
              perc = 0;
            } else {
              if (keyData.o.x.constructor === Array) {
                if (!keyframeMetadata.__fnct) {
                  keyframeMetadata.__fnct = [];
                }
                if (!keyframeMetadata.__fnct[i]) {
                  outX = keyData.o.x[i] === undefined ? keyData.o.x[0] : keyData.o.x[i];
                  outY = keyData.o.y[i] === undefined ? keyData.o.y[0] : keyData.o.y[i];
                  inX = keyData.i.x[i] === undefined ? keyData.i.x[0] : keyData.i.x[i];
                  inY = keyData.i.y[i] === undefined ? keyData.i.y[0] : keyData.i.y[i];
                  fnc = BezierFactory.getBezierEasing(outX, outY, inX, inY).get;
                  keyframeMetadata.__fnct[i] = fnc;
                } else {
                  fnc = keyframeMetadata.__fnct[i];
                }
              } else if (!keyframeMetadata.__fnct) {
                outX = keyData.o.x;
                outY = keyData.o.y;
                inX = keyData.i.x;
                inY = keyData.i.y;
                fnc = BezierFactory.getBezierEasing(outX, outY, inX, inY).get;
                keyData.keyframeMetadata = fnc;
              } else {
                fnc = keyframeMetadata.__fnct;
              }
              perc = fnc((frameNum - keyTime) / (nextKeyTime - keyTime));
            }
          }

          endValue = nextKeyData.s || keyData.e;
          keyValue = keyData.h === 1 ? keyData.s[i] : keyData.s[i] + (endValue[i] - keyData.s[i]) * perc;

          if (this.propType === 'multidimensional') {
            newValue[i] = keyValue;
          } else {
            newValue = keyValue;
          }
        }
      }
    }
    caching.lastIndex = iterationIndex;
    return newValue;
  }
```
</details>

### `slerp(a: any, b: any, t: any): number[]`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`t`** `any`

**Returns:** `number[]`

**Calls:**

- `Math.acos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function slerp(a, b, t) {
    var out = [];
    var ax = a[0];
    var ay = a[1];
    var az = a[2];
    var aw = a[3];
    var bx = b[0];
    var by = b[1];
    var bz = b[2];
    var bw = b[3];

    var omega;
    var cosom;
    var sinom;
    var scale0;
    var scale1;

    cosom = ax * bx + ay * by + az * bz + aw * bw;
    if (cosom < 0.0) {
      cosom = -cosom;
      bx = -bx;
      by = -by;
      bz = -bz;
      bw = -bw;
    }
    if ((1.0 - cosom) > 0.000001) {
      omega = Math.acos(cosom);
      sinom = Math.sin(omega);
      scale0 = Math.sin((1.0 - t) * omega) / sinom;
      scale1 = Math.sin(t * omega) / sinom;
    } else {
      scale0 = 1.0 - t;
      scale1 = t;
    }
    out[0] = scale0 * ax + scale1 * bx;
    out[1] = scale0 * ay + scale1 * by;
    out[2] = scale0 * az + scale1 * bz;
    out[3] = scale0 * aw + scale1 * bw;

    return out;
  }
```
</details>

### `quaternionToEuler(out: any, quat: any): void`

**Parameters:**

- **`out`** `any`
- **`quat`** `any`

**Returns:** `void`

**Calls:**

- `Math.atan2`
- `Math.asin`

<details><summary>Code</summary>

```typescript
function quaternionToEuler(out, quat) {
    var qx = quat[0];
    var qy = quat[1];
    var qz = quat[2];
    var qw = quat[3];
    var heading = Math.atan2(2 * qy * qw - 2 * qx * qz, 1 - 2 * qy * qy - 2 * qz * qz);
    var attitude = Math.asin(2 * qx * qy + 2 * qz * qw);
    var bank = Math.atan2(2 * qx * qw - 2 * qy * qz, 1 - 2 * qx * qx - 2 * qz * qz);
    out[0] = heading / degToRads;
    out[1] = attitude / degToRads;
    out[2] = bank / degToRads;
  }
```
</details>

### `createQuaternion(values: any): number[]`

**Parameters:**

- **`values`** `any`

**Returns:** `number[]`

**Calls:**

- `Math.cos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function createQuaternion(values) {
    var heading = values[0] * degToRads;
    var attitude = values[1] * degToRads;
    var bank = values[2] * degToRads;
    var c1 = Math.cos(heading / 2);
    var c2 = Math.cos(attitude / 2);
    var c3 = Math.cos(bank / 2);
    var s1 = Math.sin(heading / 2);
    var s2 = Math.sin(attitude / 2);
    var s3 = Math.sin(bank / 2);
    var w = c1 * c2 * c3 - s1 * s2 * s3;
    var x = s1 * s2 * c3 + c1 * c2 * s3;
    var y = s1 * c2 * c3 + c1 * s2 * s3;
    var z = c1 * s2 * c3 - s1 * c2 * s3;

    return [x, y, z, w];
  }
```
</details>

### `getValueAtCurrentTime(): any`

**Returns:** `any`

**Calls:**

- `this.interpolateValue`

<details><summary>Code</summary>

```typescript
function getValueAtCurrentTime() {
    var frameNum = this.comp.renderedFrame - this.offsetTime;
    var initTime = this.keyframes[0].t - this.offsetTime;
    var endTime = this.keyframes[this.keyframes.length - 1].t - this.offsetTime;
    if (!(frameNum === this._caching.lastFrame || (this._caching.lastFrame !== initFrame && ((this._caching.lastFrame >= endTime && frameNum >= endTime) || (this._caching.lastFrame < initTime && frameNum < initTime))))) {
      if (this._caching.lastFrame >= frameNum) {
        this._caching._lastKeyframeIndex = -1;
        this._caching.lastIndex = 0;
      }

      var renderResult = this.interpolateValue(frameNum, this._caching);
      this.pv = renderResult;
    }
    this._caching.lastFrame = frameNum;
    return this.pv;
  }
```
</details>

### `setVValue(val: any): void`

**Parameters:**

- **`val`** `any`

**Returns:** `void`

**Calls:**

- `mathAbs`

<details><summary>Code</summary>

```typescript
function setVValue(val) {
    var multipliedValue;
    if (this.propType === 'unidimensional') {
      multipliedValue = val * this.mult;
      if (mathAbs(this.v - multipliedValue) > 0.00001) {
        this.v = multipliedValue;
        this._mdf = true;
      }
    } else {
      var i = 0;
      var len = this.v.length;
      while (i < len) {
        multipliedValue = val[i] * this.mult;
        if (mathAbs(this.v[i] - multipliedValue) > 0.00001) {
          this.v[i] = multipliedValue;
          this._mdf = true;
        }
        i += 1;
      }
    }
  }
```
</details>

### `processEffectsSequence(): void`

**Returns:** `void`

**Calls:**

- `this.setVValue`
- `complex_call_97156`

<details><summary>Code</summary>

```typescript
function processEffectsSequence() {
    if (this.elem.globalData.frameId === this.frameId || !this.effectsSequence.length) {
      return;
    }
    if (this.lock) {
      this.setVValue(this.pv);
      return;
    }
    this.lock = true;
    this._mdf = this._isFirstFrame;
    var i;
    var len = this.effectsSequence.length;
    var finalValue = this.kf ? this.pv : this.data.k;
    for (i = 0; i < len; i += 1) {
      finalValue = this.effectsSequence[i](finalValue);
    }
    this.setVValue(finalValue);
    this._isFirstFrame = false;
    this.lock = false;
    this.frameId = this.elem.globalData.frameId;
  }
```
</details>

### `addEffect(effectFunction: any): void`

**Parameters:**

- **`effectFunction`** `any`

**Returns:** `void`

**Calls:**

- `this.effectsSequence.push`
- `this.container.addDynamicProperty`

<details><summary>Code</summary>

```typescript
function addEffect(effectFunction) {
    this.effectsSequence.push(effectFunction);
    this.container.addDynamicProperty(this);
  }
```
</details>

### `ValueProperty(elem: any, data: any, mult: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`mult`** `any`
- **`container`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ValueProperty(elem, data, mult, container) {
    this.propType = 'unidimensional';
    this.mult = mult || 1;
    this.data = data;
    this.v = mult ? data.k * mult : data.k;
    this.pv = data.k;
    this._mdf = false;
    this.elem = elem;
    this.container = container;
    this.comp = elem.comp;
    this.k = false;
    this.kf = false;
    this.vel = 0;
    this.effectsSequence = [];
    this._isFirstFrame = true;
    this.getValue = processEffectsSequence;
    this.setVValue = setVValue;
    this.addEffect = addEffect;
  }
```
</details>

### `MultiDimensionalProperty(elem: any, data: any, mult: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`mult`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `createTypedArray`

<details><summary>Code</summary>

```typescript
function MultiDimensionalProperty(elem, data, mult, container) {
    this.propType = 'multidimensional';
    this.mult = mult || 1;
    this.data = data;
    this._mdf = false;
    this.elem = elem;
    this.container = container;
    this.comp = elem.comp;
    this.k = false;
    this.kf = false;
    this.frameId = -1;
    var i;
    var len = data.k.length;
    this.v = createTypedArray('float32', len);
    this.pv = createTypedArray('float32', len);
    this.vel = createTypedArray('float32', len);
    for (i = 0; i < len; i += 1) {
      this.v[i] = data.k[i] * this.mult;
      this.pv[i] = data.k[i];
    }
    this._isFirstFrame = true;
    this.effectsSequence = [];
    this.getValue = processEffectsSequence;
    this.setVValue = setVValue;
    this.addEffect = addEffect;
  }
```
</details>

### `KeyframedValueProperty(elem: any, data: any, mult: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`mult`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `getValueAtCurrentTime.bind`

<details><summary>Code</summary>

```typescript
function KeyframedValueProperty(elem, data, mult, container) {
    this.propType = 'unidimensional';
    this.keyframes = data.k;
    this.keyframesMetadata = [];
    this.offsetTime = elem.data.st;
    this.frameId = -1;
    this._caching = {
      lastFrame: initFrame, lastIndex: 0, value: 0, _lastKeyframeIndex: -1,
    };
    this.k = true;
    this.kf = true;
    this.data = data;
    this.mult = mult || 1;
    this.elem = elem;
    this.container = container;
    this.comp = elem.comp;
    this.v = initFrame;
    this.pv = initFrame;
    this._isFirstFrame = true;
    this.getValue = processEffectsSequence;
    this.setVValue = setVValue;
    this.interpolateValue = interpolateValue;
    this.effectsSequence = [getValueAtCurrentTime.bind(this)];
    this.addEffect = addEffect;
  }
```
</details>

### `KeyframedMultidimensionalProperty(elem: any, data: any, mult: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`mult`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `bez.pointOnLine2D`
- `bez.pointOnLine3D`
- `getValueAtCurrentTime.bind`
- `createTypedArray`

<details><summary>Code</summary>

```typescript
function KeyframedMultidimensionalProperty(elem, data, mult, container) {
    this.propType = 'multidimensional';
    var i;
    var len = data.k.length;
    var s;
    var e;
    var to;
    var ti;
    for (i = 0; i < len - 1; i += 1) {
      if (data.k[i].to && data.k[i].s && data.k[i + 1] && data.k[i + 1].s) {
        s = data.k[i].s;
        e = data.k[i + 1].s;
        to = data.k[i].to;
        ti = data.k[i].ti;
        if ((s.length === 2 && !(s[0] === e[0] && s[1] === e[1]) && bez.pointOnLine2D(s[0], s[1], e[0], e[1], s[0] + to[0], s[1] + to[1]) && bez.pointOnLine2D(s[0], s[1], e[0], e[1], e[0] + ti[0], e[1] + ti[1])) || (s.length === 3 && !(s[0] === e[0] && s[1] === e[1] && s[2] === e[2]) && bez.pointOnLine3D(s[0], s[1], s[2], e[0], e[1], e[2], s[0] + to[0], s[1] + to[1], s[2] + to[2]) && bez.pointOnLine3D(s[0], s[1], s[2], e[0], e[1], e[2], e[0] + ti[0], e[1] + ti[1], e[2] + ti[2]))) {
          data.k[i].to = null;
          data.k[i].ti = null;
        }
        if (s[0] === e[0] && s[1] === e[1] && to[0] === 0 && to[1] === 0 && ti[0] === 0 && ti[1] === 0) {
          if (s.length === 2 || (s[2] === e[2] && to[2] === 0 && ti[2] === 0)) {
            data.k[i].to = null;
            data.k[i].ti = null;
          }
        }
      }
    }
    this.effectsSequence = [getValueAtCurrentTime.bind(this)];
    this.data = data;
    this.keyframes = data.k;
    this.keyframesMetadata = [];
    this.offsetTime = elem.data.st;
    this.k = true;
    this.kf = true;
    this._isFirstFrame = true;
    this.mult = mult || 1;
    this.elem = elem;
    this.container = container;
    this.comp = elem.comp;
    this.getValue = processEffectsSequence;
    this.setVValue = setVValue;
    this.interpolateValue = interpolateValue;
    this.frameId = -1;
    var arrLen = data.k[0].s.length;
    this.v = createTypedArray('float32', arrLen);
    this.pv = createTypedArray('float32', arrLen);
    for (i = 0; i < arrLen; i += 1) {
      this.v[i] = initFrame;
      this.pv[i] = initFrame;
    }
    this._caching = { lastFrame: initFrame, lastIndex: 0, value: createTypedArray('float32', arrLen) };
    this.addEffect = addEffect;
  }
```
</details>

### `getProp(elem: any, data: any, type: any, mult: any, container: any): ValueProperty | MultiDimensionalProperty | KeyframedValueProperty | KeyframedMultidimensionalProperty`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`type`** `any`
- **`mult`** `any`
- **`container`** `any`

**Returns:** `ValueProperty | MultiDimensionalProperty | KeyframedValueProperty | KeyframedMultidimensionalProperty`

**Calls:**

- `container.addDynamicProperty`

<details><summary>Code</summary>

```typescript
function getProp(elem, data, type, mult, container) {
    var p;
    if (!data.k.length) {
      p = new ValueProperty(elem, data, mult, container);
    } else if (typeof (data.k[0]) === 'number') {
      p = new MultiDimensionalProperty(elem, data, mult, container);
    } else {
      switch (type) {
        case 0:
          p = new KeyframedValueProperty(elem, data, mult, container);
          break;
        case 1:
          p = new KeyframedMultidimensionalProperty(elem, data, mult, container);
          break;
        default:
          break;
      }
    }
    if (p.effectsSequence.length) {
      container.addDynamicProperty(p);
    }
    return p;
  }
```
</details>

### `DynamicPropertyContainer(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function DynamicPropertyContainer() {}
```
</details>

### `addDynamicProperty(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties.indexOf`
- `this.dynamicProperties.push`
- `this.container.addDynamicProperty`

<details><summary>Code</summary>

```typescript
function (prop) {
    if (this.dynamicProperties.indexOf(prop) === -1) {
      this.dynamicProperties.push(prop);
      this.container.addDynamicProperty(this);
      this._isAnimated = true;
    }
  }
```
</details>

### `iterateDynamicProperties(): void`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties[i].getValue`

<details><summary>Code</summary>

```typescript
function () {
    this._mdf = false;
    var i;
    var len = this.dynamicProperties.length;
    for (i = 0; i < len; i += 1) {
      this.dynamicProperties[i].getValue();
      if (this.dynamicProperties[i]._mdf) {
        this._mdf = true;
      }
    }
  }
```
</details>

### `initDynamicPropertyContainer(container: any): void`

**Parameters:**

- **`container`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (container) {
    this.container = container;
    this.dynamicProperties = [];
    this._mdf = false;
    this._isAnimated = false;
  }
```
</details>

### `addDynamicProperty(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties.indexOf`
- `this.dynamicProperties.push`
- `this.container.addDynamicProperty`

<details><summary>Code</summary>

```typescript
function (prop) {
    if (this.dynamicProperties.indexOf(prop) === -1) {
      this.dynamicProperties.push(prop);
      this.container.addDynamicProperty(this);
      this._isAnimated = true;
    }
  }
```
</details>

### `iterateDynamicProperties(): void`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties[i].getValue`

<details><summary>Code</summary>

```typescript
function () {
    this._mdf = false;
    var i;
    var len = this.dynamicProperties.length;
    for (i = 0; i < len; i += 1) {
      this.dynamicProperties[i].getValue();
      if (this.dynamicProperties[i]._mdf) {
        this._mdf = true;
      }
    }
  }
```
</details>

### `initDynamicPropertyContainer(container: any): void`

**Parameters:**

- **`container`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (container) {
    this.container = container;
    this.dynamicProperties = [];
    this._mdf = false;
    this._isAnimated = false;
  }
```
</details>

### `create(): number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Returns:** `number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `createTypedArray`

<details><summary>Code</summary>

```typescript
function create() {
    return createTypedArray('float32', 2);
  }
```
</details>

### `ShapePath(): void`

**Returns:** `void`

**Calls:**

- `createSizedArray`

<details><summary>Code</summary>

```typescript
function ShapePath() {
  this.c = false;
  this._length = 0;
  this._maxLength = 8;
  this.v = createSizedArray(this._maxLength);
  this.o = createSizedArray(this._maxLength);
  this.i = createSizedArray(this._maxLength);
}
```
</details>

### `create(): ShapePath`

**Returns:** `ShapePath`

<details><summary>Code</summary>

```typescript
function create() {
    return new ShapePath();
  }
```
</details>

### `release(shapePath: any): void`

**Parameters:**

- **`shapePath`** `any`

**Returns:** `void`

**Calls:**

- `pointPool.release`

<details><summary>Code</summary>

```typescript
function release(shapePath) {
    var len = shapePath._length;
    var i;
    for (i = 0; i < len; i += 1) {
      pointPool.release(shapePath.v[i]);
      pointPool.release(shapePath.i[i]);
      pointPool.release(shapePath.o[i]);
      shapePath.v[i] = null;
      shapePath.i[i] = null;
      shapePath.o[i] = null;
    }
    shapePath._length = 0;
    shapePath.c = false;
  }
```
</details>

### `clone(shape: any): any`

**Parameters:**

- **`shape`** `any`

**Returns:** `any`

**Calls:**

- `factory.newElement`
- `cloned.setLength`
- `cloned.setTripleAt`

<details><summary>Code</summary>

```typescript
function clone(shape) {
    var cloned = factory.newElement();
    var i;
    var len = shape._length === undefined ? shape.v.length : shape._length;
    cloned.setLength(len);
    cloned.c = shape.c;

    for (i = 0; i < len; i += 1) {
      cloned.setTripleAt(shape.v[i][0], shape.v[i][1], shape.o[i][0], shape.o[i][1], shape.i[i][0], shape.i[i][1], i);
    }
    return cloned;
  }
```
</details>

### `ShapeCollection(): void`

**Returns:** `void`

**Calls:**

- `createSizedArray`

<details><summary>Code</summary>

```typescript
function ShapeCollection() {
  this._length = 0;
  this._maxLength = 4;
  this.shapes = createSizedArray(this._maxLength);
}
```
</details>

### `newShapeCollection(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function newShapeCollection() {
    var shapeCollection;
    if (_length) {
      _length -= 1;
      shapeCollection = pool[_length];
    } else {
      shapeCollection = new ShapeCollection();
    }
    return shapeCollection;
  }
```
</details>

### `release(shapeCollection: any): void`

**Parameters:**

- **`shapeCollection`** `any`

**Returns:** `void`

**Calls:**

- `shapePool.release`
- `pooling.double`

<details><summary>Code</summary>

```typescript
function release(shapeCollection) {
    var i;
    var len = shapeCollection._length;
    for (i = 0; i < len; i += 1) {
      shapePool.release(shapeCollection.shapes[i]);
    }
    shapeCollection._length = 0;

    if (_length === _maxLength) {
      pool = pooling.double(pool);
      _maxLength *= 2;
    }
    pool[_length] = shapeCollection;
    _length += 1;
  }
```
</details>

### `interpolateShape(frameNum: any, previousValue: any, caching: any): void`

**Parameters:**

- **`frameNum`** `any`
- **`previousValue`** `any`
- **`caching`** `any`

**Returns:** `void`

**Calls:**

- `BezierFactory.getBezierEasing`
- `fnc`

**Internal Comments:**
```
/* if(kf[kf.length - 1].s){
                keyPropS = kf[kf.length - 1].s[0];
            }else{
                keyPropS = kf[kf.length - 2].e[0];
            } */ (x3)
```

<details><summary>Code</summary>

```typescript
function interpolateShape(frameNum, previousValue, caching) {
    var iterationIndex = caching.lastIndex;
    var keyPropS;
    var keyPropE;
    var isHold;
    var j;
    var k;
    var jLen;
    var kLen;
    var perc;
    var vertexValue;
    var kf = this.keyframes;
    if (frameNum < kf[0].t - this.offsetTime) {
      keyPropS = kf[0].s[0];
      isHold = true;
      iterationIndex = 0;
    } else if (frameNum >= kf[kf.length - 1].t - this.offsetTime) {
      keyPropS = kf[kf.length - 1].s ? kf[kf.length - 1].s[0] : kf[kf.length - 2].e[0];
      /* if(kf[kf.length - 1].s){
                keyPropS = kf[kf.length - 1].s[0];
            }else{
                keyPropS = kf[kf.length - 2].e[0];
            } */
      isHold = true;
    } else {
      var i = iterationIndex;
      var len = kf.length - 1;
      var flag = true;
      var keyData;
      var nextKeyData;
      var keyframeMetadata;
      while (flag) {
        keyData = kf[i];
        nextKeyData = kf[i + 1];
        if ((nextKeyData.t - this.offsetTime) > frameNum) {
          break;
        }
        if (i < len - 1) {
          i += 1;
        } else {
          flag = false;
        }
      }
      keyframeMetadata = this.keyframesMetadata[i] || {};
      isHold = keyData.h === 1;
      iterationIndex = i;
      if (!isHold) {
        if (frameNum >= nextKeyData.t - this.offsetTime) {
          perc = 1;
        } else if (frameNum < keyData.t - this.offsetTime) {
          perc = 0;
        } else {
          var fnc;
          if (keyframeMetadata.__fnct) {
            fnc = keyframeMetadata.__fnct;
          } else {
            fnc = BezierFactory.getBezierEasing(keyData.o.x, keyData.o.y, keyData.i.x, keyData.i.y).get;
            keyframeMetadata.__fnct = fnc;
          }
          perc = fnc((frameNum - (keyData.t - this.offsetTime)) / ((nextKeyData.t - this.offsetTime) - (keyData.t - this.offsetTime)));
        }
        keyPropE = nextKeyData.s ? nextKeyData.s[0] : keyData.e[0];
      }
      keyPropS = keyData.s[0];
    }
    jLen = previousValue._length;
    kLen = keyPropS.i[0].length;
    caching.lastIndex = iterationIndex;

    for (j = 0; j < jLen; j += 1) {
      for (k = 0; k < kLen; k += 1) {
        vertexValue = isHold ? keyPropS.i[j][k] : keyPropS.i[j][k] + (keyPropE.i[j][k] - keyPropS.i[j][k]) * perc;
        previousValue.i[j][k] = vertexValue;
        vertexValue = isHold ? keyPropS.o[j][k] : keyPropS.o[j][k] + (keyPropE.o[j][k] - keyPropS.o[j][k]) * perc;
        previousValue.o[j][k] = vertexValue;
        vertexValue = isHold ? keyPropS.v[j][k] : keyPropS.v[j][k] + (keyPropE.v[j][k] - keyPropS.v[j][k]) * perc;
        previousValue.v[j][k] = vertexValue;
      }
    }
  }
```
</details>

### `interpolateShapeCurrentTime(): any`

**Returns:** `any`

**Calls:**

- `this.interpolateShape`

**Internal Comments:**
```
/// / (x5)
```

<details><summary>Code</summary>

```typescript
function interpolateShapeCurrentTime() {
    var frameNum = this.comp.renderedFrame - this.offsetTime;
    var initTime = this.keyframes[0].t - this.offsetTime;
    var endTime = this.keyframes[this.keyframes.length - 1].t - this.offsetTime;
    var lastFrame = this._caching.lastFrame;
    if (!(lastFrame !== initFrame && ((lastFrame < initTime && frameNum < initTime) || (lastFrame > endTime && frameNum > endTime)))) {
      /// /
      this._caching.lastIndex = lastFrame < frameNum ? this._caching.lastIndex : 0;
      this.interpolateShape(frameNum, this.pv, this._caching);
      /// /
    }
    this._caching.lastFrame = frameNum;
    return this.pv;
  }
```
</details>

### `resetShape(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function resetShape() {
    this.paths = this.localShapeCollection;
  }
```
</details>

### `shapesEqual(shape1: any, shape2: any): boolean`

**Parameters:**

- **`shape1`** `any`
- **`shape2`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function shapesEqual(shape1, shape2) {
    if (shape1._length !== shape2._length || shape1.c !== shape2.c) {
      return false;
    }
    var i;
    var len = shape1._length;
    for (i = 0; i < len; i += 1) {
      if (shape1.v[i][0] !== shape2.v[i][0]
            || shape1.v[i][1] !== shape2.v[i][1]
            || shape1.o[i][0] !== shape2.o[i][0]
            || shape1.o[i][1] !== shape2.o[i][1]
            || shape1.i[i][0] !== shape2.i[i][0]
            || shape1.i[i][1] !== shape2.i[i][1]) {
        return false;
      }
    }
    return true;
  }
```
</details>

### `setVValue(newPath: any): void`

**Parameters:**

- **`newPath`** `any`

**Returns:** `void`

**Calls:**

- `shapesEqual`
- `shapePool.clone`
- `this.localShapeCollection.releaseShapes`
- `this.localShapeCollection.addShape`

<details><summary>Code</summary>

```typescript
function setVValue(newPath) {
    if (!shapesEqual(this.v, newPath)) {
      this.v = shapePool.clone(newPath);
      this.localShapeCollection.releaseShapes();
      this.localShapeCollection.addShape(this.v);
      this._mdf = true;
      this.paths = this.localShapeCollection;
    }
  }
```
</details>

### `processEffectsSequence(): void`

**Returns:** `void`

**Calls:**

- `this.setVValue`
- `complex_call_113131`

<details><summary>Code</summary>

```typescript
function processEffectsSequence() {
    if (this.elem.globalData.frameId === this.frameId) {
      return;
    } if (!this.effectsSequence.length) {
      this._mdf = false;
      return;
    }
    if (this.lock) {
      this.setVValue(this.pv);
      return;
    }
    this.lock = true;
    this._mdf = false;
    var finalValue;
    if (this.kf) {
      finalValue = this.pv;
    } else if (this.data.ks) {
      finalValue = this.data.ks.k;
    } else {
      finalValue = this.data.pt.k;
    }
    var i;
    var len = this.effectsSequence.length;
    for (i = 0; i < len; i += 1) {
      finalValue = this.effectsSequence[i](finalValue);
    }
    this.setVValue(finalValue);
    this.lock = false;
    this.frameId = this.elem.globalData.frameId;
  }
```
</details>

### `ShapeProperty(elem: any, data: any, type: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `shapePool.clone`
- `shapeCollectionPool.newShapeCollection`
- `this.paths.addShape`

<details><summary>Code</summary>

```typescript
function ShapeProperty(elem, data, type) {
    this.propType = 'shape';
    this.comp = elem.comp;
    this.container = elem;
    this.elem = elem;
    this.data = data;
    this.k = false;
    this.kf = false;
    this._mdf = false;
    var pathData = type === 3 ? data.pt.k : data.ks.k;
    this.v = shapePool.clone(pathData);
    this.pv = shapePool.clone(this.v);
    this.localShapeCollection = shapeCollectionPool.newShapeCollection();
    this.paths = this.localShapeCollection;
    this.paths.addShape(this.v);
    this.reset = resetShape;
    this.effectsSequence = [];
  }
```
</details>

### `addEffect(effectFunction: any): void`

**Parameters:**

- **`effectFunction`** `any`

**Returns:** `void`

**Calls:**

- `this.effectsSequence.push`
- `this.container.addDynamicProperty`

<details><summary>Code</summary>

```typescript
function addEffect(effectFunction) {
    this.effectsSequence.push(effectFunction);
    this.container.addDynamicProperty(this);
  }
```
</details>

### `KeyframedShapeProperty(elem: any, data: any, type: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `shapePool.newElement`
- `this.v.setPathData`
- `shapePool.clone`
- `shapeCollectionPool.newShapeCollection`
- `this.paths.addShape`
- `interpolateShapeCurrentTime.bind`

<details><summary>Code</summary>

```typescript
function KeyframedShapeProperty(elem, data, type) {
    this.propType = 'shape';
    this.comp = elem.comp;
    this.elem = elem;
    this.container = elem;
    this.offsetTime = elem.data.st;
    this.keyframes = type === 3 ? data.pt.k : data.ks.k;
    this.keyframesMetadata = [];
    this.k = true;
    this.kf = true;
    var len = this.keyframes[0].s[0].i.length;
    this.v = shapePool.newElement();
    this.v.setPathData(this.keyframes[0].s[0].c, len);
    this.pv = shapePool.clone(this.v);
    this.localShapeCollection = shapeCollectionPool.newShapeCollection();
    this.paths = this.localShapeCollection;
    this.paths.addShape(this.v);
    this.lastFrame = initFrame;
    this.reset = resetShape;
    this._caching = { lastFrame: initFrame, lastIndex: 0 };
    this.effectsSequence = [interpolateShapeCurrentTime.bind(this)];
  }
```
</details>

### `EllShapePropertyFactory(elem: any, data: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `shapePool.newElement`
- `this.v.setPathData`
- `shapeCollectionPool.newShapeCollection`
- `this.localShapeCollection.addShape`
- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function EllShapePropertyFactory(elem, data) {
      this.v = shapePool.newElement();
      this.v.setPathData(true, 4);
      this.localShapeCollection = shapeCollectionPool.newShapeCollection();
      this.paths = this.localShapeCollection;
      this.localShapeCollection.addShape(this.v);
      this.d = data.d;
      this.elem = elem;
      this.comp = elem.comp;
      this.frameId = -1;
      this.initDynamicPropertyContainer(elem);
      this.p = PropertyFactory.getProp(elem, data.p, 1, 0, this);
      this.s = PropertyFactory.getProp(elem, data.s, 1, 0, this);
      if (this.dynamicProperties.length) {
        this.k = true;
      } else {
        this.k = false;
        this.convertEllToPath();
      }
    }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `StarShapePropertyFactory(elem: any, data: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `shapePool.newElement`
- `this.v.setPathData`
- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `shapeCollectionPool.newShapeCollection`
- `this.localShapeCollection.addShape`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function StarShapePropertyFactory(elem, data) {
      this.v = shapePool.newElement();
      this.v.setPathData(true, 0);
      this.elem = elem;
      this.comp = elem.comp;
      this.data = data;
      this.frameId = -1;
      this.d = data.d;
      this.initDynamicPropertyContainer(elem);
      if (data.sy === 1) {
        this.ir = PropertyFactory.getProp(elem, data.ir, 0, 0, this);
        this.is = PropertyFactory.getProp(elem, data.is, 0, 0.01, this);
        this.convertToPath = this.convertStarToPath;
      } else {
        this.convertToPath = this.convertPolygonToPath;
      }
      this.pt = PropertyFactory.getProp(elem, data.pt, 0, 0, this);
      this.p = PropertyFactory.getProp(elem, data.p, 1, 0, this);
      this.r = PropertyFactory.getProp(elem, data.r, 0, degToRads, this);
      this.or = PropertyFactory.getProp(elem, data.or, 0, 0, this);
      this.os = PropertyFactory.getProp(elem, data.os, 0, 0.01, this);
      this.localShapeCollection = shapeCollectionPool.newShapeCollection();
      this.localShapeCollection.addShape(this.v);
      this.paths = this.localShapeCollection;
      if (this.dynamicProperties.length) {
        this.k = true;
      } else {
        this.k = false;
        this.convertToPath();
      }
    }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `RectShapePropertyFactory(elem: any, data: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `shapePool.newElement`
- `shapeCollectionPool.newShapeCollection`
- `this.localShapeCollection.addShape`
- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function RectShapePropertyFactory(elem, data) {
      this.v = shapePool.newElement();
      this.v.c = true;
      this.localShapeCollection = shapeCollectionPool.newShapeCollection();
      this.localShapeCollection.addShape(this.v);
      this.paths = this.localShapeCollection;
      this.elem = elem;
      this.comp = elem.comp;
      this.frameId = -1;
      this.d = data.d;
      this.initDynamicPropertyContainer(elem);
      this.p = PropertyFactory.getProp(elem, data.p, 1, 0, this);
      this.s = PropertyFactory.getProp(elem, data.s, 1, 0, this);
      this.r = PropertyFactory.getProp(elem, data.r, 0, 0, this);
      if (this.dynamicProperties.length) {
        this.k = true;
      } else {
        this.k = false;
        this.convertRectToPath();
      }
    }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `getShapeProp(elem: any, data: any, type: any): KeyframedShapeProperty | ShapeProperty | RectShapePropertyFactory | EllShapePropertyFactory | StarShapePropertyFactory`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`type`** `any`

**Returns:** `KeyframedShapeProperty | ShapeProperty | RectShapePropertyFactory | EllShapePropertyFactory | StarShapePropertyFactory`

**Calls:**

- `elem.addDynamicProperty`

<details><summary>Code</summary>

```typescript
function getShapeProp(elem, data, type) {
    var prop;
    if (type === 3 || type === 4) {
      var dataProp = type === 3 ? data.pt : data.ks;
      var keys = dataProp.k;
      if (keys.length) {
        prop = new KeyframedShapeProperty(elem, data, type);
      } else {
        prop = new ShapeProperty(elem, data, type);
      }
    } else if (type === 5) {
      prop = new RectShapeProperty(elem, data);
    } else if (type === 6) {
      prop = new EllShapeProperty(elem, data);
    } else if (type === 7) {
      prop = new StarShapeProperty(elem, data);
    }
    if (prop.k) {
      elem.addDynamicProperty(prop);
    }
    return prop;
  }
```
</details>

### `getConstructorFunction(): typeof ShapeProperty`

**Returns:** `typeof ShapeProperty`

<details><summary>Code</summary>

```typescript
function getConstructorFunction() {
    return ShapeProperty;
  }
```
</details>

### `getKeyframedConstructorFunction(): typeof KeyframedShapeProperty`

**Returns:** `typeof KeyframedShapeProperty`

<details><summary>Code</summary>

```typescript
function getKeyframedConstructorFunction() {
    return KeyframedShapeProperty;
  }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertEllToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();

        if (this._mdf) {
          this.convertEllToPath();
        }
      }
```
</details>

### `convertEllToPath(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var s0 = this.s.v[0] / 2;
        var s1 = this.s.v[1] / 2;
        var _cw = this.d !== 3;
        var _v = this.v;
        _v.v[0][0] = p0;
        _v.v[0][1] = p1 - s1;
        _v.v[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.v[1][1] = p1;
        _v.v[2][0] = p0;
        _v.v[2][1] = p1 + s1;
        _v.v[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.v[3][1] = p1;
        _v.i[0][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.i[0][1] = p1 - s1;
        _v.i[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.i[1][1] = p1 - s1 * cPoint;
        _v.i[2][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.i[2][1] = p1 + s1;
        _v.i[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.i[3][1] = p1 + s1 * cPoint;
        _v.o[0][0] = _cw ? p0 + s0 * cPoint : p0 - s0 * cPoint;
        _v.o[0][1] = p1 - s1;
        _v.o[1][0] = _cw ? p0 + s0 : p0 - s0;
        _v.o[1][1] = p1 + s1 * cPoint;
        _v.o[2][0] = _cw ? p0 - s0 * cPoint : p0 + s0 * cPoint;
        _v.o[2][1] = p1 + s1;
        _v.o[3][0] = _cw ? p0 - s0 : p0 + s0;
        _v.o[3][1] = p1 - s1 * cPoint;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertToPath();
        }
      }
```
</details>

### `convertStarToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

**Internal Comments:**
```
/* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */ (x2)
/* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */ (x3)
```

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v) * 2;
        var angle = (Math.PI * 2) / numPts;
        /* this.v.v.length = numPts;
                this.v.i.length = numPts;
                this.v.o.length = numPts; */
        var longFlag = true;
        var longRad = this.or.v;
        var shortRad = this.ir.v;
        var longRound = this.os.v;
        var shortRound = this.is.v;
        var longPerimSegment = (2 * Math.PI * longRad) / (numPts * 2);
        var shortPerimSegment = (2 * Math.PI * shortRad) / (numPts * 2);
        var i;
        var rad;
        var roundness;
        var perimSegment;
        var currentAng = -Math.PI / 2;
        currentAng += this.r.v;
        var dir = this.data.d === 3 ? -1 : 1;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          rad = longFlag ? longRad : shortRad;
          roundness = longFlag ? longRound : shortRound;
          perimSegment = longFlag ? longPerimSegment : shortPerimSegment;
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);

          /* this.v.v[i] = [x,y];
                    this.v.i[i] = [x+ox*perimSegment*roundness*dir,y+oy*perimSegment*roundness*dir];
                    this.v.o[i] = [x-ox*perimSegment*roundness*dir,y-oy*perimSegment*roundness*dir];
                    this.v._length = numPts; */
          longFlag = !longFlag;
          currentAng += angle * dir;
        }
      }
```
</details>

### `convertPolygonToPath(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var numPts = Math.floor(this.pt.v);
        var angle = (Math.PI * 2) / numPts;
        var rad = this.or.v;
        var roundness = this.os.v;
        var perimSegment = (2 * Math.PI * rad) / (numPts * 4);
        var i;
        var currentAng = -Math.PI * 0.5;
        var dir = this.data.d === 3 ? -1 : 1;
        currentAng += this.r.v;
        this.v._length = 0;
        for (i = 0; i < numPts; i += 1) {
          var x = rad * Math.cos(currentAng);
          var y = rad * Math.sin(currentAng);
          var ox = x === 0 && y === 0 ? 0 : y / Math.sqrt(x * x + y * y);
          var oy = x === 0 && y === 0 ? 0 : -x / Math.sqrt(x * x + y * y);
          x += +this.p.v[0];
          y += +this.p.v[1];
          this.v.setTripleAt(x, y, x - ox * perimSegment * roundness * dir, y - oy * perimSegment * roundness * dir, x + ox * perimSegment * roundness * dir, y + oy * perimSegment * roundness * dir, i, true);
          currentAng += angle * dir;
        }
        this.paths.length = 0;
        this.paths[0] = this.v;
      }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `convertRectToPath(): void`

**Returns:** `void`

**Calls:**

- `bmMin`
- `this.v.setTripleAt`

<details><summary>Code</summary>

```typescript
function () {
        var p0 = this.p.v[0];
        var p1 = this.p.v[1];
        var v0 = this.s.v[0] / 2;
        var v1 = this.s.v[1] / 2;
        var round = bmMin(v0, v1, this.r.v);
        var cPoint = round * (1 - roundCorner);
        this.v._length = 0;

        if (this.d === 2 || this.d === 1) {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, 0, true);
          this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, p0 + v0, p1 + v1 - round, 1, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, 2, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0 + round, p1 + v1, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, 4, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1 + round, 5, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, 6, true);
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, p0 + v0 - round, p1 - v1, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0 + cPoint, p1 + v1, p0 - v0, p1 + v1, 2);
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0, p1 - v1 + cPoint, p0 - v0, p1 - v1, 3);
          }
        } else {
          this.v.setTripleAt(p0 + v0, p1 - v1 + round, p0 + v0, p1 - v1 + cPoint, p0 + v0, p1 - v1 + round, 0, true);
          if (round !== 0) {
            this.v.setTripleAt(p0 + v0 - round, p1 - v1, p0 + v0 - round, p1 - v1, p0 + v0 - cPoint, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0 + round, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0 + round, p1 - v1, 2, true);
            this.v.setTripleAt(p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + round, p0 - v0, p1 - v1 + cPoint, 3, true);
            this.v.setTripleAt(p0 - v0, p1 + v1 - round, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1 - round, 4, true);
            this.v.setTripleAt(p0 - v0 + round, p1 + v1, p0 - v0 + round, p1 + v1, p0 - v0 + cPoint, p1 + v1, 5, true);
            this.v.setTripleAt(p0 + v0 - round, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0 - round, p1 + v1, 6, true);
            this.v.setTripleAt(p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - round, p0 + v0, p1 + v1 - cPoint, 7, true);
          } else {
            this.v.setTripleAt(p0 - v0, p1 - v1, p0 - v0 + cPoint, p1 - v1, p0 - v0, p1 - v1, 1, true);
            this.v.setTripleAt(p0 - v0, p1 + v1, p0 - v0, p1 + v1 - cPoint, p0 - v0, p1 + v1, 2, true);
            this.v.setTripleAt(p0 + v0, p1 + v1, p0 + v0 - cPoint, p1 + v1, p0 + v0, p1 + v1, 3, true);
          }
        }
      }
```
</details>

### `getValue(): void`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `this.convertRectToPath`

<details><summary>Code</summary>

```typescript
function () {
        if (this.elem.globalData.frameId === this.frameId) {
          return;
        }
        this.frameId = this.elem.globalData.frameId;
        this.iterateDynamicProperties();
        if (this._mdf) {
          this.convertRectToPath();
        }
      }
```
</details>

### `reset(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function reset() {
    this.props[0] = 1;
    this.props[1] = 0;
    this.props[2] = 0;
    this.props[3] = 0;
    this.props[4] = 0;
    this.props[5] = 1;
    this.props[6] = 0;
    this.props[7] = 0;
    this.props[8] = 0;
    this.props[9] = 0;
    this.props[10] = 1;
    this.props[11] = 0;
    this.props[12] = 0;
    this.props[13] = 0;
    this.props[14] = 0;
    this.props[15] = 1;
    return this;
  }
```
</details>

### `rotate(angle: any): any`

**Parameters:**

- **`angle`** `any`

**Returns:** `any`

**Calls:**

- `_cos`
- `_sin`
- `this._t`

<details><summary>Code</summary>

```typescript
function rotate(angle) {
    if (angle === 0) {
      return this;
    }
    var mCos = _cos(angle);
    var mSin = _sin(angle);
    return this._t(mCos, -mSin, 0, 0, mSin, mCos, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
  }
```
</details>

### `rotateX(angle: any): any`

**Parameters:**

- **`angle`** `any`

**Returns:** `any`

**Calls:**

- `_cos`
- `_sin`
- `this._t`

<details><summary>Code</summary>

```typescript
function rotateX(angle) {
    if (angle === 0) {
      return this;
    }
    var mCos = _cos(angle);
    var mSin = _sin(angle);
    return this._t(1, 0, 0, 0, 0, mCos, -mSin, 0, 0, mSin, mCos, 0, 0, 0, 0, 1);
  }
```
</details>

### `rotateY(angle: any): any`

**Parameters:**

- **`angle`** `any`

**Returns:** `any`

**Calls:**

- `_cos`
- `_sin`
- `this._t`

<details><summary>Code</summary>

```typescript
function rotateY(angle) {
    if (angle === 0) {
      return this;
    }
    var mCos = _cos(angle);
    var mSin = _sin(angle);
    return this._t(mCos, 0, mSin, 0, 0, 1, 0, 0, -mSin, 0, mCos, 0, 0, 0, 0, 1);
  }
```
</details>

### `rotateZ(angle: any): any`

**Parameters:**

- **`angle`** `any`

**Returns:** `any`

**Calls:**

- `_cos`
- `_sin`
- `this._t`

<details><summary>Code</summary>

```typescript
function rotateZ(angle) {
    if (angle === 0) {
      return this;
    }
    var mCos = _cos(angle);
    var mSin = _sin(angle);
    return this._t(mCos, -mSin, 0, 0, mSin, mCos, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
  }
```
</details>

### `shear(sx: any, sy: any): any`

**Parameters:**

- **`sx`** `any`
- **`sy`** `any`

**Returns:** `any`

**Calls:**

- `this._t`

<details><summary>Code</summary>

```typescript
function shear(sx, sy) {
    return this._t(1, sy, sx, 1, 0, 0);
  }
```
</details>

### `skew(ax: any, ay: any): any`

**Parameters:**

- **`ax`** `any`
- **`ay`** `any`

**Returns:** `any`

**Calls:**

- `this.shear`
- `_tan`

<details><summary>Code</summary>

```typescript
function skew(ax, ay) {
    return this.shear(_tan(ax), _tan(ay));
  }
```
</details>

### `skewFromAxis(ax: any, angle: any): any`

**Parameters:**

- **`ax`** `any`
- **`angle`** `any`

**Returns:** `any`

**Calls:**

- `_cos`
- `_sin`
- `this._t(mCos, mSin, 0, 0, -mSin, mCos, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1)
      ._t(1, 0, 0, 0, _tan(ax), 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1)
      ._t`

<details><summary>Code</summary>

```typescript
function skewFromAxis(ax, angle) {
    var mCos = _cos(angle);
    var mSin = _sin(angle);
    return this._t(mCos, mSin, 0, 0, -mSin, mCos, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1)
      ._t(1, 0, 0, 0, _tan(ax), 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1)
      ._t(mCos, -mSin, 0, 0, mSin, mCos, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
    // return this._t(mCos, mSin, -mSin, mCos, 0, 0)._t(1, 0, _tan(ax), 1, 0, 0)._t(mCos, -mSin, mSin, mCos, 0, 0);
  }
```
</details>

### `scale(sx: any, sy: any, sz: any): any`

**Parameters:**

- **`sx`** `any`
- **`sy`** `any`
- **`sz`** `any`

**Returns:** `any`

**Calls:**

- `this._t`

<details><summary>Code</summary>

```typescript
function scale(sx, sy, sz) {
    if (!sz && sz !== 0) {
      sz = 1;
    }
    if (sx === 1 && sy === 1 && sz === 1) {
      return this;
    }
    return this._t(sx, 0, 0, 0, 0, sy, 0, 0, 0, 0, sz, 0, 0, 0, 0, 1);
  }
```
</details>

### `setTransform(a: any, b: any, c: any, d: any, e: any, f: any, g: any, h: any, i: any, j: any, k: any, l: any, m: any, n: any, o: any, p: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`d`** `any`
- **`e`** `any`
- **`f`** `any`
- **`g`** `any`
- **`h`** `any`
- **`i`** `any`
- **`j`** `any`
- **`k`** `any`
- **`l`** `any`
- **`m`** `any`
- **`n`** `any`
- **`o`** `any`
- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function setTransform(a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p) {
    this.props[0] = a;
    this.props[1] = b;
    this.props[2] = c;
    this.props[3] = d;
    this.props[4] = e;
    this.props[5] = f;
    this.props[6] = g;
    this.props[7] = h;
    this.props[8] = i;
    this.props[9] = j;
    this.props[10] = k;
    this.props[11] = l;
    this.props[12] = m;
    this.props[13] = n;
    this.props[14] = o;
    this.props[15] = p;
    return this;
  }
```
</details>

### `translate(tx: any, ty: any, tz: any): any`

**Parameters:**

- **`tx`** `any`
- **`ty`** `any`
- **`tz`** `any`

**Returns:** `any`

**Calls:**

- `this._t`

<details><summary>Code</summary>

```typescript
function translate(tx, ty, tz) {
    tz = tz || 0;
    if (tx !== 0 || ty !== 0 || tz !== 0) {
      return this._t(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, tx, ty, tz, 1);
    }
    return this;
  }
```
</details>

### `transform(a2: any, b2: any, c2: any, d2: any, e2: any, f2: any, g2: any, h2: any, i2: any, j2: any, k2: any, l2: any, m2: any, n2: any, o2: any, p2: any): this`

**Parameters:**

- **`a2`** `any`
- **`b2`** `any`
- **`c2`** `any`
- **`d2`** `any`
- **`e2`** `any`
- **`f2`** `any`
- **`g2`** `any`
- **`h2`** `any`
- **`i2`** `any`
- **`j2`** `any`
- **`k2`** `any`
- **`l2`** `any`
- **`m2`** `any`
- **`n2`** `any`
- **`o2`** `any`
- **`p2`** `any`

**Returns:** `this`

**Internal Comments:**
```
// NOTE: commenting this condition because TurboFan deoptimizes code when present (x4)
// if(m2 !== 0 || n2 !== 0 || o2 !== 0){ (x4)
// } (x4)
/* matrix order (canvas compatible):
         * ace
         * bdf
         * 001
         */ (x4)
```

<details><summary>Code</summary>

```typescript
function transform(a2, b2, c2, d2, e2, f2, g2, h2, i2, j2, k2, l2, m2, n2, o2, p2) {
    var _p = this.props;

    if (a2 === 1 && b2 === 0 && c2 === 0 && d2 === 0 && e2 === 0 && f2 === 1 && g2 === 0 && h2 === 0 && i2 === 0 && j2 === 0 && k2 === 1 && l2 === 0) {
      // NOTE: commenting this condition because TurboFan deoptimizes code when present
      // if(m2 !== 0 || n2 !== 0 || o2 !== 0){
      _p[12] = _p[12] * a2 + _p[15] * m2;
      _p[13] = _p[13] * f2 + _p[15] * n2;
      _p[14] = _p[14] * k2 + _p[15] * o2;
      _p[15] *= p2;
      // }
      this._identityCalculated = false;
      return this;
    }

    var a1 = _p[0];
    var b1 = _p[1];
    var c1 = _p[2];
    var d1 = _p[3];
    var e1 = _p[4];
    var f1 = _p[5];
    var g1 = _p[6];
    var h1 = _p[7];
    var i1 = _p[8];
    var j1 = _p[9];
    var k1 = _p[10];
    var l1 = _p[11];
    var m1 = _p[12];
    var n1 = _p[13];
    var o1 = _p[14];
    var p1 = _p[15];

    /* matrix order (canvas compatible):
         * ace
         * bdf
         * 001
         */
    _p[0] = a1 * a2 + b1 * e2 + c1 * i2 + d1 * m2;
    _p[1] = a1 * b2 + b1 * f2 + c1 * j2 + d1 * n2;
    _p[2] = a1 * c2 + b1 * g2 + c1 * k2 + d1 * o2;
    _p[3] = a1 * d2 + b1 * h2 + c1 * l2 + d1 * p2;

    _p[4] = e1 * a2 + f1 * e2 + g1 * i2 + h1 * m2;
    _p[5] = e1 * b2 + f1 * f2 + g1 * j2 + h1 * n2;
    _p[6] = e1 * c2 + f1 * g2 + g1 * k2 + h1 * o2;
    _p[7] = e1 * d2 + f1 * h2 + g1 * l2 + h1 * p2;

    _p[8] = i1 * a2 + j1 * e2 + k1 * i2 + l1 * m2;
    _p[9] = i1 * b2 + j1 * f2 + k1 * j2 + l1 * n2;
    _p[10] = i1 * c2 + j1 * g2 + k1 * k2 + l1 * o2;
    _p[11] = i1 * d2 + j1 * h2 + k1 * l2 + l1 * p2;

    _p[12] = m1 * a2 + n1 * e2 + o1 * i2 + p1 * m2;
    _p[13] = m1 * b2 + n1 * f2 + o1 * j2 + p1 * n2;
    _p[14] = m1 * c2 + n1 * g2 + o1 * k2 + p1 * o2;
    _p[15] = m1 * d2 + n1 * h2 + o1 * l2 + p1 * p2;

    this._identityCalculated = false;
    return this;
  }
```
</details>

### `isIdentity(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isIdentity() {
    if (!this._identityCalculated) {
      this._identity = !(this.props[0] !== 1 || this.props[1] !== 0 || this.props[2] !== 0 || this.props[3] !== 0 || this.props[4] !== 0 || this.props[5] !== 1 || this.props[6] !== 0 || this.props[7] !== 0 || this.props[8] !== 0 || this.props[9] !== 0 || this.props[10] !== 1 || this.props[11] !== 0 || this.props[12] !== 0 || this.props[13] !== 0 || this.props[14] !== 0 || this.props[15] !== 1);
      this._identityCalculated = true;
    }
    return this._identity;
  }
```
</details>

### `equals(matr: any): boolean`

**Parameters:**

- **`matr`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function equals(matr) {
    var i = 0;
    while (i < 16) {
      if (matr.props[i] !== this.props[i]) {
        return false;
      }
      i += 1;
    }
    return true;
  }
```
</details>

### `clone(matr: any): any`

**Parameters:**

- **`matr`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function clone(matr) {
    var i;
    for (i = 0; i < 16; i += 1) {
      matr.props[i] = this.props[i];
    }
    return matr;
  }
```
</details>

### `cloneFromProps(props: any): void`

**Parameters:**

- **`props`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function cloneFromProps(props) {
    var i;
    for (i = 0; i < 16; i += 1) {
      this.props[i] = props[i];
    }
  }
```
</details>

### `applyToPoint(x: any, y: any, z: any): { x: any; y: any; z: any; }`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `{ x: any; y: any; z: any; }`

<details><summary>Code</summary>

```typescript
function applyToPoint(x, y, z) {
    return {
      x: x * this.props[0] + y * this.props[4] + z * this.props[8] + this.props[12],
      y: x * this.props[1] + y * this.props[5] + z * this.props[9] + this.props[13],
      z: x * this.props[2] + y * this.props[6] + z * this.props[10] + this.props[14],
    };
    /* return {
         x: x * me.a + y * me.c + me.e,
         y: x * me.b + y * me.d + me.f
         }; */
  }
```
</details>

### `applyToX(x: any, y: any, z: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function applyToX(x, y, z) {
    return x * this.props[0] + y * this.props[4] + z * this.props[8] + this.props[12];
  }
```
</details>

### `applyToY(x: any, y: any, z: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function applyToY(x, y, z) {
    return x * this.props[1] + y * this.props[5] + z * this.props[9] + this.props[13];
  }
```
</details>

### `applyToZ(x: any, y: any, z: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function applyToZ(x, y, z) {
    return x * this.props[2] + y * this.props[6] + z * this.props[10] + this.props[14];
  }
```
</details>

### `getInverseMatrix(): (Anonymous function)`

**Returns:** `(Anonymous function)`

<details><summary>Code</summary>

```typescript
function getInverseMatrix() {
    var determinant = this.props[0] * this.props[5] - this.props[1] * this.props[4];
    var a = this.props[5] / determinant;
    var b = -this.props[1] / determinant;
    var c = -this.props[4] / determinant;
    var d = this.props[0] / determinant;
    var e = (this.props[4] * this.props[13] - this.props[5] * this.props[12]) / determinant;
    var f = -(this.props[0] * this.props[13] - this.props[1] * this.props[12]) / determinant;
    var inverseMatrix = new Matrix();
    inverseMatrix.props[0] = a;
    inverseMatrix.props[1] = b;
    inverseMatrix.props[4] = c;
    inverseMatrix.props[5] = d;
    inverseMatrix.props[12] = e;
    inverseMatrix.props[13] = f;
    return inverseMatrix;
  }
```
</details>

### `inversePoint(pt: any): any`

**Parameters:**

- **`pt`** `any`

**Returns:** `any`

**Calls:**

- `this.getInverseMatrix`
- `inverseMatrix.applyToPointArray`

<details><summary>Code</summary>

```typescript
function inversePoint(pt) {
    var inverseMatrix = this.getInverseMatrix();
    return inverseMatrix.applyToPointArray(pt[0], pt[1], pt[2] || 0);
  }
```
</details>

### `inversePoints(pts: any): any[]`

**Parameters:**

- **`pts`** `any`

**Returns:** `any[]`

**Calls:**

- `inversePoint`

<details><summary>Code</summary>

```typescript
function inversePoints(pts) {
    var i;
    var len = pts.length;
    var retPts = [];
    for (i = 0; i < len; i += 1) {
      retPts[i] = inversePoint(pts[i]);
    }
    return retPts;
  }
```
</details>

### `applyToTriplePoints(pt1: any, pt2: any, pt3: any): number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Parameters:**

- **`pt1`** `any`
- **`pt2`** `any`
- **`pt3`** `any`

**Returns:** `number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `createTypedArray`
- `this.isIdentity`

<details><summary>Code</summary>

```typescript
function applyToTriplePoints(pt1, pt2, pt3) {
    var arr = createTypedArray('float32', 6);
    if (this.isIdentity()) {
      arr[0] = pt1[0];
      arr[1] = pt1[1];
      arr[2] = pt2[0];
      arr[3] = pt2[1];
      arr[4] = pt3[0];
      arr[5] = pt3[1];
    } else {
      var p0 = this.props[0];
      var p1 = this.props[1];
      var p4 = this.props[4];
      var p5 = this.props[5];
      var p12 = this.props[12];
      var p13 = this.props[13];
      arr[0] = pt1[0] * p0 + pt1[1] * p4 + p12;
      arr[1] = pt1[0] * p1 + pt1[1] * p5 + p13;
      arr[2] = pt2[0] * p0 + pt2[1] * p4 + p12;
      arr[3] = pt2[0] * p1 + pt2[1] * p5 + p13;
      arr[4] = pt3[0] * p0 + pt3[1] * p4 + p12;
      arr[5] = pt3[0] * p1 + pt3[1] * p5 + p13;
    }
    return arr;
  }
```
</details>

### `applyToPointArray(x: any, y: any, z: any): any[]`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `any[]`

**Calls:**

- `this.isIdentity`

<details><summary>Code</summary>

```typescript
function applyToPointArray(x, y, z) {
    var arr;
    if (this.isIdentity()) {
      arr = [x, y, z];
    } else {
      arr = [
        x * this.props[0] + y * this.props[4] + z * this.props[8] + this.props[12],
        x * this.props[1] + y * this.props[5] + z * this.props[9] + this.props[13],
        x * this.props[2] + y * this.props[6] + z * this.props[10] + this.props[14],
      ];
    }
    return arr;
  }
```
</details>

### `applyToPointStringified(x: any, y: any): string`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `string`

**Calls:**

- `this.isIdentity`
- `Math.round`

<details><summary>Code</summary>

```typescript
function applyToPointStringified(x, y) {
    if (this.isIdentity()) {
      return x + ',' + y;
    }
    var _p = this.props;
    return Math.round((x * _p[0] + y * _p[4] + _p[12]) * 100) / 100 + ',' + Math.round((x * _p[1] + y * _p[5] + _p[13]) * 100) / 100;
  }
```
</details>

### `toCSS(): string`

**Returns:** `string`

**Calls:**

- `_rnd`

**Internal Comments:**
```
// Doesn't make much sense to add this optimization. If it is an identity matrix, it's very likely this will get called only once since it won't be keyframed. (x2)
/* if(this.isIdentity()) {
            return '';
        } */ (x2)
```

<details><summary>Code</summary>

```typescript
function toCSS() {
    // Doesn't make much sense to add this optimization. If it is an identity matrix, it's very likely this will get called only once since it won't be keyframed.
    /* if(this.isIdentity()) {
            return '';
        } */
    var i = 0;
    var props = this.props;
    var cssValue = 'matrix3d(';
    var v = 10000;
    while (i < 16) {
      cssValue += _rnd(props[i] * v) / v;
      cssValue += i === 15 ? ')' : ',';
      i += 1;
    }
    return cssValue;
  }
```
</details>

### `roundMatrixProperty(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

**Calls:**

- `_rnd`

<details><summary>Code</summary>

```typescript
function roundMatrixProperty(val) {
    var v = 10000;
    if ((val < 0.000001 && val > 0) || (val > -0.000001 && val < 0)) {
      return _rnd(val * v) / v;
    }
    return val;
  }
```
</details>

### `to2dCSS(): string`

**Returns:** `string`

**Calls:**

- `roundMatrixProperty`

**Internal Comments:**
```
// Doesn't make much sense to add this optimization. If it is an identity matrix, it's very likely this will get called only once since it won't be keyframed. (x2)
/* if(this.isIdentity()) {
            return '';
        } */ (x2)
```

<details><summary>Code</summary>

```typescript
function to2dCSS() {
    // Doesn't make much sense to add this optimization. If it is an identity matrix, it's very likely this will get called only once since it won't be keyframed.
    /* if(this.isIdentity()) {
            return '';
        } */
    var props = this.props;
    var _a = roundMatrixProperty(props[0]);
    var _b = roundMatrixProperty(props[1]);
    var _c = roundMatrixProperty(props[4]);
    var _d = roundMatrixProperty(props[5]);
    var _e = roundMatrixProperty(props[12]);
    var _f = roundMatrixProperty(props[13]);
    return 'matrix(' + _a + ',' + _b + ',' + _c + ',' + _d + ',' + _e + ',' + _f + ')';
  }
```
</details>

### `setLocation(href: any): void`

**Parameters:**

- **`href`** `any`

**Returns:** `void`

**Calls:**

- `setLocationHref`

<details><summary>Code</summary>

```typescript
function setLocation(href) {
  setLocationHref(href);
}
```
</details>

### `searchAnimations(): void`

**Returns:** `void`

**Calls:**

- `animationManager.searchAnimations`

<details><summary>Code</summary>

```typescript
function searchAnimations() {
  if (standalone === true) {
    animationManager.searchAnimations(animationData, standalone, renderer);
  } else {
    animationManager.searchAnimations();
  }
}
```
</details>

### `setSubframeRendering(flag: any): void`

**Parameters:**

- **`flag`** `any`

**Returns:** `void`

**Calls:**

- `setSubframeEnabled`

<details><summary>Code</summary>

```typescript
function setSubframeRendering(flag) {
  setSubframeEnabled(flag);
}
```
</details>

### `setPrefix(prefix: any): void`

**Parameters:**

- **`prefix`** `any`

**Returns:** `void`

**Calls:**

- `setIdPrefix`

<details><summary>Code</summary>

```typescript
function setPrefix(prefix) {
  setIdPrefix(prefix);
}
```
</details>

### `loadAnimation(params: any): AnimationItem`

**Parameters:**

- **`params`** `any`

**Returns:** `AnimationItem`

**Calls:**

- `JSON.parse`
- `animationManager.loadAnimation`

<details><summary>Code</summary>

```typescript
function loadAnimation(params) {
  if (standalone === true) {
    params.animationData = JSON.parse(animationData);
  }
  return animationManager.loadAnimation(params);
}
```
</details>

### `setQuality(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `setDefaultCurveSegments`
- `isNaN`
- `getDefaultCurveSegments`
- `roundValues`

<details><summary>Code</summary>

```typescript
function setQuality(value) {
  if (typeof value === 'string') {
    switch (value) {
      case 'high':
        setDefaultCurveSegments(200);
        break;
      default:
      case 'medium':
        setDefaultCurveSegments(50);
        break;
      case 'low':
        setDefaultCurveSegments(10);
        break;
    }
  } else if (!isNaN(value) && value > 1) {
    setDefaultCurveSegments(value);
  }
  if (getDefaultCurveSegments() >= 50) {
    roundValues(false);
  } else {
    roundValues(true);
  }
}
```
</details>

### `inBrowser(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function inBrowser() {
  return typeof navigator !== 'undefined';
}
```
</details>

### `installPlugin(type: any, plugin: any): void`

**Parameters:**

- **`type`** `any`
- **`plugin`** `any`

**Returns:** `void`

**Calls:**

- `setExpressionsPlugin`

<details><summary>Code</summary>

```typescript
function installPlugin(type, plugin) {
  if (type === 'expressions') {
    setExpressionsPlugin(plugin);
  }
}
```
</details>

### `getFactory(name: any): { getProp: (elem: any, data: any, type: any, mult: any, container: any) => ValueProperty | MultiDimensionalProperty | KeyframedValueProperty | KeyframedMultidimensionalProperty; } | typeof (Anonymous function) | { ...; }`

**Parameters:**

- **`name`** `any`

**Returns:** `{ getProp: (elem: any, data: any, type: any, mult: any, container: any) => ValueProperty | MultiDimensionalProperty | KeyframedValueProperty | KeyframedMultidimensionalProperty; } | typeof (Anonymous function) | { ...; }`

<details><summary>Code</summary>

```typescript
function getFactory(name) {
  switch (name) {
    case 'propertyFactory':
      return PropertyFactory;
    case 'shapePropertyFactory':
      return ShapePropertyFactory;
    case 'matrix':
      return Matrix;
    default:
      return null;
  }
}
```
</details>

### `checkReady(): void`

**Returns:** `void`

**Calls:**

- `clearInterval`
- `searchAnimations`

<details><summary>Code</summary>

```typescript
function checkReady() {
  if (document.readyState === 'complete') {
    clearInterval(readyStateCheckInterval);
    searchAnimations();
  }
}
```
</details>

### `getQueryVariable(variable: any): string`

**Parameters:**

- **`variable`** `any`

**Returns:** `string`

**Calls:**

- `queryString.split`
- `vars[i].split`
- `decodeURIComponent`

<details><summary>Code</summary>

```typescript
function getQueryVariable(variable) {
  var vars = queryString.split('&');
  for (var i = 0; i < vars.length; i += 1) {
    var pair = vars[i].split('=');
    if (decodeURIComponent(pair[0]) == variable) { // eslint-disable-line eqeqeq
      return decodeURIComponent(pair[1]);
    }
  }
  return null;
}
```
</details>

### `registerModifier(nm: any, factory: any): void`

**Parameters:**

- **`nm`** `any`
- **`factory`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function registerModifier(nm, factory) {
    if (!modifiers[nm]) {
      modifiers[nm] = factory;
    }
  }
```
</details>

### `getModifier(nm: any, elem: any, data: any): any`

**Parameters:**

- **`nm`** `any`
- **`elem`** `any`
- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getModifier(nm, elem, data) {
    return new modifiers[nm](elem, data);
  }
```
</details>

### `ShapeModifier(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ShapeModifier() {}
```
</details>

### `TrimModifier(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function TrimModifier() {
}
```
</details>

### `PuckerAndBloatModifier(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function PuckerAndBloatModifier() {}
```
</details>

### `applyToMatrix(mat: any): void`

**Parameters:**

- **`mat`** `any`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`
- `mat.translate`
- `mat.scale`
- `mat.skewFromAxis`
- `mat.rotate`
- `mat.rotateZ(-this.rz.v).rotateY(this.ry.v).rotateX(this.rx.v).rotateZ(-this.or.v[2])
        .rotateY(this.or.v[1])
        .rotateX`

<details><summary>Code</summary>

```typescript
function applyToMatrix(mat) {
    var _mdf = this._mdf;
    this.iterateDynamicProperties();
    this._mdf = this._mdf || _mdf;
    if (this.a) {
      mat.translate(-this.a.v[0], -this.a.v[1], this.a.v[2]);
    }
    if (this.s) {
      mat.scale(this.s.v[0], this.s.v[1], this.s.v[2]);
    }
    if (this.sk) {
      mat.skewFromAxis(-this.sk.v, this.sa.v);
    }
    if (this.r) {
      mat.rotate(-this.r.v);
    } else {
      mat.rotateZ(-this.rz.v).rotateY(this.ry.v).rotateX(this.rx.v).rotateZ(-this.or.v[2])
        .rotateY(this.or.v[1])
        .rotateX(this.or.v[0]);
    }
    if (this.data.p.s) {
      if (this.data.p.z) {
        mat.translate(this.px.v, this.py.v, -this.pz.v);
      } else {
        mat.translate(this.px.v, this.py.v, 0);
      }
    } else {
      mat.translate(this.p.v[0], this.p.v[1], -this.p.v[2]);
    }
  }
```
</details>

### `processKeys(forceRender: any): void`

**Parameters:**

- **`forceRender`** `any`

**Returns:** `void`

**Calls:**

- `this.precalculateMatrix`
- `this.iterateDynamicProperties`
- `this.v.cloneFromProps`
- `this.v.translate`
- `this.v.scale`
- `this.v.skewFromAxis`
- `this.v.rotate`
- `this.v.rotateZ(-this.rz.v).rotateY(this.ry.v).rotateX(this.rx.v).rotateZ(-this.or.v[2])
          .rotateY(this.or.v[1])
          .rotateX`
- `this.p.getValueAtTime`
- `px.getValueAtTime`
- `py.getValueAtTime`
- `Math.atan2`

<details><summary>Code</summary>

```typescript
function processKeys(forceRender) {
    if (this.elem.globalData.frameId === this.frameId) {
      return;
    }
    if (this._isDirty) {
      this.precalculateMatrix();
      this._isDirty = false;
    }

    this.iterateDynamicProperties();

    if (this._mdf || forceRender) {
      var frameRate;
      this.v.cloneFromProps(this.pre.props);
      if (this.appliedTransformations < 1) {
        this.v.translate(-this.a.v[0], -this.a.v[1], this.a.v[2]);
      }
      if (this.appliedTransformations < 2) {
        this.v.scale(this.s.v[0], this.s.v[1], this.s.v[2]);
      }
      if (this.sk && this.appliedTransformations < 3) {
        this.v.skewFromAxis(-this.sk.v, this.sa.v);
      }
      if (this.r && this.appliedTransformations < 4) {
        this.v.rotate(-this.r.v);
      } else if (!this.r && this.appliedTransformations < 4) {
        this.v.rotateZ(-this.rz.v).rotateY(this.ry.v).rotateX(this.rx.v).rotateZ(-this.or.v[2])
          .rotateY(this.or.v[1])
          .rotateX(this.or.v[0]);
      }
      if (this.autoOriented) {
        var v1;
        var v2;
        frameRate = this.elem.globalData.frameRate;
        if (this.p && this.p.keyframes && this.p.getValueAtTime) {
          if (this.p._caching.lastFrame + this.p.offsetTime <= this.p.keyframes[0].t) {
            v1 = this.p.getValueAtTime((this.p.keyframes[0].t + 0.01) / frameRate, 0);
            v2 = this.p.getValueAtTime(this.p.keyframes[0].t / frameRate, 0);
          } else if (this.p._caching.lastFrame + this.p.offsetTime >= this.p.keyframes[this.p.keyframes.length - 1].t) {
            v1 = this.p.getValueAtTime((this.p.keyframes[this.p.keyframes.length - 1].t / frameRate), 0);
            v2 = this.p.getValueAtTime((this.p.keyframes[this.p.keyframes.length - 1].t - 0.05) / frameRate, 0);
          } else {
            v1 = this.p.pv;
            v2 = this.p.getValueAtTime((this.p._caching.lastFrame + this.p.offsetTime - 0.01) / frameRate, this.p.offsetTime);
          }
        } else if (this.px && this.px.keyframes && this.py.keyframes && this.px.getValueAtTime && this.py.getValueAtTime) {
          v1 = [];
          v2 = [];
          var px = this.px;
          var py = this.py;
          if (px._caching.lastFrame + px.offsetTime <= px.keyframes[0].t) {
            v1[0] = px.getValueAtTime((px.keyframes[0].t + 0.01) / frameRate, 0);
            v1[1] = py.getValueAtTime((py.keyframes[0].t + 0.01) / frameRate, 0);
            v2[0] = px.getValueAtTime((px.keyframes[0].t) / frameRate, 0);
            v2[1] = py.getValueAtTime((py.keyframes[0].t) / frameRate, 0);
          } else if (px._caching.lastFrame + px.offsetTime >= px.keyframes[px.keyframes.length - 1].t) {
            v1[0] = px.getValueAtTime((px.keyframes[px.keyframes.length - 1].t / frameRate), 0);
            v1[1] = py.getValueAtTime((py.keyframes[py.keyframes.length - 1].t / frameRate), 0);
            v2[0] = px.getValueAtTime((px.keyframes[px.keyframes.length - 1].t - 0.01) / frameRate, 0);
            v2[1] = py.getValueAtTime((py.keyframes[py.keyframes.length - 1].t - 0.01) / frameRate, 0);
          } else {
            v1 = [px.pv, py.pv];
            v2[0] = px.getValueAtTime((px._caching.lastFrame + px.offsetTime - 0.01) / frameRate, px.offsetTime);
            v2[1] = py.getValueAtTime((py._caching.lastFrame + py.offsetTime - 0.01) / frameRate, py.offsetTime);
          }
        } else {
          v2 = defaultVector;
          v1 = v2;
        }
        this.v.rotate(-Math.atan2(v1[1] - v2[1], v1[0] - v2[0]));
      }
      if (this.data.p && this.data.p.s) {
        if (this.data.p.z) {
          this.v.translate(this.px.v, this.py.v, -this.pz.v);
        } else {
          this.v.translate(this.px.v, this.py.v, 0);
        }
      } else {
        this.v.translate(this.p.v[0], this.p.v[1], -this.p.v[2]);
      }
    }
    this.frameId = this.elem.globalData.frameId;
  }
```
</details>

### `precalculateMatrix(): void`

**Returns:** `void`

**Calls:**

- `this.pre.translate`
- `this.pre.scale`
- `this.pre.skewFromAxis`
- `this.pre.rotate`
- `this.pre.rotateZ(-this.rz.v).rotateY(this.ry.v).rotateX(this.rx.v).rotateZ(-this.or.v[2])
        .rotateY(this.or.v[1])
        .rotateX`

<details><summary>Code</summary>

```typescript
function precalculateMatrix() {
    if (!this.a.k) {
      this.pre.translate(-this.a.v[0], -this.a.v[1], this.a.v[2]);
      this.appliedTransformations = 1;
    } else {
      return;
    }
    if (!this.s.effectsSequence.length) {
      this.pre.scale(this.s.v[0], this.s.v[1], this.s.v[2]);
      this.appliedTransformations = 2;
    } else {
      return;
    }
    if (this.sk) {
      if (!this.sk.effectsSequence.length && !this.sa.effectsSequence.length) {
        this.pre.skewFromAxis(-this.sk.v, this.sa.v);
        this.appliedTransformations = 3;
      } else {
        return;
      }
    }
    if (this.r) {
      if (!this.r.effectsSequence.length) {
        this.pre.rotate(-this.r.v);
        this.appliedTransformations = 4;
      }
    } else if (!this.rz.effectsSequence.length && !this.ry.effectsSequence.length && !this.rx.effectsSequence.length && !this.or.effectsSequence.length) {
      this.pre.rotateZ(-this.rz.v).rotateY(this.ry.v).rotateX(this.rx.v).rotateZ(-this.or.v[2])
        .rotateY(this.or.v[1])
        .rotateX(this.or.v[0]);
      this.appliedTransformations = 4;
    }
  }
```
</details>

### `autoOrient(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function autoOrient() {
    //
    // var prevP = this.getValueAtTime();
  }
```
</details>

### `addDynamicProperty(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `this._addDynamicProperty`
- `this.elem.addDynamicProperty`

<details><summary>Code</summary>

```typescript
function addDynamicProperty(prop) {
    this._addDynamicProperty(prop);
    this.elem.addDynamicProperty(prop);
    this._isDirty = true;
  }
```
</details>

### `TransformProperty(elem: any, data: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `this.getValue`

**Internal Comments:**
```
// Precalculated matrix with non animated properties (x4)
// sh Indicates it needs to be capped between -180 and 180 (x5)
// Opacity is not part of the transform properties, that's why it won't use this.dynamicProperties. That way transforms won't get updated if opacity changes.
```

<details><summary>Code</summary>

```typescript
function TransformProperty(elem, data, container) {
    this.elem = elem;
    this.frameId = -1;
    this.propType = 'transform';
    this.data = data;
    this.v = new Matrix();
    // Precalculated matrix with non animated properties
    this.pre = new Matrix();
    this.appliedTransformations = 0;
    this.initDynamicPropertyContainer(container || elem);
    if (data.p && data.p.s) {
      this.px = PropertyFactory.getProp(elem, data.p.x, 0, 0, this);
      this.py = PropertyFactory.getProp(elem, data.p.y, 0, 0, this);
      if (data.p.z) {
        this.pz = PropertyFactory.getProp(elem, data.p.z, 0, 0, this);
      }
    } else {
      this.p = PropertyFactory.getProp(elem, data.p || { k: [0, 0, 0] }, 1, 0, this);
    }
    if (data.rx) {
      this.rx = PropertyFactory.getProp(elem, data.rx, 0, degToRads, this);
      this.ry = PropertyFactory.getProp(elem, data.ry, 0, degToRads, this);
      this.rz = PropertyFactory.getProp(elem, data.rz, 0, degToRads, this);
      if (data.or.k[0].ti) {
        var i;
        var len = data.or.k.length;
        for (i = 0; i < len; i += 1) {
          data.or.k[i].to = null;
          data.or.k[i].ti = null;
        }
      }
      this.or = PropertyFactory.getProp(elem, data.or, 1, degToRads, this);
      // sh Indicates it needs to be capped between -180 and 180
      this.or.sh = true;
    } else {
      this.r = PropertyFactory.getProp(elem, data.r || { k: 0 }, 0, degToRads, this);
    }
    if (data.sk) {
      this.sk = PropertyFactory.getProp(elem, data.sk, 0, degToRads, this);
      this.sa = PropertyFactory.getProp(elem, data.sa, 0, degToRads, this);
    }
    this.a = PropertyFactory.getProp(elem, data.a || { k: [0, 0, 0] }, 1, 0, this);
    this.s = PropertyFactory.getProp(elem, data.s || { k: [100, 100, 100] }, 1, 0.01, this);
    // Opacity is not part of the transform properties, that's why it won't use this.dynamicProperties. That way transforms won't get updated if opacity changes.
    if (data.o) {
      this.o = PropertyFactory.getProp(elem, data.o, 0, 0.01, elem);
    } else {
      this.o = { _mdf: false, v: 1 };
    }
    this._isDirty = true;
    if (!this.dynamicProperties.length) {
      this.getValue(true);
    }
  }
```
</details>

### `getTransformProperty(elem: any, data: any, container: any): TransformProperty`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`container`** `any`

**Returns:** `TransformProperty`

<details><summary>Code</summary>

```typescript
function getTransformProperty(elem, data, container) {
    return new TransformProperty(elem, data, container);
  }
```
</details>

### `RepeaterModifier(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RepeaterModifier() {}
```
</details>

### `RoundCornersModifier(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RoundCornersModifier() {}
```
</details>

### `getFontProperties(fontData: any): { style: string; weight: any; }`

**Parameters:**

- **`fontData`** `any`

**Returns:** `{ style: string; weight: any; }`

**Calls:**

- `fontData.fStyle.split`
- `styles[i].toLowerCase`

<details><summary>Code</summary>

```typescript
function getFontProperties(fontData) {
  var styles = fontData.fStyle ? fontData.fStyle.split(' ') : [];

  var fWeight = 'normal'; var
    fStyle = 'normal';
  var len = styles.length;
  var styleName;
  for (var i = 0; i < len; i += 1) {
    styleName = styles[i].toLowerCase();
    switch (styleName) {
      case 'italic':
        fStyle = 'italic';
        break;
      case 'bold':
        fWeight = '700';
        break;
      case 'black':
        fWeight = '900';
        break;
      case 'medium':
        fWeight = '500';
        break;
      case 'regular':
      case 'normal':
        fWeight = '400';
        break;
      case 'light':
      case 'thin':
        fWeight = '200';
        break;
      default:
        break;
    }
  }

  return {
    style: fStyle,
    weight: fontData.fWeight || fWeight,
  };
}
```
</details>

### `trimFontOptions(font: any): string`

**Parameters:**

- **`font`** `any`

**Returns:** `string`

**Calls:**

- `font.split`
- `enabledFamilies.push`
- `enabledFamilies.join`

<details><summary>Code</summary>

```typescript
function trimFontOptions(font) {
    var familyArray = font.split(',');
    var i;
    var len = familyArray.length;
    var enabledFamilies = [];
    for (i = 0; i < len; i += 1) {
      if (familyArray[i] !== 'sans-serif' && familyArray[i] !== 'monospace') {
        enabledFamilies.push(familyArray[i]);
      }
    }
    return enabledFamilies.join(',');
  }
```
</details>

### `setUpNode(font: any, family: any): { node: any; w: any; parent: any; }`

**Parameters:**

- **`font`** `any`
- **`family`** `any`

**Returns:** `{ node: any; w: any; parent: any; }`

**Calls:**

- `createTag`
- `parentNode.setAttribute`
- `parentNode.appendChild`
- `document.body.appendChild`
- `trimFontOptions`

**Internal Comments:**
```
// Node is invisible to screen readers. (x4)
// Characters that vary significantly among different fonts (x4)
// Visible - so we can measure it - but not on the screen (x5)
// Large font size makes even subtle changes obvious (x5)
// Reset any font properties (x5)
// Remember width with no applied web font (x2)
```

<details><summary>Code</summary>

```typescript
function setUpNode(font, family) {
    var parentNode = createTag('span');
    // Node is invisible to screen readers.
    parentNode.setAttribute('aria-hidden', true);
    parentNode.style.fontFamily = family;
    var node = createTag('span');
    // Characters that vary significantly among different fonts
    node.innerText = 'giItT1WQy@!-/#';
    // Visible - so we can measure it - but not on the screen
    parentNode.style.position = 'absolute';
    parentNode.style.left = '-10000px';
    parentNode.style.top = '-10000px';
    // Large font size makes even subtle changes obvious
    parentNode.style.fontSize = '300px';
    // Reset any font properties
    parentNode.style.fontVariant = 'normal';
    parentNode.style.fontStyle = 'normal';
    parentNode.style.fontWeight = 'normal';
    parentNode.style.letterSpacing = '0';
    parentNode.appendChild(node);
    document.body.appendChild(parentNode);

    // Remember width with no applied web font
    var width = node.offsetWidth;
    node.style.fontFamily = trimFontOptions(font) + ', ' + family;
    return { node: node, w: width, parent: parentNode };
  }
```
</details>

### `checkLoadedFonts(): void`

**Returns:** `void`

**Calls:**

- `this.fonts[i].sansCase.parent.parentNode.removeChild`
- `this.fonts[i].monoCase.parent.parentNode.removeChild`
- `Date.now`
- `setTimeout`

<details><summary>Code</summary>

```typescript
function checkLoadedFonts() {
    var i;
    var len = this.fonts.length;
    var node;
    var w;
    var loadedCount = len;
    for (i = 0; i < len; i += 1) {
      if (this.fonts[i].loaded) {
        loadedCount -= 1;
      } else if (this.fonts[i].fOrigin === 'n' || this.fonts[i].origin === 0) {
        this.fonts[i].loaded = true;
      } else {
        node = this.fonts[i].monoCase.node;
        w = this.fonts[i].monoCase.w;
        if (node.offsetWidth !== w) {
          loadedCount -= 1;
          this.fonts[i].loaded = true;
        } else {
          node = this.fonts[i].sansCase.node;
          w = this.fonts[i].sansCase.w;
          if (node.offsetWidth !== w) {
            loadedCount -= 1;
            this.fonts[i].loaded = true;
          }
        }
        if (this.fonts[i].loaded) {
          this.fonts[i].sansCase.parent.parentNode.removeChild(this.fonts[i].sansCase.parent);
          this.fonts[i].monoCase.parent.parentNode.removeChild(this.fonts[i].monoCase.parent);
        }
      }
    }

    if (loadedCount !== 0 && Date.now() - this.initTime < maxWaitingTime) {
      setTimeout(this.checkLoadedFontsBinded, 20);
    } else {
      setTimeout(this.setIsLoadedBinded, 10);
    }
  }
```
</details>

### `createHelper(fontData: any, def: any): { measureText: (text: any) => any; }`

**Parameters:**

- **`fontData`** `any`
- **`def`** `any`

**Returns:** `{ measureText: (text: any) => any; }`

**Calls:**

- `getFontProperties`
- `createNS`
- `tHelper.setAttribute`
- `def.appendChild`
- `new OffscreenCanvas(500, 500).getContext`
- `helper.getComputedTextLength`
- `helper.measureText`

**Internal Comments:**
```
// tHelper.style.fontFamily = fontData.fFamily; (x4)
```

<details><summary>Code</summary>

```typescript
function createHelper(fontData, def) {
    var engine = (document.body && def) ? 'svg' : 'canvas';
    var helper;
    var fontProps = getFontProperties(fontData);
    if (engine === 'svg') {
      var tHelper = createNS('text');
      tHelper.style.fontSize = '100px';
      // tHelper.style.fontFamily = fontData.fFamily;
      tHelper.setAttribute('font-family', fontData.fFamily);
      tHelper.setAttribute('font-style', fontProps.style);
      tHelper.setAttribute('font-weight', fontProps.weight);
      tHelper.textContent = '1';
      if (fontData.fClass) {
        tHelper.style.fontFamily = 'inherit';
        tHelper.setAttribute('class', fontData.fClass);
      } else {
        tHelper.style.fontFamily = fontData.fFamily;
      }
      def.appendChild(tHelper);
      helper = tHelper;
    } else {
      var tCanvasHelper = new OffscreenCanvas(500, 500).getContext('2d');
      tCanvasHelper.font = fontProps.style + ' ' + fontProps.weight + ' 100px ' + fontData.fFamily;
      helper = tCanvasHelper;
    }
    function measure(text) {
      if (engine === 'svg') {
        helper.textContent = text;
        return helper.getComputedTextLength();
      }
      return helper.measureText(text).width;
    }
    return {
      measureText: measure,
    };
  }
```
</details>

### `measure(text: any): any`

**Parameters:**

- **`text`** `any`

**Returns:** `any`

**Calls:**

- `helper.getComputedTextLength`
- `helper.measureText`

<details><summary>Code</summary>

```typescript
function measure(text) {
      if (engine === 'svg') {
        helper.textContent = text;
        return helper.getComputedTextLength();
      }
      return helper.measureText(text).width;
    }
```
</details>

### `addFonts(fontData: any, defs: any): void`

**Parameters:**

- **`fontData`** `any`
- **`defs`** `any`

**Returns:** `void`

**Calls:**

- `fontData.list.forEach`
- `createHelper`
- `setUpNode`
- `document.querySelectorAll`
- `createTag`
- `s.setAttribute`
- `defs.appendChild`
- `loadedSelector[j].href.indexOf`
- `l.setAttribute`
- `document.body.appendChild`
- `sc.setAttribute`
- `this.fonts.push`
- `setTimeout`
- `this.checkLoadedFonts.bind`

**Internal Comments:**
```
// Font is already loaded (x6)
// On some cases even if the font is loaded, it won't load correctly when measuring text on canvas. (x3)
// Adding this timeout seems to fix it (x3)
```

<details><summary>Code</summary>

```typescript
function addFonts(fontData, defs) {
    if (!fontData) {
      this.isLoaded = true;
      return;
    }
    if (this.chars) {
      this.isLoaded = true;
      this.fonts = fontData.list;
      return;
    }
    if (!document.body) {
      this.isLoaded = true;
      fontData.list.forEach((data) => {
        data.helper = createHelper(data);
        data.cache = {};
      });
      this.fonts = fontData.list;
      return;
    }

    var fontArr = fontData.list;
    var i;
    var len = fontArr.length;
    var _pendingFonts = len;
    for (i = 0; i < len; i += 1) {
      var shouldLoadFont = true;
      var loadedSelector;
      var j;
      fontArr[i].loaded = false;
      fontArr[i].monoCase = setUpNode(fontArr[i].fFamily, 'monospace');
      fontArr[i].sansCase = setUpNode(fontArr[i].fFamily, 'sans-serif');
      if (!fontArr[i].fPath) {
        fontArr[i].loaded = true;
        _pendingFonts -= 1;
      } else if (fontArr[i].fOrigin === 'p' || fontArr[i].origin === 3) {
        loadedSelector = document.querySelectorAll('style[f-forigin="p"][f-family="' + fontArr[i].fFamily + '"], style[f-origin="3"][f-family="' + fontArr[i].fFamily + '"]');

        if (loadedSelector.length > 0) {
          shouldLoadFont = false;
        }

        if (shouldLoadFont) {
          var s = createTag('style');
          s.setAttribute('f-forigin', fontArr[i].fOrigin);
          s.setAttribute('f-origin', fontArr[i].origin);
          s.setAttribute('f-family', fontArr[i].fFamily);
          s.type = 'text/css';
          s.innerText = '@font-face {font-family: ' + fontArr[i].fFamily + "; font-style: normal; src: url('" + fontArr[i].fPath + "');}";
          defs.appendChild(s);
        }
      } else if (fontArr[i].fOrigin === 'g' || fontArr[i].origin === 1) {
        loadedSelector = document.querySelectorAll('link[f-forigin="g"], link[f-origin="1"]');

        for (j = 0; j < loadedSelector.length; j += 1) {
          if (loadedSelector[j].href.indexOf(fontArr[i].fPath) !== -1) {
            // Font is already loaded
            shouldLoadFont = false;
          }
        }

        if (shouldLoadFont) {
          var l = createTag('link');
          l.setAttribute('f-forigin', fontArr[i].fOrigin);
          l.setAttribute('f-origin', fontArr[i].origin);
          l.type = 'text/css';
          l.rel = 'stylesheet';
          l.href = fontArr[i].fPath;
          document.body.appendChild(l);
        }
      } else if (fontArr[i].fOrigin === 't' || fontArr[i].origin === 2) {
        loadedSelector = document.querySelectorAll('script[f-forigin="t"], script[f-origin="2"]');

        for (j = 0; j < loadedSelector.length; j += 1) {
          if (fontArr[i].fPath === loadedSelector[j].src) {
            // Font is already loaded
            shouldLoadFont = false;
          }
        }

        if (shouldLoadFont) {
          var sc = createTag('link');
          sc.setAttribute('f-forigin', fontArr[i].fOrigin);
          sc.setAttribute('f-origin', fontArr[i].origin);
          sc.setAttribute('rel', 'stylesheet');
          sc.setAttribute('href', fontArr[i].fPath);
          defs.appendChild(sc);
        }
      }
      fontArr[i].helper = createHelper(fontArr[i], defs);
      fontArr[i].cache = {};
      this.fonts.push(fontArr[i]);
    }
    if (_pendingFonts === 0) {
      this.isLoaded = true;
    } else {
      // On some cases even if the font is loaded, it won't load correctly when measuring text on canvas.
      // Adding this timeout seems to fix it
      setTimeout(this.checkLoadedFonts.bind(this), 100);
    }
  }
```
</details>

### `addChars(chars: any): void`

**Parameters:**

- **`chars`** `any`

**Returns:** `void`

**Calls:**

- `this.chars.push`

<details><summary>Code</summary>

```typescript
function addChars(chars) {
    if (!chars) {
      return;
    }
    if (!this.chars) {
      this.chars = [];
    }
    var i;
    var len = chars.length;
    var j;
    var jLen = this.chars.length;
    var found;
    for (i = 0; i < len; i += 1) {
      j = 0;
      found = false;
      while (j < jLen) {
        if (this.chars[j].style === chars[i].style && this.chars[j].fFamily === chars[i].fFamily && this.chars[j].ch === chars[i].ch) {
          found = true;
        }
        j += 1;
      }
      if (!found) {
        this.chars.push(chars[i]);
        jLen += 1;
      }
    }
  }
```
</details>

### `getCharData(char: any, style: any, font: any): any`

**Parameters:**

- **`char`** `any`
- **`style`** `any`
- **`font`** `any`

**Returns:** `any`

**Calls:**

- `char.charCodeAt`
- `console.warn`

<details><summary>Code</summary>

```typescript
function getCharData(char, style, font) {
    var i = 0;
    var len = this.chars.length;
    while (i < len) {
      if (this.chars[i].ch === char && this.chars[i].style === style && this.chars[i].fFamily === font) {
        return this.chars[i];
      }
      i += 1;
    }
    if (((typeof char === 'string' && char.charCodeAt(0) !== 13) || !char)
            && console
            && console.warn // eslint-disable-line no-console
            && !this._warned
    ) {
      this._warned = true;
      console.warn('Missing character from exported characters list: ', char, style, font); // eslint-disable-line no-console
    }
    return emptyChar;
  }
```
</details>

### `measureText(char: any, fontName: any, size: any): number`

**Parameters:**

- **`char`** `any`
- **`fontName`** `any`
- **`size`** `any`

**Returns:** `number`

**Calls:**

- `this.getFontByName`
- `char.charCodeAt`
- `tHelper.measureText`

<details><summary>Code</summary>

```typescript
function measureText(char, fontName, size) {
    var fontData = this.getFontByName(fontName);
    var index = char.charCodeAt(0);
    if (!fontData.cache[index + 1]) {
      var tHelper = fontData.helper;
      if (char === ' ') {
        var doubleSize = tHelper.measureText('|' + char + '|');
        var singleSize = tHelper.measureText('||');
        fontData.cache[index + 1] = (doubleSize - singleSize) / 100;
      } else {
        fontData.cache[index + 1] = tHelper.measureText(char) / 100;
      }
    }
    return fontData.cache[index + 1] * size;
  }
```
</details>

### `getFontByName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getFontByName(name) {
    var i = 0;
    var len = this.fonts.length;
    while (i < len) {
      if (this.fonts[i].fName === name) {
        return this.fonts[i];
      }
      i += 1;
    }
    return this.fonts[0];
  }
```
</details>

### `isModifier(firstCharCode: any, secondCharCode: any): boolean`

**Parameters:**

- **`firstCharCode`** `any`
- **`secondCharCode`** `any`

**Returns:** `boolean`

**Calls:**

- `firstCharCode.toString`
- `secondCharCode.toString`
- `surrogateModifiers.indexOf`

<details><summary>Code</summary>

```typescript
function isModifier(firstCharCode, secondCharCode) {
    var sum = firstCharCode.toString(16) + secondCharCode.toString(16);
    return surrogateModifiers.indexOf(sum) !== -1;
  }
```
</details>

### `isZeroWidthJoiner(firstCharCode: any, secondCharCode: any): boolean`

**Parameters:**

- **`firstCharCode`** `any`
- **`secondCharCode`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isZeroWidthJoiner(firstCharCode, secondCharCode) {
    if (!secondCharCode) {
      return firstCharCode === zeroWidthJoiner[1];
    }
    return firstCharCode === zeroWidthJoiner[0] && secondCharCode === zeroWidthJoiner[1];
  }
```
</details>

### `isCombinedCharacter(char: any): boolean`

**Parameters:**

- **`char`** `any`

**Returns:** `boolean`

**Calls:**

- `combinedCharacters.indexOf`

<details><summary>Code</summary>

```typescript
function isCombinedCharacter(char) {
    return combinedCharacters.indexOf(char) !== -1;
  }
```
</details>

### `setIsLoaded(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setIsLoaded() {
    this.isLoaded = true;
  }
```
</details>

### `Font(): void`

**Returns:** `void`

**Calls:**

- `Date.now`
- `this.setIsLoaded.bind`
- `this.checkLoadedFonts.bind`

<details><summary>Code</summary>

```typescript
function () {
    this.fonts = [];
    this.chars = null;
    this.typekitLoaded = 0;
    this.isLoaded = false;
    this._warned = false;
    this.initTime = Date.now();
    this.setIsLoadedBinded = this.setIsLoaded.bind(this);
    this.checkLoadedFontsBinded = this.checkLoadedFonts.bind(this);
  }
```
</details>

### `RenderableElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RenderableElement() {

}
```
</details>

### `initRenderable(): void`

**Returns:** `void`

**Internal Comments:**
```
// layer's visibility related to inpoint and outpoint. Rename isVisible to isInRange (x4)
// layer's display state (x4)
// If layer's transparency equals 0, it can be hidden (x4)
// list of animated components (x4)
```

<details><summary>Code</summary>

```typescript
function () {
    // layer's visibility related to inpoint and outpoint. Rename isVisible to isInRange
    this.isInRange = false;
    // layer's display state
    this.hidden = false;
    // If layer's transparency equals 0, it can be hidden
    this.isTransparent = false;
    // list of animated components
    this.renderableComponents = [];
  }
```
</details>

### `addRenderableComponent(component: any): void`

**Parameters:**

- **`component`** `any`

**Returns:** `void`

**Calls:**

- `this.renderableComponents.indexOf`
- `this.renderableComponents.push`

<details><summary>Code</summary>

```typescript
function (component) {
    if (this.renderableComponents.indexOf(component) === -1) {
      this.renderableComponents.push(component);
    }
  }
```
</details>

### `removeRenderableComponent(component: any): void`

**Parameters:**

- **`component`** `any`

**Returns:** `void`

**Calls:**

- `this.renderableComponents.indexOf`
- `this.renderableComponents.splice`

<details><summary>Code</summary>

```typescript
function (component) {
    if (this.renderableComponents.indexOf(component) !== -1) {
      this.renderableComponents.splice(this.renderableComponents.indexOf(component), 1);
    }
  }
```
</details>

### `prepareRenderableFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.checkLayerLimits`

<details><summary>Code</summary>

```typescript
function (num) {
    this.checkLayerLimits(num);
  }
```
</details>

### `checkTransparency(): void`

**Returns:** `void`

**Calls:**

- `this.hide`
- `this.show`

<details><summary>Code</summary>

```typescript
function () {
    if (this.finalTransform.mProp.o.v <= 0) {
      if (!this.isTransparent && this.globalData.renderConfig.hideOnTransparent) {
        this.isTransparent = true;
        this.hide();
      }
    } else if (this.isTransparent) {
      this.isTransparent = false;
      this.show();
    }
  }
```
</details>

### `checkLayerLimits(num: number): void`

**Parameters:**

- **`num`** `number`

**Returns:** `void`

**Calls:**

- `this.show`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (num) {
    if (this.data.ip - this.data.st <= num && this.data.op - this.data.st > num) {
      if (this.isInRange !== true) {
        this.globalData._mdf = true;
        this._mdf = true;
        this.isInRange = true;
        this.show();
      }
    } else if (this.isInRange !== false) {
      this.globalData._mdf = true;
      this.isInRange = false;
      this.hide();
    }
  }
```
</details>

### `renderRenderable(): void`

**Returns:** `void`

**Calls:**

- `this.renderableComponents[i].renderFrame`

<details><summary>Code</summary>

```typescript
function () {
    var i;
    var len = this.renderableComponents.length;
    for (i = 0; i < len; i += 1) {
      this.renderableComponents[i].renderFrame(this._isFirstFrame);
    }
    /* this.maskManager.renderFrame(this.finalTransform.mat);
        this.renderableEffectsManager.renderFrame(this._isFirstFrame); */
  }
```
</details>

### `sourceRectAtTime(): { top: number; left: number; width: number; height: number; }`

**Returns:** `{ top: number; left: number; width: number; height: number; }`

<details><summary>Code</summary>

```typescript
function () {
    return {
      top: 0,
      left: 0,
      width: 100,
      height: 100,
    };
  }
```
</details>

### `getLayerSize(): { w: any; h: any; }`

**Returns:** `{ w: any; h: any; }`

<details><summary>Code</summary>

```typescript
function () {
    if (this.data.ty === 5) {
      return { w: this.data.textData.width, h: this.data.textData.height };
    }
    return { w: this.data.width, h: this.data.height };
  }
```
</details>

### `initRenderable(): void`

**Returns:** `void`

**Internal Comments:**
```
// layer's visibility related to inpoint and outpoint. Rename isVisible to isInRange (x4)
// layer's display state (x4)
// If layer's transparency equals 0, it can be hidden (x4)
// list of animated components (x4)
```

<details><summary>Code</summary>

```typescript
function () {
    // layer's visibility related to inpoint and outpoint. Rename isVisible to isInRange
    this.isInRange = false;
    // layer's display state
    this.hidden = false;
    // If layer's transparency equals 0, it can be hidden
    this.isTransparent = false;
    // list of animated components
    this.renderableComponents = [];
  }
```
</details>

### `addRenderableComponent(component: any): void`

**Parameters:**

- **`component`** `any`

**Returns:** `void`

**Calls:**

- `this.renderableComponents.indexOf`
- `this.renderableComponents.push`

<details><summary>Code</summary>

```typescript
function (component) {
    if (this.renderableComponents.indexOf(component) === -1) {
      this.renderableComponents.push(component);
    }
  }
```
</details>

### `removeRenderableComponent(component: any): void`

**Parameters:**

- **`component`** `any`

**Returns:** `void`

**Calls:**

- `this.renderableComponents.indexOf`
- `this.renderableComponents.splice`

<details><summary>Code</summary>

```typescript
function (component) {
    if (this.renderableComponents.indexOf(component) !== -1) {
      this.renderableComponents.splice(this.renderableComponents.indexOf(component), 1);
    }
  }
```
</details>

### `prepareRenderableFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.checkLayerLimits`

<details><summary>Code</summary>

```typescript
function (num) {
    this.checkLayerLimits(num);
  }
```
</details>

### `checkTransparency(): void`

**Returns:** `void`

**Calls:**

- `this.hide`
- `this.show`

<details><summary>Code</summary>

```typescript
function () {
    if (this.finalTransform.mProp.o.v <= 0) {
      if (!this.isTransparent && this.globalData.renderConfig.hideOnTransparent) {
        this.isTransparent = true;
        this.hide();
      }
    } else if (this.isTransparent) {
      this.isTransparent = false;
      this.show();
    }
  }
```
</details>

### `checkLayerLimits(num: number): void`

**Parameters:**

- **`num`** `number`

**Returns:** `void`

**Calls:**

- `this.show`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (num) {
    if (this.data.ip - this.data.st <= num && this.data.op - this.data.st > num) {
      if (this.isInRange !== true) {
        this.globalData._mdf = true;
        this._mdf = true;
        this.isInRange = true;
        this.show();
      }
    } else if (this.isInRange !== false) {
      this.globalData._mdf = true;
      this.isInRange = false;
      this.hide();
    }
  }
```
</details>

### `renderRenderable(): void`

**Returns:** `void`

**Calls:**

- `this.renderableComponents[i].renderFrame`

<details><summary>Code</summary>

```typescript
function () {
    var i;
    var len = this.renderableComponents.length;
    for (i = 0; i < len; i += 1) {
      this.renderableComponents[i].renderFrame(this._isFirstFrame);
    }
    /* this.maskManager.renderFrame(this.finalTransform.mat);
        this.renderableEffectsManager.renderFrame(this._isFirstFrame); */
  }
```
</details>

### `sourceRectAtTime(): { top: number; left: number; width: number; height: number; }`

**Returns:** `{ top: number; left: number; width: number; height: number; }`

<details><summary>Code</summary>

```typescript
function () {
    return {
      top: 0,
      left: 0,
      width: 100,
      height: 100,
    };
  }
```
</details>

### `getLayerSize(): { w: any; h: any; }`

**Returns:** `{ w: any; h: any; }`

<details><summary>Code</summary>

```typescript
function () {
    if (this.data.ty === 5) {
      return { w: this.data.textData.width, h: this.data.textData.height };
    }
    return { w: this.data.width, h: this.data.height };
  }
```
</details>

### `MaskInterface(mask: any, data: any): void`

**Parameters:**

- **`mask`** `any`
- **`data`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function MaskInterface(mask, data) {
    this._mask = mask;
    this._data = data;
  }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `this._mask.prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.prop.k) {
        this._mask.prop.getValue();
      }
      return this._mask.prop;
    }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `this._mask.prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.prop.k) {
        this._mask.prop.getValue();
      }
      return this._mask.prop;
    }
```
</details>

### `get(): number`

**Returns:** `number`

**Calls:**

- `this._mask.op.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.op.k) {
        this._mask.op.getValue();
      }
      return this._mask.op.v * 100;
    }
```
</details>

### `get(): number`

**Returns:** `number`

**Calls:**

- `this._mask.op.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.op.k) {
        this._mask.op.getValue();
      }
      return this._mask.op.v * 100;
    }
```
</details>

### `MaskManager(maskManager: any): (name: any) => any`

**Parameters:**

- **`maskManager`** `any`

**Returns:** `(name: any) => any`

**Calls:**

- `createSizedArray`

<details><summary>Code</summary>

```typescript
function (maskManager) {
    var _masksInterfaces = createSizedArray(maskManager.viewData.length);
    var i;
    var len = maskManager.viewData.length;
    for (i = 0; i < len; i += 1) {
      _masksInterfaces[i] = new MaskInterface(maskManager.viewData[i], maskManager.masksProperties[i]);
    }

    var maskFunction = function (name) {
      i = 0;
      while (i < len) {
        if (maskManager.masksProperties[i].nm === name) {
          return _masksInterfaces[i];
        }
        i += 1;
      }
      return null;
    };
    return maskFunction;
  }
```
</details>

### `maskFunction(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (name) {
      i = 0;
      while (i < len) {
        if (maskManager.masksProperties[i].nm === name) {
          return _masksInterfaces[i];
        }
        i += 1;
      }
      return null;
    }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `this._mask.prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.prop.k) {
        this._mask.prop.getValue();
      }
      return this._mask.prop;
    }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `this._mask.prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.prop.k) {
        this._mask.prop.getValue();
      }
      return this._mask.prop;
    }
```
</details>

### `get(): number`

**Returns:** `number`

**Calls:**

- `this._mask.op.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.op.k) {
        this._mask.op.getValue();
      }
      return this._mask.op.v * 100;
    }
```
</details>

### `get(): number`

**Returns:** `number`

**Calls:**

- `this._mask.op.getValue`

<details><summary>Code</summary>

```typescript
function () {
      if (this._mask.op.k) {
        this._mask.op.getValue();
      }
      return this._mask.op.v * 100;
    }
```
</details>

### `completeProperty(expressionValue: any, property: any, type: any): void`

**Parameters:**

- **`expressionValue`** `any`
- **`property`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `Object.defineProperty`
- `property.getVelocityAtTime`
- `Object.assign`

<details><summary>Code</summary>

```typescript
function completeProperty(expressionValue, property, type) {
    Object.defineProperty(expressionValue, 'velocity', {
      get: function () {
        return property.getVelocityAtTime(property.comp.currentFrame);
      },
    });
    expressionValue.numKeys = property.keyframes ? property.keyframes.length : 0;
    expressionValue.key = function (pos) {
      if (!expressionValue.numKeys) {
        return 0;
      }
      var value = '';
      if ('s' in property.keyframes[pos - 1]) {
        value = property.keyframes[pos - 1].s;
      } else if ('e' in property.keyframes[pos - 2]) {
        value = property.keyframes[pos - 2].e;
      } else {
        value = property.keyframes[pos - 2].s;
      }
      var valueProp = type === 'unidimensional' ? new Number(value) : Object.assign({}, value); // eslint-disable-line no-new-wrappers
      valueProp.time = property.keyframes[pos - 1].t / property.elem.comp.globalData.frameRate;
      valueProp.value = type === 'unidimensional' ? value[0] : value;
      return valueProp;
    };
    expressionValue.valueAtTime = property.getValueAtTime;
    expressionValue.speedAtTime = property.getSpeedAtTime;
    expressionValue.velocityAtTime = property.getVelocityAtTime;
    expressionValue.propertyGroup = property.propertyGroup;
  }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `property.getVelocityAtTime`

<details><summary>Code</summary>

```typescript
function () {
        return property.getVelocityAtTime(property.comp.currentFrame);
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `property.getVelocityAtTime`

<details><summary>Code</summary>

```typescript
function () {
        return property.getVelocityAtTime(property.comp.currentFrame);
      }
```
</details>

### `UnidimensionalPropertyInterface(property: any): () => Number`

**Parameters:**

- **`property`** `any`

**Returns:** `() => Number`

**Calls:**

- `completeProperty`
- `property.getValue`

<details><summary>Code</summary>

```typescript
function UnidimensionalPropertyInterface(property) {
    if (!property || !('pv' in property)) {
      property = defaultUnidimensionalValue;
    }
    var mult = 1 / property.mult;
    var val = property.pv * mult;
    var expressionValue = new Number(val); // eslint-disable-line no-new-wrappers
    expressionValue.value = val;
    completeProperty(expressionValue, property, 'unidimensional');

    return function () {
      if (property.k) {
        property.getValue();
      }
      val = property.v * mult;
      if (expressionValue.value !== val) {
        expressionValue = new Number(val); // eslint-disable-line no-new-wrappers
        expressionValue.value = val;
        completeProperty(expressionValue, property, 'unidimensional');
      }
      return expressionValue;
    };
  }
```
</details>

### `MultidimensionalPropertyInterface(property: any): () => number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Parameters:**

- **`property`** `any`

**Returns:** `() => number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `createTypedArray`
- `completeProperty`
- `property.getValue`

<details><summary>Code</summary>

```typescript
function MultidimensionalPropertyInterface(property) {
    if (!property || !('pv' in property)) {
      property = defaultMultidimensionalValue;
    }
    var mult = 1 / property.mult;
    var len = (property.data && property.data.l) || property.pv.length;
    var expressionValue = createTypedArray('float32', len);
    var arrValue = createTypedArray('float32', len);
    expressionValue.value = arrValue;
    completeProperty(expressionValue, property, 'multidimensional');

    return function () {
      if (property.k) {
        property.getValue();
      }
      for (var i = 0; i < len; i += 1) {
        arrValue[i] = property.v[i] * mult;
        expressionValue[i] = arrValue[i];
      }
      return expressionValue;
    };
  }
```
</details>

### `defaultGetter(): { pv: number; v: number; mult: number; }`

**Returns:** `{ pv: number; v: number; mult: number; }`

<details><summary>Code</summary>

```typescript
function defaultGetter() {
    return defaultUnidimensionalValue;
  }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `property.getVelocityAtTime`

<details><summary>Code</summary>

```typescript
function () {
        return property.getVelocityAtTime(property.comp.currentFrame);
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `property.getVelocityAtTime`

<details><summary>Code</summary>

```typescript
function () {
        return property.getVelocityAtTime(property.comp.currentFrame);
      }
```
</details>

### `_thisFunction(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _thisFunction(name) {
      switch (name) {
        case 'scale':
        case 'Scale':
        case 'ADBE Scale':
        case 6:
          return _thisFunction.scale;
        case 'rotation':
        case 'Rotation':
        case 'ADBE Rotation':
        case 'ADBE Rotate Z':
        case 10:
          return _thisFunction.rotation;
        case 'ADBE Rotate X':
          return _thisFunction.xRotation;
        case 'ADBE Rotate Y':
          return _thisFunction.yRotation;
        case 'position':
        case 'Position':
        case 'ADBE Position':
        case 2:
          return _thisFunction.position;
        case 'ADBE Position_0':
          return _thisFunction.xPosition;
        case 'ADBE Position_1':
          return _thisFunction.yPosition;
        case 'ADBE Position_2':
          return _thisFunction.zPosition;
        case 'anchorPoint':
        case 'AnchorPoint':
        case 'Anchor Point':
        case 'ADBE AnchorPoint':
        case 1:
          return _thisFunction.anchorPoint;
        case 'opacity':
        case 'Opacity':
        case 11:
          return _thisFunction.opacity;
        default:
          return null;
      }
    }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `_transformFactory`
- `_px`
- `_py`
- `_pz`

<details><summary>Code</summary>

```typescript
function () {
        if (transform.p) {
          return _transformFactory();
        }
        return [
          _px(),
          _py(),
          _pz ? _pz() : 0];
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `_transformFactory`
- `_px`
- `_py`
- `_pz`

<details><summary>Code</summary>

```typescript
function () {
        if (transform.p) {
          return _transformFactory();
        }
        return [
          _px(),
          _py(),
          _pz ? _pz() : 0];
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `_transformFactory`
- `_px`
- `_py`
- `_pz`

<details><summary>Code</summary>

```typescript
function () {
        if (transform.p) {
          return _transformFactory();
        }
        return [
          _px(),
          _py(),
          _pz ? _pz() : 0];
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `_transformFactory`
- `_px`
- `_py`
- `_pz`

<details><summary>Code</summary>

```typescript
function () {
        if (transform.p) {
          return _transformFactory();
        }
        return [
          _px(),
          _py(),
          _pz ? _pz() : 0];
      }
```
</details>

### `getMatrix(time: any): (Anonymous function)`

**Parameters:**

- **`time`** `any`

**Returns:** `(Anonymous function)`

**Calls:**

- `this._elem.finalTransform.mProp.getValueAtTime`
- `propMatrix.clone`
- `transformMat.applyToMatrix`

<details><summary>Code</summary>

```typescript
function getMatrix(time) {
    var toWorldMat = new Matrix();
    if (time !== undefined) {
      var propMatrix = this._elem.finalTransform.mProp.getValueAtTime(time);
      propMatrix.clone(toWorldMat);
    } else {
      var transformMat = this._elem.finalTransform.mProp;
      transformMat.applyToMatrix(toWorldMat);
    }
    return toWorldMat;
  }
```
</details>

### `toWorldVec(arr: any, time: any): any`

**Parameters:**

- **`arr`** `any`
- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.getMatrix`
- `this.applyPoint`

<details><summary>Code</summary>

```typescript
function toWorldVec(arr, time) {
    var toWorldMat = this.getMatrix(time);
    toWorldMat.props[12] = 0;
    toWorldMat.props[13] = 0;
    toWorldMat.props[14] = 0;
    return this.applyPoint(toWorldMat, arr);
  }
```
</details>

### `toWorld(arr: any, time: any): any`

**Parameters:**

- **`arr`** `any`
- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.getMatrix`
- `this.applyPoint`

<details><summary>Code</summary>

```typescript
function toWorld(arr, time) {
    var toWorldMat = this.getMatrix(time);
    return this.applyPoint(toWorldMat, arr);
  }
```
</details>

### `fromWorldVec(arr: any, time: any): any`

**Parameters:**

- **`arr`** `any`
- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.getMatrix`
- `this.invertPoint`

<details><summary>Code</summary>

```typescript
function fromWorldVec(arr, time) {
    var toWorldMat = this.getMatrix(time);
    toWorldMat.props[12] = 0;
    toWorldMat.props[13] = 0;
    toWorldMat.props[14] = 0;
    return this.invertPoint(toWorldMat, arr);
  }
```
</details>

### `fromWorld(arr: any, time: any): any`

**Parameters:**

- **`arr`** `any`
- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.getMatrix`
- `this.invertPoint`

<details><summary>Code</summary>

```typescript
function fromWorld(arr, time) {
    var toWorldMat = this.getMatrix(time);
    return this.invertPoint(toWorldMat, arr);
  }
```
</details>

### `applyPoint(matrix: any, arr: any): any`

**Parameters:**

- **`matrix`** `any`
- **`arr`** `any`

**Returns:** `any`

**Calls:**

- `this._elem.hierarchy[i].finalTransform.mProp.applyToMatrix`
- `matrix.applyToPointArray`

<details><summary>Code</summary>

```typescript
function applyPoint(matrix, arr) {
    if (this._elem.hierarchy && this._elem.hierarchy.length) {
      var i;
      var len = this._elem.hierarchy.length;
      for (i = 0; i < len; i += 1) {
        this._elem.hierarchy[i].finalTransform.mProp.applyToMatrix(matrix);
      }
    }
    return matrix.applyToPointArray(arr[0], arr[1], arr[2] || 0);
  }
```
</details>

### `invertPoint(matrix: any, arr: any): any`

**Parameters:**

- **`matrix`** `any`
- **`arr`** `any`

**Returns:** `any`

**Calls:**

- `this._elem.hierarchy[i].finalTransform.mProp.applyToMatrix`
- `matrix.inversePoint`

<details><summary>Code</summary>

```typescript
function invertPoint(matrix, arr) {
    if (this._elem.hierarchy && this._elem.hierarchy.length) {
      var i;
      var len = this._elem.hierarchy.length;
      for (i = 0; i < len; i += 1) {
        this._elem.hierarchy[i].finalTransform.mProp.applyToMatrix(matrix);
      }
    }
    return matrix.inversePoint(arr);
  }
```
</details>

### `fromComp(arr: any): any`

**Parameters:**

- **`arr`** `any`

**Returns:** `any`

**Calls:**

- `toWorldMat.reset`
- `this._elem.finalTransform.mProp.applyToMatrix`
- `this._elem.hierarchy[i].finalTransform.mProp.applyToMatrix`
- `toWorldMat.inversePoint`

<details><summary>Code</summary>

```typescript
function fromComp(arr) {
    var toWorldMat = new Matrix();
    toWorldMat.reset();
    this._elem.finalTransform.mProp.applyToMatrix(toWorldMat);
    if (this._elem.hierarchy && this._elem.hierarchy.length) {
      var i;
      var len = this._elem.hierarchy.length;
      for (i = 0; i < len; i += 1) {
        this._elem.hierarchy[i].finalTransform.mProp.applyToMatrix(toWorldMat);
      }
      return toWorldMat.inversePoint(arr);
    }
    return toWorldMat.inversePoint(arr);
  }
```
</details>

### `sampleImage(): number[]`

**Returns:** `number[]`

<details><summary>Code</summary>

```typescript
function sampleImage() {
    return [1, 1, 1, 1];
  }
```
</details>

### `_registerMaskInterface(maskManager: any): void`

**Parameters:**

- **`maskManager`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function _registerMaskInterface(maskManager) {
      _thisLayerFunction.mask = new MaskManagerInterface(maskManager, elem);
    }
```
</details>

### `_registerEffectsInterface(effects: any): void`

**Parameters:**

- **`effects`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function _registerEffectsInterface(effects) {
      _thisLayerFunction.effect = effects;
    }
```
</details>

### `_thisLayerFunction(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _thisLayerFunction(name) {
      switch (name) {
        case 'ADBE Root Vectors Group':
        case 'Contents':
        case 2:
          return _thisLayerFunction.shapeInterface;
        case 1:
        case 6:
        case 'Transform':
        case 'transform':
        case 'ADBE Transform Group':
          return transformInterface;
        case 4:
        case 'ADBE Effect Parade':
        case 'effects':
        case 'Effects':
          return _thisLayerFunction.effect;
        case 'ADBE Text Properties':
          return _thisLayerFunction.textInterface;
        default:
          return null;
      }
    }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.hierarchy[0].layerInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return transformInterface;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return elem.isInRange;
        }
```
</details>

### `_propertyGroup(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

**Calls:**

- `propertyGroup`

<details><summary>Code</summary>

```typescript
function _propertyGroup(val) {
      val = val === undefined ? 1 : val;
      if (val <= 0) {
        return interfaceFunction;
      }
      return propertyGroup(val - 1);
    }
```
</details>

### `createEffectsInterface(elem: any, propertyGroup: any): { (name: any): any; readonly numProperties: any; }`

**Parameters:**

- **`elem`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (name: any): any; readonly numProperties: any; }`

**Calls:**

- `effectElements.push`
- `createGroupInterface`
- `Object.defineProperty`

<details><summary>Code</summary>

```typescript
function createEffectsInterface(elem, propertyGroup) {
    if (elem.effectsManager) {
      var effectElements = [];
      var effectsData = elem.data.ef;
      var i;
      var len = elem.effectsManager.effectElements.length;
      for (i = 0; i < len; i += 1) {
        effectElements.push(createGroupInterface(effectsData[i], elem.effectsManager.effectElements[i], propertyGroup, elem));
      }

      var effects = elem.data.ef || [];
      var groupInterface = function (name) {
        i = 0;
        len = effects.length;
        while (i < len) {
          if (name === effects[i].nm || name === effects[i].mn || name === effects[i].ix) {
            return effectElements[i];
          }
          i += 1;
        }
        return null;
      };
      Object.defineProperty(groupInterface, 'numProperties', {
        get: function () {
          return effects.length;
        },
      });
      return groupInterface;
    }
    return null;
  }
```
</details>

### `groupInterface(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (name) {
        i = 0;
        len = effects.length;
        while (i < len) {
          if (name === effects[i].nm || name === effects[i].mn || name === effects[i].ix) {
            return effectElements[i];
          }
          i += 1;
        }
        return null;
      }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return effects.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return effects.length;
        }
```
</details>

### `createGroupInterface(data: any, elements: any, propertyGroup: any, elem: any): { (name: any): any; readonly color: any; enabled: boolean; active: boolean; }`

**Parameters:**

- **`data`** `any`
- **`elements`** `any`
- **`propertyGroup`** `any`
- **`elem`** `any`

**Returns:** `{ (name: any): any; readonly color: any; enabled: boolean; active: boolean; }`

**Calls:**

- `complex_call_211188`
- `propertyGroupFactory`
- `effectElements.push`
- `createGroupInterface`
- `createValueInterface`
- `Object.defineProperty`
- `complex_call_211919`
- `Object.defineProperties`

<details><summary>Code</summary>

```typescript
function createGroupInterface(data, elements, propertyGroup, elem) {
    function groupInterface(name) {
      var effects = data.ef;
      var i = 0;
      var len = effects.length;
      while (i < len) {
        if (name === effects[i].nm || name === effects[i].mn || name === effects[i].ix) {
          if (effects[i].ty === 5) {
            return effectElements[i];
          }
          return effectElements[i]();
        }
        i += 1;
      }
      throw new Error();
    }
    var _propertyGroup = propertyGroupFactory(groupInterface, propertyGroup);

    var effectElements = [];
    var i;
    var len = data.ef.length;
    for (i = 0; i < len; i += 1) {
      if (data.ef[i].ty === 5) {
        effectElements.push(createGroupInterface(data.ef[i], elements.effectElements[i], elements.effectElements[i].propertyGroup, elem));
      } else {
        effectElements.push(createValueInterface(elements.effectElements[i], data.ef[i].ty, elem, _propertyGroup));
      }
    }

    if (data.mn === 'ADBE Color Control') {
      Object.defineProperty(groupInterface, 'color', {
        get: function () {
          return effectElements[0]();
        },
      });
    }
    Object.defineProperties(groupInterface, {
      numProperties: {
        get: function () {
          return data.np;
        },
      },
      _name: { value: data.nm },
      propertyGroup: { value: _propertyGroup },
    });
    groupInterface.enabled = data.en !== 0;
    groupInterface.active = groupInterface.enabled;
    return groupInterface;
  }
```
</details>

### `groupInterface(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_211188`

<details><summary>Code</summary>

```typescript
function groupInterface(name) {
      var effects = data.ef;
      var i = 0;
      var len = effects.length;
      while (i < len) {
        if (name === effects[i].nm || name === effects[i].mn || name === effects[i].ix) {
          if (effects[i].ty === 5) {
            return effectElements[i];
          }
          return effectElements[i]();
        }
        i += 1;
      }
      throw new Error();
    }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `complex_call_211919`

<details><summary>Code</summary>

```typescript
function () {
          return effectElements[0]();
        }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `complex_call_211919`

<details><summary>Code</summary>

```typescript
function () {
          return effectElements[0]();
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `createValueInterface(element: any, type: any, elem: any, propertyGroup: any): () => any`

**Parameters:**

- **`element`** `any`
- **`type`** `any`
- **`elem`** `any`
- **`propertyGroup`** `any`

**Returns:** `() => any`

**Calls:**

- `ExpressionPropertyInterface`
- `elem.comp.compInterface`
- `expressionProperty`
- `element.p.setGroupProperty`
- `PropertyInterface`

<details><summary>Code</summary>

```typescript
function createValueInterface(element, type, elem, propertyGroup) {
    var expressionProperty = ExpressionPropertyInterface(element.p);
    function interfaceFunction() {
      if (type === 10) {
        return elem.comp.compInterface(element.p.v);
      }
      return expressionProperty();
    }

    if (element.p.setGroupProperty) {
      element.p.setGroupProperty(PropertyInterface('', propertyGroup));
    }

    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(): any`

**Returns:** `any`

**Calls:**

- `elem.comp.compInterface`
- `expressionProperty`

<details><summary>Code</summary>

```typescript
function interfaceFunction() {
      if (type === 10) {
        return elem.comp.compInterface(element.p.v);
      }
      return expressionProperty();
    }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return effects.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return effects.length;
        }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `complex_call_211919`

<details><summary>Code</summary>

```typescript
function () {
          return effectElements[0]();
        }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `complex_call_211919`

<details><summary>Code</summary>

```typescript
function () {
          return effectElements[0]();
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
          return data.np;
        }
```
</details>

### `_thisLayerFunction(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _thisLayerFunction(name) {
      var i = 0;
      var len = comp.layers.length;
      while (i < len) {
        if (comp.layers[i].nm === name || comp.layers[i].ind === name) {
          return comp.elements[i].layerInterface;
        }
        i += 1;
      }
      return null;
      // return {active:false};
    }
```
</details>

### `interfaceFunction(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(val) {
        if (val === 'Shape' || val === 'shape' || val === 'Path' || val === 'path' || val === 'ADBE Vector Shape' || val === 2) {
          return interfaceFunction.path;
        }
        return null;
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `prop.getValue`

<details><summary>Code</summary>

```typescript
function () {
            if (prop.k) {
              prop.getValue();
            }
            return prop;
          }
```
</details>

### `iterateElements(shapes: any, view: any, propertyGroup: any): ((val: any) => any)[]`

**Parameters:**

- **`shapes`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `((val: any) => any)[]`

**Calls:**

- `arr.push`
- `groupInterfaceFactory`
- `fillInterfaceFactory`
- `strokeInterfaceFactory`
- `trimInterfaceFactory`
- `ellipseInterfaceFactory`
- `starInterfaceFactory`
- `ShapePathInterface`
- `rectInterfaceFactory`
- `roundedInterfaceFactory`
- `repeaterInterfaceFactory`
- `gradientFillInterfaceFactory`
- `defaultInterfaceFactory`

<details><summary>Code</summary>

```typescript
function iterateElements(shapes, view, propertyGroup) {
    var arr = [];
    var i;
    var len = shapes ? shapes.length : 0;
    for (i = 0; i < len; i += 1) {
      if (shapes[i].ty === 'gr') {
        arr.push(groupInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'fl') {
        arr.push(fillInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'st') {
        arr.push(strokeInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'tm') {
        arr.push(trimInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'tr') {
        // arr.push(transformInterfaceFactory(shapes[i],view[i],propertyGroup));
      } else if (shapes[i].ty === 'el') {
        arr.push(ellipseInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'sr') {
        arr.push(starInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'sh') {
        arr.push(ShapePathInterface(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'rc') {
        arr.push(rectInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'rd') {
        arr.push(roundedInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'rp') {
        arr.push(repeaterInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else if (shapes[i].ty === 'gf') {
        arr.push(gradientFillInterfaceFactory(shapes[i], view[i], propertyGroup));
      } else {
        arr.push(defaultInterfaceFactory(shapes[i], view[i], propertyGroup));
      }
    }
    return arr;
  }
```
</details>

### `contentsInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): any; propertyGroup: (val: any) => any; numProperties: number; transform: { (value: any): any; ty: string; mn: any; propertyGroup: any; }; propertyIndex: any; _name: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): any; propertyGroup: (val: any) => any; numProperties: number; transform: { (value: any): any; ty: string; mn: any; propertyGroup: any; }; propertyIndex: any; _name: any; }`

**Calls:**

- `propertyGroupFactory`
- `iterateElements`
- `transformInterfaceFactory`

<details><summary>Code</summary>

```typescript
function contentsInterfaceFactory(shape, view, propertyGroup) {
    var interfaces;
    var interfaceFunction = function _interfaceFunction(value) {
      var i = 0;
      var len = interfaces.length;
      while (i < len) {
        if (interfaces[i]._name === value || interfaces[i].mn === value || interfaces[i].propertyIndex === value || interfaces[i].ix === value || interfaces[i].ind === value) {
          return interfaces[i];
        }
        i += 1;
      }
      if (typeof value === 'number') {
        return interfaces[value - 1];
      }
      return null;
    };

    interfaceFunction.propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    interfaces = iterateElements(shape.it, view.it, interfaceFunction.propertyGroup);
    interfaceFunction.numProperties = interfaces.length;
    var transformInterface = transformInterfaceFactory(shape.it[shape.it.length - 1], view.it[view.it.length - 1], interfaceFunction.propertyGroup);
    interfaceFunction.transform = transformInterface;
    interfaceFunction.propertyIndex = shape.cix;
    interfaceFunction._name = shape.nm;

    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _interfaceFunction(value) {
      var i = 0;
      var len = interfaces.length;
      while (i < len) {
        if (interfaces[i]._name === value || interfaces[i].mn === value || interfaces[i].propertyIndex === value || interfaces[i].ix === value || interfaces[i].ind === value) {
          return interfaces[i];
        }
        i += 1;
      }
      if (typeof value === 'number') {
        return interfaces[value - 1];
      }
      return null;
    }
```
</details>

### `groupInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): { (value: any): any; propertyGroup: (val: any) => any; numProperties: number; transform: { (value: any): any; ty: string; mn: any; propertyGroup: any; }; propertyIndex: any; _name: any; } | { ...; }; ... 7 more ...; mn: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): { (value: any): any; propertyGroup: (val: any) => any; numProperties: number; transform: { (value: any): any; ty: string; mn: any; propertyGroup: any; }; propertyIndex: any; _name: any; } | { ...; }; ... 7 more ...; mn: any; }`

**Calls:**

- `propertyGroupFactory`
- `contentsInterfaceFactory`
- `transformInterfaceFactory`
- `Object.defineProperty`

**Internal Comments:**
```
// Not necessary for now. Keeping them here in case a new case appears
// case 'ADBE Vector Transform Group':
// case 3:
// interfaceFunction.content = interfaceFunction; (x4)
```

<details><summary>Code</summary>

```typescript
function groupInterfaceFactory(shape, view, propertyGroup) {
    var interfaceFunction = function _interfaceFunction(value) {
      switch (value) {
        case 'ADBE Vectors Group':
        case 'Contents':
        case 2:
          return interfaceFunction.content;
          // Not necessary for now. Keeping them here in case a new case appears
          // case 'ADBE Vector Transform Group':
          // case 3:
        default:
          return interfaceFunction.transform;
      }
    };
    interfaceFunction.propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    var content = contentsInterfaceFactory(shape, view, interfaceFunction.propertyGroup);
    var transformInterface = transformInterfaceFactory(shape.it[shape.it.length - 1], view.it[view.it.length - 1], interfaceFunction.propertyGroup);
    interfaceFunction.content = content;
    interfaceFunction.transform = transformInterface;
    Object.defineProperty(interfaceFunction, '_name', {
      get: function () {
        return shape.nm;
      },
    });
    // interfaceFunction.content = interfaceFunction;
    interfaceFunction.numProperties = shape.np;
    interfaceFunction.propertyIndex = shape.ix;
    interfaceFunction.nm = shape.nm;
    interfaceFunction.mn = shape.mn;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): { (value: any): any; propertyGroup: (val: any) => any; numProperties: number; transform: { (value: any): any; ty: string; mn: any; propertyGroup: any; }; propertyIndex: any; _name: any; } | { (value: any): any; ty: string; mn: any; propertyGroup: any; }`

**Parameters:**

- **`value`** `any`

**Returns:** `{ (value: any): any; propertyGroup: (val: any) => any; numProperties: number; transform: { (value: any): any; ty: string; mn: any; propertyGroup: any; }; propertyIndex: any; _name: any; } | { (value: any): any; ty: string; mn: any; propertyGroup: any; }`

**Internal Comments:**
```
// Not necessary for now. Keeping them here in case a new case appears
// case 'ADBE Vector Transform Group':
// case 3:
```

<details><summary>Code</summary>

```typescript
function _interfaceFunction(value) {
      switch (value) {
        case 'ADBE Vectors Group':
        case 'Contents':
        case 2:
          return interfaceFunction.content;
          // Not necessary for now. Keeping them here in case a new case appears
          // case 'ADBE Vector Transform Group':
          // case 3:
        default:
          return interfaceFunction.transform;
      }
    }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return shape.nm;
      }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return shape.nm;
      }
```
</details>

### `fillInterfaceFactory(shape: any, view: any, propertyGroup: any): (val: any) => any`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `(val: any) => any`

**Calls:**

- `Object.defineProperties`
- `ExpressionPropertyInterface`
- `view.c.setGroupProperty`
- `PropertyInterface`
- `view.o.setGroupProperty`

<details><summary>Code</summary>

```typescript
function fillInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(val) {
      if (val === 'Color' || val === 'color') {
        return interfaceFunction.color;
      } if (val === 'Opacity' || val === 'opacity') {
        return interfaceFunction.opacity;
      }
      return null;
    }
    Object.defineProperties(interfaceFunction, {
      color: {
        get: ExpressionPropertyInterface(view.c),
      },
      opacity: {
        get: ExpressionPropertyInterface(view.o),
      },
      _name: { value: shape.nm },
      mn: { value: shape.mn },
    });

    view.c.setGroupProperty(PropertyInterface('Color', propertyGroup));
    view.o.setGroupProperty(PropertyInterface('Opacity', propertyGroup));
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(val) {
      if (val === 'Color' || val === 'color') {
        return interfaceFunction.color;
      } if (val === 'Opacity' || val === 'opacity') {
        return interfaceFunction.opacity;
      }
      return null;
    }
```
</details>

### `gradientFillInterfaceFactory(shape: any, view: any, propertyGroup: any): (val: any) => any`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `(val: any) => any`

**Calls:**

- `Object.defineProperties`
- `ExpressionPropertyInterface`
- `view.s.setGroupProperty`
- `PropertyInterface`
- `view.e.setGroupProperty`
- `view.o.setGroupProperty`

<details><summary>Code</summary>

```typescript
function gradientFillInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(val) {
      if (val === 'Start Point' || val === 'start point') {
        return interfaceFunction.startPoint;
      }
      if (val === 'End Point' || val === 'end point') {
        return interfaceFunction.endPoint;
      }
      if (val === 'Opacity' || val === 'opacity') {
        return interfaceFunction.opacity;
      }
      return null;
    }
    Object.defineProperties(interfaceFunction, {
      startPoint: {
        get: ExpressionPropertyInterface(view.s),
      },
      endPoint: {
        get: ExpressionPropertyInterface(view.e),
      },
      opacity: {
        get: ExpressionPropertyInterface(view.o),
      },
      type: {
        get: function () {
          return 'a';
        },
      },
      _name: { value: shape.nm },
      mn: { value: shape.mn },
    });

    view.s.setGroupProperty(PropertyInterface('Start Point', propertyGroup));
    view.e.setGroupProperty(PropertyInterface('End Point', propertyGroup));
    view.o.setGroupProperty(PropertyInterface('Opacity', propertyGroup));
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(val) {
      if (val === 'Start Point' || val === 'start point') {
        return interfaceFunction.startPoint;
      }
      if (val === 'End Point' || val === 'end point') {
        return interfaceFunction.endPoint;
      }
      if (val === 'Opacity' || val === 'opacity') {
        return interfaceFunction.opacity;
      }
      return null;
    }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `defaultInterfaceFactory(): () => any`

**Returns:** `() => any`

<details><summary>Code</summary>

```typescript
function defaultInterfaceFactory() {
    function interfaceFunction() {
      return null;
    }
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction() {
      return null;
    }
```
</details>

### `strokeInterfaceFactory(shape: any, view: any, propertyGroup: any): (val: any) => any`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `(val: any) => any`

**Calls:**

- `propertyGroupFactory`
- `Object.defineProperty`
- `ExpressionPropertyInterface`
- `addPropertyToDashOb`
- `view.d.dataProps[i].p.setGroupProperty`
- `Object.defineProperties`
- `view.c.setGroupProperty`
- `PropertyInterface`
- `view.o.setGroupProperty`
- `view.w.setGroupProperty`

<details><summary>Code</summary>

```typescript
function strokeInterfaceFactory(shape, view, propertyGroup) {
    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    var _dashPropertyGroup = propertyGroupFactory(dashOb, _propertyGroup);
    function addPropertyToDashOb(i) {
      Object.defineProperty(dashOb, shape.d[i].nm, {
        get: ExpressionPropertyInterface(view.d.dataProps[i].p),
      });
    }
    var i;
    var len = shape.d ? shape.d.length : 0;
    var dashOb = {};
    for (i = 0; i < len; i += 1) {
      addPropertyToDashOb(i);
      view.d.dataProps[i].p.setGroupProperty(_dashPropertyGroup);
    }

    function interfaceFunction(val) {
      if (val === 'Color' || val === 'color') {
        return interfaceFunction.color;
      } if (val === 'Opacity' || val === 'opacity') {
        return interfaceFunction.opacity;
      } if (val === 'Stroke Width' || val === 'stroke width') {
        return interfaceFunction.strokeWidth;
      }
      return null;
    }
    Object.defineProperties(interfaceFunction, {
      color: {
        get: ExpressionPropertyInterface(view.c),
      },
      opacity: {
        get: ExpressionPropertyInterface(view.o),
      },
      strokeWidth: {
        get: ExpressionPropertyInterface(view.w),
      },
      dash: {
        get: function () {
          return dashOb;
        },
      },
      _name: { value: shape.nm },
      mn: { value: shape.mn },
    });

    view.c.setGroupProperty(PropertyInterface('Color', _propertyGroup));
    view.o.setGroupProperty(PropertyInterface('Opacity', _propertyGroup));
    view.w.setGroupProperty(PropertyInterface('Stroke Width', _propertyGroup));
    return interfaceFunction;
  }
```
</details>

### `addPropertyToDashOb(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `Object.defineProperty`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function addPropertyToDashOb(i) {
      Object.defineProperty(dashOb, shape.d[i].nm, {
        get: ExpressionPropertyInterface(view.d.dataProps[i].p),
      });
    }
```
</details>

### `interfaceFunction(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(val) {
      if (val === 'Color' || val === 'color') {
        return interfaceFunction.color;
      } if (val === 'Opacity' || val === 'opacity') {
        return interfaceFunction.opacity;
      } if (val === 'Stroke Width' || val === 'stroke width') {
        return interfaceFunction.strokeWidth;
      }
      return null;
    }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `trimInterfaceFactory(shape: any, view: any, propertyGroup: any): { (val: any): any; propertyIndex: any; propertyGroup: any; mn: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (val: any): any; propertyIndex: any; propertyGroup: any; mn: any; }`

**Calls:**

- `propertyGroupFactory`
- `view.s.setGroupProperty`
- `PropertyInterface`
- `view.e.setGroupProperty`
- `view.o.setGroupProperty`
- `Object.defineProperties`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function trimInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(val) {
      if (val === shape.e.ix || val === 'End' || val === 'end') {
        return interfaceFunction.end;
      }
      if (val === shape.s.ix) {
        return interfaceFunction.start;
      }
      if (val === shape.o.ix) {
        return interfaceFunction.offset;
      }
      return null;
    }

    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    interfaceFunction.propertyIndex = shape.ix;

    view.s.setGroupProperty(PropertyInterface('Start', _propertyGroup));
    view.e.setGroupProperty(PropertyInterface('End', _propertyGroup));
    view.o.setGroupProperty(PropertyInterface('Offset', _propertyGroup));
    interfaceFunction.propertyIndex = shape.ix;
    interfaceFunction.propertyGroup = propertyGroup;

    Object.defineProperties(interfaceFunction, {
      start: {
        get: ExpressionPropertyInterface(view.s),
      },
      end: {
        get: ExpressionPropertyInterface(view.e),
      },
      offset: {
        get: ExpressionPropertyInterface(view.o),
      },
      _name: { value: shape.nm },
    });
    interfaceFunction.mn = shape.mn;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(val) {
      if (val === shape.e.ix || val === 'End' || val === 'end') {
        return interfaceFunction.end;
      }
      if (val === shape.s.ix) {
        return interfaceFunction.start;
      }
      if (val === shape.o.ix) {
        return interfaceFunction.offset;
      }
      return null;
    }
```
</details>

### `transformInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): any; ty: string; mn: any; propertyGroup: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): any; ty: string; mn: any; propertyGroup: any; }`

**Calls:**

- `propertyGroupFactory`
- `view.transform.mProps.o.setGroupProperty`
- `PropertyInterface`
- `view.transform.mProps.p.setGroupProperty`
- `view.transform.mProps.a.setGroupProperty`
- `view.transform.mProps.s.setGroupProperty`
- `view.transform.mProps.r.setGroupProperty`
- `view.transform.mProps.sk.setGroupProperty`
- `view.transform.mProps.sa.setGroupProperty`
- `view.transform.op.setGroupProperty`
- `Object.defineProperties`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function transformInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(value) {
      if (shape.a.ix === value || value === 'Anchor Point') {
        return interfaceFunction.anchorPoint;
      }
      if (shape.o.ix === value || value === 'Opacity') {
        return interfaceFunction.opacity;
      }
      if (shape.p.ix === value || value === 'Position') {
        return interfaceFunction.position;
      }
      if (shape.r.ix === value || value === 'Rotation' || value === 'ADBE Vector Rotation') {
        return interfaceFunction.rotation;
      }
      if (shape.s.ix === value || value === 'Scale') {
        return interfaceFunction.scale;
      }
      if ((shape.sk && shape.sk.ix === value) || value === 'Skew') {
        return interfaceFunction.skew;
      }
      if ((shape.sa && shape.sa.ix === value) || value === 'Skew Axis') {
        return interfaceFunction.skewAxis;
      }
      return null;
    }
    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    view.transform.mProps.o.setGroupProperty(PropertyInterface('Opacity', _propertyGroup));
    view.transform.mProps.p.setGroupProperty(PropertyInterface('Position', _propertyGroup));
    view.transform.mProps.a.setGroupProperty(PropertyInterface('Anchor Point', _propertyGroup));
    view.transform.mProps.s.setGroupProperty(PropertyInterface('Scale', _propertyGroup));
    view.transform.mProps.r.setGroupProperty(PropertyInterface('Rotation', _propertyGroup));
    if (view.transform.mProps.sk) {
      view.transform.mProps.sk.setGroupProperty(PropertyInterface('Skew', _propertyGroup));
      view.transform.mProps.sa.setGroupProperty(PropertyInterface('Skew Angle', _propertyGroup));
    }
    view.transform.op.setGroupProperty(PropertyInterface('Opacity', _propertyGroup));
    Object.defineProperties(interfaceFunction, {
      opacity: {
        get: ExpressionPropertyInterface(view.transform.mProps.o),
      },
      position: {
        get: ExpressionPropertyInterface(view.transform.mProps.p),
      },
      anchorPoint: {
        get: ExpressionPropertyInterface(view.transform.mProps.a),
      },
      scale: {
        get: ExpressionPropertyInterface(view.transform.mProps.s),
      },
      rotation: {
        get: ExpressionPropertyInterface(view.transform.mProps.r),
      },
      skew: {
        get: ExpressionPropertyInterface(view.transform.mProps.sk),
      },
      skewAxis: {
        get: ExpressionPropertyInterface(view.transform.mProps.sa),
      },
      _name: { value: shape.nm },
    });
    interfaceFunction.ty = 'tr';
    interfaceFunction.mn = shape.mn;
    interfaceFunction.propertyGroup = propertyGroup;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(value) {
      if (shape.a.ix === value || value === 'Anchor Point') {
        return interfaceFunction.anchorPoint;
      }
      if (shape.o.ix === value || value === 'Opacity') {
        return interfaceFunction.opacity;
      }
      if (shape.p.ix === value || value === 'Position') {
        return interfaceFunction.position;
      }
      if (shape.r.ix === value || value === 'Rotation' || value === 'ADBE Vector Rotation') {
        return interfaceFunction.rotation;
      }
      if (shape.s.ix === value || value === 'Scale') {
        return interfaceFunction.scale;
      }
      if ((shape.sk && shape.sk.ix === value) || value === 'Skew') {
        return interfaceFunction.skew;
      }
      if ((shape.sa && shape.sa.ix === value) || value === 'Skew Axis') {
        return interfaceFunction.skewAxis;
      }
      return null;
    }
```
</details>

### `ellipseInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): any; propertyIndex: any; mn: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): any; propertyIndex: any; mn: any; }`

**Calls:**

- `propertyGroupFactory`
- `prop.s.setGroupProperty`
- `PropertyInterface`
- `prop.p.setGroupProperty`
- `Object.defineProperties`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function ellipseInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(value) {
      if (shape.p.ix === value) {
        return interfaceFunction.position;
      }
      if (shape.s.ix === value) {
        return interfaceFunction.size;
      }
      return null;
    }
    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    interfaceFunction.propertyIndex = shape.ix;
    var prop = view.sh.ty === 'tm' ? view.sh.prop : view.sh;
    prop.s.setGroupProperty(PropertyInterface('Size', _propertyGroup));
    prop.p.setGroupProperty(PropertyInterface('Position', _propertyGroup));

    Object.defineProperties(interfaceFunction, {
      size: {
        get: ExpressionPropertyInterface(prop.s),
      },
      position: {
        get: ExpressionPropertyInterface(prop.p),
      },
      _name: { value: shape.nm },
    });
    interfaceFunction.mn = shape.mn;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(value) {
      if (shape.p.ix === value) {
        return interfaceFunction.position;
      }
      if (shape.s.ix === value) {
        return interfaceFunction.size;
      }
      return null;
    }
```
</details>

### `starInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): any; propertyIndex: any; mn: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): any; propertyIndex: any; mn: any; }`

**Calls:**

- `propertyGroupFactory`
- `prop.or.setGroupProperty`
- `PropertyInterface`
- `prop.os.setGroupProperty`
- `prop.pt.setGroupProperty`
- `prop.p.setGroupProperty`
- `prop.r.setGroupProperty`
- `prop.ir.setGroupProperty`
- `prop.is.setGroupProperty`
- `Object.defineProperties`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function starInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(value) {
      if (shape.p.ix === value) {
        return interfaceFunction.position;
      }
      if (shape.r.ix === value) {
        return interfaceFunction.rotation;
      }
      if (shape.pt.ix === value) {
        return interfaceFunction.points;
      }
      if (shape.or.ix === value || value === 'ADBE Vector Star Outer Radius') {
        return interfaceFunction.outerRadius;
      }
      if (shape.os.ix === value) {
        return interfaceFunction.outerRoundness;
      }
      if (shape.ir && (shape.ir.ix === value || value === 'ADBE Vector Star Inner Radius')) {
        return interfaceFunction.innerRadius;
      }
      if (shape.is && shape.is.ix === value) {
        return interfaceFunction.innerRoundness;
      }
      return null;
    }

    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    var prop = view.sh.ty === 'tm' ? view.sh.prop : view.sh;
    interfaceFunction.propertyIndex = shape.ix;
    prop.or.setGroupProperty(PropertyInterface('Outer Radius', _propertyGroup));
    prop.os.setGroupProperty(PropertyInterface('Outer Roundness', _propertyGroup));
    prop.pt.setGroupProperty(PropertyInterface('Points', _propertyGroup));
    prop.p.setGroupProperty(PropertyInterface('Position', _propertyGroup));
    prop.r.setGroupProperty(PropertyInterface('Rotation', _propertyGroup));
    if (shape.ir) {
      prop.ir.setGroupProperty(PropertyInterface('Inner Radius', _propertyGroup));
      prop.is.setGroupProperty(PropertyInterface('Inner Roundness', _propertyGroup));
    }

    Object.defineProperties(interfaceFunction, {
      position: {
        get: ExpressionPropertyInterface(prop.p),
      },
      rotation: {
        get: ExpressionPropertyInterface(prop.r),
      },
      points: {
        get: ExpressionPropertyInterface(prop.pt),
      },
      outerRadius: {
        get: ExpressionPropertyInterface(prop.or),
      },
      outerRoundness: {
        get: ExpressionPropertyInterface(prop.os),
      },
      innerRadius: {
        get: ExpressionPropertyInterface(prop.ir),
      },
      innerRoundness: {
        get: ExpressionPropertyInterface(prop.is),
      },
      _name: { value: shape.nm },
    });
    interfaceFunction.mn = shape.mn;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(value) {
      if (shape.p.ix === value) {
        return interfaceFunction.position;
      }
      if (shape.r.ix === value) {
        return interfaceFunction.rotation;
      }
      if (shape.pt.ix === value) {
        return interfaceFunction.points;
      }
      if (shape.or.ix === value || value === 'ADBE Vector Star Outer Radius') {
        return interfaceFunction.outerRadius;
      }
      if (shape.os.ix === value) {
        return interfaceFunction.outerRoundness;
      }
      if (shape.ir && (shape.ir.ix === value || value === 'ADBE Vector Star Inner Radius')) {
        return interfaceFunction.innerRadius;
      }
      if (shape.is && shape.is.ix === value) {
        return interfaceFunction.innerRoundness;
      }
      return null;
    }
```
</details>

### `rectInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): any; propertyIndex: any; mn: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): any; propertyIndex: any; mn: any; }`

**Calls:**

- `propertyGroupFactory`
- `prop.p.setGroupProperty`
- `PropertyInterface`
- `prop.s.setGroupProperty`
- `prop.r.setGroupProperty`
- `Object.defineProperties`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function rectInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(value) {
      if (shape.p.ix === value) {
        return interfaceFunction.position;
      }
      if (shape.r.ix === value) {
        return interfaceFunction.roundness;
      }
      if (shape.s.ix === value || value === 'Size' || value === 'ADBE Vector Rect Size') {
        return interfaceFunction.size;
      }
      return null;
    }
    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);

    var prop = view.sh.ty === 'tm' ? view.sh.prop : view.sh;
    interfaceFunction.propertyIndex = shape.ix;
    prop.p.setGroupProperty(PropertyInterface('Position', _propertyGroup));
    prop.s.setGroupProperty(PropertyInterface('Size', _propertyGroup));
    prop.r.setGroupProperty(PropertyInterface('Rotation', _propertyGroup));

    Object.defineProperties(interfaceFunction, {
      position: {
        get: ExpressionPropertyInterface(prop.p),
      },
      roundness: {
        get: ExpressionPropertyInterface(prop.r),
      },
      size: {
        get: ExpressionPropertyInterface(prop.s),
      },
      _name: { value: shape.nm },
    });
    interfaceFunction.mn = shape.mn;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(value) {
      if (shape.p.ix === value) {
        return interfaceFunction.position;
      }
      if (shape.r.ix === value) {
        return interfaceFunction.roundness;
      }
      if (shape.s.ix === value || value === 'Size' || value === 'ADBE Vector Rect Size') {
        return interfaceFunction.size;
      }
      return null;
    }
```
</details>

### `roundedInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): any; propertyIndex: any; mn: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): any; propertyIndex: any; mn: any; }`

**Calls:**

- `propertyGroupFactory`
- `prop.rd.setGroupProperty`
- `PropertyInterface`
- `Object.defineProperties`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function roundedInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(value) {
      if (shape.r.ix === value || value === 'Round Corners 1') {
        return interfaceFunction.radius;
      }
      return null;
    }

    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    var prop = view;
    interfaceFunction.propertyIndex = shape.ix;
    prop.rd.setGroupProperty(PropertyInterface('Radius', _propertyGroup));

    Object.defineProperties(interfaceFunction, {
      radius: {
        get: ExpressionPropertyInterface(prop.rd),
      },
      _name: { value: shape.nm },
    });
    interfaceFunction.mn = shape.mn;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(value) {
      if (shape.r.ix === value || value === 'Round Corners 1') {
        return interfaceFunction.radius;
      }
      return null;
    }
```
</details>

### `repeaterInterfaceFactory(shape: any, view: any, propertyGroup: any): { (value: any): any; propertyIndex: any; mn: any; }`

**Parameters:**

- **`shape`** `any`
- **`view`** `any`
- **`propertyGroup`** `any`

**Returns:** `{ (value: any): any; propertyIndex: any; mn: any; }`

**Calls:**

- `propertyGroupFactory`
- `prop.c.setGroupProperty`
- `PropertyInterface`
- `prop.o.setGroupProperty`
- `Object.defineProperties`
- `ExpressionPropertyInterface`

<details><summary>Code</summary>

```typescript
function repeaterInterfaceFactory(shape, view, propertyGroup) {
    function interfaceFunction(value) {
      if (shape.c.ix === value || value === 'Copies') {
        return interfaceFunction.copies;
      } if (shape.o.ix === value || value === 'Offset') {
        return interfaceFunction.offset;
      }
      return null;
    }

    var _propertyGroup = propertyGroupFactory(interfaceFunction, propertyGroup);
    var prop = view;
    interfaceFunction.propertyIndex = shape.ix;
    prop.c.setGroupProperty(PropertyInterface('Copies', _propertyGroup));
    prop.o.setGroupProperty(PropertyInterface('Offset', _propertyGroup));
    Object.defineProperties(interfaceFunction, {
      copies: {
        get: ExpressionPropertyInterface(prop.c),
      },
      offset: {
        get: ExpressionPropertyInterface(prop.o),
      },
      _name: { value: shape.nm },
    });
    interfaceFunction.mn = shape.mn;
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function interfaceFunction(value) {
      if (shape.c.ix === value || value === 'Copies') {
        return interfaceFunction.copies;
      } if (shape.o.ix === value || value === 'Offset') {
        return interfaceFunction.offset;
      }
      return null;
    }
```
</details>

### `_interfaceFunction(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _interfaceFunction(value) {
      if (typeof value === 'number') {
        value = value === undefined ? 1 : value;
        if (value === 0) {
          return propertyGroup;
        }
        return interfaces[value - 1];
      }
      var i = 0;
      var len = interfaces.length;
      while (i < len) {
        if (interfaces[i]._name === value) {
          return interfaces[i];
        }
        i += 1;
      }
      return null;
    }
```
</details>

### `parentGroupWrapper(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function parentGroupWrapper() {
      return propertyGroup;
    }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return shape.nm;
      }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return shape.nm;
      }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `get(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
          return 'a';
        }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `get(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function () {
          return dashOb;
        }
```
</details>

### `_thisLayerFunction(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _thisLayerFunction(name) {
      switch (name) {
        case 'ADBE Text Document':
          return _thisLayerFunction.sourceText;
        default:
          return null;
      }
    }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `elem.textProperty.getValue`

**Internal Comments:**
```
// If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive (x4)
```

<details><summary>Code</summary>

```typescript
function () {
        elem.textProperty.getValue();
        var stringValue = elem.textProperty.currentData.t;
        if (stringValue !== _prevValue) {
          elem.textProperty.currentData.t = _prevValue;
          _sourceText = new String(stringValue); // eslint-disable-line no-new-wrappers
          // If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive
          _sourceText.value = stringValue || new String(stringValue); // eslint-disable-line no-new-wrappers
        }
        return _sourceText;
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `elem.textProperty.getValue`

**Internal Comments:**
```
// If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive (x4)
```

<details><summary>Code</summary>

```typescript
function () {
        elem.textProperty.getValue();
        var stringValue = elem.textProperty.currentData.t;
        if (stringValue !== _prevValue) {
          elem.textProperty.currentData.t = _prevValue;
          _sourceText = new String(stringValue); // eslint-disable-line no-new-wrappers
          // If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive
          _sourceText.value = stringValue || new String(stringValue); // eslint-disable-line no-new-wrappers
        }
        return _sourceText;
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `elem.textProperty.getValue`

**Internal Comments:**
```
// If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive (x4)
```

<details><summary>Code</summary>

```typescript
function () {
        elem.textProperty.getValue();
        var stringValue = elem.textProperty.currentData.t;
        if (stringValue !== _prevValue) {
          elem.textProperty.currentData.t = _prevValue;
          _sourceText = new String(stringValue); // eslint-disable-line no-new-wrappers
          // If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive
          _sourceText.value = stringValue || new String(stringValue); // eslint-disable-line no-new-wrappers
        }
        return _sourceText;
      }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `elem.textProperty.getValue`

**Internal Comments:**
```
// If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive (x4)
```

<details><summary>Code</summary>

```typescript
function () {
        elem.textProperty.getValue();
        var stringValue = elem.textProperty.currentData.t;
        if (stringValue !== _prevValue) {
          elem.textProperty.currentData.t = _prevValue;
          _sourceText = new String(stringValue); // eslint-disable-line no-new-wrappers
          // If stringValue is an empty string, eval returns undefined, so it has to be returned as a String primitive
          _sourceText.value = stringValue || new String(stringValue); // eslint-disable-line no-new-wrappers
        }
        return _sourceText;
      }
```
</details>

### `SliderEffect(data: any, elem: any, container: any): void`

**Parameters:**

- **`data`** `any`
- **`elem`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function SliderEffect(data, elem, container) {
  this.p = PropertyFactory.getProp(elem, data.v, 0, 0, container);
}
```
</details>

### `AngleEffect(data: any, elem: any, container: any): void`

**Parameters:**

- **`data`** `any`
- **`elem`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function AngleEffect(data, elem, container) {
  this.p = PropertyFactory.getProp(elem, data.v, 0, 0, container);
}
```
</details>

### `ColorEffect(data: any, elem: any, container: any): void`

**Parameters:**

- **`data`** `any`
- **`elem`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function ColorEffect(data, elem, container) {
  this.p = PropertyFactory.getProp(elem, data.v, 1, 0, container);
}
```
</details>

### `PointEffect(data: any, elem: any, container: any): void`

**Parameters:**

- **`data`** `any`
- **`elem`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function PointEffect(data, elem, container) {
  this.p = PropertyFactory.getProp(elem, data.v, 1, 0, container);
}
```
</details>

### `LayerIndexEffect(data: any, elem: any, container: any): void`

**Parameters:**

- **`data`** `any`
- **`elem`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function LayerIndexEffect(data, elem, container) {
  this.p = PropertyFactory.getProp(elem, data.v, 0, 0, container);
}
```
</details>

### `MaskIndexEffect(data: any, elem: any, container: any): void`

**Parameters:**

- **`data`** `any`
- **`elem`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function MaskIndexEffect(data, elem, container) {
  this.p = PropertyFactory.getProp(elem, data.v, 0, 0, container);
}
```
</details>

### `CheckboxEffect(data: any, elem: any, container: any): void`

**Parameters:**

- **`data`** `any`
- **`elem`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function CheckboxEffect(data, elem, container) {
  this.p = PropertyFactory.getProp(elem, data.v, 0, 0, container);
}
```
</details>

### `NoValueEffect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function NoValueEffect() {
  this.p = {};
}
```
</details>

### `EffectsManager(data: any, element: any): void`

**Parameters:**

- **`data`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `this.effectElements.push`

<details><summary>Code</summary>

```typescript
function EffectsManager(data, element) {
  var effects = data.ef || [];
  this.effectElements = [];
  var i;
  var len = effects.length;
  var effectItem;
  for (i = 0; i < len; i += 1) {
    effectItem = new GroupEffect(effects[i], element);
    this.effectElements.push(effectItem);
  }
}
```
</details>

### `GroupEffect(data: any, element: any): void`

**Parameters:**

- **`data`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `this.init`

<details><summary>Code</summary>

```typescript
function GroupEffect(data, element) {
  this.init(data, element);
}
```
</details>

### `BaseElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BaseElement() {
}
```
</details>

### `checkMasks(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () {
    if (!this.data.hasMask) {
      return false;
    }
    var i = 0;
    var len = this.data.masksProperties.length;
    while (i < len) {
      if ((this.data.masksProperties[i].mode !== 'n' && this.data.masksProperties[i].cl !== false)) {
        return true;
      }
      i += 1;
    }
    return false;
  }
```
</details>

### `initExpressions(): void`

**Returns:** `void`

**Calls:**

- `LayerExpressionInterface`
- `this.layerInterface.registerMaskInterface`
- `EffectsExpressionInterface.createEffectsInterface`
- `this.layerInterface.registerEffectsInterface`
- `CompExpressionInterface`
- `ShapeExpressionInterface`
- `TextExpressionInterface`

<details><summary>Code</summary>

```typescript
function () {
    this.layerInterface = LayerExpressionInterface(this);
    if (this.data.hasMask && this.maskManager) {
      this.layerInterface.registerMaskInterface(this.maskManager);
    }
    var effectsInterface = EffectsExpressionInterface.createEffectsInterface(this, this.layerInterface);
    this.layerInterface.registerEffectsInterface(effectsInterface);

    if (this.data.ty === 0 || this.data.xt) {
      this.compInterface = CompExpressionInterface(this);
    } else if (this.data.ty === 4) {
      this.layerInterface.shapeInterface = ShapeExpressionInterface(this.shapesData, this.itemsData, this.layerInterface);
      this.layerInterface.content = this.layerInterface.shapeInterface;
    } else if (this.data.ty === 5) {
      this.layerInterface.textInterface = TextExpressionInterface(this);
      this.layerInterface.text = this.layerInterface.textInterface;
    }
  }
```
</details>

### `setBlendMode(): void`

**Returns:** `void`

**Calls:**

- `getBlendMode`

<details><summary>Code</summary>

```typescript
function () {
    var blendModeValue = getBlendMode(this.data.bm);
    var elem = this.baseElement || this.layerElement;

    elem.style['mix-blend-mode'] = blendModeValue;
  }
```
</details>

### `initBaseData(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `createElementID`

**Internal Comments:**
```
// Stretch factor for old animations missing this property.
// effects manager (x4)
```

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
    this.globalData = globalData;
    this.comp = comp;
    this.data = data;
    this.layerId = createElementID();

    // Stretch factor for old animations missing this property.
    if (!this.data.sr) {
      this.data.sr = 1;
    }
    // effects manager
    this.effectsManager = new EffectsManager(this.data, this, this.dynamicProperties);
  }
```
</details>

### `getType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
    return this.type;
  }
```
</details>

### `sourceRectAtTime(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `checkMasks(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () {
    if (!this.data.hasMask) {
      return false;
    }
    var i = 0;
    var len = this.data.masksProperties.length;
    while (i < len) {
      if ((this.data.masksProperties[i].mode !== 'n' && this.data.masksProperties[i].cl !== false)) {
        return true;
      }
      i += 1;
    }
    return false;
  }
```
</details>

### `initExpressions(): void`

**Returns:** `void`

**Calls:**

- `LayerExpressionInterface`
- `this.layerInterface.registerMaskInterface`
- `EffectsExpressionInterface.createEffectsInterface`
- `this.layerInterface.registerEffectsInterface`
- `CompExpressionInterface`
- `ShapeExpressionInterface`
- `TextExpressionInterface`

<details><summary>Code</summary>

```typescript
function () {
    this.layerInterface = LayerExpressionInterface(this);
    if (this.data.hasMask && this.maskManager) {
      this.layerInterface.registerMaskInterface(this.maskManager);
    }
    var effectsInterface = EffectsExpressionInterface.createEffectsInterface(this, this.layerInterface);
    this.layerInterface.registerEffectsInterface(effectsInterface);

    if (this.data.ty === 0 || this.data.xt) {
      this.compInterface = CompExpressionInterface(this);
    } else if (this.data.ty === 4) {
      this.layerInterface.shapeInterface = ShapeExpressionInterface(this.shapesData, this.itemsData, this.layerInterface);
      this.layerInterface.content = this.layerInterface.shapeInterface;
    } else if (this.data.ty === 5) {
      this.layerInterface.textInterface = TextExpressionInterface(this);
      this.layerInterface.text = this.layerInterface.textInterface;
    }
  }
```
</details>

### `setBlendMode(): void`

**Returns:** `void`

**Calls:**

- `getBlendMode`

<details><summary>Code</summary>

```typescript
function () {
    var blendModeValue = getBlendMode(this.data.bm);
    var elem = this.baseElement || this.layerElement;

    elem.style['mix-blend-mode'] = blendModeValue;
  }
```
</details>

### `initBaseData(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `createElementID`

**Internal Comments:**
```
// Stretch factor for old animations missing this property.
// effects manager (x4)
```

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
    this.globalData = globalData;
    this.comp = comp;
    this.data = data;
    this.layerId = createElementID();

    // Stretch factor for old animations missing this property.
    if (!this.data.sr) {
      this.data.sr = 1;
    }
    // effects manager
    this.effectsManager = new EffectsManager(this.data, this, this.dynamicProperties);
  }
```
</details>

### `getType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
    return this.type;
  }
```
</details>

### `sourceRectAtTime(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `FrameElement(): void`

**JSDoc:**
```typescript
/**
 * @file
 * Handles element's layer frame update.
 * Checks layer in point and out point
 *
 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function FrameElement() {}
```
</details>

### `initFrame(): void`

**Returns:** `void`

**Internal Comments:**
```
// set to true when inpoint is rendered (x4)
// list of animated properties (x4)
// If layer has been modified in current tick this will be true (x4)
```

<details><summary>Code</summary>

```typescript
function () {
    // set to true when inpoint is rendered
    this._isFirstFrame = false;
    // list of animated properties
    this.dynamicProperties = [];
    // If layer has been modified in current tick this will be true
    this._mdf = false;
  }
```
</details>

### `prepareProperties(num: number, isVisible: boolean): void`

**Parameters:**

- **`num`** `number`
- **`isVisible`** `boolean`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties[i].getValue`

<details><summary>Code</summary>

```typescript
function (num, isVisible) {
    var i;
    var len = this.dynamicProperties.length;
    for (i = 0; i < len; i += 1) {
      if (isVisible || (this._isParent && this.dynamicProperties[i].propType === 'transform')) {
        this.dynamicProperties[i].getValue();
        if (this.dynamicProperties[i]._mdf) {
          this.globalData._mdf = true;
          this._mdf = true;
        }
      }
    }
  }
```
</details>

### `addDynamicProperty(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties.indexOf`
- `this.dynamicProperties.push`

<details><summary>Code</summary>

```typescript
function (prop) {
    if (this.dynamicProperties.indexOf(prop) === -1) {
      this.dynamicProperties.push(prop);
    }
  }
```
</details>

### `initFrame(): void`

**Returns:** `void`

**Internal Comments:**
```
// set to true when inpoint is rendered (x4)
// list of animated properties (x4)
// If layer has been modified in current tick this will be true (x4)
```

<details><summary>Code</summary>

```typescript
function () {
    // set to true when inpoint is rendered
    this._isFirstFrame = false;
    // list of animated properties
    this.dynamicProperties = [];
    // If layer has been modified in current tick this will be true
    this._mdf = false;
  }
```
</details>

### `prepareProperties(num: number, isVisible: boolean): void`

**Parameters:**

- **`num`** `number`
- **`isVisible`** `boolean`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties[i].getValue`

<details><summary>Code</summary>

```typescript
function (num, isVisible) {
    var i;
    var len = this.dynamicProperties.length;
    for (i = 0; i < len; i += 1) {
      if (isVisible || (this._isParent && this.dynamicProperties[i].propType === 'transform')) {
        this.dynamicProperties[i].getValue();
        if (this.dynamicProperties[i]._mdf) {
          this.globalData._mdf = true;
          this._mdf = true;
        }
      }
    }
  }
```
</details>

### `addDynamicProperty(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `this.dynamicProperties.indexOf`
- `this.dynamicProperties.push`

<details><summary>Code</summary>

```typescript
function (prop) {
    if (this.dynamicProperties.indexOf(prop) === -1) {
      this.dynamicProperties.push(prop);
    }
  }
```
</details>

### `init(): (value: any) => any`

**Returns:** `(value: any) => any`

**Calls:**

- `elem.getFootageData`

<details><summary>Code</summary>

```typescript
function init() {
      currentPropertyName = '';
      currentProperty = elem.getFootageData();
      return searchProperty;
    }
```
</details>

### `searchProperty(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `value.indexOf`
- `parseInt`
- `value.substr`

<details><summary>Code</summary>

```typescript
function searchProperty(value) {
      if (currentProperty[value]) {
        currentPropertyName = value;
        currentProperty = currentProperty[value];
        if (typeof currentProperty === 'object') {
          return searchProperty;
        }
        return currentProperty;
      }
      var propertyNameIndex = value.indexOf(currentPropertyName);
      if (propertyNameIndex !== -1) {
        var index = parseInt(value.substr(propertyNameIndex + currentPropertyName.length), 10);
        currentProperty = currentProperty[index];
        if (typeof currentProperty === 'object') {
          return searchProperty;
        }
        return currentProperty;
      }
      return '';
    }
```
</details>

### `dataInterfaceFactory(elem: any): { (value: any): (value: any) => any; _name: string; outlineInterface: () => (value: any) => any; }`

**Parameters:**

- **`elem`** `any`

**Returns:** `{ (value: any): (value: any) => any; _name: string; outlineInterface: () => (value: any) => any; }`

**Calls:**

- `interfaceFunction.outlineInterface`
- `outlineInterfaceFactory`

<details><summary>Code</summary>

```typescript
function (elem) {
    function interfaceFunction(value) {
      if (value === 'Outline') {
        return interfaceFunction.outlineInterface();
      }
      return null;
    }

    interfaceFunction._name = 'Outline';
    interfaceFunction.outlineInterface = outlineInterfaceFactory(elem);
    return interfaceFunction;
  }
```
</details>

### `interfaceFunction(value: any): (value: any) => any`

**Parameters:**

- **`value`** `any`

**Returns:** `(value: any) => any`

**Calls:**

- `interfaceFunction.outlineInterface`

<details><summary>Code</summary>

```typescript
function interfaceFunction(value) {
      if (value === 'Outline') {
        return interfaceFunction.outlineInterface();
      }
      return null;
    }
```
</details>

### `_interfaceFunction(value: any): { (value: any): (value: any) => any; _name: string; outlineInterface: () => (value: any) => any; }`

**Parameters:**

- **`value`** `any`

**Returns:** `{ (value: any): (value: any) => any; _name: string; outlineInterface: () => (value: any) => any; }`

<details><summary>Code</summary>

```typescript
function _interfaceFunction(value) {
      if (value === 'Data') {
        return _interfaceFunction.dataInterface;
      }
      return null;
    }
```
</details>

### `FootageElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initRenderable`
- `globalData.getAssetData`
- `globalData.imageLoader.getAsset`
- `this.initBaseData`

<details><summary>Code</summary>

```typescript
function FootageElement(data, globalData, comp) {
  this.initFrame();
  this.initRenderable();
  this.assetData = globalData.getAssetData(data.refId);
  this.footageData = globalData.imageLoader.getAsset(this.assetData);
  this.initBaseData(data, globalData, comp);
}
```
</details>

### `AudioElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initRenderable`
- `globalData.getAssetData`
- `this.initBaseData`
- `this.globalData.getAssetsPath`
- `this.globalData.audioController.createAudio`
- `this.globalData.audioController.addAudio`
- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function AudioElement(data, globalData, comp) {
  this.initFrame();
  this.initRenderable();
  this.assetData = globalData.getAssetData(data.refId);
  this.initBaseData(data, globalData, comp);
  this._isPlaying = false;
  this._canPlay = false;
  var assetPath = this.globalData.getAssetsPath(this.assetData);
  this.audio = this.globalData.audioController.createAudio(assetPath);
  this._currentTime = 0;
  this.globalData.audioController.addAudio(this);
  this._volumeMultiplier = 1;
  this._volume = 1;
  this._previousVolume = null;
  this.tm = data.tm ? PropertyFactory.getProp(this, data.tm, 0, globalData.frameRate, this) : { _placeholder: true };
  this.lv = PropertyFactory.getProp(this, data.au && data.au.lv ? data.au.lv : { k: [100] }, 1, 0.01, this);
}
```
</details>

### `BaseRenderer(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BaseRenderer() {}
```
</details>

### `TransformElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function TransformElement() {}
```
</details>

### `initTransform(): void`

**Returns:** `void`

**Calls:**

- `TransformPropertyFactory.getTransformProperty`

**Internal Comments:**
```
// TODO: check TYPE 11: Guided elements
```

<details><summary>Code</summary>

```typescript
function () {
    this.finalTransform = {
      mProp: this.data.ks ? TransformPropertyFactory.getTransformProperty(this, this.data.ks, this) : { o: 0 },
      _matMdf: false,
      _opMdf: false,
      mat: new Matrix(),
    };
    if (this.data.ao) {
      this.finalTransform.mProp.autoOriented = true;
    }

    // TODO: check TYPE 11: Guided elements
    if (this.data.ty !== 11) {
      // this.createElements();
    }
  }
```
</details>

### `renderTransform(): void`

**Returns:** `void`

**Calls:**

- `finalMat.cloneFromProps`
- `finalMat.transform`

**Internal Comments:**
```
// Checking if any of the transformation matrices in the hierarchy chain has changed.
```

<details><summary>Code</summary>

```typescript
function () {
    this.finalTransform._opMdf = this.finalTransform.mProp.o._mdf || this._isFirstFrame;
    this.finalTransform._matMdf = this.finalTransform.mProp._mdf || this._isFirstFrame;

    if (this.hierarchy) {
      var mat;
      var finalMat = this.finalTransform.mat;
      var i = 0;
      var len = this.hierarchy.length;
      // Checking if any of the transformation matrices in the hierarchy chain has changed.
      if (!this.finalTransform._matMdf) {
        while (i < len) {
          if (this.hierarchy[i].finalTransform.mProp._mdf) {
            this.finalTransform._matMdf = true;
            break;
          }
          i += 1;
        }
      }

      if (this.finalTransform._matMdf) {
        mat = this.finalTransform.mProp.v.props;
        finalMat.cloneFromProps(mat);
        for (i = 0; i < len; i += 1) {
          mat = this.hierarchy[i].finalTransform.mProp.v.props;
          finalMat.transform(mat[0], mat[1], mat[2], mat[3], mat[4], mat[5], mat[6], mat[7], mat[8], mat[9], mat[10], mat[11], mat[12], mat[13], mat[14], mat[15]);
        }
      }
    }
  }
```
</details>

### `globalToLocal(pt: any): any`

**Parameters:**

- **`pt`** `any`

**Returns:** `any`

**Calls:**

- `transforms.push`
- `transforms.splice`
- `transforms[i].mat.applyToPointArray`

**Internal Comments:**
```
// ptNew = transforms[i].mat.applyToPointArray(pt[0],pt[1],pt[2]); (x3)
```

<details><summary>Code</summary>

```typescript
function (pt) {
    var transforms = [];
    transforms.push(this.finalTransform);
    var flag = true;
    var comp = this.comp;
    while (flag) {
      if (comp.finalTransform) {
        if (comp.data.hasMask) {
          transforms.splice(0, 0, comp.finalTransform);
        }
        comp = comp.comp;
      } else {
        flag = false;
      }
    }
    var i;
    var len = transforms.length;
    var ptNew;
    for (i = 0; i < len; i += 1) {
      ptNew = transforms[i].mat.applyToPointArray(0, 0, 0);
      // ptNew = transforms[i].mat.applyToPointArray(pt[0],pt[1],pt[2]);
      pt = [pt[0] - ptNew[0], pt[1] - ptNew[1], 0];
    }
    return pt;
  }
```
</details>

### `initTransform(): void`

**Returns:** `void`

**Calls:**

- `TransformPropertyFactory.getTransformProperty`

**Internal Comments:**
```
// TODO: check TYPE 11: Guided elements
```

<details><summary>Code</summary>

```typescript
function () {
    this.finalTransform = {
      mProp: this.data.ks ? TransformPropertyFactory.getTransformProperty(this, this.data.ks, this) : { o: 0 },
      _matMdf: false,
      _opMdf: false,
      mat: new Matrix(),
    };
    if (this.data.ao) {
      this.finalTransform.mProp.autoOriented = true;
    }

    // TODO: check TYPE 11: Guided elements
    if (this.data.ty !== 11) {
      // this.createElements();
    }
  }
```
</details>

### `renderTransform(): void`

**Returns:** `void`

**Calls:**

- `finalMat.cloneFromProps`
- `finalMat.transform`

**Internal Comments:**
```
// Checking if any of the transformation matrices in the hierarchy chain has changed.
```

<details><summary>Code</summary>

```typescript
function () {
    this.finalTransform._opMdf = this.finalTransform.mProp.o._mdf || this._isFirstFrame;
    this.finalTransform._matMdf = this.finalTransform.mProp._mdf || this._isFirstFrame;

    if (this.hierarchy) {
      var mat;
      var finalMat = this.finalTransform.mat;
      var i = 0;
      var len = this.hierarchy.length;
      // Checking if any of the transformation matrices in the hierarchy chain has changed.
      if (!this.finalTransform._matMdf) {
        while (i < len) {
          if (this.hierarchy[i].finalTransform.mProp._mdf) {
            this.finalTransform._matMdf = true;
            break;
          }
          i += 1;
        }
      }

      if (this.finalTransform._matMdf) {
        mat = this.finalTransform.mProp.v.props;
        finalMat.cloneFromProps(mat);
        for (i = 0; i < len; i += 1) {
          mat = this.hierarchy[i].finalTransform.mProp.v.props;
          finalMat.transform(mat[0], mat[1], mat[2], mat[3], mat[4], mat[5], mat[6], mat[7], mat[8], mat[9], mat[10], mat[11], mat[12], mat[13], mat[14], mat[15]);
        }
      }
    }
  }
```
</details>

### `globalToLocal(pt: any): any`

**Parameters:**

- **`pt`** `any`

**Returns:** `any`

**Calls:**

- `transforms.push`
- `transforms.splice`
- `transforms[i].mat.applyToPointArray`

**Internal Comments:**
```
// ptNew = transforms[i].mat.applyToPointArray(pt[0],pt[1],pt[2]); (x3)
```

<details><summary>Code</summary>

```typescript
function (pt) {
    var transforms = [];
    transforms.push(this.finalTransform);
    var flag = true;
    var comp = this.comp;
    while (flag) {
      if (comp.finalTransform) {
        if (comp.data.hasMask) {
          transforms.splice(0, 0, comp.finalTransform);
        }
        comp = comp.comp;
      } else {
        flag = false;
      }
    }
    var i;
    var len = transforms.length;
    var ptNew;
    for (i = 0; i < len; i += 1) {
      ptNew = transforms[i].mat.applyToPointArray(0, 0, 0);
      // ptNew = transforms[i].mat.applyToPointArray(pt[0],pt[1],pt[2]);
      pt = [pt[0] - ptNew[0], pt[1] - ptNew[1], 0];
    }
    return pt;
  }
```
</details>

### `MaskElement(data: any, element: any, globalData: any): void`

**Parameters:**

- **`data`** `any`
- **`element`** `any`
- **`globalData`** `any`

**Returns:** `void`

**Calls:**

- `createSizedArray`
- `createElementID`
- `createNS`
- `rect.setAttribute`
- `currentMasks.push`
- `PropertyFactory.getProp`
- `ShapePropertyFactory.getShapeProp`
- `defs.appendChild`
- `path.setAttribute`
- `expansor.setAttribute`
- `feMorph.setAttribute`
- `expansor.appendChild`
- `g.appendChild`
- `mask.setAttribute`
- `mask.appendChild`
- `g.setAttribute`
- `getLocationHref`
- `this.createLayerSolidPath`
- `this.drawPath`
- `this.maskElement.appendChild`
- `this.maskElement.setAttribute`
- `this.element.maskedElement.setAttribute`
- `this.element.addRenderableComponent`

**Internal Comments:**
```
// TODO move this to a factory or to a constructor (x15)
```

<details><summary>Code</summary>

```typescript
function MaskElement(data, element, globalData) {
  this.data = data;
  this.element = element;
  this.globalData = globalData;
  this.storedData = [];
  this.masksProperties = this.data.masksProperties || [];
  this.maskElement = null;
  var defs = this.globalData.defs;
  var i;
  var len = this.masksProperties ? this.masksProperties.length : 0;
  this.viewData = createSizedArray(len);
  this.solidPath = '';

  var path;
  var properties = this.masksProperties;
  var count = 0;
  var currentMasks = [];
  var j;
  var jLen;
  var layerId = createElementID();
  var rect;
  var expansor;
  var feMorph;
  var x;
  var maskType = 'clipPath';
  var maskRef = 'clip-path';
  for (i = 0; i < len; i += 1) {
    if ((properties[i].mode !== 'a' && properties[i].mode !== 'n') || properties[i].inv || properties[i].o.k !== 100 || properties[i].o.x) {
      maskType = 'mask';
      maskRef = 'mask';
    }

    if ((properties[i].mode === 's' || properties[i].mode === 'i') && count === 0) {
      rect = createNS('rect');
      rect.setAttribute('fill', '#ffffff');
      rect.setAttribute('width', this.element.comp.data.w || 0);
      rect.setAttribute('height', this.element.comp.data.h || 0);
      currentMasks.push(rect);
    } else {
      rect = null;
    }

    path = createNS('path');
    if (properties[i].mode === 'n') {
      // TODO move this to a factory or to a constructor
      this.viewData[i] = {
        op: PropertyFactory.getProp(this.element, properties[i].o, 0, 0.01, this.element),
        prop: ShapePropertyFactory.getShapeProp(this.element, properties[i], 3),
        elem: path,
        lastPath: '',
      };
      defs.appendChild(path);
    } else {
      count += 1;

      path.setAttribute('fill', properties[i].mode === 's' ? '#000000' : '#ffffff');
      path.setAttribute('clip-rule', 'nonzero');
      var filterID;

      if (properties[i].x.k !== 0) {
        maskType = 'mask';
        maskRef = 'mask';
        x = PropertyFactory.getProp(this.element, properties[i].x, 0, null, this.element);
        filterID = createElementID();
        expansor = createNS('filter');
        expansor.setAttribute('id', filterID);
        feMorph = createNS('feMorphology');
        feMorph.setAttribute('operator', 'erode');
        feMorph.setAttribute('in', 'SourceGraphic');
        feMorph.setAttribute('radius', '0');
        expansor.appendChild(feMorph);
        defs.appendChild(expansor);
        path.setAttribute('stroke', properties[i].mode === 's' ? '#000000' : '#ffffff');
      } else {
        feMorph = null;
        x = null;
      }

      // TODO move this to a factory or to a constructor
      this.storedData[i] = {
        elem: path,
        x: x,
        expan: feMorph,
        lastPath: '',
        lastOperator: '',
        filterId: filterID,
        lastRadius: 0,
      };
      if (properties[i].mode === 'i') {
        jLen = currentMasks.length;
        var g = createNS('g');
        for (j = 0; j < jLen; j += 1) {
          g.appendChild(currentMasks[j]);
        }
        var mask = createNS('mask');
        mask.setAttribute('mask-type', 'alpha');
        mask.setAttribute('id', layerId + '_' + count);
        mask.appendChild(path);
        defs.appendChild(mask);
        g.setAttribute('mask', 'url(' + getLocationHref() + '#' + layerId + '_' + count + ')');

        currentMasks.length = 0;
        currentMasks.push(g);
      } else {
        currentMasks.push(path);
      }
      if (properties[i].inv && !this.solidPath) {
        this.solidPath = this.createLayerSolidPath();
      }
      // TODO move this to a factory or to a constructor
      this.viewData[i] = {
        elem: path,
        lastPath: '',
        op: PropertyFactory.getProp(this.element, properties[i].o, 0, 0.01, this.element),
        prop: ShapePropertyFactory.getShapeProp(this.element, properties[i], 3),
        invRect: rect,
      };
      if (!this.viewData[i].prop.k) {
        this.drawPath(properties[i], this.viewData[i].prop.v, this.viewData[i]);
      }
    }
  }

  this.maskElement = createNS(maskType);

  len = currentMasks.length;
  for (i = 0; i < len; i += 1) {
    this.maskElement.appendChild(currentMasks[i]);
  }

  if (count > 0) {
    this.maskElement.setAttribute('id', layerId);
    this.element.maskedElement.setAttribute(maskRef, 'url(' + getLocationHref() + '#' + layerId + ')');
    defs.appendChild(this.maskElement);
  }
  if (this.viewData.length) {
    this.element.addRenderableComponent(this);
  }
}
```
</details>

### `createFilter(filId: any, skipCoordinates: any): any`

**Parameters:**

- **`filId`** `any`
- **`skipCoordinates`** `any`

**Returns:** `any`

**Calls:**

- `createNS`
- `fil.setAttribute`

<details><summary>Code</summary>

```typescript
function createFilter(filId, skipCoordinates) {
    var fil = createNS('filter');
    fil.setAttribute('id', filId);
    if (skipCoordinates !== true) {
      fil.setAttribute('filterUnits', 'objectBoundingBox');
      fil.setAttribute('x', '0%');
      fil.setAttribute('y', '0%');
      fil.setAttribute('width', '100%');
      fil.setAttribute('height', '100%');
    }
    return fil;
  }
```
</details>

### `createAlphaToLuminanceFilter(): any`

**Returns:** `any`

**Calls:**

- `createNS`
- `feColorMatrix.setAttribute`

<details><summary>Code</summary>

```typescript
function createAlphaToLuminanceFilter() {
    var feColorMatrix = createNS('feColorMatrix');
    feColorMatrix.setAttribute('type', 'matrix');
    feColorMatrix.setAttribute('color-interpolation-filters', 'sRGB');
    feColorMatrix.setAttribute('values', '0 0 0 1 0  0 0 0 1 0  0 0 0 1 0  0 0 0 1 1');
    return feColorMatrix;
  }
```
</details>

### `SVGEffects(elem: any): void`

**Parameters:**

- **`elem`** `any`

**Returns:** `void`

**Calls:**

- `createElementID`
- `filtersFactory.createFilter`
- `this.filters.push`
- `elem.globalData.defs.appendChild`
- `elem.layerElement.setAttribute`
- `getLocationHref`
- `elem.addRenderableComponent`

<details><summary>Code</summary>

```typescript
function SVGEffects(elem) {
  var i;
  var source = 'SourceGraphic';
  var len = elem.data.ef ? elem.data.ef.length : 0;
  var filId = createElementID();
  var fil = filtersFactory.createFilter(filId, true);
  var count = 0;
  this.filters = [];
  var filterManager;
  for (i = 0; i < len; i += 1) {
    filterManager = null;
    var type = elem.data.ef[i].ty;
    if (registeredEffects[type]) {
      var Effect = registeredEffects[type].effect;
      filterManager = new Effect(fil, elem.effectsManager.effectElements[i], elem, idPrefix + count, source);
      source = idPrefix + count;
      if (registeredEffects[type].countsAsEffect) {
        count += 1;
      }
    }
    if (filterManager) {
      this.filters.push(filterManager);
    }
  }
  if (count) {
    elem.globalData.defs.appendChild(fil);
    elem.layerElement.setAttribute('filter', 'url(' + getLocationHref() + '#' + filId + ')');
  }
  if (this.filters.length) {
    elem.addRenderableComponent(this);
  }
}
```
</details>

### `registerEffect(id: any, effect: any, countsAsEffect: any): void`

**Parameters:**

- **`id`** `any`
- **`effect`** `any`
- **`countsAsEffect`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function registerEffect(id, effect, countsAsEffect) {
  registeredEffects[id] = {
    effect,
    countsAsEffect,
  };
}
```
</details>

### `SVGBaseElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SVGBaseElement() {
}
```
</details>

### `initRendererElement(): void`

**Returns:** `void`

**Calls:**

- `createNS`

<details><summary>Code</summary>

```typescript
function () {
    this.layerElement = createNS('g');
  }
```
</details>

### `createContainerElements(): void`

**Returns:** `void`

**Calls:**

- `createNS`
- `masker.setAttribute`
- `masker.appendChild`
- `this.globalData.defs.appendChild`
- `createElementID`
- `filtersFactory.createFilter`
- `fil.appendChild`
- `filtersFactory.createAlphaToLuminanceFilter`
- `gg.appendChild`
- `gg.setAttribute`
- `getLocationHref`
- `maskGroup.setAttribute`
- `maskGroup.appendChild`
- `feCTr.setAttribute`
- `feFunc.setAttribute`
- `feCTr.appendChild`
- `alphaRect.setAttribute`
- `maskGrouper.setAttribute`
- `maskGrouper.appendChild`
- `this.matteElement.appendChild`
- `this.layerElement.setAttribute`
- `pt.setAttribute`
- `cp.setAttribute`
- `cp.appendChild`
- `this.checkMasks`
- `cpGroup.setAttribute`
- `cpGroup.appendChild`
- `layerElementParent.appendChild`
- `this.setBlendMode`

**Internal Comments:**
```
// If this layer acts as a mask for the following layer (x2)
// This is only for IE and Edge when mask if of type alpha
/// / (x10)
// This solution doesn't work on Android when meta tag with viewport attribute is set (x2)
/* var feColorMatrix = createNS('feColorMatrix');
                feColorMatrix.setAttribute('type', 'matrix');
                feColorMatrix.setAttribute('color-interpolation-filters', 'sRGB');
                feColorMatrix.setAttribute('values','1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 -1 1');
                fil.appendChild(feColorMatrix); */ (x2)
// Clipping compositions to hide content that exceeds boundaries. If collapsed transformations is on, component should not be clipped
```

<details><summary>Code</summary>

```typescript
function () {
    this.matteElement = createNS('g');
    this.transformedElement = this.layerElement;
    this.maskedElement = this.layerElement;
    this._sizeChanged = false;
    var layerElementParent = null;
    // If this layer acts as a mask for the following layer
    var filId;
    var fil;
    var gg;
    if (this.data.td) {
      if (this.data.td == 3 || this.data.td == 1) { // eslint-disable-line eqeqeq
        var masker = createNS('mask');
        masker.setAttribute('id', this.layerId);
        masker.setAttribute('mask-type', this.data.td == 3 ? 'luminance' : 'alpha'); // eslint-disable-line eqeqeq
        masker.appendChild(this.layerElement);
        layerElementParent = masker;
        this.globalData.defs.appendChild(masker);
        // This is only for IE and Edge when mask if of type alpha
        if (!featureSupport.maskType && this.data.td == 1) { // eslint-disable-line eqeqeq
          masker.setAttribute('mask-type', 'luminance');
          filId = createElementID();
          fil = filtersFactory.createFilter(filId);
          this.globalData.defs.appendChild(fil);
          fil.appendChild(filtersFactory.createAlphaToLuminanceFilter());
          gg = createNS('g');
          gg.appendChild(this.layerElement);
          layerElementParent = gg;
          masker.appendChild(gg);
          gg.setAttribute('filter', 'url(' + getLocationHref() + '#' + filId + ')');
        }
      } else if (this.data.td == 2) { // eslint-disable-line eqeqeq
        var maskGroup = createNS('mask');
        maskGroup.setAttribute('id', this.layerId);
        maskGroup.setAttribute('mask-type', 'alpha');
        var maskGrouper = createNS('g');
        maskGroup.appendChild(maskGrouper);
        filId = createElementID();
        fil = filtersFactory.createFilter(filId);
        /// /

        // This solution doesn't work on Android when meta tag with viewport attribute is set
        /* var feColorMatrix = createNS('feColorMatrix');
                feColorMatrix.setAttribute('type', 'matrix');
                feColorMatrix.setAttribute('color-interpolation-filters', 'sRGB');
                feColorMatrix.setAttribute('values','1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 -1 1');
                fil.appendChild(feColorMatrix); */
        /// /
        var feCTr = createNS('feComponentTransfer');
        feCTr.setAttribute('in', 'SourceGraphic');
        fil.appendChild(feCTr);
        var feFunc = createNS('feFuncA');
        feFunc.setAttribute('type', 'table');
        feFunc.setAttribute('tableValues', '1.0 0.0');
        feCTr.appendChild(feFunc);
        /// /
        this.globalData.defs.appendChild(fil);
        var alphaRect = createNS('rect');
        alphaRect.setAttribute('width', this.comp.data.w);
        alphaRect.setAttribute('height', this.comp.data.h);
        alphaRect.setAttribute('x', '0');
        alphaRect.setAttribute('y', '0');
        alphaRect.setAttribute('fill', '#ffffff');
        alphaRect.setAttribute('opacity', '0');
        maskGrouper.setAttribute('filter', 'url(' + getLocationHref() + '#' + filId + ')');
        maskGrouper.appendChild(alphaRect);
        maskGrouper.appendChild(this.layerElement);
        layerElementParent = maskGrouper;
        if (!featureSupport.maskType) {
          maskGroup.setAttribute('mask-type', 'luminance');
          fil.appendChild(filtersFactory.createAlphaToLuminanceFilter());
          gg = createNS('g');
          maskGrouper.appendChild(alphaRect);
          gg.appendChild(this.layerElement);
          layerElementParent = gg;
          maskGrouper.appendChild(gg);
        }
        this.globalData.defs.appendChild(maskGroup);
      }
    } else if (this.data.tt) {
      this.matteElement.appendChild(this.layerElement);
      layerElementParent = this.matteElement;
      this.baseElement = this.matteElement;
    } else {
      this.baseElement = this.layerElement;
    }
    if (this.data.ln) {
      this.layerElement.setAttribute('id', this.data.ln);
    }
    if (this.data.cl) {
      this.layerElement.setAttribute('class', this.data.cl);
    }
    // Clipping compositions to hide content that exceeds boundaries. If collapsed transformations is on, component should not be clipped
    if (this.data.ty === 0 && !this.data.hd) {
      var cp = createNS('clipPath');
      var pt = createNS('path');
      pt.setAttribute('d', 'M0,0 L' + this.data.w + ',0 L' + this.data.w + ',' + this.data.h + ' L0,' + this.data.h + 'z');
      var clipId = createElementID();
      cp.setAttribute('id', clipId);
      cp.appendChild(pt);
      this.globalData.defs.appendChild(cp);

      if (this.checkMasks()) {
        var cpGroup = createNS('g');
        cpGroup.setAttribute('clip-path', 'url(' + getLocationHref() + '#' + clipId + ')');
        cpGroup.appendChild(this.layerElement);
        this.transformedElement = cpGroup;
        if (layerElementParent) {
          layerElementParent.appendChild(this.transformedElement);
        } else {
          this.baseElement = this.transformedElement;
        }
      } else {
        this.layerElement.setAttribute('clip-path', 'url(' + getLocationHref() + '#' + clipId + ')');
      }
    }
    if (this.data.bm !== 0) {
      this.setBlendMode();
    }
  }
```
</details>

### `renderElement(): void`

**Returns:** `void`

**Calls:**

- `this.transformedElement.setAttribute`
- `this.finalTransform.mat.to2dCSS`

<details><summary>Code</summary>

```typescript
function () {
    if (this.finalTransform._matMdf) {
      this.transformedElement.setAttribute('transform', this.finalTransform.mat.to2dCSS());
    }
    if (this.finalTransform._opMdf) {
      this.transformedElement.setAttribute('opacity', this.finalTransform.mProp.o.v);
    }
  }
```
</details>

### `destroyBaseElement(): void`

**Returns:** `void`

**Calls:**

- `this.maskManager.destroy`

<details><summary>Code</summary>

```typescript
function () {
    this.layerElement = null;
    this.matteElement = null;
    this.maskManager.destroy();
  }
```
</details>

### `getBaseElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
    if (this.data.hd) {
      return null;
    }
    return this.baseElement;
  }
```
</details>

### `createRenderableComponents(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this.maskManager = new MaskElement(this.data, this, this.globalData);
    this.renderableEffectsManager = new SVGEffects(this);
  }
```
</details>

### `setMatte(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `this.matteElement.setAttribute`
- `getLocationHref`

<details><summary>Code</summary>

```typescript
function (id) {
    if (!this.matteElement) {
      return;
    }
    this.matteElement.setAttribute('mask', 'url(' + getLocationHref() + '#' + id + ')');
  }
```
</details>

### `initRendererElement(): void`

**Returns:** `void`

**Calls:**

- `createNS`

<details><summary>Code</summary>

```typescript
function () {
    this.layerElement = createNS('g');
  }
```
</details>

### `createContainerElements(): void`

**Returns:** `void`

**Calls:**

- `createNS`
- `masker.setAttribute`
- `masker.appendChild`
- `this.globalData.defs.appendChild`
- `createElementID`
- `filtersFactory.createFilter`
- `fil.appendChild`
- `filtersFactory.createAlphaToLuminanceFilter`
- `gg.appendChild`
- `gg.setAttribute`
- `getLocationHref`
- `maskGroup.setAttribute`
- `maskGroup.appendChild`
- `feCTr.setAttribute`
- `feFunc.setAttribute`
- `feCTr.appendChild`
- `alphaRect.setAttribute`
- `maskGrouper.setAttribute`
- `maskGrouper.appendChild`
- `this.matteElement.appendChild`
- `this.layerElement.setAttribute`
- `pt.setAttribute`
- `cp.setAttribute`
- `cp.appendChild`
- `this.checkMasks`
- `cpGroup.setAttribute`
- `cpGroup.appendChild`
- `layerElementParent.appendChild`
- `this.setBlendMode`

**Internal Comments:**
```
// If this layer acts as a mask for the following layer (x2)
// This is only for IE and Edge when mask if of type alpha
/// / (x10)
// This solution doesn't work on Android when meta tag with viewport attribute is set (x2)
/* var feColorMatrix = createNS('feColorMatrix');
                feColorMatrix.setAttribute('type', 'matrix');
                feColorMatrix.setAttribute('color-interpolation-filters', 'sRGB');
                feColorMatrix.setAttribute('values','1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 -1 1');
                fil.appendChild(feColorMatrix); */ (x2)
// Clipping compositions to hide content that exceeds boundaries. If collapsed transformations is on, component should not be clipped
```

<details><summary>Code</summary>

```typescript
function () {
    this.matteElement = createNS('g');
    this.transformedElement = this.layerElement;
    this.maskedElement = this.layerElement;
    this._sizeChanged = false;
    var layerElementParent = null;
    // If this layer acts as a mask for the following layer
    var filId;
    var fil;
    var gg;
    if (this.data.td) {
      if (this.data.td == 3 || this.data.td == 1) { // eslint-disable-line eqeqeq
        var masker = createNS('mask');
        masker.setAttribute('id', this.layerId);
        masker.setAttribute('mask-type', this.data.td == 3 ? 'luminance' : 'alpha'); // eslint-disable-line eqeqeq
        masker.appendChild(this.layerElement);
        layerElementParent = masker;
        this.globalData.defs.appendChild(masker);
        // This is only for IE and Edge when mask if of type alpha
        if (!featureSupport.maskType && this.data.td == 1) { // eslint-disable-line eqeqeq
          masker.setAttribute('mask-type', 'luminance');
          filId = createElementID();
          fil = filtersFactory.createFilter(filId);
          this.globalData.defs.appendChild(fil);
          fil.appendChild(filtersFactory.createAlphaToLuminanceFilter());
          gg = createNS('g');
          gg.appendChild(this.layerElement);
          layerElementParent = gg;
          masker.appendChild(gg);
          gg.setAttribute('filter', 'url(' + getLocationHref() + '#' + filId + ')');
        }
      } else if (this.data.td == 2) { // eslint-disable-line eqeqeq
        var maskGroup = createNS('mask');
        maskGroup.setAttribute('id', this.layerId);
        maskGroup.setAttribute('mask-type', 'alpha');
        var maskGrouper = createNS('g');
        maskGroup.appendChild(maskGrouper);
        filId = createElementID();
        fil = filtersFactory.createFilter(filId);
        /// /

        // This solution doesn't work on Android when meta tag with viewport attribute is set
        /* var feColorMatrix = createNS('feColorMatrix');
                feColorMatrix.setAttribute('type', 'matrix');
                feColorMatrix.setAttribute('color-interpolation-filters', 'sRGB');
                feColorMatrix.setAttribute('values','1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 -1 1');
                fil.appendChild(feColorMatrix); */
        /// /
        var feCTr = createNS('feComponentTransfer');
        feCTr.setAttribute('in', 'SourceGraphic');
        fil.appendChild(feCTr);
        var feFunc = createNS('feFuncA');
        feFunc.setAttribute('type', 'table');
        feFunc.setAttribute('tableValues', '1.0 0.0');
        feCTr.appendChild(feFunc);
        /// /
        this.globalData.defs.appendChild(fil);
        var alphaRect = createNS('rect');
        alphaRect.setAttribute('width', this.comp.data.w);
        alphaRect.setAttribute('height', this.comp.data.h);
        alphaRect.setAttribute('x', '0');
        alphaRect.setAttribute('y', '0');
        alphaRect.setAttribute('fill', '#ffffff');
        alphaRect.setAttribute('opacity', '0');
        maskGrouper.setAttribute('filter', 'url(' + getLocationHref() + '#' + filId + ')');
        maskGrouper.appendChild(alphaRect);
        maskGrouper.appendChild(this.layerElement);
        layerElementParent = maskGrouper;
        if (!featureSupport.maskType) {
          maskGroup.setAttribute('mask-type', 'luminance');
          fil.appendChild(filtersFactory.createAlphaToLuminanceFilter());
          gg = createNS('g');
          maskGrouper.appendChild(alphaRect);
          gg.appendChild(this.layerElement);
          layerElementParent = gg;
          maskGrouper.appendChild(gg);
        }
        this.globalData.defs.appendChild(maskGroup);
      }
    } else if (this.data.tt) {
      this.matteElement.appendChild(this.layerElement);
      layerElementParent = this.matteElement;
      this.baseElement = this.matteElement;
    } else {
      this.baseElement = this.layerElement;
    }
    if (this.data.ln) {
      this.layerElement.setAttribute('id', this.data.ln);
    }
    if (this.data.cl) {
      this.layerElement.setAttribute('class', this.data.cl);
    }
    // Clipping compositions to hide content that exceeds boundaries. If collapsed transformations is on, component should not be clipped
    if (this.data.ty === 0 && !this.data.hd) {
      var cp = createNS('clipPath');
      var pt = createNS('path');
      pt.setAttribute('d', 'M0,0 L' + this.data.w + ',0 L' + this.data.w + ',' + this.data.h + ' L0,' + this.data.h + 'z');
      var clipId = createElementID();
      cp.setAttribute('id', clipId);
      cp.appendChild(pt);
      this.globalData.defs.appendChild(cp);

      if (this.checkMasks()) {
        var cpGroup = createNS('g');
        cpGroup.setAttribute('clip-path', 'url(' + getLocationHref() + '#' + clipId + ')');
        cpGroup.appendChild(this.layerElement);
        this.transformedElement = cpGroup;
        if (layerElementParent) {
          layerElementParent.appendChild(this.transformedElement);
        } else {
          this.baseElement = this.transformedElement;
        }
      } else {
        this.layerElement.setAttribute('clip-path', 'url(' + getLocationHref() + '#' + clipId + ')');
      }
    }
    if (this.data.bm !== 0) {
      this.setBlendMode();
    }
  }
```
</details>

### `renderElement(): void`

**Returns:** `void`

**Calls:**

- `this.transformedElement.setAttribute`
- `this.finalTransform.mat.to2dCSS`

<details><summary>Code</summary>

```typescript
function () {
    if (this.finalTransform._matMdf) {
      this.transformedElement.setAttribute('transform', this.finalTransform.mat.to2dCSS());
    }
    if (this.finalTransform._opMdf) {
      this.transformedElement.setAttribute('opacity', this.finalTransform.mProp.o.v);
    }
  }
```
</details>

### `destroyBaseElement(): void`

**Returns:** `void`

**Calls:**

- `this.maskManager.destroy`

<details><summary>Code</summary>

```typescript
function () {
    this.layerElement = null;
    this.matteElement = null;
    this.maskManager.destroy();
  }
```
</details>

### `getBaseElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
    if (this.data.hd) {
      return null;
    }
    return this.baseElement;
  }
```
</details>

### `createRenderableComponents(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this.maskManager = new MaskElement(this.data, this, this.globalData);
    this.renderableEffectsManager = new SVGEffects(this);
  }
```
</details>

### `setMatte(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `this.matteElement.setAttribute`
- `getLocationHref`

<details><summary>Code</summary>

```typescript
function (id) {
    if (!this.matteElement) {
      return;
    }
    this.matteElement.setAttribute('mask', 'url(' + getLocationHref() + '#' + id + ')');
  }
```
</details>

### `HierarchyElement(): void`

**JSDoc:**
```typescript
/**
 * @file
 * Handles AE's layer parenting property.
 *
 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function HierarchyElement() {}
```
</details>

### `initHierarchy(): void`

**Returns:** `void`

**Calls:**

- `this.checkParenting`

**Internal Comments:**
```
// element's parent list (x4)
// if element is parent of another layer _isParent will be true (x4)
```

<details><summary>Code</summary>

```typescript
function () {
    // element's parent list
    this.hierarchy = [];
    // if element is parent of another layer _isParent will be true
    this._isParent = false;
    this.checkParenting();
  }
```
</details>

### `setHierarchy(hierarchy: any): void`

**Parameters:**

- **`hierarchy`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (hierarchy) {
    this.hierarchy = hierarchy;
  }
```
</details>

### `setAsParent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this._isParent = true;
  }
```
</details>

### `checkParenting(): void`

**Returns:** `void`

**Calls:**

- `this.comp.buildElementParenting`

<details><summary>Code</summary>

```typescript
function () {
    if (this.data.parent !== undefined) {
      this.comp.buildElementParenting(this, this.data.parent, []);
    }
  }
```
</details>

### `initHierarchy(): void`

**Returns:** `void`

**Calls:**

- `this.checkParenting`

**Internal Comments:**
```
// element's parent list (x4)
// if element is parent of another layer _isParent will be true (x4)
```

<details><summary>Code</summary>

```typescript
function () {
    // element's parent list
    this.hierarchy = [];
    // if element is parent of another layer _isParent will be true
    this._isParent = false;
    this.checkParenting();
  }
```
</details>

### `setHierarchy(hierarchy: any): void`

**Parameters:**

- **`hierarchy`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (hierarchy) {
    this.hierarchy = hierarchy;
  }
```
</details>

### `setAsParent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this._isParent = true;
  }
```
</details>

### `checkParenting(): void`

**Returns:** `void`

**Calls:**

- `this.comp.buildElementParenting`

<details><summary>Code</summary>

```typescript
function () {
    if (this.data.parent !== undefined) {
      this.comp.buildElementParenting(this, this.data.parent, []);
    }
  }
```
</details>

### `RenderableDOMElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RenderableDOMElement() {}
```
</details>

### `initElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initBaseData`
- `this.initTransform`
- `this.initHierarchy`
- `this.initRenderable`
- `this.initRendererElement`
- `this.createContainerElements`
- `this.createRenderableComponents`
- `this.createContent`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
      this.initFrame();
      this.initBaseData(data, globalData, comp);
      this.initTransform(data, globalData, comp);
      this.initHierarchy();
      this.initRenderable();
      this.initRendererElement();
      this.createContainerElements();
      this.createRenderableComponents();
      this.createContent();
      this.hide();
    }
```
</details>

### `hide(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('HIDE', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('HIDE', this);
      if (!this.hidden && (!this.isInRange || this.isTransparent)) {
        var elem = this.baseElement || this.layerElement;
        elem.style.display = 'none';
        this.hidden = true;
      }
    }
```
</details>

### `show(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('SHOW', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('SHOW', this);
      if (this.isInRange && !this.isTransparent) {
        if (!this.data.hd) {
          var elem = this.baseElement || this.layerElement;
          elem.style.display = 'block';
        }
        this.hidden = false;
        this._isFirstFrame = true;
      }
    }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.renderElement`
- `this.renderInnerContent`

**Internal Comments:**
```
// If it is exported as hidden (data.hd === true) no need to render
// If it is not visible no need to render
```

<details><summary>Code</summary>

```typescript
function () {
      // If it is exported as hidden (data.hd === true) no need to render
      // If it is not visible no need to render
      if (this.data.hd || this.hidden) {
        return;
      }
      this.renderTransform();
      this.renderRenderable();
      this.renderElement();
      this.renderInnerContent();
      if (this._isFirstFrame) {
        this._isFirstFrame = false;
      }
    }
```
</details>

### `renderInnerContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`
- `this.checkTransparency`

<details><summary>Code</summary>

```typescript
function (num) {
      this._mdf = false;
      this.prepareRenderableFrame(num);
      this.prepareProperties(num, this.isInRange);
      this.checkTransparency();
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.destroyBaseElement`

<details><summary>Code</summary>

```typescript
function () {
      this.innerElem = null;
      this.destroyBaseElement();
    }
```
</details>

### `initElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initBaseData`
- `this.initTransform`
- `this.initHierarchy`
- `this.initRenderable`
- `this.initRendererElement`
- `this.createContainerElements`
- `this.createRenderableComponents`
- `this.createContent`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
      this.initFrame();
      this.initBaseData(data, globalData, comp);
      this.initTransform(data, globalData, comp);
      this.initHierarchy();
      this.initRenderable();
      this.initRendererElement();
      this.createContainerElements();
      this.createRenderableComponents();
      this.createContent();
      this.hide();
    }
```
</details>

### `hide(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('HIDE', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('HIDE', this);
      if (!this.hidden && (!this.isInRange || this.isTransparent)) {
        var elem = this.baseElement || this.layerElement;
        elem.style.display = 'none';
        this.hidden = true;
      }
    }
```
</details>

### `show(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('SHOW', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('SHOW', this);
      if (this.isInRange && !this.isTransparent) {
        if (!this.data.hd) {
          var elem = this.baseElement || this.layerElement;
          elem.style.display = 'block';
        }
        this.hidden = false;
        this._isFirstFrame = true;
      }
    }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.renderElement`
- `this.renderInnerContent`

**Internal Comments:**
```
// If it is exported as hidden (data.hd === true) no need to render
// If it is not visible no need to render
```

<details><summary>Code</summary>

```typescript
function () {
      // If it is exported as hidden (data.hd === true) no need to render
      // If it is not visible no need to render
      if (this.data.hd || this.hidden) {
        return;
      }
      this.renderTransform();
      this.renderRenderable();
      this.renderElement();
      this.renderInnerContent();
      if (this._isFirstFrame) {
        this._isFirstFrame = false;
      }
    }
```
</details>

### `renderInnerContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`
- `this.checkTransparency`

<details><summary>Code</summary>

```typescript
function (num) {
      this._mdf = false;
      this.prepareRenderableFrame(num);
      this.prepareProperties(num, this.isInRange);
      this.checkTransparency();
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.destroyBaseElement`

<details><summary>Code</summary>

```typescript
function () {
      this.innerElem = null;
      this.destroyBaseElement();
    }
```
</details>

### `initElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initBaseData`
- `this.initTransform`
- `this.initHierarchy`
- `this.initRenderable`
- `this.initRendererElement`
- `this.createContainerElements`
- `this.createRenderableComponents`
- `this.createContent`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
      this.initFrame();
      this.initBaseData(data, globalData, comp);
      this.initTransform(data, globalData, comp);
      this.initHierarchy();
      this.initRenderable();
      this.initRendererElement();
      this.createContainerElements();
      this.createRenderableComponents();
      this.createContent();
      this.hide();
    }
```
</details>

### `hide(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('HIDE', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('HIDE', this);
      if (!this.hidden && (!this.isInRange || this.isTransparent)) {
        var elem = this.baseElement || this.layerElement;
        elem.style.display = 'none';
        this.hidden = true;
      }
    }
```
</details>

### `show(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('SHOW', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('SHOW', this);
      if (this.isInRange && !this.isTransparent) {
        if (!this.data.hd) {
          var elem = this.baseElement || this.layerElement;
          elem.style.display = 'block';
        }
        this.hidden = false;
        this._isFirstFrame = true;
      }
    }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.renderElement`
- `this.renderInnerContent`

**Internal Comments:**
```
// If it is exported as hidden (data.hd === true) no need to render
// If it is not visible no need to render
```

<details><summary>Code</summary>

```typescript
function () {
      // If it is exported as hidden (data.hd === true) no need to render
      // If it is not visible no need to render
      if (this.data.hd || this.hidden) {
        return;
      }
      this.renderTransform();
      this.renderRenderable();
      this.renderElement();
      this.renderInnerContent();
      if (this._isFirstFrame) {
        this._isFirstFrame = false;
      }
    }
```
</details>

### `renderInnerContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`
- `this.checkTransparency`

<details><summary>Code</summary>

```typescript
function (num) {
      this._mdf = false;
      this.prepareRenderableFrame(num);
      this.prepareProperties(num, this.isInRange);
      this.checkTransparency();
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.destroyBaseElement`

<details><summary>Code</summary>

```typescript
function () {
      this.innerElem = null;
      this.destroyBaseElement();
    }
```
</details>

### `initElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initBaseData`
- `this.initTransform`
- `this.initHierarchy`
- `this.initRenderable`
- `this.initRendererElement`
- `this.createContainerElements`
- `this.createRenderableComponents`
- `this.createContent`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
      this.initFrame();
      this.initBaseData(data, globalData, comp);
      this.initTransform(data, globalData, comp);
      this.initHierarchy();
      this.initRenderable();
      this.initRendererElement();
      this.createContainerElements();
      this.createRenderableComponents();
      this.createContent();
      this.hide();
    }
```
</details>

### `hide(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('HIDE', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('HIDE', this);
      if (!this.hidden && (!this.isInRange || this.isTransparent)) {
        var elem = this.baseElement || this.layerElement;
        elem.style.display = 'none';
        this.hidden = true;
      }
    }
```
</details>

### `show(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('SHOW', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('SHOW', this);
      if (this.isInRange && !this.isTransparent) {
        if (!this.data.hd) {
          var elem = this.baseElement || this.layerElement;
          elem.style.display = 'block';
        }
        this.hidden = false;
        this._isFirstFrame = true;
      }
    }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.renderElement`
- `this.renderInnerContent`

**Internal Comments:**
```
// If it is exported as hidden (data.hd === true) no need to render
// If it is not visible no need to render
```

<details><summary>Code</summary>

```typescript
function () {
      // If it is exported as hidden (data.hd === true) no need to render
      // If it is not visible no need to render
      if (this.data.hd || this.hidden) {
        return;
      }
      this.renderTransform();
      this.renderRenderable();
      this.renderElement();
      this.renderInnerContent();
      if (this._isFirstFrame) {
        this._isFirstFrame = false;
      }
    }
```
</details>

### `renderInnerContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`
- `this.checkTransparency`

<details><summary>Code</summary>

```typescript
function (num) {
      this._mdf = false;
      this.prepareRenderableFrame(num);
      this.prepareProperties(num, this.isInRange);
      this.checkTransparency();
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.destroyBaseElement`

<details><summary>Code</summary>

```typescript
function () {
      this.innerElem = null;
      this.destroyBaseElement();
    }
```
</details>

### `initElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initBaseData`
- `this.initTransform`
- `this.initHierarchy`
- `this.initRenderable`
- `this.initRendererElement`
- `this.createContainerElements`
- `this.createRenderableComponents`
- `this.createContent`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
      this.initFrame();
      this.initBaseData(data, globalData, comp);
      this.initTransform(data, globalData, comp);
      this.initHierarchy();
      this.initRenderable();
      this.initRendererElement();
      this.createContainerElements();
      this.createRenderableComponents();
      this.createContent();
      this.hide();
    }
```
</details>

### `hide(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('HIDE', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('HIDE', this);
      if (!this.hidden && (!this.isInRange || this.isTransparent)) {
        var elem = this.baseElement || this.layerElement;
        elem.style.display = 'none';
        this.hidden = true;
      }
    }
```
</details>

### `show(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('SHOW', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('SHOW', this);
      if (this.isInRange && !this.isTransparent) {
        if (!this.data.hd) {
          var elem = this.baseElement || this.layerElement;
          elem.style.display = 'block';
        }
        this.hidden = false;
        this._isFirstFrame = true;
      }
    }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.renderElement`
- `this.renderInnerContent`

**Internal Comments:**
```
// If it is exported as hidden (data.hd === true) no need to render
// If it is not visible no need to render
```

<details><summary>Code</summary>

```typescript
function () {
      // If it is exported as hidden (data.hd === true) no need to render
      // If it is not visible no need to render
      if (this.data.hd || this.hidden) {
        return;
      }
      this.renderTransform();
      this.renderRenderable();
      this.renderElement();
      this.renderInnerContent();
      if (this._isFirstFrame) {
        this._isFirstFrame = false;
      }
    }
```
</details>

### `renderInnerContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`
- `this.checkTransparency`

<details><summary>Code</summary>

```typescript
function (num) {
      this._mdf = false;
      this.prepareRenderableFrame(num);
      this.prepareProperties(num, this.isInRange);
      this.checkTransparency();
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.destroyBaseElement`

<details><summary>Code</summary>

```typescript
function () {
      this.innerElem = null;
      this.destroyBaseElement();
    }
```
</details>

### `initElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initBaseData`
- `this.initTransform`
- `this.initHierarchy`
- `this.initRenderable`
- `this.initRendererElement`
- `this.createContainerElements`
- `this.createRenderableComponents`
- `this.createContent`
- `this.hide`

<details><summary>Code</summary>

```typescript
function (data, globalData, comp) {
      this.initFrame();
      this.initBaseData(data, globalData, comp);
      this.initTransform(data, globalData, comp);
      this.initHierarchy();
      this.initRenderable();
      this.initRendererElement();
      this.createContainerElements();
      this.createRenderableComponents();
      this.createContent();
      this.hide();
    }
```
</details>

### `hide(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('HIDE', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('HIDE', this);
      if (!this.hidden && (!this.isInRange || this.isTransparent)) {
        var elem = this.baseElement || this.layerElement;
        elem.style.display = 'none';
        this.hidden = true;
      }
    }
```
</details>

### `show(): void`

**Returns:** `void`

**Internal Comments:**
```
// console.log('SHOW', this);
```

<details><summary>Code</summary>

```typescript
function () {
      // console.log('SHOW', this);
      if (this.isInRange && !this.isTransparent) {
        if (!this.data.hd) {
          var elem = this.baseElement || this.layerElement;
          elem.style.display = 'block';
        }
        this.hidden = false;
        this._isFirstFrame = true;
      }
    }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.renderElement`
- `this.renderInnerContent`

**Internal Comments:**
```
// If it is exported as hidden (data.hd === true) no need to render
// If it is not visible no need to render
```

<details><summary>Code</summary>

```typescript
function () {
      // If it is exported as hidden (data.hd === true) no need to render
      // If it is not visible no need to render
      if (this.data.hd || this.hidden) {
        return;
      }
      this.renderTransform();
      this.renderRenderable();
      this.renderElement();
      this.renderInnerContent();
      if (this._isFirstFrame) {
        this._isFirstFrame = false;
      }
    }
```
</details>

### `renderInnerContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`
- `this.checkTransparency`

<details><summary>Code</summary>

```typescript
function (num) {
      this._mdf = false;
      this.prepareRenderableFrame(num);
      this.prepareProperties(num, this.isInRange);
      this.checkTransparency();
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.destroyBaseElement`

<details><summary>Code</summary>

```typescript
function () {
      this.innerElem = null;
      this.destroyBaseElement();
    }
```
</details>

### `IImageElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `globalData.getAssetData`
- `this.initElement`

<details><summary>Code</summary>

```typescript
function IImageElement(data, globalData, comp) {
  this.assetData = globalData.getAssetData(data.refId);
  this.initElement(data, globalData, comp);
  this.sourceRect = {
    top: 0, left: 0, width: this.assetData.w, height: this.assetData.h,
  };
}
```
</details>

### `ProcessedElement(element: any, position: any): void`

**Parameters:**

- **`element`** `any`
- **`position`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ProcessedElement(element, position) {
  this.elem = element;
  this.pos = position;
}
```
</details>

### `IShapeElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function IShapeElement() {
}
```
</details>

### `addShapeToModifiers(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.shapeModifiers[i].addShape`

<details><summary>Code</summary>

```typescript
function (data) {
    var i;
    var len = this.shapeModifiers.length;
    for (i = 0; i < len; i += 1) {
      this.shapeModifiers[i].addShape(data);
    }
  }
```
</details>

### `isShapeInAnimatedModifiers(data: any): boolean`

**Parameters:**

- **`data`** `any`

**Returns:** `boolean`

**Calls:**

- `this.shapeModifiers[i].isAnimatedWithShape`

<details><summary>Code</summary>

```typescript
function (data) {
    var i = 0;
    var len = this.shapeModifiers.length;
    while (i < len) {
      if (this.shapeModifiers[i].isAnimatedWithShape(data)) {
        return true;
      }
    }
    return false;
  }
```
</details>

### `renderModifiers(): void`

**Returns:** `void`

**Calls:**

- `this.shapes[i].sh.reset`
- `this.shapeModifiers[i].processShapes`

**Internal Comments:**
```
// workaround to fix cases where a repeater resets the shape so the following processes get called twice
// TODO: find a better solution for this
```

<details><summary>Code</summary>

```typescript
function () {
    if (!this.shapeModifiers.length) {
      return;
    }
    var i;
    var len = this.shapes.length;
    for (i = 0; i < len; i += 1) {
      this.shapes[i].sh.reset();
    }

    len = this.shapeModifiers.length;
    var shouldBreakProcess;
    for (i = len - 1; i >= 0; i -= 1) {
      shouldBreakProcess = this.shapeModifiers[i].processShapes(this._isFirstFrame);
      // workaround to fix cases where a repeater resets the shape so the following processes get called twice
      // TODO: find a better solution for this
      if (shouldBreakProcess) {
        break;
      }
    }
  }
```
</details>

### `searchProcessedElement(elem: any): any`

**Parameters:**

- **`elem`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (elem) {
    var elements = this.processedElements;
    var i = 0;
    var len = elements.length;
    while (i < len) {
      if (elements[i].elem === elem) {
        return elements[i].pos;
      }
      i += 1;
    }
    return 0;
  }
```
</details>

### `addProcessedElement(elem: any, pos: any): void`

**Parameters:**

- **`elem`** `any`
- **`pos`** `any`

**Returns:** `void`

**Calls:**

- `elements.push`

<details><summary>Code</summary>

```typescript
function (elem, pos) {
    var elements = this.processedElements;
    var i = elements.length;
    while (i) {
      i -= 1;
      if (elements[i].elem === elem) {
        elements[i].pos = pos;
        return;
      }
    }
    elements.push(new ProcessedElement(elem, pos));
  }
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`

<details><summary>Code</summary>

```typescript
function (num) {
    this.prepareRenderableFrame(num);
    this.prepareProperties(num, this.isInRange);
  }
```
</details>

### `addShapeToModifiers(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.shapeModifiers[i].addShape`

<details><summary>Code</summary>

```typescript
function (data) {
    var i;
    var len = this.shapeModifiers.length;
    for (i = 0; i < len; i += 1) {
      this.shapeModifiers[i].addShape(data);
    }
  }
```
</details>

### `isShapeInAnimatedModifiers(data: any): boolean`

**Parameters:**

- **`data`** `any`

**Returns:** `boolean`

**Calls:**

- `this.shapeModifiers[i].isAnimatedWithShape`

<details><summary>Code</summary>

```typescript
function (data) {
    var i = 0;
    var len = this.shapeModifiers.length;
    while (i < len) {
      if (this.shapeModifiers[i].isAnimatedWithShape(data)) {
        return true;
      }
    }
    return false;
  }
```
</details>

### `renderModifiers(): void`

**Returns:** `void`

**Calls:**

- `this.shapes[i].sh.reset`
- `this.shapeModifiers[i].processShapes`

**Internal Comments:**
```
// workaround to fix cases where a repeater resets the shape so the following processes get called twice
// TODO: find a better solution for this
```

<details><summary>Code</summary>

```typescript
function () {
    if (!this.shapeModifiers.length) {
      return;
    }
    var i;
    var len = this.shapes.length;
    for (i = 0; i < len; i += 1) {
      this.shapes[i].sh.reset();
    }

    len = this.shapeModifiers.length;
    var shouldBreakProcess;
    for (i = len - 1; i >= 0; i -= 1) {
      shouldBreakProcess = this.shapeModifiers[i].processShapes(this._isFirstFrame);
      // workaround to fix cases where a repeater resets the shape so the following processes get called twice
      // TODO: find a better solution for this
      if (shouldBreakProcess) {
        break;
      }
    }
  }
```
</details>

### `searchProcessedElement(elem: any): any`

**Parameters:**

- **`elem`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (elem) {
    var elements = this.processedElements;
    var i = 0;
    var len = elements.length;
    while (i < len) {
      if (elements[i].elem === elem) {
        return elements[i].pos;
      }
      i += 1;
    }
    return 0;
  }
```
</details>

### `addProcessedElement(elem: any, pos: any): void`

**Parameters:**

- **`elem`** `any`
- **`pos`** `any`

**Returns:** `void`

**Calls:**

- `elements.push`

<details><summary>Code</summary>

```typescript
function (elem, pos) {
    var elements = this.processedElements;
    var i = elements.length;
    while (i) {
      i -= 1;
      if (elements[i].elem === elem) {
        elements[i].pos = pos;
        return;
      }
    }
    elements.push(new ProcessedElement(elem, pos));
  }
```
</details>

### `prepareFrame(num: any): void`

**Parameters:**

- **`num`** `any`

**Returns:** `void`

**Calls:**

- `this.prepareRenderableFrame`
- `this.prepareProperties`

<details><summary>Code</summary>

```typescript
function (num) {
    this.prepareRenderableFrame(num);
    this.prepareProperties(num, this.isInRange);
  }
```
</details>

### `SVGShapeData(transformers: any, level: any, shape: any): void`

**Parameters:**

- **`transformers`** `any`
- **`level`** `any`
- **`shape`** `any`

**Returns:** `void`

**Internal Comments:**
```
// TODO find if there are some cases where _isAnimated can be false. (x4)
// For now, since shapes add up with other shapes. They have to be calculated every time. (x4)
// One way of finding out is checking if all styles associated to this shape depend only of this shape (x4)
// TODO: commenting this for now since all shapes are animated (x2)
```

<details><summary>Code</summary>

```typescript
function SVGShapeData(transformers, level, shape) {
  this.caches = [];
  this.styles = [];
  this.transformers = transformers;
  this.lStr = '';
  this.sh = shape;
  this.lvl = level;
  // TODO find if there are some cases where _isAnimated can be false.
  // For now, since shapes add up with other shapes. They have to be calculated every time.
  // One way of finding out is checking if all styles associated to this shape depend only of this shape
  this._isAnimated = !!shape.k;
  // TODO: commenting this for now since all shapes are animated
  var i = 0;
  var len = transformers.length;
  while (i < len) {
    if (transformers[i].mProps.dynamicProperties.length) {
      this._isAnimated = true;
      break;
    }
    i += 1;
  }
}
```
</details>

### `SVGStyleData(data: any, level: any): void`

**Parameters:**

- **`data`** `any`
- **`level`** `any`

**Returns:** `void`

**Calls:**

- `createNS`

<details><summary>Code</summary>

```typescript
function SVGStyleData(data, level) {
  this.data = data;
  this.type = data.ty;
  this.d = '';
  this.lvl = level;
  this._mdf = false;
  this.closed = data.hd === true;
  this.pElem = createNS('path');
  this.msElem = null;
}
```
</details>

### `DashProperty(elem: any, data: any, renderer: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`renderer`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `createSizedArray`
- `createTypedArray`
- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `this.getValue`

<details><summary>Code</summary>

```typescript
function DashProperty(elem, data, renderer, container) {
  this.elem = elem;
  this.frameId = -1;
  this.dataProps = createSizedArray(data.length);
  this.renderer = renderer;
  this.k = false;
  this.dashStr = '';
  this.dashArray = createTypedArray('float32', data.length ? data.length - 1 : 0);
  this.dashoffset = createTypedArray('float32', 1);
  this.initDynamicPropertyContainer(container);
  var i;
  var len = data.length || 0;
  var prop;
  for (i = 0; i < len; i += 1) {
    prop = PropertyFactory.getProp(elem, data[i].v, 0, 0, this);
    this.k = prop.k || this.k;
    this.dataProps[i] = { n: data[i].n, p: prop };
  }
  if (!this.k) {
    this.getValue(true);
  }
  this._isAnimated = this.k;
}
```
</details>

### `SVGStrokeStyleData(elem: any, data: any, styleOb: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`styleOb`** `any`

**Returns:** `void`

**Calls:**

- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function SVGStrokeStyleData(elem, data, styleOb) {
  this.initDynamicPropertyContainer(elem);
  this.getValue = this.iterateDynamicProperties;
  this.o = PropertyFactory.getProp(elem, data.o, 0, 0.01, this);
  this.w = PropertyFactory.getProp(elem, data.w, 0, null, this);
  this.d = new DashProperty(elem, data.d || {}, 'svg', this);
  this.c = PropertyFactory.getProp(elem, data.c, 1, 255, this);
  this.style = styleOb;
  this._isAnimated = !!this._isAnimated;
}
```
</details>

### `SVGFillStyleData(elem: any, data: any, styleOb: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`styleOb`** `any`

**Returns:** `void`

**Calls:**

- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function SVGFillStyleData(elem, data, styleOb) {
  this.initDynamicPropertyContainer(elem);
  this.getValue = this.iterateDynamicProperties;
  this.o = PropertyFactory.getProp(elem, data.o, 0, 0.01, this);
  this.c = PropertyFactory.getProp(elem, data.c, 1, 255, this);
  this.style = styleOb;
}
```
</details>

### `SVGNoStyleData(elem: any, data: any, styleOb: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`styleOb`** `any`

**Returns:** `void`

**Calls:**

- `this.initDynamicPropertyContainer`

<details><summary>Code</summary>

```typescript
function SVGNoStyleData(elem, data, styleOb) {
  this.initDynamicPropertyContainer(elem);
  this.getValue = this.iterateDynamicProperties;
  this.style = styleOb;
}
```
</details>

### `GradientProperty(elem: any, data: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `createTypedArray`
- `this.checkCollapsable`
- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `this.getValue`

<details><summary>Code</summary>

```typescript
function GradientProperty(elem, data, container) {
  this.data = data;
  this.c = createTypedArray('uint8c', data.p * 4);
  var cLength = data.k.k[0].s ? (data.k.k[0].s.length - data.p * 4) : data.k.k.length - data.p * 4;
  this.o = createTypedArray('float32', cLength);
  this._cmdf = false;
  this._omdf = false;
  this._collapsable = this.checkCollapsable();
  this._hasOpacity = cLength;
  this.initDynamicPropertyContainer(container);
  this.prop = PropertyFactory.getProp(elem, data.k, 1, null, this);
  this.k = this.prop.k;
  this.getValue(true);
}
```
</details>

### `SVGGradientFillStyleData(elem: any, data: any, styleOb: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`styleOb`** `any`

**Returns:** `void`

**Calls:**

- `this.initDynamicPropertyContainer`
- `this.initGradientData`

<details><summary>Code</summary>

```typescript
function SVGGradientFillStyleData(elem, data, styleOb) {
  this.initDynamicPropertyContainer(elem);
  this.getValue = this.iterateDynamicProperties;
  this.initGradientData(elem, data, styleOb);
}
```
</details>

### `SVGGradientStrokeStyleData(elem: any, data: any, styleOb: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`styleOb`** `any`

**Returns:** `void`

**Calls:**

- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `this.initGradientData`

<details><summary>Code</summary>

```typescript
function SVGGradientStrokeStyleData(elem, data, styleOb) {
  this.initDynamicPropertyContainer(elem);
  this.getValue = this.iterateDynamicProperties;
  this.w = PropertyFactory.getProp(elem, data.w, 0, null, this);
  this.d = new DashProperty(elem, data.d || {}, 'svg', this);
  this.initGradientData(elem, data, styleOb);
  this._isAnimated = !!this._isAnimated;
}
```
</details>

### `ShapeGroupData(): void`

**Returns:** `void`

**Calls:**

- `createNS`

<details><summary>Code</summary>

```typescript
function ShapeGroupData() {
  this.it = [];
  this.prevViewData = [];
  this.gr = createNS('g');
}
```
</details>

### `SVGTransformData(mProps: any, op: any, container: any): void`

**Parameters:**

- **`mProps`** `any`
- **`op`** `any`
- **`container`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SVGTransformData(mProps, op, container) {
  this.transform = {
    mProps: mProps,
    op: op,
    container: container,
  };
  this.elements = [];
  this._isAnimated = this.transform.mProps.dynamicProperties.length || this.transform.op.effectsSequence.length;
}
```
</details>

### `buildShapeString(pathNodes: any, length: any, closed: any, mat: any): string`

**Parameters:**

- **`pathNodes`** `any`
- **`length`** `any`
- **`closed`** `any`
- **`mat`** `any`

**Returns:** `string`

**Calls:**

- `mat.applyToPointStringified`

<details><summary>Code</summary>

```typescript
function (pathNodes, length, closed, mat) {
  if (length === 0) {
    return '';
  }
  var _o = pathNodes.o;
  var _i = pathNodes.i;
  var _v = pathNodes.v;
  var i;
  var shapeString = ' M' + mat.applyToPointStringified(_v[0][0], _v[0][1]);
  for (i = 1; i < length; i += 1) {
    shapeString += ' C' + mat.applyToPointStringified(_o[i - 1][0], _o[i - 1][1]) + ' ' + mat.applyToPointStringified(_i[i][0], _i[i][1]) + ' ' + mat.applyToPointStringified(_v[i][0], _v[i][1]);
  }
  if (closed && length) {
    shapeString += ' C' + mat.applyToPointStringified(_o[i - 1][0], _o[i - 1][1]) + ' ' + mat.applyToPointStringified(_i[0][0], _i[0][1]) + ' ' + mat.applyToPointStringified(_v[0][0], _v[0][1]);
    shapeString += 'z';
  }
  return shapeString;
}
```
</details>

### `createRenderFunction(data: any): (styleData: any, itemData: any, isFirstFrame: any) => void`

**Parameters:**

- **`data`** `any`

**Returns:** `(styleData: any, itemData: any, isFirstFrame: any) => void`

<details><summary>Code</summary>

```typescript
function createRenderFunction(data) {
    switch (data.ty) {
      case 'fl':
        return renderFill;
      case 'gf':
        return renderGradient;
      case 'gs':
        return renderGradientStroke;
      case 'st':
        return renderStroke;
      case 'sh':
      case 'el':
      case 'rc':
      case 'sr':
        return renderPath;
      case 'tr':
        return renderContentTransform;
      case 'no':
        return renderNoop;
      default:
        return null;
    }
  }
```
</details>

### `renderContentTransform(styleData: any, itemData: any, isFirstFrame: any): void`

**Parameters:**

- **`styleData`** `any`
- **`itemData`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `itemData.transform.container.setAttribute`
- `itemData.transform.mProps.v.to2dCSS`

<details><summary>Code</summary>

```typescript
function renderContentTransform(styleData, itemData, isFirstFrame) {
    if (isFirstFrame || itemData.transform.op._mdf) {
      itemData.transform.container.setAttribute('opacity', itemData.transform.op.v);
    }
    if (isFirstFrame || itemData.transform.mProps._mdf) {
      itemData.transform.container.setAttribute('transform', itemData.transform.mProps.v.to2dCSS());
    }
  }
```
</details>

### `renderNoop(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function renderNoop() {

  }
```
</details>

### `renderPath(styleData: any, itemData: any, isFirstFrame: any): void`

**Parameters:**

- **`styleData`** `any`
- **`itemData`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `_matrixHelper.reset`
- `mat.transform`
- `buildShapeString`

<details><summary>Code</summary>

```typescript
function renderPath(styleData, itemData, isFirstFrame) {
    var j;
    var jLen;
    var pathStringTransformed;
    var redraw;
    var pathNodes;
    var l;
    var lLen = itemData.styles.length;
    var lvl = itemData.lvl;
    var paths;
    var mat;
    var props;
    var iterations;
    var k;
    for (l = 0; l < lLen; l += 1) {
      redraw = itemData.sh._mdf || isFirstFrame;
      if (itemData.styles[l].lvl < lvl) {
        mat = _matrixHelper.reset();
        iterations = lvl - itemData.styles[l].lvl;
        k = itemData.transformers.length - 1;
        while (!redraw && iterations > 0) {
          redraw = itemData.transformers[k].mProps._mdf || redraw;
          iterations -= 1;
          k -= 1;
        }
        if (redraw) {
          iterations = lvl - itemData.styles[l].lvl;
          k = itemData.transformers.length - 1;
          while (iterations > 0) {
            props = itemData.transformers[k].mProps.v.props;
            mat.transform(props[0], props[1], props[2], props[3], props[4], props[5], props[6], props[7], props[8], props[9], props[10], props[11], props[12], props[13], props[14], props[15]);
            iterations -= 1;
            k -= 1;
          }
        }
      } else {
        mat = _identityMatrix;
      }
      paths = itemData.sh.paths;
      jLen = paths._length;
      if (redraw) {
        pathStringTransformed = '';
        for (j = 0; j < jLen; j += 1) {
          pathNodes = paths.shapes[j];
          if (pathNodes && pathNodes._length) {
            pathStringTransformed += buildShapeString(pathNodes, pathNodes._length, pathNodes.c, mat);
          }
        }
        itemData.caches[l] = pathStringTransformed;
      } else {
        pathStringTransformed = itemData.caches[l];
      }
      itemData.styles[l].d += styleData.hd === true ? '' : pathStringTransformed;
      itemData.styles[l]._mdf = redraw || itemData.styles[l]._mdf;
    }
  }
```
</details>

### `renderFill(styleData: any, itemData: any, isFirstFrame: any): void`

**Parameters:**

- **`styleData`** `any`
- **`itemData`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `styleElem.pElem.setAttribute`
- `bmFloor`

<details><summary>Code</summary>

```typescript
function renderFill(styleData, itemData, isFirstFrame) {
    var styleElem = itemData.style;

    if (itemData.c._mdf || isFirstFrame) {
      styleElem.pElem.setAttribute('fill', 'rgb(' + bmFloor(itemData.c.v[0]) + ',' + bmFloor(itemData.c.v[1]) + ',' + bmFloor(itemData.c.v[2]) + ')');
    }
    if (itemData.o._mdf || isFirstFrame) {
      styleElem.pElem.setAttribute('fill-opacity', itemData.o.v);
    }
  }
```
</details>

### `renderGradientStroke(styleData: any, itemData: any, isFirstFrame: any): void`

**Parameters:**

- **`styleData`** `any`
- **`itemData`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `renderGradient`
- `renderStroke`

<details><summary>Code</summary>

```typescript
function renderGradientStroke(styleData, itemData, isFirstFrame) {
    renderGradient(styleData, itemData, isFirstFrame);
    renderStroke(styleData, itemData, isFirstFrame);
  }
```
</details>

### `renderGradient(styleData: any, itemData: any, isFirstFrame: any): void`

**Parameters:**

- **`styleData`** `any`
- **`itemData`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `itemData.style.pElem.setAttribute`
- `gfill.setAttribute`
- `itemData.of.setAttribute`
- `stop.setAttribute`
- `Math.sqrt`
- `Math.pow`
- `Math.atan2`
- `Math.cos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function renderGradient(styleData, itemData, isFirstFrame) {
    var gfill = itemData.gf;
    var hasOpacity = itemData.g._hasOpacity;
    var pt1 = itemData.s.v;
    var pt2 = itemData.e.v;

    if (itemData.o._mdf || isFirstFrame) {
      var attr = styleData.ty === 'gf' ? 'fill-opacity' : 'stroke-opacity';
      itemData.style.pElem.setAttribute(attr, itemData.o.v);
    }
    if (itemData.s._mdf || isFirstFrame) {
      var attr1 = styleData.t === 1 ? 'x1' : 'cx';
      var attr2 = attr1 === 'x1' ? 'y1' : 'cy';
      gfill.setAttribute(attr1, pt1[0]);
      gfill.setAttribute(attr2, pt1[1]);
      if (hasOpacity && !itemData.g._collapsable) {
        itemData.of.setAttribute(attr1, pt1[0]);
        itemData.of.setAttribute(attr2, pt1[1]);
      }
    }
    var stops;
    var i;
    var len;
    var stop;
    if (itemData.g._cmdf || isFirstFrame) {
      stops = itemData.cst;
      var cValues = itemData.g.c;
      len = stops.length;
      for (i = 0; i < len; i += 1) {
        stop = stops[i];
        stop.setAttribute('offset', cValues[i * 4] + '%');
        stop.setAttribute('stop-color', 'rgb(' + cValues[i * 4 + 1] + ',' + cValues[i * 4 + 2] + ',' + cValues[i * 4 + 3] + ')');
      }
    }
    if (hasOpacity && (itemData.g._omdf || isFirstFrame)) {
      var oValues = itemData.g.o;
      if (itemData.g._collapsable) {
        stops = itemData.cst;
      } else {
        stops = itemData.ost;
      }
      len = stops.length;
      for (i = 0; i < len; i += 1) {
        stop = stops[i];
        if (!itemData.g._collapsable) {
          stop.setAttribute('offset', oValues[i * 2] + '%');
        }
        stop.setAttribute('stop-opacity', oValues[i * 2 + 1]);
      }
    }
    if (styleData.t === 1) {
      if (itemData.e._mdf || isFirstFrame) {
        gfill.setAttribute('x2', pt2[0]);
        gfill.setAttribute('y2', pt2[1]);
        if (hasOpacity && !itemData.g._collapsable) {
          itemData.of.setAttribute('x2', pt2[0]);
          itemData.of.setAttribute('y2', pt2[1]);
        }
      }
    } else {
      var rad;
      if (itemData.s._mdf || itemData.e._mdf || isFirstFrame) {
        rad = Math.sqrt(Math.pow(pt1[0] - pt2[0], 2) + Math.pow(pt1[1] - pt2[1], 2));
        gfill.setAttribute('r', rad);
        if (hasOpacity && !itemData.g._collapsable) {
          itemData.of.setAttribute('r', rad);
        }
      }
      if (itemData.e._mdf || itemData.h._mdf || itemData.a._mdf || isFirstFrame) {
        if (!rad) {
          rad = Math.sqrt(Math.pow(pt1[0] - pt2[0], 2) + Math.pow(pt1[1] - pt2[1], 2));
        }
        var ang = Math.atan2(pt2[1] - pt1[1], pt2[0] - pt1[0]);

        var percent = itemData.h.v;
        if (percent >= 1) {
          percent = 0.99;
        } else if (percent <= -1) {
          percent = -0.99;
        }
        var dist = rad * percent;
        var x = Math.cos(ang + itemData.a.v) * dist + pt1[0];
        var y = Math.sin(ang + itemData.a.v) * dist + pt1[1];
        gfill.setAttribute('fx', x);
        gfill.setAttribute('fy', y);
        if (hasOpacity && !itemData.g._collapsable) {
          itemData.of.setAttribute('fx', x);
          itemData.of.setAttribute('fy', y);
        }
      }
      // gfill.setAttribute('fy','200');
    }
  }
```
</details>

### `renderStroke(styleData: any, itemData: any, isFirstFrame: any): void`

**Parameters:**

- **`styleData`** `any`
- **`itemData`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `styleElem.pElem.setAttribute`
- `bmFloor`
- `styleElem.msElem.setAttribute`

<details><summary>Code</summary>

```typescript
function renderStroke(styleData, itemData, isFirstFrame) {
    var styleElem = itemData.style;
    var d = itemData.d;
    if (d && (d._mdf || isFirstFrame) && d.dashStr) {
      styleElem.pElem.setAttribute('stroke-dasharray', d.dashStr);
      styleElem.pElem.setAttribute('stroke-dashoffset', d.dashoffset[0]);
    }
    if (itemData.c && (itemData.c._mdf || isFirstFrame)) {
      styleElem.pElem.setAttribute('stroke', 'rgb(' + bmFloor(itemData.c.v[0]) + ',' + bmFloor(itemData.c.v[1]) + ',' + bmFloor(itemData.c.v[2]) + ')');
    }
    if (itemData.o._mdf || isFirstFrame) {
      styleElem.pElem.setAttribute('stroke-opacity', itemData.o.v);
    }
    if (itemData.w._mdf || isFirstFrame) {
      styleElem.pElem.setAttribute('stroke-width', itemData.w.v);
      if (styleElem.msElem) {
        styleElem.msElem.setAttribute('stroke-width', itemData.w.v);
      }
    }
  }
```
</details>

### `SVGShapeElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initElement`

**Internal Comments:**
```
// List of drawable elements (x4)
// Full shape data (x4)
// List of styles that will be applied to shapes (x4)
// List of modifiers that will be applied to shapes (x4)
// List of items in shape tree (x4)
// List of items in previous shape tree (x4)
// List of animated components (x4)
// Moving any property that doesn't get too much access after initialization because of v8 way of handling more than 10 properties. (x4)
// List of elements that have been created (x4)
```

<details><summary>Code</summary>

```typescript
function SVGShapeElement(data, globalData, comp) {
  // List of drawable elements
  this.shapes = [];
  // Full shape data
  this.shapesData = data.shapes;
  // List of styles that will be applied to shapes
  this.stylesList = [];
  // List of modifiers that will be applied to shapes
  this.shapeModifiers = [];
  // List of items in shape tree
  this.itemsData = [];
  // List of items in previous shape tree
  this.processedElements = [];
  // List of animated components
  this.animatedContents = [];
  this.initElement(data, globalData, comp);
  // Moving any property that doesn't get too much access after initialization because of v8 way of handling more than 10 properties.
  // List of elements that have been created
  this.prevViewData = [];
  // Moving any property that doesn't get too much access after initialization because of v8 way of handling more than 10 properties.
}
```
</details>

### `LetterProps(o: any, sw: any, sc: any, fc: any, m: any, p: any): void`

**Parameters:**

- **`o`** `any`
- **`sw`** `any`
- **`sc`** `any`
- **`fc`** `any`
- **`m`** `any`
- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function LetterProps(o, sw, sc, fc, m, p) {
  this.o = o;
  this.sw = sw;
  this.sc = sc;
  this.fc = fc;
  this.m = m;
  this.p = p;
  this._mdf = {
    o: true,
    sw: !!sw,
    sc: !!sc,
    fc: !!fc,
    m: true,
    p: true,
  };
}
```
</details>

### `TextProperty(elem: any, data: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.copyData`
- `this.searchProperty`
- `this.completeTextData`

<details><summary>Code</summary>

```typescript
function TextProperty(elem, data) {
  this._frameId = initialDefaultFrame;
  this.pv = '';
  this.v = '';
  this.kf = false;
  this._isFirstFrame = true;
  this._mdf = false;
  this.data = data;
  this.elem = elem;
  this.comp = this.elem.comp;
  this.keysIndex = 0;
  this.canResize = false;
  this.minimumFontSize = 1;
  this.effectsSequence = [];
  this.currentData = {
    ascent: 0,
    boxWidth: this.defaultBoxWidth,
    f: '',
    fStyle: '',
    fWeight: '',
    fc: '',
    j: '',
    justifyOffset: '',
    l: [],
    lh: 0,
    lineWidths: [],
    ls: '',
    of: '',
    s: '',
    sc: '',
    sw: 0,
    t: 0,
    tr: 0,
    sz: 0,
    ps: null,
    fillColorAnim: false,
    strokeColorAnim: false,
    strokeWidthAnim: false,
    yOffset: 0,
    finalSize: 0,
    finalText: [],
    finalLineHeight: 0,
    __complete: false,

  };
  this.copyData(this.currentData, this.data.d.k[0].s);

  if (!this.searchProperty()) {
    this.completeTextData(this.currentData);
  }
}
```
</details>

### `TextSelectorPropFactory(elem: any, data: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.initDynamicPropertyContainer`
- `PropertyFactory.getProp`
- `this.getValue`

<details><summary>Code</summary>

```typescript
function TextSelectorPropFactory(elem, data) {
    this._currentTextLength = -1;
    this.k = false;
    this.data = data;
    this.elem = elem;
    this.comp = elem.comp;
    this.finalS = 0;
    this.finalE = 0;
    this.initDynamicPropertyContainer(elem);
    this.s = PropertyFactory.getProp(elem, data.s || { k: 0 }, 0, 0, this);
    if ('e' in data) {
      this.e = PropertyFactory.getProp(elem, data.e, 0, 0, this);
    } else {
      this.e = { v: 100 };
    }
    this.o = PropertyFactory.getProp(elem, data.o || { k: 0 }, 0, 0, this);
    this.xe = PropertyFactory.getProp(elem, data.xe || { k: 0 }, 0, 0, this);
    this.ne = PropertyFactory.getProp(elem, data.ne || { k: 0 }, 0, 0, this);
    this.sm = PropertyFactory.getProp(elem, data.sm || { k: 100 }, 0, 0, this);
    this.a = PropertyFactory.getProp(elem, data.a, 0, 0.01, this);
    if (!this.dynamicProperties.length) {
      this.getValue();
    }
  }
```
</details>

### `getMult(ind: any): number`

**Parameters:**

- **`ind`** `any`

**Returns:** `number`

**Calls:**

- `this.getValue`
- `BezierFactory.getBezierEasing`
- `max`
- `min`
- `easer`
- `Math.sqrt`
- `Math.cos`
- `floor`

**Internal Comments:**
```
/* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */ (x3)
// Smoothness implementation.
// The smoothness represents a reduced range of the original [0; 1] range.
// if smoothness is 25%, the new range will be [0.375; 0.625]
// Steps are:
// - find the lower value of the new range (threshold)
// - if multiplier is smaller than that value, floor it to 0
// - if it is larger,
//     - subtract the threshold
//     - divide it by the smoothness (this will return the range to [0; 1])
// Note: If it doesn't work on some scenarios, consider applying it before the easer.
```

<details><summary>Code</summary>

```typescript
function (ind) {
      if (this._currentTextLength !== this.elem.textProperty.currentData.l.length) {
        this.getValue();
      }
      var x1 = 0;
      var y1 = 0;
      var x2 = 1;
      var y2 = 1;
      if (this.ne.v > 0) {
        x1 = this.ne.v / 100.0;
      } else {
        y1 = -this.ne.v / 100.0;
      }
      if (this.xe.v > 0) {
        x2 = 1.0 - this.xe.v / 100.0;
      } else {
        y2 = 1.0 + this.xe.v / 100.0;
      }
      var easer = BezierFactory.getBezierEasing(x1, y1, x2, y2).get;

      var mult = 0;
      var s = this.finalS;
      var e = this.finalE;
      var type = this.data.sh;
      if (type === 2) {
        if (e === s) {
          mult = ind >= e ? 1 : 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }
        mult = easer(mult);
      } else if (type === 3) {
        if (e === s) {
          mult = ind >= e ? 0 : 1;
        } else {
          mult = 1 - max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }

        mult = easer(mult);
      } else if (type === 4) {
        if (e === s) {
          mult = 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
          if (mult < 0.5) {
            mult *= 2;
          } else {
            mult = 1 - 2 * (mult - 0.5);
          }
        }
        mult = easer(mult);
      } else if (type === 5) {
        if (e === s) {
          mult = 0;
        } else {
          var tot = e - s;
          /* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */
          ind = min(max(0, ind + 0.5 - s), e - s);
          var x = -tot / 2 + ind;
          var a = tot / 2;
          mult = Math.sqrt(1 - (x * x) / (a * a));
        }
        mult = easer(mult);
      } else if (type === 6) {
        if (e === s) {
          mult = 0;
        } else {
          ind = min(max(0, ind + 0.5 - s), e - s);
          mult = (1 + (Math.cos((Math.PI + Math.PI * 2 * (ind) / (e - s))))) / 2; // eslint-disable-line
        }
        mult = easer(mult);
      } else {
        if (ind >= floor(s)) {
          if (ind - s < 0) {
            mult = max(0, min(min(e, 1) - (s - ind), 1));
          } else {
            mult = max(0, min(e - ind, 1));
          }
        }
        mult = easer(mult);
      }
      // Smoothness implementation.
      // The smoothness represents a reduced range of the original [0; 1] range.
      // if smoothness is 25%, the new range will be [0.375; 0.625]
      // Steps are:
      // - find the lower value of the new range (threshold)
      // - if multiplier is smaller than that value, floor it to 0
      // - if it is larger,
      //     - subtract the threshold
      //     - divide it by the smoothness (this will return the range to [0; 1])
      // Note: If it doesn't work on some scenarios, consider applying it before the easer.
      if (this.sm.v !== 100) {
        var smoothness = this.sm.v * 0.01;
        if (smoothness === 0) {
          smoothness = 0.00000001;
        }
        var threshold = 0.5 - smoothness * 0.5;
        if (mult < threshold) {
          mult = 0;
        } else {
          mult = (mult - threshold) / smoothness;
          if (mult > 1) {
            mult = 1;
          }
        }
      }
      return mult * this.a.v;
    }
```
</details>

### `getValue(newCharsFlag: any): void`

**Parameters:**

- **`newCharsFlag`** `any`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`

<details><summary>Code</summary>

```typescript
function (newCharsFlag) {
      this.iterateDynamicProperties();
      this._mdf = newCharsFlag || this._mdf;
      this._currentTextLength = this.elem.textProperty.currentData.l.length || 0;
      if (newCharsFlag && this.data.r === 2) {
        this.e.v = this._currentTextLength;
      }
      var divisor = this.data.r === 2 ? 1 : 100 / this.data.totalChars;
      var o = this.o.v / divisor;
      var s = this.s.v / divisor + o;
      var e = (this.e.v / divisor) + o;
      if (s > e) {
        var _s = s;
        s = e;
        e = _s;
      }
      this.finalS = s;
      this.finalE = e;
    }
```
</details>

### `getMult(ind: any): number`

**Parameters:**

- **`ind`** `any`

**Returns:** `number`

**Calls:**

- `this.getValue`
- `BezierFactory.getBezierEasing`
- `max`
- `min`
- `easer`
- `Math.sqrt`
- `Math.cos`
- `floor`

**Internal Comments:**
```
/* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */ (x3)
// Smoothness implementation.
// The smoothness represents a reduced range of the original [0; 1] range.
// if smoothness is 25%, the new range will be [0.375; 0.625]
// Steps are:
// - find the lower value of the new range (threshold)
// - if multiplier is smaller than that value, floor it to 0
// - if it is larger,
//     - subtract the threshold
//     - divide it by the smoothness (this will return the range to [0; 1])
// Note: If it doesn't work on some scenarios, consider applying it before the easer.
```

<details><summary>Code</summary>

```typescript
function (ind) {
      if (this._currentTextLength !== this.elem.textProperty.currentData.l.length) {
        this.getValue();
      }
      var x1 = 0;
      var y1 = 0;
      var x2 = 1;
      var y2 = 1;
      if (this.ne.v > 0) {
        x1 = this.ne.v / 100.0;
      } else {
        y1 = -this.ne.v / 100.0;
      }
      if (this.xe.v > 0) {
        x2 = 1.0 - this.xe.v / 100.0;
      } else {
        y2 = 1.0 + this.xe.v / 100.0;
      }
      var easer = BezierFactory.getBezierEasing(x1, y1, x2, y2).get;

      var mult = 0;
      var s = this.finalS;
      var e = this.finalE;
      var type = this.data.sh;
      if (type === 2) {
        if (e === s) {
          mult = ind >= e ? 1 : 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }
        mult = easer(mult);
      } else if (type === 3) {
        if (e === s) {
          mult = ind >= e ? 0 : 1;
        } else {
          mult = 1 - max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }

        mult = easer(mult);
      } else if (type === 4) {
        if (e === s) {
          mult = 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
          if (mult < 0.5) {
            mult *= 2;
          } else {
            mult = 1 - 2 * (mult - 0.5);
          }
        }
        mult = easer(mult);
      } else if (type === 5) {
        if (e === s) {
          mult = 0;
        } else {
          var tot = e - s;
          /* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */
          ind = min(max(0, ind + 0.5 - s), e - s);
          var x = -tot / 2 + ind;
          var a = tot / 2;
          mult = Math.sqrt(1 - (x * x) / (a * a));
        }
        mult = easer(mult);
      } else if (type === 6) {
        if (e === s) {
          mult = 0;
        } else {
          ind = min(max(0, ind + 0.5 - s), e - s);
          mult = (1 + (Math.cos((Math.PI + Math.PI * 2 * (ind) / (e - s))))) / 2; // eslint-disable-line
        }
        mult = easer(mult);
      } else {
        if (ind >= floor(s)) {
          if (ind - s < 0) {
            mult = max(0, min(min(e, 1) - (s - ind), 1));
          } else {
            mult = max(0, min(e - ind, 1));
          }
        }
        mult = easer(mult);
      }
      // Smoothness implementation.
      // The smoothness represents a reduced range of the original [0; 1] range.
      // if smoothness is 25%, the new range will be [0.375; 0.625]
      // Steps are:
      // - find the lower value of the new range (threshold)
      // - if multiplier is smaller than that value, floor it to 0
      // - if it is larger,
      //     - subtract the threshold
      //     - divide it by the smoothness (this will return the range to [0; 1])
      // Note: If it doesn't work on some scenarios, consider applying it before the easer.
      if (this.sm.v !== 100) {
        var smoothness = this.sm.v * 0.01;
        if (smoothness === 0) {
          smoothness = 0.00000001;
        }
        var threshold = 0.5 - smoothness * 0.5;
        if (mult < threshold) {
          mult = 0;
        } else {
          mult = (mult - threshold) / smoothness;
          if (mult > 1) {
            mult = 1;
          }
        }
      }
      return mult * this.a.v;
    }
```
</details>

### `getValue(newCharsFlag: any): void`

**Parameters:**

- **`newCharsFlag`** `any`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`

<details><summary>Code</summary>

```typescript
function (newCharsFlag) {
      this.iterateDynamicProperties();
      this._mdf = newCharsFlag || this._mdf;
      this._currentTextLength = this.elem.textProperty.currentData.l.length || 0;
      if (newCharsFlag && this.data.r === 2) {
        this.e.v = this._currentTextLength;
      }
      var divisor = this.data.r === 2 ? 1 : 100 / this.data.totalChars;
      var o = this.o.v / divisor;
      var s = this.s.v / divisor + o;
      var e = (this.e.v / divisor) + o;
      if (s > e) {
        var _s = s;
        s = e;
        e = _s;
      }
      this.finalS = s;
      this.finalE = e;
    }
```
</details>

### `getTextSelectorProp(elem: any, data: any, arr: any): TextSelectorPropFactory`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`arr`** `any`

**Returns:** `TextSelectorPropFactory`

<details><summary>Code</summary>

```typescript
function getTextSelectorProp(elem, data, arr) {
    return new TextSelectorPropFactory(elem, data, arr);
  }
```
</details>

### `getMult(ind: any): number`

**Parameters:**

- **`ind`** `any`

**Returns:** `number`

**Calls:**

- `this.getValue`
- `BezierFactory.getBezierEasing`
- `max`
- `min`
- `easer`
- `Math.sqrt`
- `Math.cos`
- `floor`

**Internal Comments:**
```
/* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */ (x3)
// Smoothness implementation.
// The smoothness represents a reduced range of the original [0; 1] range.
// if smoothness is 25%, the new range will be [0.375; 0.625]
// Steps are:
// - find the lower value of the new range (threshold)
// - if multiplier is smaller than that value, floor it to 0
// - if it is larger,
//     - subtract the threshold
//     - divide it by the smoothness (this will return the range to [0; 1])
// Note: If it doesn't work on some scenarios, consider applying it before the easer.
```

<details><summary>Code</summary>

```typescript
function (ind) {
      if (this._currentTextLength !== this.elem.textProperty.currentData.l.length) {
        this.getValue();
      }
      var x1 = 0;
      var y1 = 0;
      var x2 = 1;
      var y2 = 1;
      if (this.ne.v > 0) {
        x1 = this.ne.v / 100.0;
      } else {
        y1 = -this.ne.v / 100.0;
      }
      if (this.xe.v > 0) {
        x2 = 1.0 - this.xe.v / 100.0;
      } else {
        y2 = 1.0 + this.xe.v / 100.0;
      }
      var easer = BezierFactory.getBezierEasing(x1, y1, x2, y2).get;

      var mult = 0;
      var s = this.finalS;
      var e = this.finalE;
      var type = this.data.sh;
      if (type === 2) {
        if (e === s) {
          mult = ind >= e ? 1 : 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }
        mult = easer(mult);
      } else if (type === 3) {
        if (e === s) {
          mult = ind >= e ? 0 : 1;
        } else {
          mult = 1 - max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }

        mult = easer(mult);
      } else if (type === 4) {
        if (e === s) {
          mult = 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
          if (mult < 0.5) {
            mult *= 2;
          } else {
            mult = 1 - 2 * (mult - 0.5);
          }
        }
        mult = easer(mult);
      } else if (type === 5) {
        if (e === s) {
          mult = 0;
        } else {
          var tot = e - s;
          /* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */
          ind = min(max(0, ind + 0.5 - s), e - s);
          var x = -tot / 2 + ind;
          var a = tot / 2;
          mult = Math.sqrt(1 - (x * x) / (a * a));
        }
        mult = easer(mult);
      } else if (type === 6) {
        if (e === s) {
          mult = 0;
        } else {
          ind = min(max(0, ind + 0.5 - s), e - s);
          mult = (1 + (Math.cos((Math.PI + Math.PI * 2 * (ind) / (e - s))))) / 2; // eslint-disable-line
        }
        mult = easer(mult);
      } else {
        if (ind >= floor(s)) {
          if (ind - s < 0) {
            mult = max(0, min(min(e, 1) - (s - ind), 1));
          } else {
            mult = max(0, min(e - ind, 1));
          }
        }
        mult = easer(mult);
      }
      // Smoothness implementation.
      // The smoothness represents a reduced range of the original [0; 1] range.
      // if smoothness is 25%, the new range will be [0.375; 0.625]
      // Steps are:
      // - find the lower value of the new range (threshold)
      // - if multiplier is smaller than that value, floor it to 0
      // - if it is larger,
      //     - subtract the threshold
      //     - divide it by the smoothness (this will return the range to [0; 1])
      // Note: If it doesn't work on some scenarios, consider applying it before the easer.
      if (this.sm.v !== 100) {
        var smoothness = this.sm.v * 0.01;
        if (smoothness === 0) {
          smoothness = 0.00000001;
        }
        var threshold = 0.5 - smoothness * 0.5;
        if (mult < threshold) {
          mult = 0;
        } else {
          mult = (mult - threshold) / smoothness;
          if (mult > 1) {
            mult = 1;
          }
        }
      }
      return mult * this.a.v;
    }
```
</details>

### `getValue(newCharsFlag: any): void`

**Parameters:**

- **`newCharsFlag`** `any`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`

<details><summary>Code</summary>

```typescript
function (newCharsFlag) {
      this.iterateDynamicProperties();
      this._mdf = newCharsFlag || this._mdf;
      this._currentTextLength = this.elem.textProperty.currentData.l.length || 0;
      if (newCharsFlag && this.data.r === 2) {
        this.e.v = this._currentTextLength;
      }
      var divisor = this.data.r === 2 ? 1 : 100 / this.data.totalChars;
      var o = this.o.v / divisor;
      var s = this.s.v / divisor + o;
      var e = (this.e.v / divisor) + o;
      if (s > e) {
        var _s = s;
        s = e;
        e = _s;
      }
      this.finalS = s;
      this.finalE = e;
    }
```
</details>

### `getMult(ind: any): number`

**Parameters:**

- **`ind`** `any`

**Returns:** `number`

**Calls:**

- `this.getValue`
- `BezierFactory.getBezierEasing`
- `max`
- `min`
- `easer`
- `Math.sqrt`
- `Math.cos`
- `floor`

**Internal Comments:**
```
/* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */ (x3)
// Smoothness implementation.
// The smoothness represents a reduced range of the original [0; 1] range.
// if smoothness is 25%, the new range will be [0.375; 0.625]
// Steps are:
// - find the lower value of the new range (threshold)
// - if multiplier is smaller than that value, floor it to 0
// - if it is larger,
//     - subtract the threshold
//     - divide it by the smoothness (this will return the range to [0; 1])
// Note: If it doesn't work on some scenarios, consider applying it before the easer.
```

<details><summary>Code</summary>

```typescript
function (ind) {
      if (this._currentTextLength !== this.elem.textProperty.currentData.l.length) {
        this.getValue();
      }
      var x1 = 0;
      var y1 = 0;
      var x2 = 1;
      var y2 = 1;
      if (this.ne.v > 0) {
        x1 = this.ne.v / 100.0;
      } else {
        y1 = -this.ne.v / 100.0;
      }
      if (this.xe.v > 0) {
        x2 = 1.0 - this.xe.v / 100.0;
      } else {
        y2 = 1.0 + this.xe.v / 100.0;
      }
      var easer = BezierFactory.getBezierEasing(x1, y1, x2, y2).get;

      var mult = 0;
      var s = this.finalS;
      var e = this.finalE;
      var type = this.data.sh;
      if (type === 2) {
        if (e === s) {
          mult = ind >= e ? 1 : 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }
        mult = easer(mult);
      } else if (type === 3) {
        if (e === s) {
          mult = ind >= e ? 0 : 1;
        } else {
          mult = 1 - max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
        }

        mult = easer(mult);
      } else if (type === 4) {
        if (e === s) {
          mult = 0;
        } else {
          mult = max(0, min(0.5 / (e - s) + (ind - s) / (e - s), 1));
          if (mult < 0.5) {
            mult *= 2;
          } else {
            mult = 1 - 2 * (mult - 0.5);
          }
        }
        mult = easer(mult);
      } else if (type === 5) {
        if (e === s) {
          mult = 0;
        } else {
          var tot = e - s;
          /* ind += 0.5;
                    mult = -4/(tot*tot)*(ind*ind)+(4/tot)*ind; */
          ind = min(max(0, ind + 0.5 - s), e - s);
          var x = -tot / 2 + ind;
          var a = tot / 2;
          mult = Math.sqrt(1 - (x * x) / (a * a));
        }
        mult = easer(mult);
      } else if (type === 6) {
        if (e === s) {
          mult = 0;
        } else {
          ind = min(max(0, ind + 0.5 - s), e - s);
          mult = (1 + (Math.cos((Math.PI + Math.PI * 2 * (ind) / (e - s))))) / 2; // eslint-disable-line
        }
        mult = easer(mult);
      } else {
        if (ind >= floor(s)) {
          if (ind - s < 0) {
            mult = max(0, min(min(e, 1) - (s - ind), 1));
          } else {
            mult = max(0, min(e - ind, 1));
          }
        }
        mult = easer(mult);
      }
      // Smoothness implementation.
      // The smoothness represents a reduced range of the original [0; 1] range.
      // if smoothness is 25%, the new range will be [0.375; 0.625]
      // Steps are:
      // - find the lower value of the new range (threshold)
      // - if multiplier is smaller than that value, floor it to 0
      // - if it is larger,
      //     - subtract the threshold
      //     - divide it by the smoothness (this will return the range to [0; 1])
      // Note: If it doesn't work on some scenarios, consider applying it before the easer.
      if (this.sm.v !== 100) {
        var smoothness = this.sm.v * 0.01;
        if (smoothness === 0) {
          smoothness = 0.00000001;
        }
        var threshold = 0.5 - smoothness * 0.5;
        if (mult < threshold) {
          mult = 0;
        } else {
          mult = (mult - threshold) / smoothness;
          if (mult > 1) {
            mult = 1;
          }
        }
      }
      return mult * this.a.v;
    }
```
</details>

### `getValue(newCharsFlag: any): void`

**Parameters:**

- **`newCharsFlag`** `any`

**Returns:** `void`

**Calls:**

- `this.iterateDynamicProperties`

<details><summary>Code</summary>

```typescript
function (newCharsFlag) {
      this.iterateDynamicProperties();
      this._mdf = newCharsFlag || this._mdf;
      this._currentTextLength = this.elem.textProperty.currentData.l.length || 0;
      if (newCharsFlag && this.data.r === 2) {
        this.e.v = this._currentTextLength;
      }
      var divisor = this.data.r === 2 ? 1 : 100 / this.data.totalChars;
      var o = this.o.v / divisor;
      var s = this.s.v / divisor + o;
      var e = (this.e.v / divisor) + o;
      if (s > e) {
        var _s = s;
        s = e;
        e = _s;
      }
      this.finalS = s;
      this.finalE = e;
    }
```
</details>

### `TextAnimatorDataProperty(elem: any, animatorProps: any, container: any): void`

**Parameters:**

- **`elem`** `any`
- **`animatorProps`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `getProp`
- `TextSelectorProp.getTextSelectorProp`

<details><summary>Code</summary>

```typescript
function TextAnimatorDataProperty(elem, animatorProps, container) {
  var defaultData = { propType: false };
  var getProp = PropertyFactory.getProp;
  var textAnimatorAnimatables = animatorProps.a;
  this.a = {
    r: textAnimatorAnimatables.r ? getProp(elem, textAnimatorAnimatables.r, 0, degToRads, container) : defaultData,
    rx: textAnimatorAnimatables.rx ? getProp(elem, textAnimatorAnimatables.rx, 0, degToRads, container) : defaultData,
    ry: textAnimatorAnimatables.ry ? getProp(elem, textAnimatorAnimatables.ry, 0, degToRads, container) : defaultData,
    sk: textAnimatorAnimatables.sk ? getProp(elem, textAnimatorAnimatables.sk, 0, degToRads, container) : defaultData,
    sa: textAnimatorAnimatables.sa ? getProp(elem, textAnimatorAnimatables.sa, 0, degToRads, container) : defaultData,
    s: textAnimatorAnimatables.s ? getProp(elem, textAnimatorAnimatables.s, 1, 0.01, container) : defaultData,
    a: textAnimatorAnimatables.a ? getProp(elem, textAnimatorAnimatables.a, 1, 0, container) : defaultData,
    o: textAnimatorAnimatables.o ? getProp(elem, textAnimatorAnimatables.o, 0, 0.01, container) : defaultData,
    p: textAnimatorAnimatables.p ? getProp(elem, textAnimatorAnimatables.p, 1, 0, container) : defaultData,
    sw: textAnimatorAnimatables.sw ? getProp(elem, textAnimatorAnimatables.sw, 0, 0, container) : defaultData,
    sc: textAnimatorAnimatables.sc ? getProp(elem, textAnimatorAnimatables.sc, 1, 0, container) : defaultData,
    fc: textAnimatorAnimatables.fc ? getProp(elem, textAnimatorAnimatables.fc, 1, 0, container) : defaultData,
    fh: textAnimatorAnimatables.fh ? getProp(elem, textAnimatorAnimatables.fh, 0, 0, container) : defaultData,
    fs: textAnimatorAnimatables.fs ? getProp(elem, textAnimatorAnimatables.fs, 0, 0.01, container) : defaultData,
    fb: textAnimatorAnimatables.fb ? getProp(elem, textAnimatorAnimatables.fb, 0, 0.01, container) : defaultData,
    t: textAnimatorAnimatables.t ? getProp(elem, textAnimatorAnimatables.t, 0, 0, container) : defaultData,
  };

  this.s = TextSelectorProp.getTextSelectorProp(elem, animatorProps.s, container);
  this.s.t = animatorProps.s.t;
}
```
</details>

### `TextAnimatorProperty(textData: any, renderType: any, elem: any): void`

**Parameters:**

- **`textData`** `any`
- **`renderType`** `any`
- **`elem`** `any`

**Returns:** `void`

**Calls:**

- `createSizedArray`
- `this.initDynamicPropertyContainer`

<details><summary>Code</summary>

```typescript
function TextAnimatorProperty(textData, renderType, elem) {
  this._isFirstFrame = true;
  this._hasMaskedPath = false;
  this._frameId = -1;
  this._textData = textData;
  this._renderType = renderType;
  this._elem = elem;
  this._animatorsData = createSizedArray(this._textData.a.length);
  this._pathData = {};
  this._moreOptions = {
    alignment: {},
  };
  this.renderedLetters = [];
  this.lettersChangedFlag = false;
  this.initDynamicPropertyContainer(elem);
}
```
</details>

### `ITextElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ITextElement() {
}
```
</details>

### `SVGTextLottieElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initElement`

<details><summary>Code</summary>

```typescript
function SVGTextLottieElement(data, globalData, comp) {
  this.textSpans = [];
  this.renderType = 'svg';
  this.initElement(data, globalData, comp);
}
```
</details>

### `ISolidElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initElement`

<details><summary>Code</summary>

```typescript
function ISolidElement(data, globalData, comp) {
  this.initElement(data, globalData, comp);
}
```
</details>

### `NullElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initFrame`
- `this.initBaseData`
- `this.initTransform`
- `this.initHierarchy`

<details><summary>Code</summary>

```typescript
function NullElement(data, globalData, comp) {
  this.initFrame();
  this.initBaseData(data, globalData, comp);
  this.initFrame();
  this.initTransform(data, globalData, comp);
  this.initHierarchy();
}
```
</details>

### `SVGRendererBase(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SVGRendererBase() {
}
```
</details>

### `ICompElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ICompElement() {}
```
</details>

### `SVGCompElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `createSizedArray`
- `this.initElement`
- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function SVGCompElement(data, globalData, comp) {
  this.layers = data.layers;
  this.supports3d = true;
  this.completeLayers = false;
  this.pendingElements = [];
  this.elements = this.layers ? createSizedArray(this.layers.length) : [];
  this.initElement(data, globalData, comp);
  this.tm = data.tm ? PropertyFactory.getProp(this, data.tm, 0, globalData.frameRate, this) : { _placeholder: true };
}
```
</details>

### `SVGRenderer(animationItem: any, config: any): void`

**Parameters:**

- **`animationItem`** `any`
- **`config`** `any`

**Returns:** `void`

**Calls:**

- `createNS`
- `createElementID`
- `titleElement.setAttribute`
- `this.svgElement.appendChild`
- `descElement.setAttribute`
- `this.svgElement.setAttribute`

<details><summary>Code</summary>

```typescript
function SVGRenderer(animationItem, config) {
  this.animationItem = animationItem;
  this.layers = null;
  this.renderedFrame = -1;
  this.svgElement = createNS('svg');
  var ariaLabel = '';
  if (config && config.title) {
    var titleElement = createNS('title');
    var titleId = createElementID();
    titleElement.setAttribute('id', titleId);
    titleElement.textContent = config.title;
    this.svgElement.appendChild(titleElement);
    ariaLabel += titleId;
  }
  if (config && config.description) {
    var descElement = createNS('desc');
    var descId = createElementID();
    descElement.setAttribute('id', descId);
    descElement.textContent = config.description;
    this.svgElement.appendChild(descElement);
    ariaLabel += ' ' + descId;
  }
  if (ariaLabel) {
    this.svgElement.setAttribute('aria-labelledby', ariaLabel);
  }
  var defs = createNS('defs');
  this.svgElement.appendChild(defs);
  var maskElement = createNS('g');
  this.svgElement.appendChild(maskElement);
  this.layerElement = maskElement;
  this.renderConfig = {
    preserveAspectRatio: (config && config.preserveAspectRatio) || 'xMidYMid meet',
    imagePreserveAspectRatio: (config && config.imagePreserveAspectRatio) || 'xMidYMid slice',
    contentVisibility: (config && config.contentVisibility) || 'visible',
    progressiveLoad: (config && config.progressiveLoad) || false,
    hideOnTransparent: !((config && config.hideOnTransparent === false)),
    viewBoxOnly: (config && config.viewBoxOnly) || false,
    viewBoxSize: (config && config.viewBoxSize) || false,
    className: (config && config.className) || '',
    id: (config && config.id) || '',
    focusable: config && config.focusable,
    filterSize: {
      width: (config && config.filterSize && config.filterSize.width) || '100%',
      height: (config && config.filterSize && config.filterSize.height) || '100%',
      x: (config && config.filterSize && config.filterSize.x) || '0%',
      y: (config && config.filterSize && config.filterSize.y) || '0%',
    },
    width: (config && config.width),
    height: (config && config.height),
  };

  this.globalData = {
    _mdf: false,
    frameNum: -1,
    defs: defs,
    renderConfig: this.renderConfig,
  };
  this.elements = [];
  this.pendingElements = [];
  this.destroyed = false;
  this.rendererType = 'svg';
}
```
</details>

### `CVContextData(): void`

**Returns:** `void`

**Calls:**

- `createTypedArray`

<details><summary>Code</summary>

```typescript
function CVContextData() {
  this.saved = [];
  this.cArrPos = 0;
  this.cTr = new Matrix();
  this.cO = 1;
  var i;
  var len = 15;
  this.savedOp = createTypedArray('float32', len);
  for (i = 0; i < len; i += 1) {
    this.saved[i] = createTypedArray('float32', 16);
  }
  this._length = len;
}
```
</details>

### `ShapeTransformManager(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ShapeTransformManager() {
  this.sequences = {};
  this.sequenceList = [];
  this.transform_key_count = 0;
}
```
</details>

### `addTransformSequence(transforms: any): any`

**Parameters:**

- **`transforms`** `any`

**Returns:** `any`

**Calls:**

- `[].concat`
- `this.sequenceList.push`

<details><summary>Code</summary>

```typescript
function (transforms) {
    var i;
    var len = transforms.length;
    var key = '_';
    for (i = 0; i < len; i += 1) {
      key += transforms[i].transform.key + '_';
    }
    var sequence = this.sequences[key];
    if (!sequence) {
      sequence = {
        transforms: [].concat(transforms),
        finalTransform: new Matrix(),
        _mdf: false,
      };
      this.sequences[key] = sequence;
      this.sequenceList.push(sequence);
    }
    return sequence;
  }
```
</details>

### `processSequence(sequence: any, isFirstFrame: any): void`

**Parameters:**

- **`sequence`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `sequence.finalTransform.reset`
- `sequence.finalTransform.transform`

<details><summary>Code</summary>

```typescript
function (sequence, isFirstFrame) {
    var i = 0;
    var len = sequence.transforms.length;
    var _mdf = isFirstFrame;
    while (i < len && !isFirstFrame) {
      if (sequence.transforms[i].transform.mProps._mdf) {
        _mdf = true;
        break;
      }
      i += 1;
    }
    if (_mdf) {
      var props;
      sequence.finalTransform.reset();
      for (i = len - 1; i >= 0; i -= 1) {
        props = sequence.transforms[i].transform.mProps.v.props;
        sequence.finalTransform.transform(props[0], props[1], props[2], props[3], props[4], props[5], props[6], props[7], props[8], props[9], props[10], props[11], props[12], props[13], props[14], props[15]);
      }
    }
    sequence._mdf = _mdf;
  }
```
</details>

### `processSequences(isFirstFrame: any): void`

**Parameters:**

- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `this.processSequence`

<details><summary>Code</summary>

```typescript
function (isFirstFrame) {
    var i;
    var len = this.sequenceList.length;
    for (i = 0; i < len; i += 1) {
      this.processSequence(this.sequenceList[i], isFirstFrame);
    }
  }
```
</details>

### `getNewKey(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
    this.transform_key_count += 1;
    return '_' + this.transform_key_count;
  }
```
</details>

### `addTransformSequence(transforms: any): any`

**Parameters:**

- **`transforms`** `any`

**Returns:** `any`

**Calls:**

- `[].concat`
- `this.sequenceList.push`

<details><summary>Code</summary>

```typescript
function (transforms) {
    var i;
    var len = transforms.length;
    var key = '_';
    for (i = 0; i < len; i += 1) {
      key += transforms[i].transform.key + '_';
    }
    var sequence = this.sequences[key];
    if (!sequence) {
      sequence = {
        transforms: [].concat(transforms),
        finalTransform: new Matrix(),
        _mdf: false,
      };
      this.sequences[key] = sequence;
      this.sequenceList.push(sequence);
    }
    return sequence;
  }
```
</details>

### `processSequence(sequence: any, isFirstFrame: any): void`

**Parameters:**

- **`sequence`** `any`
- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `sequence.finalTransform.reset`
- `sequence.finalTransform.transform`

<details><summary>Code</summary>

```typescript
function (sequence, isFirstFrame) {
    var i = 0;
    var len = sequence.transforms.length;
    var _mdf = isFirstFrame;
    while (i < len && !isFirstFrame) {
      if (sequence.transforms[i].transform.mProps._mdf) {
        _mdf = true;
        break;
      }
      i += 1;
    }
    if (_mdf) {
      var props;
      sequence.finalTransform.reset();
      for (i = len - 1; i >= 0; i -= 1) {
        props = sequence.transforms[i].transform.mProps.v.props;
        sequence.finalTransform.transform(props[0], props[1], props[2], props[3], props[4], props[5], props[6], props[7], props[8], props[9], props[10], props[11], props[12], props[13], props[14], props[15]);
      }
    }
    sequence._mdf = _mdf;
  }
```
</details>

### `processSequences(isFirstFrame: any): void`

**Parameters:**

- **`isFirstFrame`** `any`

**Returns:** `void`

**Calls:**

- `this.processSequence`

<details><summary>Code</summary>

```typescript
function (isFirstFrame) {
    var i;
    var len = this.sequenceList.length;
    for (i = 0; i < len; i += 1) {
      this.processSequence(this.sequenceList[i], isFirstFrame);
    }
  }
```
</details>

### `getNewKey(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function () {
    this.transform_key_count += 1;
    return '_' + this.transform_key_count;
  }
```
</details>

### `CVEffects(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CVEffects() {

}
```
</details>

### `CVMaskElement(data: any, element: any): void`

**Parameters:**

- **`data`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `createSizedArray`
- `ShapePropertyFactory.getShapeProp`
- `this.element.addRenderableComponent`

<details><summary>Code</summary>

```typescript
function CVMaskElement(data, element) {
  this.data = data;
  this.element = element;
  this.masksProperties = this.data.masksProperties || [];
  this.viewData = createSizedArray(this.masksProperties.length);
  var i;
  var len = this.masksProperties.length;
  var hasMasks = false;
  for (i = 0; i < len; i += 1) {
    if (this.masksProperties[i].mode !== 'n') {
      hasMasks = true;
    }
    this.viewData[i] = ShapePropertyFactory.getShapeProp(this.element, this.masksProperties[i], 3);
  }
  this.hasMasks = hasMasks;
  if (hasMasks) {
    this.element.addRenderableComponent(this);
  }
}
```
</details>

### `CVBaseElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CVBaseElement() {
}
```
</details>

### `createElements(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `initRendererElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `createContainerElements(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this.canvasContext = this.globalData.canvasContext;
    this.renderableEffectsManager = new CVEffects(this);
  }
```
</details>

### `createContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setBlendMode(): void`

**Returns:** `void`

**Calls:**

- `getBlendMode`

<details><summary>Code</summary>

```typescript
function () {
    var globalData = this.globalData;
    if (globalData.blendMode !== this.data.bm) {
      globalData.blendMode = this.data.bm;
      var blendModeValue = getBlendMode(this.data.bm);
      globalData.canvasContext.globalCompositeOperation = blendModeValue;
    }
  }
```
</details>

### `createRenderableComponents(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this.maskManager = new CVMaskElement(this.data, this);
  }
```
</details>

### `hideElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    if (!this.hidden && (!this.isInRange || this.isTransparent)) {
      this.hidden = true;
    }
  }
```
</details>

### `showElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    if (this.isInRange && !this.isTransparent) {
      this.hidden = false;
      this._isFirstFrame = true;
      this.maskManager._isFirstFrame = true;
    }
  }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.setBlendMode`
- `this.globalData.renderer.save`
- `this.globalData.renderer.ctxTransform`
- `this.globalData.renderer.ctxOpacity`
- `this.renderInnerContent`
- `this.globalData.renderer.restore`

<details><summary>Code</summary>

```typescript
function () {
    if (this.hidden || this.data.hd) {
      return;
    }
    this.renderTransform();
    this.renderRenderable();
    this.setBlendMode();
    var forceRealStack = this.data.ty === 0;
    this.globalData.renderer.save(forceRealStack);
    this.globalData.renderer.ctxTransform(this.finalTransform.mat.props);
    this.globalData.renderer.ctxOpacity(this.finalTransform.mProp.o.v);
    this.renderInnerContent();
    this.globalData.renderer.restore(forceRealStack);
    if (this.maskManager.hasMasks) {
      this.globalData.renderer.restore(true);
    }
    if (this._isFirstFrame) {
      this._isFirstFrame = false;
    }
  }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.maskManager.destroy`

<details><summary>Code</summary>

```typescript
function () {
    this.canvasContext = null;
    this.data = null;
    this.globalData = null;
    this.maskManager.destroy();
  }
```
</details>

### `createElements(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `initRendererElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `createContainerElements(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this.canvasContext = this.globalData.canvasContext;
    this.renderableEffectsManager = new CVEffects(this);
  }
```
</details>

### `createContent(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `setBlendMode(): void`

**Returns:** `void`

**Calls:**

- `getBlendMode`

<details><summary>Code</summary>

```typescript
function () {
    var globalData = this.globalData;
    if (globalData.blendMode !== this.data.bm) {
      globalData.blendMode = this.data.bm;
      var blendModeValue = getBlendMode(this.data.bm);
      globalData.canvasContext.globalCompositeOperation = blendModeValue;
    }
  }
```
</details>

### `createRenderableComponents(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    this.maskManager = new CVMaskElement(this.data, this);
  }
```
</details>

### `hideElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    if (!this.hidden && (!this.isInRange || this.isTransparent)) {
      this.hidden = true;
    }
  }
```
</details>

### `showElement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {
    if (this.isInRange && !this.isTransparent) {
      this.hidden = false;
      this._isFirstFrame = true;
      this.maskManager._isFirstFrame = true;
    }
  }
```
</details>

### `renderFrame(): void`

**Returns:** `void`

**Calls:**

- `this.renderTransform`
- `this.renderRenderable`
- `this.setBlendMode`
- `this.globalData.renderer.save`
- `this.globalData.renderer.ctxTransform`
- `this.globalData.renderer.ctxOpacity`
- `this.renderInnerContent`
- `this.globalData.renderer.restore`

<details><summary>Code</summary>

```typescript
function () {
    if (this.hidden || this.data.hd) {
      return;
    }
    this.renderTransform();
    this.renderRenderable();
    this.setBlendMode();
    var forceRealStack = this.data.ty === 0;
    this.globalData.renderer.save(forceRealStack);
    this.globalData.renderer.ctxTransform(this.finalTransform.mat.props);
    this.globalData.renderer.ctxOpacity(this.finalTransform.mProp.o.v);
    this.renderInnerContent();
    this.globalData.renderer.restore(forceRealStack);
    if (this.maskManager.hasMasks) {
      this.globalData.renderer.restore(true);
    }
    if (this._isFirstFrame) {
      this._isFirstFrame = false;
    }
  }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `this.maskManager.destroy`

<details><summary>Code</summary>

```typescript
function () {
    this.canvasContext = null;
    this.data = null;
    this.globalData = null;
    this.maskManager.destroy();
  }
```
</details>

### `CVShapeData(element: any, data: any, styles: any, transformsManager: any): void`

**Parameters:**

- **`element`** `any`
- **`data`** `any`
- **`styles`** `any`
- **`transformsManager`** `any`

**Returns:** `void`

**Calls:**

- `ShapePropertyFactory.getShapeProp`
- `transformsManager.addTransformSequence`
- `this.styledShapes.push`
- `styles[i].elements.push`

<details><summary>Code</summary>

```typescript
function CVShapeData(element, data, styles, transformsManager) {
  this.styledShapes = [];
  this.tr = [0, 0, 0, 0, 0, 0];
  var ty = 4;
  if (data.ty === 'rc') {
    ty = 5;
  } else if (data.ty === 'el') {
    ty = 6;
  } else if (data.ty === 'sr') {
    ty = 7;
  }
  this.sh = ShapePropertyFactory.getShapeProp(element, data, ty, element);
  var i;
  var len = styles.length;
  var styledShape;
  for (i = 0; i < len; i += 1) {
    if (!styles[i].closed) {
      styledShape = {
        transforms: transformsManager.addTransformSequence(styles[i].transforms),
        trNodes: [],
      };
      this.styledShapes.push(styledShape);
      styles[i].elements.push(styledShape);
    }
  }
}
```
</details>

### `CVShapeElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initElement`

<details><summary>Code</summary>

```typescript
function CVShapeElement(data, globalData, comp) {
  this.shapes = [];
  this.shapesData = data.shapes;
  this.stylesList = [];
  this.itemsData = [];
  this.prevViewData = [];
  this.shapeModifiers = [];
  this.processedElements = [];
  this.transformsManager = new ShapeTransformManager();
  this.initElement(data, globalData, comp);
}
```
</details>

### `CVTextElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initElement`

<details><summary>Code</summary>

```typescript
function CVTextElement(data, globalData, comp) {
  this.textSpans = [];
  this.yOffset = 0;
  this.fillColorAnim = false;
  this.strokeColorAnim = false;
  this.strokeWidthAnim = false;
  this.stroke = false;
  this.fill = false;
  this.justifyOffset = 0;
  this.currentRender = null;
  this.renderType = 'canvas';
  this.values = {
    fill: 'rgba(0,0,0,0)',
    stroke: 'rgba(0,0,0,0)',
    sWidth: 0,
    fValue: '',
  };
  this.initElement(data, globalData, comp);
}
```
</details>

### `CVImageElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `globalData.getAssetData`
- `globalData.imageLoader.getAsset`
- `this.initElement`

<details><summary>Code</summary>

```typescript
function CVImageElement(data, globalData, comp) {
  this.assetData = globalData.getAssetData(data.refId);
  this.img = globalData.imageLoader.getAsset(this.assetData);
  this.initElement(data, globalData, comp);
}
```
</details>

### `CVSolidElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `this.initElement`

<details><summary>Code</summary>

```typescript
function CVSolidElement(data, globalData, comp) {
  this.initElement(data, globalData, comp);
}
```
</details>

### `CanvasRendererBase(animationItem: any, config: any): void`

**Parameters:**

- **`animationItem`** `any`
- **`config`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CanvasRendererBase(animationItem, config) {
  this.animationItem = animationItem;
  this.renderConfig = {
    clearCanvas: (config && config.clearCanvas !== undefined) ? config.clearCanvas : true,
    context: (config && config.context) || null,
    progressiveLoad: (config && config.progressiveLoad) || false,
    preserveAspectRatio: (config && config.preserveAspectRatio) || 'xMidYMid meet',
    imagePreserveAspectRatio: (config && config.imagePreserveAspectRatio) || 'xMidYMid slice',
    contentVisibility: (config && config.contentVisibility) || 'visible',
    className: (config && config.className) || '',
    id: (config && config.id) || '',
  };
  this.renderConfig.dpr = (config && config.dpr) || 1;
  if (this.animationItem.wrapper) {
    this.renderConfig.dpr = (config && config.dpr) || window.devicePixelRatio || 1;
  }
  this.renderedFrame = -1;
  this.globalData = {
    frameNum: -1,
    _mdf: false,
    renderConfig: this.renderConfig,
    currentGlobalAlpha: -1,
  };
  this.contextData = new CVContextData();
  this.elements = [];
  this.pendingElements = [];
  this.transformMat = new Matrix();
  this.completeLayers = false;
  this.rendererType = 'canvas';
}
```
</details>

### `CVCompElement(data: any, globalData: any, comp: any): void`

**Parameters:**

- **`data`** `any`
- **`globalData`** `any`
- **`comp`** `any`

**Returns:** `void`

**Calls:**

- `createSizedArray`
- `this.initElement`
- `PropertyFactory.getProp`

<details><summary>Code</summary>

```typescript
function CVCompElement(data, globalData, comp) {
  this.completeLayers = false;
  this.layers = data.layers;
  this.pendingElements = [];
  this.elements = createSizedArray(this.layers.length);
  this.initElement(data, globalData, comp);
  this.tm = data.tm ? PropertyFactory.getProp(this, data.tm, 0, globalData.frameRate, this) : { _placeholder: true };
}
```
</details>

### `CanvasRenderer(animationItem: any, config: any): void`

**Parameters:**

- **`animationItem`** `any`
- **`config`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CanvasRenderer(animationItem, config) {
  this.animationItem = animationItem;
  this.renderConfig = {
    clearCanvas: (config && config.clearCanvas !== undefined) ? config.clearCanvas : true,
    context: (config && config.context) || null,
    progressiveLoad: (config && config.progressiveLoad) || false,
    preserveAspectRatio: (config && config.preserveAspectRatio) || 'xMidYMid meet',
    imagePreserveAspectRatio: (config && config.imagePreserveAspectRatio) || 'xMidYMid slice',
    contentVisibility: (config && config.contentVisibility) || 'visible',
    className: (config && config.className) || '',
    id: (config && config.id) || '',
  };
  this.renderConfig.dpr = (config && config.dpr) || 1;
  if (this.animationItem.wrapper) {
    this.renderConfig.dpr = (config && config.dpr) || window.devicePixelRatio || 1;
  }
  this.renderedFrame = -1;
  this.globalData = {
    frameNum: -1,
    _mdf: false,
    renderConfig: this.renderConfig,
    currentGlobalAlpha: -1,
  };
  this.contextData = new CVContextData();
  this.elements = [];
  this.pendingElements = [];
  this.transformMat = new Matrix();
  this.completeLayers = false;
  this.rendererType = 'canvas';
}
```
</details>

### `initExpressions(animation: any): void`

**Parameters:**

- **`animation`** `any`

**Returns:** `void`

**Calls:**

- `releaseInstances`
- `registers.indexOf`
- `registers.push`
- `registers[i].release`
- `CompExpressionInterface`
- `animation.renderer.globalData.projectInterface.registerComposition`

<details><summary>Code</summary>

```typescript
function initExpressions(animation) {
    var stackCount = 0;
    var registers = [];

    function pushExpression() {
      stackCount += 1;
    }

    function popExpression() {
      stackCount -= 1;
      if (stackCount === 0) {
        releaseInstances();
      }
    }

    function registerExpressionProperty(expression) {
      if (registers.indexOf(expression) === -1) {
        registers.push(expression);
      }
    }

    function releaseInstances() {
      var i;
      var len = registers.length;
      for (i = 0; i < len; i += 1) {
        registers[i].release();
      }
      registers.length = 0;
    }

    animation.renderer.compInterface = CompExpressionInterface(animation.renderer);
    animation.renderer.globalData.projectInterface.registerComposition(animation.renderer);
    animation.renderer.globalData.pushExpression = pushExpression;
    animation.renderer.globalData.popExpression = popExpression;
    animation.renderer.globalData.registerExpressionProperty = registerExpressionProperty;
  }
```
</details>

### `pushExpression(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function pushExpression() {
      stackCount += 1;
    }
```
</details>

### `popExpression(): void`

**Returns:** `void`

**Calls:**

- `releaseInstances`

<details><summary>Code</summary>

```typescript
function popExpression() {
      stackCount -= 1;
      if (stackCount === 0) {
        releaseInstances();
      }
    }
```
</details>

### `registerExpressionProperty(expression: any): void`

**Parameters:**

- **`expression`** `any`

**Returns:** `void`

**Calls:**

- `registers.indexOf`
- `registers.push`

<details><summary>Code</summary>

```typescript
function registerExpressionProperty(expression) {
      if (registers.indexOf(expression) === -1) {
        registers.push(expression);
      }
    }
```
</details>

### `releaseInstances(): void`

**Returns:** `void`

**Calls:**

- `registers[i].release`

<details><summary>Code</summary>

```typescript
function releaseInstances() {
      var i;
      var len = registers.length;
      for (i = 0; i < len; i += 1) {
        registers[i].release();
      }
      registers.length = 0;
    }
```
</details>

### `seedRandom(pool: any, math: any): void`

**Parameters:**

- **`pool`** `any`
- **`math`** `any`

**Returns:** `void`

**Calls:**

- `math.pow`
- `mixkey`
- `flatten`
- `tostring`
- `autoseed`
- `arc4.g`
- `complex_call_431548`
- `copy`
- `f.S.slice`
- `result.push`
- `stringseed.charCodeAt`
- `nodecrypto.randomBytes`
- `(global.crypto || global.msCrypto).getRandomValues`
- `String.fromCharCode.apply`
- `math.random`

**Internal Comments:**
```
// (x26)
// The following constants are related to IEEE 754 limits. (x2)
// seedrandom()
// This is the seedrandom function described above.
// Flatten the seed string or build one from local entropy if needed. (x2)
// Use the seed to initialize an ARC4 generator. (x2)
// This function returns a random double in [0, 1) that contains (x2)
// randomness in every bit of the mantissa of the IEEE 754 value. (x2)
// Mix the randomness into accumulated entropy. (x3)
// Calling convention: what to return as a function of prng, seed, is_math.
// Load the arc4 state from the given state if it has an S array.
// Only provide the .state method if requested via options.state. (x4)
// If called as a method of Math (Math.seedrandom()), mutate
// Math.random because that is how seedrandom.js has worked since v1.0.
// ARC4
// An ARC4 implementation.  The constructor takes a key in the form of
// an array of at most (width) integers that should be 0 <= x < (width).
// The g(count) method returns a pseudorandom integer that concatenates
// the next (count) outputs from ARC4.  Its return value is a number x
// that is in the range 0 <= x < (width ^ count).
// The empty key [] is treated as [0].
// Set up S using the standard key scheduling algorithm.
// The "g" method returns the next (count) outputs as one number. (x4)
// Using instance members instead of closure state nearly doubles speed. (x2)
// copy()
// Copies internal state of ARC4 to or from a plain object.
// flatten()
// Converts an object tree to nested arrays of strings.
// mixkey()
// Mixes a string seed into a key that is an array of integers, and
// returns a shortened string seed that is equivalent to the result key.
// autoseed()
// Returns an object for autoseeding, using window.crypto and Node crypto
// module if available.
// tostring()
// Converts an array of charcodes to a string
// When seedrandom.js is loaded, we immediately mix a few bits (x3)
// from the built-in RNG into the entropy pool.  Because we do (x3)
// not want to interfere with deterministic PRNG state later, (x3)
// seedrandom will not call math.random on its own again after (x3)
// initialization. (x3)
```

<details><summary>Code</summary>

```typescript
function seedRandom(pool, math) {
//
// The following constants are related to IEEE 754 limits.
//
    var global = this,
        width = 256,        // each RC4 output is 0 <= x < 256
        chunks = 6,         // at least six RC4 outputs for each double
        digits = 52,        // there are 52 significant digits in a double
        rngname = 'random', // rngname: name for Math.random and Math.seedrandom
        startdenom = math.pow(width, chunks),
        significance = math.pow(2, digits),
        overflow = significance * 2,
        mask = width - 1,
        nodecrypto;         // node.js crypto module, initialized at the bottom.

//
// seedrandom()
// This is the seedrandom function described above.
//
    function seedrandom(seed, options, callback) {
        var key = [];
        options = (options === true) ? { entropy: true } : (options || {});

        // Flatten the seed string or build one from local entropy if needed.
        var shortseed = mixkey(flatten(
            options.entropy ? [seed, tostring(pool)] :
                (seed === null) ? autoseed() : seed, 3), key);

        // Use the seed to initialize an ARC4 generator.
        var arc4 = new ARC4(key);

        // This function returns a random double in [0, 1) that contains
        // randomness in every bit of the mantissa of the IEEE 754 value.
        var prng = function() {
            var n = arc4.g(chunks),             // Start with a numerator n < 2 ^ 48
                d = startdenom,                 //   and denominator d = 2 ^ 48.
                x = 0;                          //   and no 'extra last byte'.
            while (n < significance) {          // Fill up all significant digits by
                n = (n + x) * width;              //   shifting numerator and
                d *= width;                       //   denominator and generating a
                x = arc4.g(1);                    //   new least-significant-byte.
            }
            while (n >= overflow) {             // To avoid rounding up, before adding
                n /= 2;                           //   last byte, shift everything
                d /= 2;                           //   right using integer math until
                x >>>= 1;                         //   we have exactly the desired bits.
            }
            return (n + x) / d;                 // Form the number within [0, 1).
        };

        prng.int32 = function() { return arc4.g(4) | 0; };
        prng.quick = function() { return arc4.g(4) / 0x100000000; };
        prng.double = prng;

        // Mix the randomness into accumulated entropy.
        mixkey(tostring(arc4.S), pool);

        // Calling convention: what to return as a function of prng, seed, is_math.
        return (options.pass || callback ||
        function(prng, seed, is_math_call, state) {
            if (state) {
                // Load the arc4 state from the given state if it has an S array.
                if (state.S) { copy(state, arc4); }
                // Only provide the .state method if requested via options.state.
                prng.state = function() { return copy(arc4, {}); };
            }

            // If called as a method of Math (Math.seedrandom()), mutate
            // Math.random because that is how seedrandom.js has worked since v1.0.
            if (is_math_call) { math[rngname] = prng; return seed; }

            // Otherwise, it is a newer calling convention, so return the
            // prng directly.
            else return prng;
        })(
            prng,
            shortseed,
            'global' in options ? options.global : (this == math),
            options.state);
    }
    math['seed' + rngname] = seedrandom;

//
// ARC4
//
// An ARC4 implementation.  The constructor takes a key in the form of
// an array of at most (width) integers that should be 0 <= x < (width).
//
// The g(count) method returns a pseudorandom integer that concatenates
// the next (count) outputs from ARC4.  Its return value is a number x
// that is in the range 0 <= x < (width ^ count).
//
    function ARC4(key) {
        var t, keylen = key.length,
            me = this, i = 0, j = me.i = me.j = 0, s = me.S = [];

        // The empty key [] is treated as [0].
        if (!keylen) { key = [keylen++]; }

        // Set up S using the standard key scheduling algorithm.
        while (i < width) {
            s[i] = i++;
        }
        for (i = 0; i < width; i++) {
            s[i] = s[j = mask & (j + key[i % keylen] + (t = s[i]))];
            s[j] = t;
        }

        // The "g" method returns the next (count) outputs as one number.
        me.g = function(count) {
            // Using instance members instead of closure state nearly doubles speed.
            var t, r = 0,
                i = me.i, j = me.j, s = me.S;
            while (count--) {
                t = s[i = mask & (i + 1)];
                r = r * width + s[mask & ((s[i] = s[j = mask & (j + t)]) + (s[j] = t))];
            }
            me.i = i; me.j = j;
            return r;
            // For robust unpredictability, the function call below automatically
            // discards an initial batch of values.  This is called RC4-drop[256].
            // See http://google.com/search?q=rsa+fluhrer+response&btnI
        };
    }

//
// copy()
// Copies internal state of ARC4 to or from a plain object.
//
    function copy(f, t) {
        t.i = f.i;
        t.j = f.j;
        t.S = f.S.slice();
        return t;
    }

//
// flatten()
// Converts an object tree to nested arrays of strings.
//
    function flatten(obj, depth) {
        var result = [], typ = (typeof obj), prop;
        if (depth && typ == 'object') {
            for (prop in obj) {
                try { result.push(flatten(obj[prop], depth - 1)); } catch (e) {}
            }
        }
        return (result.length ? result : typ == 'string' ? obj : obj + '\0');
    }

//
// mixkey()
// Mixes a string seed into a key that is an array of integers, and
// returns a shortened string seed that is equivalent to the result key.
//
    function mixkey(seed, key) {
        var stringseed = seed + '', smear, j = 0;
        while (j < stringseed.length) {
            key[mask & j] =
                mask & ((smear ^= key[mask & j] * 19) + stringseed.charCodeAt(j++));
        }
        return tostring(key);
    }

//
// autoseed()
// Returns an object for autoseeding, using window.crypto and Node crypto
// module if available.
//
    function autoseed() {
        try {
            if (nodecrypto) { return tostring(nodecrypto.randomBytes(width)); }
            var out = new Uint8Array(width);
            (global.crypto || global.msCrypto).getRandomValues(out);
            return tostring(out);
        } catch (e) {
            var browser = global.navigator,
                plugins = browser && browser.plugins;
            return [+new Date(), global, plugins, global.screen, tostring(pool)];
        }
    }

//
// tostring()
// Converts an array of charcodes to a string
//
    function tostring(a) {
        return String.fromCharCode.apply(0, a);
    }

//
// When seedrandom.js is loaded, we immediately mix a few bits
// from the built-in RNG into the entropy pool.  Because we do
// not want to interfere with deterministic PRNG state later,
// seedrandom will not call math.random on its own again after
// initialization.
//
    mixkey(math.random(), pool);

//
// Nodejs and AMD support: export the implementation as a module using
// either convention.
//

// End anonymous scope, and pass initial values.
}
```
</details>

### `seedrandom(seed: any, options: any, callback: any): any`

**Parameters:**

- **`seed`** `any`
- **`options`** `any`
- **`callback`** `any`

**Returns:** `any`

**Calls:**

- `mixkey`
- `flatten`
- `tostring`
- `autoseed`
- `arc4.g`
- `complex_call_431548`
- `copy`

**Internal Comments:**
```
// Flatten the seed string or build one from local entropy if needed. (x2)
// Use the seed to initialize an ARC4 generator. (x2)
// This function returns a random double in [0, 1) that contains (x2)
// randomness in every bit of the mantissa of the IEEE 754 value. (x2)
// Mix the randomness into accumulated entropy. (x3)
// Calling convention: what to return as a function of prng, seed, is_math.
// Load the arc4 state from the given state if it has an S array.
// Only provide the .state method if requested via options.state. (x4)
// If called as a method of Math (Math.seedrandom()), mutate
// Math.random because that is how seedrandom.js has worked since v1.0.
```

<details><summary>Code</summary>

```typescript
function seedrandom(seed, options, callback) {
        var key = [];
        options = (options === true) ? { entropy: true } : (options || {});

        // Flatten the seed string or build one from local entropy if needed.
        var shortseed = mixkey(flatten(
            options.entropy ? [seed, tostring(pool)] :
                (seed === null) ? autoseed() : seed, 3), key);

        // Use the seed to initialize an ARC4 generator.
        var arc4 = new ARC4(key);

        // This function returns a random double in [0, 1) that contains
        // randomness in every bit of the mantissa of the IEEE 754 value.
        var prng = function() {
            var n = arc4.g(chunks),             // Start with a numerator n < 2 ^ 48
                d = startdenom,                 //   and denominator d = 2 ^ 48.
                x = 0;                          //   and no 'extra last byte'.
            while (n < significance) {          // Fill up all significant digits by
                n = (n + x) * width;              //   shifting numerator and
                d *= width;                       //   denominator and generating a
                x = arc4.g(1);                    //   new least-significant-byte.
            }
            while (n >= overflow) {             // To avoid rounding up, before adding
                n /= 2;                           //   last byte, shift everything
                d /= 2;                           //   right using integer math until
                x >>>= 1;                         //   we have exactly the desired bits.
            }
            return (n + x) / d;                 // Form the number within [0, 1).
        };

        prng.int32 = function() { return arc4.g(4) | 0; };
        prng.quick = function() { return arc4.g(4) / 0x100000000; };
        prng.double = prng;

        // Mix the randomness into accumulated entropy.
        mixkey(tostring(arc4.S), pool);

        // Calling convention: what to return as a function of prng, seed, is_math.
        return (options.pass || callback ||
        function(prng, seed, is_math_call, state) {
            if (state) {
                // Load the arc4 state from the given state if it has an S array.
                if (state.S) { copy(state, arc4); }
                // Only provide the .state method if requested via options.state.
                prng.state = function() { return copy(arc4, {}); };
            }

            // If called as a method of Math (Math.seedrandom()), mutate
            // Math.random because that is how seedrandom.js has worked since v1.0.
            if (is_math_call) { math[rngname] = prng; return seed; }

            // Otherwise, it is a newer calling convention, so return the
            // prng directly.
            else return prng;
        })(
            prng,
            shortseed,
            'global' in options ? options.global : (this == math),
            options.state);
    }
```
</details>

### `prng(): number`

**Returns:** `number`

**Calls:**

- `arc4.g`

<details><summary>Code</summary>

```typescript
function() {
            var n = arc4.g(chunks),             // Start with a numerator n < 2 ^ 48
                d = startdenom,                 //   and denominator d = 2 ^ 48.
                x = 0;                          //   and no 'extra last byte'.
            while (n < significance) {          // Fill up all significant digits by
                n = (n + x) * width;              //   shifting numerator and
                d *= width;                       //   denominator and generating a
                x = arc4.g(1);                    //   new least-significant-byte.
            }
            while (n >= overflow) {             // To avoid rounding up, before adding
                n /= 2;                           //   last byte, shift everything
                d /= 2;                           //   right using integer math until
                x >>>= 1;                         //   we have exactly the desired bits.
            }
            return (n + x) / d;                 // Form the number within [0, 1).
        }
```
</details>

### `ARC4(key: any): void`

**Parameters:**

- **`key`** `any`

**Returns:** `void`

**Internal Comments:**
```
// The empty key [] is treated as [0].
// Set up S using the standard key scheduling algorithm.
// The "g" method returns the next (count) outputs as one number. (x4)
// Using instance members instead of closure state nearly doubles speed. (x2)
```

<details><summary>Code</summary>

```typescript
function ARC4(key) {
        var t, keylen = key.length,
            me = this, i = 0, j = me.i = me.j = 0, s = me.S = [];

        // The empty key [] is treated as [0].
        if (!keylen) { key = [keylen++]; }

        // Set up S using the standard key scheduling algorithm.
        while (i < width) {
            s[i] = i++;
        }
        for (i = 0; i < width; i++) {
            s[i] = s[j = mask & (j + key[i % keylen] + (t = s[i]))];
            s[j] = t;
        }

        // The "g" method returns the next (count) outputs as one number.
        me.g = function(count) {
            // Using instance members instead of closure state nearly doubles speed.
            var t, r = 0,
                i = me.i, j = me.j, s = me.S;
            while (count--) {
                t = s[i = mask & (i + 1)];
                r = r * width + s[mask & ((s[i] = s[j = mask & (j + t)]) + (s[j] = t))];
            }
            me.i = i; me.j = j;
            return r;
            // For robust unpredictability, the function call below automatically
            // discards an initial batch of values.  This is called RC4-drop[256].
            // See http://google.com/search?q=rsa+fluhrer+response&btnI
        };
    }
```
</details>

### `copy(f: any, t: any): any`

**Parameters:**

- **`f`** `any`
- **`t`** `any`

**Returns:** `any`

**Calls:**

- `f.S.slice`

<details><summary>Code</summary>

```typescript
function copy(f, t) {
        t.i = f.i;
        t.j = f.j;
        t.S = f.S.slice();
        return t;
    }
```
</details>

### `flatten(obj: any, depth: any): any`

**Parameters:**

- **`obj`** `any`
- **`depth`** `any`

**Returns:** `any`

**Calls:**

- `result.push`
- `flatten`

<details><summary>Code</summary>

```typescript
function flatten(obj, depth) {
        var result = [], typ = (typeof obj), prop;
        if (depth && typ == 'object') {
            for (prop in obj) {
                try { result.push(flatten(obj[prop], depth - 1)); } catch (e) {}
            }
        }
        return (result.length ? result : typ == 'string' ? obj : obj + '\0');
    }
```
</details>

### `mixkey(seed: any, key: any): any`

**Parameters:**

- **`seed`** `any`
- **`key`** `any`

**Returns:** `any`

**Calls:**

- `stringseed.charCodeAt`
- `tostring`

<details><summary>Code</summary>

```typescript
function mixkey(seed, key) {
        var stringseed = seed + '', smear, j = 0;
        while (j < stringseed.length) {
            key[mask & j] =
                mask & ((smear ^= key[mask & j] * 19) + stringseed.charCodeAt(j++));
        }
        return tostring(key);
    }
```
</details>

### `autoseed(): any`

**Returns:** `any`

**Calls:**

- `tostring`
- `nodecrypto.randomBytes`
- `(global.crypto || global.msCrypto).getRandomValues`

<details><summary>Code</summary>

```typescript
function autoseed() {
        try {
            if (nodecrypto) { return tostring(nodecrypto.randomBytes(width)); }
            var out = new Uint8Array(width);
            (global.crypto || global.msCrypto).getRandomValues(out);
            return tostring(out);
        } catch (e) {
            var browser = global.navigator,
                plugins = browser && browser.plugins;
            return [+new Date(), global, plugins, global.screen, tostring(pool)];
        }
    }
```
</details>

### `tostring(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `String.fromCharCode.apply`

<details><summary>Code</summary>

```typescript
function tostring(a) {
        return String.fromCharCode.apply(0, a);
    }
```
</details>

### `initialize$2(BMMath: any): void`

**Parameters:**

- **`BMMath`** `any`

**Returns:** `void`

**Calls:**

- `seedRandom`

<details><summary>Code</summary>

```typescript
function initialize$2(BMMath) {
    seedRandom([], BMMath);
}
```
</details>

### `$bm_isInstanceOfArray(arr: any): boolean`

**Parameters:**

- **`arr`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function $bm_isInstanceOfArray(arr) {
    return arr.constructor === Array || arr.constructor === Float32Array;
  }
```
</details>

### `isNumerable(tOfV: any, v: any): boolean`

**Parameters:**

- **`tOfV`** `any`
- **`v`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isNumerable(tOfV, v) {
    return tOfV === 'number' || tOfV === 'boolean' || tOfV === 'string' || v instanceof Number;
  }
```
</details>

### `$bm_neg(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `$bm_isInstanceOfArray`

<details><summary>Code</summary>

```typescript
function $bm_neg(a) {
    var tOfA = typeof a;
    if (tOfA === 'number' || tOfA === 'boolean' || a instanceof Number) {
      return -a;
    }
    if ($bm_isInstanceOfArray(a)) {
      var i;
      var lenA = a.length;
      var retArr = [];
      for (i = 0; i < lenA; i += 1) {
        retArr[i] = -a[i];
      }
      return retArr;
    }
    if (a.propType) {
      return a.v;
    }
    return -a;
  }
```
</details>

### `sum(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `isNumerable`
- `$bm_isInstanceOfArray`
- `a.slice`
- `b.slice`

<details><summary>Code</summary>

```typescript
function sum(a, b) {
    var tOfA = typeof a;
    var tOfB = typeof b;
    if (tOfA === 'string' || tOfB === 'string') {
      return a + b;
    }
    if (isNumerable(tOfA, a) && isNumerable(tOfB, b)) {
      return a + b;
    }
    if ($bm_isInstanceOfArray(a) && isNumerable(tOfB, b)) {
      a = a.slice(0);
      a[0] += b;
      return a;
    }
    if (isNumerable(tOfA, a) && $bm_isInstanceOfArray(b)) {
      b = b.slice(0);
      b[0] = a + b[0];
      return b;
    }
    if ($bm_isInstanceOfArray(a) && $bm_isInstanceOfArray(b)) {
      var i = 0;
      var lenA = a.length;
      var lenB = b.length;
      var retArr = [];
      while (i < lenA || i < lenB) {
        if ((typeof a[i] === 'number' || a[i] instanceof Number) && (typeof b[i] === 'number' || b[i] instanceof Number)) {
          retArr[i] = a[i] + b[i];
        } else {
          retArr[i] = b[i] === undefined ? a[i] : a[i] || b[i];
        }
        i += 1;
      }
      return retArr;
    }
    return 0;
  }
```
</details>

### `sub(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `isNumerable`
- `parseInt`
- `$bm_isInstanceOfArray`
- `a.slice`
- `b.slice`

<details><summary>Code</summary>

```typescript
function sub(a, b) {
    var tOfA = typeof a;
    var tOfB = typeof b;
    if (isNumerable(tOfA, a) && isNumerable(tOfB, b)) {
      if (tOfA === 'string') {
        a = parseInt(a, 10);
      }
      if (tOfB === 'string') {
        b = parseInt(b, 10);
      }
      return a - b;
    }
    if ($bm_isInstanceOfArray(a) && isNumerable(tOfB, b)) {
      a = a.slice(0);
      a[0] -= b;
      return a;
    }
    if (isNumerable(tOfA, a) && $bm_isInstanceOfArray(b)) {
      b = b.slice(0);
      b[0] = a - b[0];
      return b;
    }
    if ($bm_isInstanceOfArray(a) && $bm_isInstanceOfArray(b)) {
      var i = 0;
      var lenA = a.length;
      var lenB = b.length;
      var retArr = [];
      while (i < lenA || i < lenB) {
        if ((typeof a[i] === 'number' || a[i] instanceof Number) && (typeof b[i] === 'number' || b[i] instanceof Number)) {
          retArr[i] = a[i] - b[i];
        } else {
          retArr[i] = b[i] === undefined ? a[i] : a[i] || b[i];
        }
        i += 1;
      }
      return retArr;
    }
    return 0;
  }
```
</details>

### `mul(a: any, b: any): number | number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number | number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `isNumerable`
- `$bm_isInstanceOfArray`
- `createTypedArray`

<details><summary>Code</summary>

```typescript
function mul(a, b) {
    var tOfA = typeof a;
    var tOfB = typeof b;
    var arr;
    if (isNumerable(tOfA, a) && isNumerable(tOfB, b)) {
      return a * b;
    }

    var i;
    var len;
    if ($bm_isInstanceOfArray(a) && isNumerable(tOfB, b)) {
      len = a.length;
      arr = createTypedArray('float32', len);
      for (i = 0; i < len; i += 1) {
        arr[i] = a[i] * b;
      }
      return arr;
    }
    if (isNumerable(tOfA, a) && $bm_isInstanceOfArray(b)) {
      len = b.length;
      arr = createTypedArray('float32', len);
      for (i = 0; i < len; i += 1) {
        arr[i] = a * b[i];
      }
      return arr;
    }
    return 0;
  }
```
</details>

### `div(a: any, b: any): number | number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number | number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `isNumerable`
- `$bm_isInstanceOfArray`
- `createTypedArray`

<details><summary>Code</summary>

```typescript
function div(a, b) {
    var tOfA = typeof a;
    var tOfB = typeof b;
    var arr;
    if (isNumerable(tOfA, a) && isNumerable(tOfB, b)) {
      return a / b;
    }
    var i;
    var len;
    if ($bm_isInstanceOfArray(a) && isNumerable(tOfB, b)) {
      len = a.length;
      arr = createTypedArray('float32', len);
      for (i = 0; i < len; i += 1) {
        arr[i] = a[i] / b;
      }
      return arr;
    }
    if (isNumerable(tOfA, a) && $bm_isInstanceOfArray(b)) {
      len = b.length;
      arr = createTypedArray('float32', len);
      for (i = 0; i < len; i += 1) {
        arr[i] = a / b[i];
      }
      return arr;
    }
    return 0;
  }
```
</details>

### `mod(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function mod(a, b) {
    if (typeof a === 'string') {
      a = parseInt(a, 10);
    }
    if (typeof b === 'string') {
      b = parseInt(b, 10);
    }
    return a % b;
  }
```
</details>

### `clamp(num: any, min: any, max: any): any`

**Parameters:**

- **`num`** `any`
- **`min`** `any`
- **`max`** `any`

**Returns:** `any`

**Calls:**

- `Math.min`
- `Math.max`

<details><summary>Code</summary>

```typescript
function clamp(num, min, max) {
    if (min > max) {
      var mm = max;
      max = min;
      min = mm;
    }
    return Math.min(Math.max(num, min), max);
  }
```
</details>

### `radiansToDegrees(val: any): number`

**Parameters:**

- **`val`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function radiansToDegrees(val) {
    return val / degToRads;
  }
```
</details>

### `degreesToRadians(val: any): number`

**Parameters:**

- **`val`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function degreesToRadians(val) {
    return val * degToRads;
  }
```
</details>

### `length(arr1: any, arr2: any): any`

**Parameters:**

- **`arr1`** `any`
- **`arr2`** `any`

**Returns:** `any`

**Calls:**

- `Math.abs`
- `Math.min`
- `Math.pow`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function length(arr1, arr2) {
    if (typeof arr1 === 'number' || arr1 instanceof Number) {
      arr2 = arr2 || 0;
      return Math.abs(arr1 - arr2);
    }
    if (!arr2) {
      arr2 = helperLengthArray;
    }
    var i;
    var len = Math.min(arr1.length, arr2.length);
    var addedLength = 0;
    for (i = 0; i < len; i += 1) {
      addedLength += Math.pow(arr2[i] - arr1[i], 2);
    }
    return Math.sqrt(addedLength);
  }
```
</details>

### `normalize(vec: any): number | number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Parameters:**

- **`vec`** `any`

**Returns:** `number | number[] | Float32Array<any> | Int16Array<any> | Uint8ClampedArray<any>`

**Calls:**

- `div`
- `length`

<details><summary>Code</summary>

```typescript
function normalize(vec) {
    return div(vec, length(vec));
  }
```
</details>

### `rgbToHsl(val: any): any[]`

**Parameters:**

- **`val`** `any`

**Returns:** `any[]`

**Calls:**

- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function rgbToHsl(val) {
    var r = val[0]; var g = val[1]; var b = val[2];
    var max = Math.max(r, g, b);
    var min = Math.min(r, g, b);
    var h;
    var s;
    var l = (max + min) / 2;

    if (max === min) {
      h = 0; // achromatic
      s = 0; // achromatic
    } else {
      var d = max - min;
      s = l > 0.5 ? d / (2 - max - min) : d / (max + min);
      switch (max) {
        case r: h = (g - b) / d + (g < b ? 6 : 0); break;
        case g: h = (b - r) / d + 2; break;
        case b: h = (r - g) / d + 4; break;
        default: break;
      }
      h /= 6;
    }

    return [h, s, l, val[3]];
  }
```
</details>

### `hue2rgb(p: any, q: any, t: any): any`

**Parameters:**

- **`p`** `any`
- **`q`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function hue2rgb(p, q, t) {
    if (t < 0) t += 1;
    if (t > 1) t -= 1;
    if (t < 1 / 6) return p + (q - p) * 6 * t;
    if (t < 1 / 2) return q;
    if (t < 2 / 3) return p + (q - p) * (2 / 3 - t) * 6;
    return p;
  }
```
</details>

### `hslToRgb(val: any): any[]`

**Parameters:**

- **`val`** `any`

**Returns:** `any[]`

**Calls:**

- `hue2rgb`

<details><summary>Code</summary>

```typescript
function hslToRgb(val) {
    var h = val[0];
    var s = val[1];
    var l = val[2];

    var r;
    var g;
    var b;

    if (s === 0) {
      r = l; // achromatic
      b = l; // achromatic
      g = l; // achromatic
    } else {
      var q = l < 0.5 ? l * (1 + s) : l + s - l * s;
      var p = 2 * l - q;
      r = hue2rgb(p, q, h + 1 / 3);
      g = hue2rgb(p, q, h);
      b = hue2rgb(p, q, h - 1 / 3);
    }

    return [r, g, b, val[3]];
  }
```
</details>

### `linear(t: any, tMin: any, tMax: any, value1: any, value2: any): any`

**Parameters:**

- **`t`** `any`
- **`tMin`** `any`
- **`tMax`** `any`
- **`value1`** `any`
- **`value2`** `any`

**Returns:** `any`

**Calls:**

- `createTypedArray`

<details><summary>Code</summary>

```typescript
function linear(t, tMin, tMax, value1, value2) {
    if (value1 === undefined || value2 === undefined) {
      value1 = tMin;
      value2 = tMax;
      tMin = 0;
      tMax = 1;
    }
    if (tMax < tMin) {
      var _tMin = tMax;
      tMax = tMin;
      tMin = _tMin;
    }
    if (t <= tMin) {
      return value1;
    } if (t >= tMax) {
      return value2;
    }
    var perc = tMax === tMin ? 0 : (t - tMin) / (tMax - tMin);
    if (!value1.length) {
      return value1 + (value2 - value1) * perc;
    }
    var i;
    var len = value1.length;
    var arr = createTypedArray('float32', len);
    for (i = 0; i < len; i += 1) {
      arr[i] = value1[i] + (value2[i] - value1[i]) * perc;
    }
    return arr;
  }
```
</details>

### `random(min: any, max: any): any`

**Parameters:**

- **`min`** `any`
- **`max`** `any`

**Returns:** `any`

**Calls:**

- `createTypedArray`
- `BMMath.random`

<details><summary>Code</summary>

```typescript
function random(min, max) {
    if (max === undefined) {
      if (min === undefined) {
        min = 0;
        max = 1;
      } else {
        max = min;
        min = undefined;
      }
    }
    if (max.length) {
      var i;
      var len = max.length;
      if (!min) {
        min = createTypedArray('float32', len);
      }
      var arr = createTypedArray('float32', len);
      var rnd = BMMath.random();
      for (i = 0; i < len; i += 1) {
        arr[i] = min[i] + rnd * (max[i] - min[i]);
      }
      return arr;
    }
    if (min === undefined) {
      min = 0;
    }
    var rndm = BMMath.random();
    return min + rndm * (max - min);
  }
```
</details>

### `createPath(points: any, inTangents: any, outTangents: any, closed: any): any`

**Parameters:**

- **`points`** `any`
- **`inTangents`** `any`
- **`outTangents`** `any`
- **`closed`** `any`

**Returns:** `any`

**Calls:**

- `shapePool.newElement`
- `path.setPathData`
- `path.setTripleAt`

<details><summary>Code</summary>

```typescript
function createPath(points, inTangents, outTangents, closed) {
    var i;
    var len = points.length;
    var path = shapePool.newElement();
    path.setPathData(!!closed, len);
    var arrPlaceholder = [0, 0];
    var inVertexPoint;
    var outVertexPoint;
    for (i = 0; i < len; i += 1) {
      inVertexPoint = (inTangents && inTangents[i]) ? inTangents[i] : arrPlaceholder;
      outVertexPoint = (outTangents && outTangents[i]) ? outTangents[i] : arrPlaceholder;
      path.setTripleAt(points[i][0], points[i][1], outVertexPoint[0] + points[i][0], outVertexPoint[1] + points[i][1], inVertexPoint[0] + points[i][0], inVertexPoint[1] + points[i][1], i, true);
    }
    return path;
  }
```
</details>

### `initiateExpression(elem: any, data: any, property: any): typeof executeExpression`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`property`** `any`

**Returns:** `typeof executeExpression`

**Calls:**

- `/velocity(?![\w\d])/.test`
- `val.indexOf`
- `Object.defineProperty`
- `eval`
- `function wiggle(freq, amp) {
      var iWiggle;
      var j;
      var lenWiggle = this.pv.length ? this.pv.length : 1;
      var addedAmps = createTypedArray('float32', lenWiggle);
      freq = 5;
      var iterations = Math.floor(time * freq);
      iWiggle = 0;
      j = 0;
      while (iWiggle < iterations) {
        // var rnd = BMMath.random();
        for (j = 0; j < lenWiggle; j += 1) {
          addedAmps[j] += -amp + amp * 2 * BMMath.random();
          // addedAmps[j] += -amp + amp*2*rnd;
        }
        iWiggle += 1;
      }
      // var rnd2 = BMMath.random();
      var periods = time * freq;
      var perc = periods - Math.floor(periods);
      var arr = createTypedArray('float32', lenWiggle);
      if (lenWiggle > 1) {
        for (j = 0; j < lenWiggle; j += 1) {
          arr[j] = this.pv[j] + addedAmps[j] + (-amp + amp * 2 * BMMath.random()) * perc;
          // arr[j] = this.pv[j] + addedAmps[j] + (-amp + amp*2*rnd)*perc;
          // arr[i] = this.pv[i] + addedAmp + amp1*perc + amp2*(1-perc);
        }
        return arr;
      }
      return this.pv + addedAmps[0] + (-amp + amp * 2 * BMMath.random()) * perc;
    }.bind`
- `createTypedArray`
- `Math.floor`
- `BMMath.random`
- `thisProperty.loopIn.bind`
- `thisProperty.loopOut.bind`
- `thisProperty.smooth.bind`
- `loopIn`
- `loopOut`
- `this.getValueAtTime.bind`
- `this.getVelocityAtTime.bind`
- `elem.comp.globalData.projectInterface.bind`
- `Math.atan2`
- `Math.sqrt`
- `applyEase`
- `fn`
- `$bm_isInstanceOfArray`
- `Object.prototype.hasOwnProperty.call`
- `BMMath.seedrandom`
- `elem.sourceRectAtTime`
- `value.substring`
- `value.substr`
- `valueAtTime`
- `Math.random`
- `thisLayer.toWorld.bind`
- `thisLayer.fromWorld.bind`
- `thisLayer.fromComp.bind`
- `thisLayer.toComp.bind`
- `thisLayer.mask.bind`
- `elem.layerInterface`
- `thisLayer`
- `seedRandom`
- `velocityAtTime`
- `expression_function`

**Internal Comments:**
```
// val = val.replace(/(\\?"|')((http)(s)?(:\/))?\/.*?(\\?"|')/g, "\"\""); // deter potential network calls (x2)
// var rnd = BMMath.random();
// var rnd2 = BMMath.random(); (x2)
// globalData.pushExpression(); (x3)
// TODO: Check if it's possible to return on ShapeInterface the .v value (x3)
// Changed this to a ternary operation because Rollup failed compiling it correctly (x3)
// Bundlers will see these as dead code and unless we reference them (x4)
```

<details><summary>Code</summary>

```typescript
function initiateExpression(elem, data, property) {
    var val = data.x;
    var needsVelocity = /velocity(?![\w\d])/.test(val);
    var _needsRandom = val.indexOf('random') !== -1;
    var elemType = elem.data.ty;
    var transform;
    var $bm_transform;
    var content;
    var effect;
    var thisProperty = property;
    thisProperty.valueAtTime = thisProperty.getValueAtTime;
    Object.defineProperty(thisProperty, 'value', {
      get: function () {
        return thisProperty.v;
      },
    });
    elem.comp.frameDuration = 1 / elem.comp.globalData.frameRate;
    elem.comp.displayStartTime = 0;
    var inPoint = elem.data.ip / elem.comp.globalData.frameRate;
    var outPoint = elem.data.op / elem.comp.globalData.frameRate;
    var width = elem.data.sw ? elem.data.sw : 0;
    var height = elem.data.sh ? elem.data.sh : 0;
    var name = elem.data.nm;
    var loopIn;
    var loop_in;
    var loopOut;
    var loop_out;
    var smooth;
    var toWorld;
    var fromWorld;
    var fromComp;
    var toComp;
    var fromCompToSurface;
    var position;
    var rotation;
    var anchorPoint;
    var scale;
    var thisLayer;
    var thisComp;
    var mask;
    var valueAtTime;
    var velocityAtTime;

    var scoped_bm_rt;
    // val = val.replace(/(\\?"|')((http)(s)?(:\/))?\/.*?(\\?"|')/g, "\"\""); // deter potential network calls
    var expression_function = eval('[function _expression_function(){' + val + ';scoped_bm_rt=$bm_rt}]')[0]; // eslint-disable-line no-eval
    var numKeys = property.kf ? data.k.length : 0;

    var active = !this.data || this.data.hd !== true;

    var wiggle = function wiggle(freq, amp) {
      var iWiggle;
      var j;
      var lenWiggle = this.pv.length ? this.pv.length : 1;
      var addedAmps = createTypedArray('float32', lenWiggle);
      freq = 5;
      var iterations = Math.floor(time * freq);
      iWiggle = 0;
      j = 0;
      while (iWiggle < iterations) {
        // var rnd = BMMath.random();
        for (j = 0; j < lenWiggle; j += 1) {
          addedAmps[j] += -amp + amp * 2 * BMMath.random();
          // addedAmps[j] += -amp + amp*2*rnd;
        }
        iWiggle += 1;
      }
      // var rnd2 = BMMath.random();
      var periods = time * freq;
      var perc = periods - Math.floor(periods);
      var arr = createTypedArray('float32', lenWiggle);
      if (lenWiggle > 1) {
        for (j = 0; j < lenWiggle; j += 1) {
          arr[j] = this.pv[j] + addedAmps[j] + (-amp + amp * 2 * BMMath.random()) * perc;
          // arr[j] = this.pv[j] + addedAmps[j] + (-amp + amp*2*rnd)*perc;
          // arr[i] = this.pv[i] + addedAmp + amp1*perc + amp2*(1-perc);
        }
        return arr;
      }
      return this.pv + addedAmps[0] + (-amp + amp * 2 * BMMath.random()) * perc;
    }.bind(this);

    if (thisProperty.loopIn) {
      loopIn = thisProperty.loopIn.bind(thisProperty);
      loop_in = loopIn;
    }

    if (thisProperty.loopOut) {
      loopOut = thisProperty.loopOut.bind(thisProperty);
      loop_out = loopOut;
    }

    if (thisProperty.smooth) {
      smooth = thisProperty.smooth.bind(thisProperty);
    }

    function loopInDuration(type, duration) {
      return loopIn(type, duration, true);
    }

    function loopOutDuration(type, duration) {
      return loopOut(type, duration, true);
    }

    if (this.getValueAtTime) {
      valueAtTime = this.getValueAtTime.bind(this);
    }

    if (this.getVelocityAtTime) {
      velocityAtTime = this.getVelocityAtTime.bind(this);
    }

    var comp = elem.comp.globalData.projectInterface.bind(elem.comp.globalData.projectInterface);

    function lookAt(elem1, elem2) {
      var fVec = [elem2[0] - elem1[0], elem2[1] - elem1[1], elem2[2] - elem1[2]];
      var pitch = Math.atan2(fVec[0], Math.sqrt(fVec[1] * fVec[1] + fVec[2] * fVec[2])) / degToRads;
      var yaw = -Math.atan2(fVec[1], fVec[2]) / degToRads;
      return [yaw, pitch, 0];
    }

    function easeOut(t, tMin, tMax, val1, val2) {
      return applyEase(easeOutBez, t, tMin, tMax, val1, val2);
    }

    function easeIn(t, tMin, tMax, val1, val2) {
      return applyEase(easeInBez, t, tMin, tMax, val1, val2);
    }

    function ease(t, tMin, tMax, val1, val2) {
      return applyEase(easeInOutBez, t, tMin, tMax, val1, val2);
    }

    function applyEase(fn, t, tMin, tMax, val1, val2) {
      if (val1 === undefined) {
        val1 = tMin;
        val2 = tMax;
      } else {
        t = (t - tMin) / (tMax - tMin);
      }
      if (t > 1) {
        t = 1;
      } else if (t < 0) {
        t = 0;
      }
      var mult = fn(t);
      if ($bm_isInstanceOfArray(val1)) {
        var iKey;
        var lenKey = val1.length;
        var arr = createTypedArray('float32', lenKey);
        for (iKey = 0; iKey < lenKey; iKey += 1) {
          arr[iKey] = (val2[iKey] - val1[iKey]) * mult + val1[iKey];
        }
        return arr;
      }
      return (val2 - val1) * mult + val1;
    }

    function nearestKey(time) {
      var iKey;
      var lenKey = data.k.length;
      var index;
      var keyTime;
      if (!data.k.length || typeof (data.k[0]) === 'number') {
        index = 0;
        keyTime = 0;
      } else {
        index = -1;
        time *= elem.comp.globalData.frameRate;
        if (time < data.k[0].t) {
          index = 1;
          keyTime = data.k[0].t;
        } else {
          for (iKey = 0; iKey < lenKey - 1; iKey += 1) {
            if (time === data.k[iKey].t) {
              index = iKey + 1;
              keyTime = data.k[iKey].t;
              break;
            } else if (time > data.k[iKey].t && time < data.k[iKey + 1].t) {
              if (time - data.k[iKey].t > data.k[iKey + 1].t - time) {
                index = iKey + 2;
                keyTime = data.k[iKey + 1].t;
              } else {
                index = iKey + 1;
                keyTime = data.k[iKey].t;
              }
              break;
            }
          }
          if (index === -1) {
            index = iKey + 1;
            keyTime = data.k[iKey].t;
          }
        }
      }
      var obKey = {};
      obKey.index = index;
      obKey.time = keyTime / elem.comp.globalData.frameRate;
      return obKey;
    }

    function key(ind) {
      var obKey;
      var iKey;
      var lenKey;
      if (!data.k.length || typeof (data.k[0]) === 'number') {
        throw new Error('The property has no keyframe at index ' + ind);
      }
      ind -= 1;
      obKey = {
        time: data.k[ind].t / elem.comp.globalData.frameRate,
        value: [],
      };
      var arr = Object.prototype.hasOwnProperty.call(data.k[ind], 's') ? data.k[ind].s : data.k[ind - 1].e;

      lenKey = arr.length;
      for (iKey = 0; iKey < lenKey; iKey += 1) {
        obKey[iKey] = arr[iKey];
        obKey.value[iKey] = arr[iKey];
      }
      return obKey;
    }

    function framesToTime(fr, fps) {
      if (!fps) {
        fps = elem.comp.globalData.frameRate;
      }
      return fr / fps;
    }

    function timeToFrames(t, fps) {
      if (!t && t !== 0) {
        t = time;
      }
      if (!fps) {
        fps = elem.comp.globalData.frameRate;
      }
      return t * fps;
    }

    function seedRandom(seed) {
      BMMath.seedrandom(randSeed + seed);
    }

    function sourceRectAtTime() {
      return elem.sourceRectAtTime();
    }

    function substring(init, end) {
      if (typeof value === 'string') {
        if (end === undefined) {
          return value.substring(init);
        }
        return value.substring(init, end);
      }
      return '';
    }

    function substr(init, end) {
      if (typeof value === 'string') {
        if (end === undefined) {
          return value.substr(init);
        }
        return value.substr(init, end);
      }
      return '';
    }

    function posterizeTime(framesPerSecond) {
      time = framesPerSecond === 0 ? 0 : Math.floor(time * framesPerSecond) / framesPerSecond;
      value = valueAtTime(time);
    }

    var time;
    var velocity;
    var value;
    var text;
    var textIndex;
    var textTotal;
    var selectorValue;
    var index = elem.data.ind;
    var hasParent = !!(elem.hierarchy && elem.hierarchy.length);
    var parent;
    var randSeed = Math.floor(Math.random() * 1000000);
    var globalData = elem.globalData;
    function executeExpression(_value) {
      // globalData.pushExpression();
      value = _value;
      if (this.frameExpressionId === elem.globalData.frameId && this.propType !== 'textSelector') {
        return value;
      }
      if (this.propType === 'textSelector') {
        textIndex = this.textIndex;
        textTotal = this.textTotal;
        selectorValue = this.selectorValue;
      }
      if (!thisLayer) {
        text = elem.layerInterface.text;
        thisLayer = elem.layerInterface;
        thisComp = elem.comp.compInterface;
        toWorld = thisLayer.toWorld.bind(thisLayer);
        fromWorld = thisLayer.fromWorld.bind(thisLayer);
        fromComp = thisLayer.fromComp.bind(thisLayer);
        toComp = thisLayer.toComp.bind(thisLayer);
        mask = thisLayer.mask ? thisLayer.mask.bind(thisLayer) : null;
        fromCompToSurface = fromComp;
      }
      if (!transform) {
        transform = elem.layerInterface('ADBE Transform Group');
        $bm_transform = transform;
        if (transform) {
          anchorPoint = transform.anchorPoint;
          /* position = transform.position;
                    rotation = transform.rotation;
                    scale = transform.scale; */
        }
      }

      if (elemType === 4 && !content) {
        content = thisLayer('ADBE Root Vectors Group');
      }
      if (!effect) {
        effect = thisLayer(4);
      }
      hasParent = !!(elem.hierarchy && elem.hierarchy.length);
      if (hasParent && !parent) {
        parent = elem.hierarchy[0].layerInterface;
      }
      time = this.comp.renderedFrame / this.comp.globalData.frameRate;
      if (_needsRandom) {
        seedRandom(randSeed + time);
      }
      if (needsVelocity) {
        velocity = velocityAtTime(time);
      }
      expression_function();
      this.frameExpressionId = elem.globalData.frameId;

      // TODO: Check if it's possible to return on ShapeInterface the .v value
      // Changed this to a ternary operation because Rollup failed compiling it correctly
      scoped_bm_rt = scoped_bm_rt.propType === propTypes.SHAPE
        ? scoped_bm_rt.v
        : scoped_bm_rt;
      return scoped_bm_rt;
    }
    // Bundlers will see these as dead code and unless we reference them
    executeExpression.__preventDeadCodeRemoval = [$bm_transform, anchorPoint, time, velocity, inPoint, outPoint, width, height, name, loop_in, loop_out, smooth, toComp, fromCompToSurface, toWorld, fromWorld, mask, position, rotation, scale, thisComp, numKeys, active, wiggle, loopInDuration, loopOutDuration, comp, lookAt, easeOut, easeIn, ease, nearestKey, key, text, textIndex, textTotal, selectorValue, framesToTime, timeToFrames, sourceRectAtTime, substring, substr, posterizeTime, index, globalData];
    return executeExpression;
  }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return thisProperty.v;
      }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return thisProperty.v;
      }
```
</details>

### `loopInDuration(type: any, duration: any): any`

**Parameters:**

- **`type`** `any`
- **`duration`** `any`

**Returns:** `any`

**Calls:**

- `loopIn`

<details><summary>Code</summary>

```typescript
function loopInDuration(type, duration) {
      return loopIn(type, duration, true);
    }
```
</details>

### `loopOutDuration(type: any, duration: any): any`

**Parameters:**

- **`type`** `any`
- **`duration`** `any`

**Returns:** `any`

**Calls:**

- `loopOut`

<details><summary>Code</summary>

```typescript
function loopOutDuration(type, duration) {
      return loopOut(type, duration, true);
    }
```
</details>

### `lookAt(elem1: any, elem2: any): number[]`

**Parameters:**

- **`elem1`** `any`
- **`elem2`** `any`

**Returns:** `number[]`

**Calls:**

- `Math.atan2`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function lookAt(elem1, elem2) {
      var fVec = [elem2[0] - elem1[0], elem2[1] - elem1[1], elem2[2] - elem1[2]];
      var pitch = Math.atan2(fVec[0], Math.sqrt(fVec[1] * fVec[1] + fVec[2] * fVec[2])) / degToRads;
      var yaw = -Math.atan2(fVec[1], fVec[2]) / degToRads;
      return [yaw, pitch, 0];
    }
```
</details>

### `easeOut(t: any, tMin: any, tMax: any, val1: any, val2: any): any`

**Parameters:**

- **`t`** `any`
- **`tMin`** `any`
- **`tMax`** `any`
- **`val1`** `any`
- **`val2`** `any`

**Returns:** `any`

**Calls:**

- `applyEase`

<details><summary>Code</summary>

```typescript
function easeOut(t, tMin, tMax, val1, val2) {
      return applyEase(easeOutBez, t, tMin, tMax, val1, val2);
    }
```
</details>

### `easeIn(t: any, tMin: any, tMax: any, val1: any, val2: any): any`

**Parameters:**

- **`t`** `any`
- **`tMin`** `any`
- **`tMax`** `any`
- **`val1`** `any`
- **`val2`** `any`

**Returns:** `any`

**Calls:**

- `applyEase`

<details><summary>Code</summary>

```typescript
function easeIn(t, tMin, tMax, val1, val2) {
      return applyEase(easeInBez, t, tMin, tMax, val1, val2);
    }
```
</details>

### `ease(t: any, tMin: any, tMax: any, val1: any, val2: any): any`

**Parameters:**

- **`t`** `any`
- **`tMin`** `any`
- **`tMax`** `any`
- **`val1`** `any`
- **`val2`** `any`

**Returns:** `any`

**Calls:**

- `applyEase`

<details><summary>Code</summary>

```typescript
function ease(t, tMin, tMax, val1, val2) {
      return applyEase(easeInOutBez, t, tMin, tMax, val1, val2);
    }
```
</details>

### `applyEase(fn: any, t: any, tMin: any, tMax: any, val1: any, val2: any): any`

**Parameters:**

- **`fn`** `any`
- **`t`** `any`
- **`tMin`** `any`
- **`tMax`** `any`
- **`val1`** `any`
- **`val2`** `any`

**Returns:** `any`

**Calls:**

- `fn`
- `$bm_isInstanceOfArray`
- `createTypedArray`

<details><summary>Code</summary>

```typescript
function applyEase(fn, t, tMin, tMax, val1, val2) {
      if (val1 === undefined) {
        val1 = tMin;
        val2 = tMax;
      } else {
        t = (t - tMin) / (tMax - tMin);
      }
      if (t > 1) {
        t = 1;
      } else if (t < 0) {
        t = 0;
      }
      var mult = fn(t);
      if ($bm_isInstanceOfArray(val1)) {
        var iKey;
        var lenKey = val1.length;
        var arr = createTypedArray('float32', lenKey);
        for (iKey = 0; iKey < lenKey; iKey += 1) {
          arr[iKey] = (val2[iKey] - val1[iKey]) * mult + val1[iKey];
        }
        return arr;
      }
      return (val2 - val1) * mult + val1;
    }
```
</details>

### `nearestKey(time: any): { index: number; time: number; }`

**Parameters:**

- **`time`** `any`

**Returns:** `{ index: number; time: number; }`

<details><summary>Code</summary>

```typescript
function nearestKey(time) {
      var iKey;
      var lenKey = data.k.length;
      var index;
      var keyTime;
      if (!data.k.length || typeof (data.k[0]) === 'number') {
        index = 0;
        keyTime = 0;
      } else {
        index = -1;
        time *= elem.comp.globalData.frameRate;
        if (time < data.k[0].t) {
          index = 1;
          keyTime = data.k[0].t;
        } else {
          for (iKey = 0; iKey < lenKey - 1; iKey += 1) {
            if (time === data.k[iKey].t) {
              index = iKey + 1;
              keyTime = data.k[iKey].t;
              break;
            } else if (time > data.k[iKey].t && time < data.k[iKey + 1].t) {
              if (time - data.k[iKey].t > data.k[iKey + 1].t - time) {
                index = iKey + 2;
                keyTime = data.k[iKey + 1].t;
              } else {
                index = iKey + 1;
                keyTime = data.k[iKey].t;
              }
              break;
            }
          }
          if (index === -1) {
            index = iKey + 1;
            keyTime = data.k[iKey].t;
          }
        }
      }
      var obKey = {};
      obKey.index = index;
      obKey.time = keyTime / elem.comp.globalData.frameRate;
      return obKey;
    }
```
</details>

### `key(ind: any): { time: number; value: any[]; }`

**Parameters:**

- **`ind`** `any`

**Returns:** `{ time: number; value: any[]; }`

**Calls:**

- `Object.prototype.hasOwnProperty.call`

<details><summary>Code</summary>

```typescript
function key(ind) {
      var obKey;
      var iKey;
      var lenKey;
      if (!data.k.length || typeof (data.k[0]) === 'number') {
        throw new Error('The property has no keyframe at index ' + ind);
      }
      ind -= 1;
      obKey = {
        time: data.k[ind].t / elem.comp.globalData.frameRate,
        value: [],
      };
      var arr = Object.prototype.hasOwnProperty.call(data.k[ind], 's') ? data.k[ind].s : data.k[ind - 1].e;

      lenKey = arr.length;
      for (iKey = 0; iKey < lenKey; iKey += 1) {
        obKey[iKey] = arr[iKey];
        obKey.value[iKey] = arr[iKey];
      }
      return obKey;
    }
```
</details>

### `framesToTime(fr: any, fps: any): number`

**Parameters:**

- **`fr`** `any`
- **`fps`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function framesToTime(fr, fps) {
      if (!fps) {
        fps = elem.comp.globalData.frameRate;
      }
      return fr / fps;
    }
```
</details>

### `timeToFrames(t: any, fps: any): number`

**Parameters:**

- **`t`** `any`
- **`fps`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function timeToFrames(t, fps) {
      if (!t && t !== 0) {
        t = time;
      }
      if (!fps) {
        fps = elem.comp.globalData.frameRate;
      }
      return t * fps;
    }
```
</details>

### `seedRandom(seed: any): void`

**Parameters:**

- **`seed`** `any`

**Returns:** `void`

**Calls:**

- `BMMath.seedrandom`

<details><summary>Code</summary>

```typescript
function seedRandom(seed) {
      BMMath.seedrandom(randSeed + seed);
    }
```
</details>

### `sourceRectAtTime(): any`

**Returns:** `any`

**Calls:**

- `elem.sourceRectAtTime`

<details><summary>Code</summary>

```typescript
function sourceRectAtTime() {
      return elem.sourceRectAtTime();
    }
```
</details>

### `substring(init: any, end: any): string`

**Parameters:**

- **`init`** `any`
- **`end`** `any`

**Returns:** `string`

**Calls:**

- `value.substring`

<details><summary>Code</summary>

```typescript
function substring(init, end) {
      if (typeof value === 'string') {
        if (end === undefined) {
          return value.substring(init);
        }
        return value.substring(init, end);
      }
      return '';
    }
```
</details>

### `substr(init: any, end: any): string`

**Parameters:**

- **`init`** `any`
- **`end`** `any`

**Returns:** `string`

**Calls:**

- `value.substr`

<details><summary>Code</summary>

```typescript
function substr(init, end) {
      if (typeof value === 'string') {
        if (end === undefined) {
          return value.substr(init);
        }
        return value.substr(init, end);
      }
      return '';
    }
```
</details>

### `posterizeTime(framesPerSecond: any): void`

**Parameters:**

- **`framesPerSecond`** `any`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `valueAtTime`

<details><summary>Code</summary>

```typescript
function posterizeTime(framesPerSecond) {
      time = framesPerSecond === 0 ? 0 : Math.floor(time * framesPerSecond) / framesPerSecond;
      value = valueAtTime(time);
    }
```
</details>

### `executeExpression(_value: any): any`

**Parameters:**

- **`_value`** `any`

**Returns:** `any`

**Calls:**

- `thisLayer.toWorld.bind`
- `thisLayer.fromWorld.bind`
- `thisLayer.fromComp.bind`
- `thisLayer.toComp.bind`
- `thisLayer.mask.bind`
- `elem.layerInterface`
- `thisLayer`
- `seedRandom`
- `velocityAtTime`
- `expression_function`

**Internal Comments:**
```
// globalData.pushExpression(); (x3)
// TODO: Check if it's possible to return on ShapeInterface the .v value (x3)
// Changed this to a ternary operation because Rollup failed compiling it correctly (x3)
```

<details><summary>Code</summary>

```typescript
function executeExpression(_value) {
      // globalData.pushExpression();
      value = _value;
      if (this.frameExpressionId === elem.globalData.frameId && this.propType !== 'textSelector') {
        return value;
      }
      if (this.propType === 'textSelector') {
        textIndex = this.textIndex;
        textTotal = this.textTotal;
        selectorValue = this.selectorValue;
      }
      if (!thisLayer) {
        text = elem.layerInterface.text;
        thisLayer = elem.layerInterface;
        thisComp = elem.comp.compInterface;
        toWorld = thisLayer.toWorld.bind(thisLayer);
        fromWorld = thisLayer.fromWorld.bind(thisLayer);
        fromComp = thisLayer.fromComp.bind(thisLayer);
        toComp = thisLayer.toComp.bind(thisLayer);
        mask = thisLayer.mask ? thisLayer.mask.bind(thisLayer) : null;
        fromCompToSurface = fromComp;
      }
      if (!transform) {
        transform = elem.layerInterface('ADBE Transform Group');
        $bm_transform = transform;
        if (transform) {
          anchorPoint = transform.anchorPoint;
          /* position = transform.position;
                    rotation = transform.rotation;
                    scale = transform.scale; */
        }
      }

      if (elemType === 4 && !content) {
        content = thisLayer('ADBE Root Vectors Group');
      }
      if (!effect) {
        effect = thisLayer(4);
      }
      hasParent = !!(elem.hierarchy && elem.hierarchy.length);
      if (hasParent && !parent) {
        parent = elem.hierarchy[0].layerInterface;
      }
      time = this.comp.renderedFrame / this.comp.globalData.frameRate;
      if (_needsRandom) {
        seedRandom(randSeed + time);
      }
      if (needsVelocity) {
        velocity = velocityAtTime(time);
      }
      expression_function();
      this.frameExpressionId = elem.globalData.frameId;

      // TODO: Check if it's possible to return on ShapeInterface the .v value
      // Changed this to a ternary operation because Rollup failed compiling it correctly
      scoped_bm_rt = scoped_bm_rt.propType === propTypes.SHAPE
        ? scoped_bm_rt.v
        : scoped_bm_rt;
      return scoped_bm_rt;
    }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return thisProperty.v;
      }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return thisProperty.v;
      }
```
</details>

### `searchExpressions(elem: any, data: any, prop: any): void`

**Parameters:**

- **`elem`** `any`
- **`data`** `any`
- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `prop.effectsSequence.push`
- `prop.initiateExpression(elem, data, prop).bind`

<details><summary>Code</summary>

```typescript
function searchExpressions(elem, data, prop) {
    if (data.x) {
      prop.k = true;
      prop.x = true;
      prop.initiateExpression = ExpressionManager.initiateExpression;
      prop.effectsSequence.push(prop.initiateExpression(elem, data, prop).bind(prop));
    }
  }
```
</details>

### `getValueAtTime(frameNum: any): any`

**Parameters:**

- **`frameNum`** `any`

**Returns:** `any`

**Calls:**

- `this.interpolateValue`

<details><summary>Code</summary>

```typescript
function getValueAtTime(frameNum) {
    frameNum *= this.elem.globalData.frameRate;
    frameNum -= this.offsetTime;
    if (frameNum !== this._cachingAtTime.lastFrame) {
      this._cachingAtTime.lastIndex = this._cachingAtTime.lastFrame < frameNum ? this._cachingAtTime.lastIndex : 0;
      this._cachingAtTime.value = this.interpolateValue(frameNum, this._cachingAtTime);
      this._cachingAtTime.lastFrame = frameNum;
    }
    return this._cachingAtTime.value;
  }
```
</details>

### `getSpeedAtTime(frameNum: any): number`

**Parameters:**

- **`frameNum`** `any`

**Returns:** `number`

**Calls:**

- `this.getValueAtTime`
- `Math.pow`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function getSpeedAtTime(frameNum) {
    var delta = -0.01;
    var v1 = this.getValueAtTime(frameNum);
    var v2 = this.getValueAtTime(frameNum + delta);
    var speed = 0;
    if (v1.length) {
      var i;
      for (i = 0; i < v1.length; i += 1) {
        speed += Math.pow(v2[i] - v1[i], 2);
      }
      speed = Math.sqrt(speed) * 100;
    } else {
      speed = 0;
    }
    return speed;
  }
```
</details>

### `getVelocityAtTime(frameNum: any): any`

**Parameters:**

- **`frameNum`** `any`

**Returns:** `any`

**Calls:**

- `this.getValueAtTime`
- `createTypedArray`

**Internal Comments:**
```
// frameNum += this.elem.data.st; (x2)
// removing frameRate (x4)
// if needed, don't add it here (x4)
// velocity[i] = this.elem.globalData.frameRate*((v2[i] - v1[i])/delta); (x4)
```

<details><summary>Code</summary>

```typescript
function getVelocityAtTime(frameNum) {
    if (this.vel !== undefined) {
      return this.vel;
    }
    var delta = -0.001;
    // frameNum += this.elem.data.st;
    var v1 = this.getValueAtTime(frameNum);
    var v2 = this.getValueAtTime(frameNum + delta);
    var velocity;
    if (v1.length) {
      velocity = createTypedArray('float32', v1.length);
      var i;
      for (i = 0; i < v1.length; i += 1) {
        // removing frameRate
        // if needed, don't add it here
        // velocity[i] = this.elem.globalData.frameRate*((v2[i] - v1[i])/delta);
        velocity[i] = (v2[i] - v1[i]) / delta;
      }
    } else {
      velocity = (v2 - v1) / delta;
    }
    return velocity;
  }
```
</details>

### `getStaticValueAtTime(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getStaticValueAtTime() {
    return this.pv;
  }
```
</details>

### `setGroupProperty(propertyGroup: any): void`

**Parameters:**

- **`propertyGroup`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setGroupProperty(propertyGroup) {
    this.propertyGroup = propertyGroup;
  }
```
</details>

### `addPropertyDecorator(): void`

**Returns:** `void`

**Calls:**

- `type.toLowerCase`
- `Math.max`
- `Math.abs`
- `Math.floor`
- `this.getValueAtTime`
- `createTypedArray`
- `matrix.cloneFromProps`
- `this.a.getValueAtTime`
- `matrix.translate`
- `this.s.getValueAtTime`
- `matrix.scale`
- `this.sk.getValueAtTime`
- `this.sa.getValueAtTime`
- `matrix.skewFromAxis`
- `this.r.getValueAtTime`
- `matrix.rotate`
- `this.rz.getValueAtTime`
- `this.ry.getValueAtTime`
- `this.rx.getValueAtTime`
- `this.or.getValueAtTime`
- `matrix.rotateZ(-rotationZ * this.rz.mult)
        .rotateY(rotationY * this.ry.mult)
        .rotateX(rotationX * this.rx.mult)
        .rotateZ(-orientation[2] * this.or.mult)
        .rotateY(orientation[1] * this.or.mult)
        .rotateX`
- `this.px.getValueAtTime`
- `this.py.getValueAtTime`
- `this.pz.getValueAtTime`
- `this.p.getValueAtTime`
- `this.v.clone`
- `getTransformProperty`
- `getTransformValueAtTime.bind`
- `getTransformStaticValueAtTime.bind`
- `propertyGetProp`
- `expressionHelpers.getValueAtTime.bind`
- `expressionHelpers.getStaticValueAtTime.bind`
- `expressionHelpers.getVelocityAtTime.bind`
- `expressionHelpers.getSpeedAtTime.bind`
- `expressionHelpers.searchExpressions`
- `container.addDynamicProperty`
- `shapePool.clone`
- `this.interpolateShape`
- `ShapePropertyFactory.getConstructorFunction`
- `ShapePropertyFactory.getKeyframedConstructorFunction`
- `this.getValue`
- `createSizedArray`
- `this.vertices`
- `bez.getSegmentsLength`
- `bez.getPointInSegment`
- `this.pointOnPath`
- `Math.sqrt`
- `Math.pow`
- `this.vectorOnPath`
- `extendPrototype`
- `propertyGetShapeProp`
- `elem.addDynamicProperty`

**Internal Comments:**
```
/// / (x2)
// prop.getVelocityAtTime = getVelocityAtTime;
// prop.loopOut = loopOut;
// prop.loopIn = loopIn;
// For now this caching object is created only when needed instead of creating it when the shape is initialized.
// perc doesn't use triple equality because it can be a Number object as well as a primitive.
```

<details><summary>Code</summary>

```typescript
function addPropertyDecorator() {
  function loopOut(type, duration, durationFlag) {
    if (!this.k || !this.keyframes) {
      return this.pv;
    }
    type = type ? type.toLowerCase() : '';
    var currentFrame = this.comp.renderedFrame;
    var keyframes = this.keyframes;
    var lastKeyFrame = keyframes[keyframes.length - 1].t;
    if (currentFrame <= lastKeyFrame) {
      return this.pv;
    }
    var cycleDuration;
    var firstKeyFrame;
    if (!durationFlag) {
      if (!duration || duration > keyframes.length - 1) {
        duration = keyframes.length - 1;
      }
      firstKeyFrame = keyframes[keyframes.length - 1 - duration].t;
      cycleDuration = lastKeyFrame - firstKeyFrame;
    } else {
      if (!duration) {
        cycleDuration = Math.max(0, lastKeyFrame - this.elem.data.ip);
      } else {
        cycleDuration = Math.abs(lastKeyFrame - this.elem.comp.globalData.frameRate * duration);
      }
      firstKeyFrame = lastKeyFrame - cycleDuration;
    }
    var i;
    var len;
    var ret;
    if (type === 'pingpong') {
      var iterations = Math.floor((currentFrame - firstKeyFrame) / cycleDuration);
      if (iterations % 2 !== 0) {
          return this.getValueAtTime(((cycleDuration - (currentFrame - firstKeyFrame) % cycleDuration + firstKeyFrame)) / this.comp.globalData.frameRate, 0); // eslint-disable-line
      }
    } else if (type === 'offset') {
      var initV = this.getValueAtTime(firstKeyFrame / this.comp.globalData.frameRate, 0);
      var endV = this.getValueAtTime(lastKeyFrame / this.comp.globalData.frameRate, 0);
        var current = this.getValueAtTime(((currentFrame - firstKeyFrame) % cycleDuration + firstKeyFrame) / this.comp.globalData.frameRate, 0); // eslint-disable-line
      var repeats = Math.floor((currentFrame - firstKeyFrame) / cycleDuration);
      if (this.pv.length) {
        ret = new Array(initV.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
          ret[i] = (endV[i] - initV[i]) * repeats + current[i];
        }
        return ret;
      }
      return (endV - initV) * repeats + current;
    } else if (type === 'continue') {
      var lastValue = this.getValueAtTime(lastKeyFrame / this.comp.globalData.frameRate, 0);
      var nextLastValue = this.getValueAtTime((lastKeyFrame - 0.001) / this.comp.globalData.frameRate, 0);
      if (this.pv.length) {
        ret = new Array(lastValue.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
            ret[i] = lastValue[i] + (lastValue[i] - nextLastValue[i]) * ((currentFrame - lastKeyFrame) / this.comp.globalData.frameRate) / 0.0005; // eslint-disable-line
        }
        return ret;
      }
      return lastValue + (lastValue - nextLastValue) * (((currentFrame - lastKeyFrame)) / 0.001);
    }
      return this.getValueAtTime((((currentFrame - firstKeyFrame) % cycleDuration + firstKeyFrame)) / this.comp.globalData.frameRate, 0); // eslint-disable-line

  }

  function loopIn(type, duration, durationFlag) {
    if (!this.k) {
      return this.pv;
    }
    type = type ? type.toLowerCase() : '';
    var currentFrame = this.comp.renderedFrame;
    var keyframes = this.keyframes;
    var firstKeyFrame = keyframes[0].t;
    if (currentFrame >= firstKeyFrame) {
      return this.pv;
    }
    var cycleDuration;
    var lastKeyFrame;
    if (!durationFlag) {
      if (!duration || duration > keyframes.length - 1) {
        duration = keyframes.length - 1;
      }
      lastKeyFrame = keyframes[duration].t;
      cycleDuration = lastKeyFrame - firstKeyFrame;
    } else {
      if (!duration) {
        cycleDuration = Math.max(0, this.elem.data.op - firstKeyFrame);
      } else {
        cycleDuration = Math.abs(this.elem.comp.globalData.frameRate * duration);
      }
      lastKeyFrame = firstKeyFrame + cycleDuration;
    }
    var i;
    var len;
    var ret;
    if (type === 'pingpong') {
      var iterations = Math.floor((firstKeyFrame - currentFrame) / cycleDuration);
      if (iterations % 2 === 0) {
          return this.getValueAtTime((((firstKeyFrame - currentFrame) % cycleDuration + firstKeyFrame)) / this.comp.globalData.frameRate, 0); // eslint-disable-line
      }
    } else if (type === 'offset') {
      var initV = this.getValueAtTime(firstKeyFrame / this.comp.globalData.frameRate, 0);
      var endV = this.getValueAtTime(lastKeyFrame / this.comp.globalData.frameRate, 0);
      var current = this.getValueAtTime((cycleDuration - ((firstKeyFrame - currentFrame) % cycleDuration) + firstKeyFrame) / this.comp.globalData.frameRate, 0);
      var repeats = Math.floor((firstKeyFrame - currentFrame) / cycleDuration) + 1;
      if (this.pv.length) {
        ret = new Array(initV.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
          ret[i] = current[i] - (endV[i] - initV[i]) * repeats;
        }
        return ret;
      }
      return current - (endV - initV) * repeats;
    } else if (type === 'continue') {
      var firstValue = this.getValueAtTime(firstKeyFrame / this.comp.globalData.frameRate, 0);
      var nextFirstValue = this.getValueAtTime((firstKeyFrame + 0.001) / this.comp.globalData.frameRate, 0);
      if (this.pv.length) {
        ret = new Array(firstValue.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
          ret[i] = firstValue[i] + ((firstValue[i] - nextFirstValue[i]) * (firstKeyFrame - currentFrame)) / 0.001;
        }
        return ret;
      }
      return firstValue + ((firstValue - nextFirstValue) * (firstKeyFrame - currentFrame)) / 0.001;
    }
      return this.getValueAtTime(((cycleDuration - ((firstKeyFrame - currentFrame) % cycleDuration + firstKeyFrame))) / this.comp.globalData.frameRate, 0); // eslint-disable-line

  }

  function smooth(width, samples) {
    if (!this.k) {
      return this.pv;
    }
    width = (width || 0.4) * 0.5;
    samples = Math.floor(samples || 5);
    if (samples <= 1) {
      return this.pv;
    }
    var currentTime = this.comp.renderedFrame / this.comp.globalData.frameRate;
    var initFrame = currentTime - width;
    var endFrame = currentTime + width;
    var sampleFrequency = samples > 1 ? (endFrame - initFrame) / (samples - 1) : 1;
    var i = 0;
    var j = 0;
    var value;
    if (this.pv.length) {
      value = createTypedArray('float32', this.pv.length);
    } else {
      value = 0;
    }
    var sampleValue;
    while (i < samples) {
      sampleValue = this.getValueAtTime(initFrame + i * sampleFrequency);
      if (this.pv.length) {
        for (j = 0; j < this.pv.length; j += 1) {
          value[j] += sampleValue[j];
        }
      } else {
        value += sampleValue;
      }
      i += 1;
    }
    if (this.pv.length) {
      for (j = 0; j < this.pv.length; j += 1) {
        value[j] /= samples;
      }
    } else {
      value /= samples;
    }
    return value;
  }

  function getTransformValueAtTime(time) {
    if (!this._transformCachingAtTime) {
      this._transformCachingAtTime = {
        v: new Matrix(),
      };
    }
    /// /
    var matrix = this._transformCachingAtTime.v;
    matrix.cloneFromProps(this.pre.props);
    if (this.appliedTransformations < 1) {
      var anchor = this.a.getValueAtTime(time);
      matrix.translate(
        -anchor[0] * this.a.mult,
        -anchor[1] * this.a.mult,
        anchor[2] * this.a.mult
      );
    }
    if (this.appliedTransformations < 2) {
      var scale = this.s.getValueAtTime(time);
      matrix.scale(
        scale[0] * this.s.mult,
        scale[1] * this.s.mult,
        scale[2] * this.s.mult
      );
    }
    if (this.sk && this.appliedTransformations < 3) {
      var skew = this.sk.getValueAtTime(time);
      var skewAxis = this.sa.getValueAtTime(time);
      matrix.skewFromAxis(-skew * this.sk.mult, skewAxis * this.sa.mult);
    }
    if (this.r && this.appliedTransformations < 4) {
      var rotation = this.r.getValueAtTime(time);
      matrix.rotate(-rotation * this.r.mult);
    } else if (!this.r && this.appliedTransformations < 4) {
      var rotationZ = this.rz.getValueAtTime(time);
      var rotationY = this.ry.getValueAtTime(time);
      var rotationX = this.rx.getValueAtTime(time);
      var orientation = this.or.getValueAtTime(time);
      matrix.rotateZ(-rotationZ * this.rz.mult)
        .rotateY(rotationY * this.ry.mult)
        .rotateX(rotationX * this.rx.mult)
        .rotateZ(-orientation[2] * this.or.mult)
        .rotateY(orientation[1] * this.or.mult)
        .rotateX(orientation[0] * this.or.mult);
    }
    if (this.data.p && this.data.p.s) {
      var positionX = this.px.getValueAtTime(time);
      var positionY = this.py.getValueAtTime(time);
      if (this.data.p.z) {
        var positionZ = this.pz.getValueAtTime(time);
        matrix.translate(
          positionX * this.px.mult,
          positionY * this.py.mult,
          -positionZ * this.pz.mult
        );
      } else {
        matrix.translate(positionX * this.px.mult, positionY * this.py.mult, 0);
      }
    } else {
      var position = this.p.getValueAtTime(time);
      matrix.translate(
        position[0] * this.p.mult,
        position[1] * this.p.mult,
        -position[2] * this.p.mult
      );
    }
    return matrix;
    /// /
  }

  function getTransformStaticValueAtTime() {
    return this.v.clone(new Matrix());
  }

  var getTransformProperty = TransformPropertyFactory.getTransformProperty;
  TransformPropertyFactory.getTransformProperty = function (elem, data, container) {
    var prop = getTransformProperty(elem, data, container);
    if (prop.dynamicProperties.length) {
      prop.getValueAtTime = getTransformValueAtTime.bind(prop);
    } else {
      prop.getValueAtTime = getTransformStaticValueAtTime.bind(prop);
    }
    prop.setGroupProperty = expressionHelpers.setGroupProperty;
    return prop;
  };

  var propertyGetProp = PropertyFactory.getProp;
  PropertyFactory.getProp = function (elem, data, type, mult, container) {
    var prop = propertyGetProp(elem, data, type, mult, container);
    // prop.getVelocityAtTime = getVelocityAtTime;
    // prop.loopOut = loopOut;
    // prop.loopIn = loopIn;
    if (prop.kf) {
      prop.getValueAtTime = expressionHelpers.getValueAtTime.bind(prop);
    } else {
      prop.getValueAtTime = expressionHelpers.getStaticValueAtTime.bind(prop);
    }
    prop.setGroupProperty = expressionHelpers.setGroupProperty;
    prop.loopOut = loopOut;
    prop.loopIn = loopIn;
    prop.smooth = smooth;
    prop.getVelocityAtTime = expressionHelpers.getVelocityAtTime.bind(prop);
    prop.getSpeedAtTime = expressionHelpers.getSpeedAtTime.bind(prop);
    prop.numKeys = data.a === 1 ? data.k.length : 0;
    prop.propertyIndex = data.ix;
    var value = 0;
    if (type !== 0) {
      value = createTypedArray('float32', data.a === 1 ? data.k[0].s.length : data.k.length);
    }
    prop._cachingAtTime = {
      lastFrame: initialDefaultFrame,
      lastIndex: 0,
      value: value,
    };
    expressionHelpers.searchExpressions(elem, data, prop);
    if (prop.k) {
      container.addDynamicProperty(prop);
    }

    return prop;
  };

  function getShapeValueAtTime(frameNum) {
    // For now this caching object is created only when needed instead of creating it when the shape is initialized.
    if (!this._cachingAtTime) {
      this._cachingAtTime = {
        shapeValue: shapePool.clone(this.pv),
        lastIndex: 0,
        lastTime: initialDefaultFrame,
      };
    }

    frameNum *= this.elem.globalData.frameRate;
    frameNum -= this.offsetTime;
    if (frameNum !== this._cachingAtTime.lastTime) {
      this._cachingAtTime.lastIndex = this._cachingAtTime.lastTime < frameNum ? this._caching.lastIndex : 0;
      this._cachingAtTime.lastTime = frameNum;
      this.interpolateShape(frameNum, this._cachingAtTime.shapeValue, this._cachingAtTime);
    }
    return this._cachingAtTime.shapeValue;
  }

  var ShapePropertyConstructorFunction = ShapePropertyFactory.getConstructorFunction();
  var KeyframedShapePropertyConstructorFunction = ShapePropertyFactory.getKeyframedConstructorFunction();

  function ShapeExpressions() {}
  ShapeExpressions.prototype = {
    vertices: function (prop, time) {
      if (this.k) {
        this.getValue();
      }
      var shapePath = this.v;
      if (time !== undefined) {
        shapePath = this.getValueAtTime(time, 0);
      }
      var i;
      var len = shapePath._length;
      var vertices = shapePath[prop];
      var points = shapePath.v;
      var arr = createSizedArray(len);
      for (i = 0; i < len; i += 1) {
        if (prop === 'i' || prop === 'o') {
          arr[i] = [vertices[i][0] - points[i][0], vertices[i][1] - points[i][1]];
        } else {
          arr[i] = [vertices[i][0], vertices[i][1]];
        }
      }
      return arr;
    },
    points: function (time) {
      return this.vertices('v', time);
    },
    inTangents: function (time) {
      return this.vertices('i', time);
    },
    outTangents: function (time) {
      return this.vertices('o', time);
    },
    isClosed: function () {
      return this.v.c;
    },
    pointOnPath: function (perc, time) {
      var shapePath = this.v;
      if (time !== undefined) {
        shapePath = this.getValueAtTime(time, 0);
      }
      if (!this._segmentsLength) {
        this._segmentsLength = bez.getSegmentsLength(shapePath);
      }

      var segmentsLength = this._segmentsLength;
      var lengths = segmentsLength.lengths;
      var lengthPos = segmentsLength.totalLength * perc;
      var i = 0;
      var len = lengths.length;
      var accumulatedLength = 0;
      var pt;
      while (i < len) {
        if (accumulatedLength + lengths[i].addedLength > lengthPos) {
          var initIndex = i;
          var endIndex = (shapePath.c && i === len - 1) ? 0 : i + 1;
          var segmentPerc = (lengthPos - accumulatedLength) / lengths[i].addedLength;
          pt = bez.getPointInSegment(shapePath.v[initIndex], shapePath.v[endIndex], shapePath.o[initIndex], shapePath.i[endIndex], segmentPerc, lengths[i]);
          break;
        } else {
          accumulatedLength += lengths[i].addedLength;
        }
        i += 1;
      }
      if (!pt) {
        pt = shapePath.c ? [shapePath.v[0][0], shapePath.v[0][1]] : [shapePath.v[shapePath._length - 1][0], shapePath.v[shapePath._length - 1][1]];
      }
      return pt;
    },
    vectorOnPath: function (perc, time, vectorType) {
      // perc doesn't use triple equality because it can be a Number object as well as a primitive.
      if (perc == 1) { // eslint-disable-line eqeqeq
        perc = this.v.c;
      } else if (perc == 0) { // eslint-disable-line eqeqeq
        perc = 0.999;
      }
      var pt1 = this.pointOnPath(perc, time);
      var pt2 = this.pointOnPath(perc + 0.001, time);
      var xLength = pt2[0] - pt1[0];
      var yLength = pt2[1] - pt1[1];
      var magnitude = Math.sqrt(Math.pow(xLength, 2) + Math.pow(yLength, 2));
      if (magnitude === 0) {
        return [0, 0];
      }
      var unitVector = vectorType === 'tangent' ? [xLength / magnitude, yLength / magnitude] : [-yLength / magnitude, xLength / magnitude];
      return unitVector;
    },
    tangentOnPath: function (perc, time) {
      return this.vectorOnPath(perc, time, 'tangent');
    },
    normalOnPath: function (perc, time) {
      return this.vectorOnPath(perc, time, 'normal');
    },
    setGroupProperty: expressionHelpers.setGroupProperty,
    getValueAtTime: expressionHelpers.getStaticValueAtTime,
  };
  extendPrototype([ShapeExpressions], ShapePropertyConstructorFunction);
  extendPrototype([ShapeExpressions], KeyframedShapePropertyConstructorFunction);
  KeyframedShapePropertyConstructorFunction.prototype.getValueAtTime = getShapeValueAtTime;
  KeyframedShapePropertyConstructorFunction.prototype.initiateExpression = ExpressionManager.initiateExpression;

  var propertyGetShapeProp = ShapePropertyFactory.getShapeProp;
  ShapePropertyFactory.getShapeProp = function (elem, data, type, arr, trims) {
    var prop = propertyGetShapeProp(elem, data, type, arr, trims);
    prop.propertyIndex = data.ix;
    prop.lock = false;
    if (type === 3) {
      expressionHelpers.searchExpressions(elem, data.pt, prop);
    } else if (type === 4) {
      expressionHelpers.searchExpressions(elem, data.ks, prop);
    }
    if (prop.k) {
      elem.addDynamicProperty(prop);
    }
    return prop;
  };
}
```
</details>

### `loopOut(type: any, duration: any, durationFlag: any): any`

**Parameters:**

- **`type`** `any`
- **`duration`** `any`
- **`durationFlag`** `any`

**Returns:** `any`

**Calls:**

- `type.toLowerCase`
- `Math.max`
- `Math.abs`
- `Math.floor`
- `this.getValueAtTime`

<details><summary>Code</summary>

```typescript
function loopOut(type, duration, durationFlag) {
    if (!this.k || !this.keyframes) {
      return this.pv;
    }
    type = type ? type.toLowerCase() : '';
    var currentFrame = this.comp.renderedFrame;
    var keyframes = this.keyframes;
    var lastKeyFrame = keyframes[keyframes.length - 1].t;
    if (currentFrame <= lastKeyFrame) {
      return this.pv;
    }
    var cycleDuration;
    var firstKeyFrame;
    if (!durationFlag) {
      if (!duration || duration > keyframes.length - 1) {
        duration = keyframes.length - 1;
      }
      firstKeyFrame = keyframes[keyframes.length - 1 - duration].t;
      cycleDuration = lastKeyFrame - firstKeyFrame;
    } else {
      if (!duration) {
        cycleDuration = Math.max(0, lastKeyFrame - this.elem.data.ip);
      } else {
        cycleDuration = Math.abs(lastKeyFrame - this.elem.comp.globalData.frameRate * duration);
      }
      firstKeyFrame = lastKeyFrame - cycleDuration;
    }
    var i;
    var len;
    var ret;
    if (type === 'pingpong') {
      var iterations = Math.floor((currentFrame - firstKeyFrame) / cycleDuration);
      if (iterations % 2 !== 0) {
          return this.getValueAtTime(((cycleDuration - (currentFrame - firstKeyFrame) % cycleDuration + firstKeyFrame)) / this.comp.globalData.frameRate, 0); // eslint-disable-line
      }
    } else if (type === 'offset') {
      var initV = this.getValueAtTime(firstKeyFrame / this.comp.globalData.frameRate, 0);
      var endV = this.getValueAtTime(lastKeyFrame / this.comp.globalData.frameRate, 0);
        var current = this.getValueAtTime(((currentFrame - firstKeyFrame) % cycleDuration + firstKeyFrame) / this.comp.globalData.frameRate, 0); // eslint-disable-line
      var repeats = Math.floor((currentFrame - firstKeyFrame) / cycleDuration);
      if (this.pv.length) {
        ret = new Array(initV.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
          ret[i] = (endV[i] - initV[i]) * repeats + current[i];
        }
        return ret;
      }
      return (endV - initV) * repeats + current;
    } else if (type === 'continue') {
      var lastValue = this.getValueAtTime(lastKeyFrame / this.comp.globalData.frameRate, 0);
      var nextLastValue = this.getValueAtTime((lastKeyFrame - 0.001) / this.comp.globalData.frameRate, 0);
      if (this.pv.length) {
        ret = new Array(lastValue.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
            ret[i] = lastValue[i] + (lastValue[i] - nextLastValue[i]) * ((currentFrame - lastKeyFrame) / this.comp.globalData.frameRate) / 0.0005; // eslint-disable-line
        }
        return ret;
      }
      return lastValue + (lastValue - nextLastValue) * (((currentFrame - lastKeyFrame)) / 0.001);
    }
      return this.getValueAtTime((((currentFrame - firstKeyFrame) % cycleDuration + firstKeyFrame)) / this.comp.globalData.frameRate, 0); // eslint-disable-line

  }
```
</details>

### `loopIn(type: any, duration: any, durationFlag: any): any`

**Parameters:**

- **`type`** `any`
- **`duration`** `any`
- **`durationFlag`** `any`

**Returns:** `any`

**Calls:**

- `type.toLowerCase`
- `Math.max`
- `Math.abs`
- `Math.floor`
- `this.getValueAtTime`

<details><summary>Code</summary>

```typescript
function loopIn(type, duration, durationFlag) {
    if (!this.k) {
      return this.pv;
    }
    type = type ? type.toLowerCase() : '';
    var currentFrame = this.comp.renderedFrame;
    var keyframes = this.keyframes;
    var firstKeyFrame = keyframes[0].t;
    if (currentFrame >= firstKeyFrame) {
      return this.pv;
    }
    var cycleDuration;
    var lastKeyFrame;
    if (!durationFlag) {
      if (!duration || duration > keyframes.length - 1) {
        duration = keyframes.length - 1;
      }
      lastKeyFrame = keyframes[duration].t;
      cycleDuration = lastKeyFrame - firstKeyFrame;
    } else {
      if (!duration) {
        cycleDuration = Math.max(0, this.elem.data.op - firstKeyFrame);
      } else {
        cycleDuration = Math.abs(this.elem.comp.globalData.frameRate * duration);
      }
      lastKeyFrame = firstKeyFrame + cycleDuration;
    }
    var i;
    var len;
    var ret;
    if (type === 'pingpong') {
      var iterations = Math.floor((firstKeyFrame - currentFrame) / cycleDuration);
      if (iterations % 2 === 0) {
          return this.getValueAtTime((((firstKeyFrame - currentFrame) % cycleDuration + firstKeyFrame)) / this.comp.globalData.frameRate, 0); // eslint-disable-line
      }
    } else if (type === 'offset') {
      var initV = this.getValueAtTime(firstKeyFrame / this.comp.globalData.frameRate, 0);
      var endV = this.getValueAtTime(lastKeyFrame / this.comp.globalData.frameRate, 0);
      var current = this.getValueAtTime((cycleDuration - ((firstKeyFrame - currentFrame) % cycleDuration) + firstKeyFrame) / this.comp.globalData.frameRate, 0);
      var repeats = Math.floor((firstKeyFrame - currentFrame) / cycleDuration) + 1;
      if (this.pv.length) {
        ret = new Array(initV.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
          ret[i] = current[i] - (endV[i] - initV[i]) * repeats;
        }
        return ret;
      }
      return current - (endV - initV) * repeats;
    } else if (type === 'continue') {
      var firstValue = this.getValueAtTime(firstKeyFrame / this.comp.globalData.frameRate, 0);
      var nextFirstValue = this.getValueAtTime((firstKeyFrame + 0.001) / this.comp.globalData.frameRate, 0);
      if (this.pv.length) {
        ret = new Array(firstValue.length);
        len = ret.length;
        for (i = 0; i < len; i += 1) {
          ret[i] = firstValue[i] + ((firstValue[i] - nextFirstValue[i]) * (firstKeyFrame - currentFrame)) / 0.001;
        }
        return ret;
      }
      return firstValue + ((firstValue - nextFirstValue) * (firstKeyFrame - currentFrame)) / 0.001;
    }
      return this.getValueAtTime(((cycleDuration - ((firstKeyFrame - currentFrame) % cycleDuration + firstKeyFrame))) / this.comp.globalData.frameRate, 0); // eslint-disable-line

  }
```
</details>

### `smooth(width: any, samples: any): any`

**Parameters:**

- **`width`** `any`
- **`samples`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `createTypedArray`
- `this.getValueAtTime`

<details><summary>Code</summary>

```typescript
function smooth(width, samples) {
    if (!this.k) {
      return this.pv;
    }
    width = (width || 0.4) * 0.5;
    samples = Math.floor(samples || 5);
    if (samples <= 1) {
      return this.pv;
    }
    var currentTime = this.comp.renderedFrame / this.comp.globalData.frameRate;
    var initFrame = currentTime - width;
    var endFrame = currentTime + width;
    var sampleFrequency = samples > 1 ? (endFrame - initFrame) / (samples - 1) : 1;
    var i = 0;
    var j = 0;
    var value;
    if (this.pv.length) {
      value = createTypedArray('float32', this.pv.length);
    } else {
      value = 0;
    }
    var sampleValue;
    while (i < samples) {
      sampleValue = this.getValueAtTime(initFrame + i * sampleFrequency);
      if (this.pv.length) {
        for (j = 0; j < this.pv.length; j += 1) {
          value[j] += sampleValue[j];
        }
      } else {
        value += sampleValue;
      }
      i += 1;
    }
    if (this.pv.length) {
      for (j = 0; j < this.pv.length; j += 1) {
        value[j] /= samples;
      }
    } else {
      value /= samples;
    }
    return value;
  }
```
</details>

### `getTransformValueAtTime(time: any): (Anonymous function)`

**Parameters:**

- **`time`** `any`

**Returns:** `(Anonymous function)`

**Calls:**

- `matrix.cloneFromProps`
- `this.a.getValueAtTime`
- `matrix.translate`
- `this.s.getValueAtTime`
- `matrix.scale`
- `this.sk.getValueAtTime`
- `this.sa.getValueAtTime`
- `matrix.skewFromAxis`
- `this.r.getValueAtTime`
- `matrix.rotate`
- `this.rz.getValueAtTime`
- `this.ry.getValueAtTime`
- `this.rx.getValueAtTime`
- `this.or.getValueAtTime`
- `matrix.rotateZ(-rotationZ * this.rz.mult)
        .rotateY(rotationY * this.ry.mult)
        .rotateX(rotationX * this.rx.mult)
        .rotateZ(-orientation[2] * this.or.mult)
        .rotateY(orientation[1] * this.or.mult)
        .rotateX`
- `this.px.getValueAtTime`
- `this.py.getValueAtTime`
- `this.pz.getValueAtTime`
- `this.p.getValueAtTime`

**Internal Comments:**
```
/// / (x2)
```

<details><summary>Code</summary>

```typescript
function getTransformValueAtTime(time) {
    if (!this._transformCachingAtTime) {
      this._transformCachingAtTime = {
        v: new Matrix(),
      };
    }
    /// /
    var matrix = this._transformCachingAtTime.v;
    matrix.cloneFromProps(this.pre.props);
    if (this.appliedTransformations < 1) {
      var anchor = this.a.getValueAtTime(time);
      matrix.translate(
        -anchor[0] * this.a.mult,
        -anchor[1] * this.a.mult,
        anchor[2] * this.a.mult
      );
    }
    if (this.appliedTransformations < 2) {
      var scale = this.s.getValueAtTime(time);
      matrix.scale(
        scale[0] * this.s.mult,
        scale[1] * this.s.mult,
        scale[2] * this.s.mult
      );
    }
    if (this.sk && this.appliedTransformations < 3) {
      var skew = this.sk.getValueAtTime(time);
      var skewAxis = this.sa.getValueAtTime(time);
      matrix.skewFromAxis(-skew * this.sk.mult, skewAxis * this.sa.mult);
    }
    if (this.r && this.appliedTransformations < 4) {
      var rotation = this.r.getValueAtTime(time);
      matrix.rotate(-rotation * this.r.mult);
    } else if (!this.r && this.appliedTransformations < 4) {
      var rotationZ = this.rz.getValueAtTime(time);
      var rotationY = this.ry.getValueAtTime(time);
      var rotationX = this.rx.getValueAtTime(time);
      var orientation = this.or.getValueAtTime(time);
      matrix.rotateZ(-rotationZ * this.rz.mult)
        .rotateY(rotationY * this.ry.mult)
        .rotateX(rotationX * this.rx.mult)
        .rotateZ(-orientation[2] * this.or.mult)
        .rotateY(orientation[1] * this.or.mult)
        .rotateX(orientation[0] * this.or.mult);
    }
    if (this.data.p && this.data.p.s) {
      var positionX = this.px.getValueAtTime(time);
      var positionY = this.py.getValueAtTime(time);
      if (this.data.p.z) {
        var positionZ = this.pz.getValueAtTime(time);
        matrix.translate(
          positionX * this.px.mult,
          positionY * this.py.mult,
          -positionZ * this.pz.mult
        );
      } else {
        matrix.translate(positionX * this.px.mult, positionY * this.py.mult, 0);
      }
    } else {
      var position = this.p.getValueAtTime(time);
      matrix.translate(
        position[0] * this.p.mult,
        position[1] * this.p.mult,
        -position[2] * this.p.mult
      );
    }
    return matrix;
    /// /
  }
```
</details>

### `getTransformStaticValueAtTime(): any`

**Returns:** `any`

**Calls:**

- `this.v.clone`

<details><summary>Code</summary>

```typescript
function getTransformStaticValueAtTime() {
    return this.v.clone(new Matrix());
  }
```
</details>

### `getShapeValueAtTime(frameNum: any): any`

**Parameters:**

- **`frameNum`** `any`

**Returns:** `any`

**Calls:**

- `shapePool.clone`
- `this.interpolateShape`

**Internal Comments:**
```
// For now this caching object is created only when needed instead of creating it when the shape is initialized.
```

<details><summary>Code</summary>

```typescript
function getShapeValueAtTime(frameNum) {
    // For now this caching object is created only when needed instead of creating it when the shape is initialized.
    if (!this._cachingAtTime) {
      this._cachingAtTime = {
        shapeValue: shapePool.clone(this.pv),
        lastIndex: 0,
        lastTime: initialDefaultFrame,
      };
    }

    frameNum *= this.elem.globalData.frameRate;
    frameNum -= this.offsetTime;
    if (frameNum !== this._cachingAtTime.lastTime) {
      this._cachingAtTime.lastIndex = this._cachingAtTime.lastTime < frameNum ? this._caching.lastIndex : 0;
      this._cachingAtTime.lastTime = frameNum;
      this.interpolateShape(frameNum, this._cachingAtTime.shapeValue, this._cachingAtTime);
    }
    return this._cachingAtTime.shapeValue;
  }
```
</details>

### `ShapeExpressions(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ShapeExpressions() {}
```
</details>

### `vertices(prop: any, time: any): any`

**Parameters:**

- **`prop`** `any`
- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.getValue`
- `this.getValueAtTime`
- `createSizedArray`

<details><summary>Code</summary>

```typescript
function (prop, time) {
      if (this.k) {
        this.getValue();
      }
      var shapePath = this.v;
      if (time !== undefined) {
        shapePath = this.getValueAtTime(time, 0);
      }
      var i;
      var len = shapePath._length;
      var vertices = shapePath[prop];
      var points = shapePath.v;
      var arr = createSizedArray(len);
      for (i = 0; i < len; i += 1) {
        if (prop === 'i' || prop === 'o') {
          arr[i] = [vertices[i][0] - points[i][0], vertices[i][1] - points[i][1]];
        } else {
          arr[i] = [vertices[i][0], vertices[i][1]];
        }
      }
      return arr;
    }
```
</details>

### `points(time: any): any`

**Parameters:**

- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.vertices`

<details><summary>Code</summary>

```typescript
function (time) {
      return this.vertices('v', time);
    }
```
</details>

### `inTangents(time: any): any`

**Parameters:**

- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.vertices`

<details><summary>Code</summary>

```typescript
function (time) {
      return this.vertices('i', time);
    }
```
</details>

### `outTangents(time: any): any`

**Parameters:**

- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.vertices`

<details><summary>Code</summary>

```typescript
function (time) {
      return this.vertices('o', time);
    }
```
</details>

### `isClosed(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
      return this.v.c;
    }
```
</details>

### `pointOnPath(perc: any, time: any): any[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`

**Returns:** `any[]`

**Calls:**

- `this.getValueAtTime`
- `bez.getSegmentsLength`
- `bez.getPointInSegment`

<details><summary>Code</summary>

```typescript
function (perc, time) {
      var shapePath = this.v;
      if (time !== undefined) {
        shapePath = this.getValueAtTime(time, 0);
      }
      if (!this._segmentsLength) {
        this._segmentsLength = bez.getSegmentsLength(shapePath);
      }

      var segmentsLength = this._segmentsLength;
      var lengths = segmentsLength.lengths;
      var lengthPos = segmentsLength.totalLength * perc;
      var i = 0;
      var len = lengths.length;
      var accumulatedLength = 0;
      var pt;
      while (i < len) {
        if (accumulatedLength + lengths[i].addedLength > lengthPos) {
          var initIndex = i;
          var endIndex = (shapePath.c && i === len - 1) ? 0 : i + 1;
          var segmentPerc = (lengthPos - accumulatedLength) / lengths[i].addedLength;
          pt = bez.getPointInSegment(shapePath.v[initIndex], shapePath.v[endIndex], shapePath.o[initIndex], shapePath.i[endIndex], segmentPerc, lengths[i]);
          break;
        } else {
          accumulatedLength += lengths[i].addedLength;
        }
        i += 1;
      }
      if (!pt) {
        pt = shapePath.c ? [shapePath.v[0][0], shapePath.v[0][1]] : [shapePath.v[shapePath._length - 1][0], shapePath.v[shapePath._length - 1][1]];
      }
      return pt;
    }
```
</details>

### `vectorOnPath(perc: any, time: any, vectorType: any): number[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`
- **`vectorType`** `any`

**Returns:** `number[]`

**Calls:**

- `this.pointOnPath`
- `Math.sqrt`
- `Math.pow`

**Internal Comments:**
```
// perc doesn't use triple equality because it can be a Number object as well as a primitive.
```

<details><summary>Code</summary>

```typescript
function (perc, time, vectorType) {
      // perc doesn't use triple equality because it can be a Number object as well as a primitive.
      if (perc == 1) { // eslint-disable-line eqeqeq
        perc = this.v.c;
      } else if (perc == 0) { // eslint-disable-line eqeqeq
        perc = 0.999;
      }
      var pt1 = this.pointOnPath(perc, time);
      var pt2 = this.pointOnPath(perc + 0.001, time);
      var xLength = pt2[0] - pt1[0];
      var yLength = pt2[1] - pt1[1];
      var magnitude = Math.sqrt(Math.pow(xLength, 2) + Math.pow(yLength, 2));
      if (magnitude === 0) {
        return [0, 0];
      }
      var unitVector = vectorType === 'tangent' ? [xLength / magnitude, yLength / magnitude] : [-yLength / magnitude, xLength / magnitude];
      return unitVector;
    }
```
</details>

### `tangentOnPath(perc: any, time: any): number[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`

**Returns:** `number[]`

**Calls:**

- `this.vectorOnPath`

<details><summary>Code</summary>

```typescript
function (perc, time) {
      return this.vectorOnPath(perc, time, 'tangent');
    }
```
</details>

### `normalOnPath(perc: any, time: any): number[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`

**Returns:** `number[]`

**Calls:**

- `this.vectorOnPath`

<details><summary>Code</summary>

```typescript
function (perc, time) {
      return this.vectorOnPath(perc, time, 'normal');
    }
```
</details>

### `vertices(prop: any, time: any): any`

**Parameters:**

- **`prop`** `any`
- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.getValue`
- `this.getValueAtTime`
- `createSizedArray`

<details><summary>Code</summary>

```typescript
function (prop, time) {
      if (this.k) {
        this.getValue();
      }
      var shapePath = this.v;
      if (time !== undefined) {
        shapePath = this.getValueAtTime(time, 0);
      }
      var i;
      var len = shapePath._length;
      var vertices = shapePath[prop];
      var points = shapePath.v;
      var arr = createSizedArray(len);
      for (i = 0; i < len; i += 1) {
        if (prop === 'i' || prop === 'o') {
          arr[i] = [vertices[i][0] - points[i][0], vertices[i][1] - points[i][1]];
        } else {
          arr[i] = [vertices[i][0], vertices[i][1]];
        }
      }
      return arr;
    }
```
</details>

### `points(time: any): any`

**Parameters:**

- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.vertices`

<details><summary>Code</summary>

```typescript
function (time) {
      return this.vertices('v', time);
    }
```
</details>

### `inTangents(time: any): any`

**Parameters:**

- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.vertices`

<details><summary>Code</summary>

```typescript
function (time) {
      return this.vertices('i', time);
    }
```
</details>

### `outTangents(time: any): any`

**Parameters:**

- **`time`** `any`

**Returns:** `any`

**Calls:**

- `this.vertices`

<details><summary>Code</summary>

```typescript
function (time) {
      return this.vertices('o', time);
    }
```
</details>

### `isClosed(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
      return this.v.c;
    }
```
</details>

### `pointOnPath(perc: any, time: any): any[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`

**Returns:** `any[]`

**Calls:**

- `this.getValueAtTime`
- `bez.getSegmentsLength`
- `bez.getPointInSegment`

<details><summary>Code</summary>

```typescript
function (perc, time) {
      var shapePath = this.v;
      if (time !== undefined) {
        shapePath = this.getValueAtTime(time, 0);
      }
      if (!this._segmentsLength) {
        this._segmentsLength = bez.getSegmentsLength(shapePath);
      }

      var segmentsLength = this._segmentsLength;
      var lengths = segmentsLength.lengths;
      var lengthPos = segmentsLength.totalLength * perc;
      var i = 0;
      var len = lengths.length;
      var accumulatedLength = 0;
      var pt;
      while (i < len) {
        if (accumulatedLength + lengths[i].addedLength > lengthPos) {
          var initIndex = i;
          var endIndex = (shapePath.c && i === len - 1) ? 0 : i + 1;
          var segmentPerc = (lengthPos - accumulatedLength) / lengths[i].addedLength;
          pt = bez.getPointInSegment(shapePath.v[initIndex], shapePath.v[endIndex], shapePath.o[initIndex], shapePath.i[endIndex], segmentPerc, lengths[i]);
          break;
        } else {
          accumulatedLength += lengths[i].addedLength;
        }
        i += 1;
      }
      if (!pt) {
        pt = shapePath.c ? [shapePath.v[0][0], shapePath.v[0][1]] : [shapePath.v[shapePath._length - 1][0], shapePath.v[shapePath._length - 1][1]];
      }
      return pt;
    }
```
</details>

### `vectorOnPath(perc: any, time: any, vectorType: any): number[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`
- **`vectorType`** `any`

**Returns:** `number[]`

**Calls:**

- `this.pointOnPath`
- `Math.sqrt`
- `Math.pow`

**Internal Comments:**
```
// perc doesn't use triple equality because it can be a Number object as well as a primitive.
```

<details><summary>Code</summary>

```typescript
function (perc, time, vectorType) {
      // perc doesn't use triple equality because it can be a Number object as well as a primitive.
      if (perc == 1) { // eslint-disable-line eqeqeq
        perc = this.v.c;
      } else if (perc == 0) { // eslint-disable-line eqeqeq
        perc = 0.999;
      }
      var pt1 = this.pointOnPath(perc, time);
      var pt2 = this.pointOnPath(perc + 0.001, time);
      var xLength = pt2[0] - pt1[0];
      var yLength = pt2[1] - pt1[1];
      var magnitude = Math.sqrt(Math.pow(xLength, 2) + Math.pow(yLength, 2));
      if (magnitude === 0) {
        return [0, 0];
      }
      var unitVector = vectorType === 'tangent' ? [xLength / magnitude, yLength / magnitude] : [-yLength / magnitude, xLength / magnitude];
      return unitVector;
    }
```
</details>

### `tangentOnPath(perc: any, time: any): number[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`

**Returns:** `number[]`

**Calls:**

- `this.vectorOnPath`

<details><summary>Code</summary>

```typescript
function (perc, time) {
      return this.vectorOnPath(perc, time, 'tangent');
    }
```
</details>

### `normalOnPath(perc: any, time: any): number[]`

**Parameters:**

- **`perc`** `any`
- **`time`** `any`

**Returns:** `number[]`

**Calls:**

- `this.vectorOnPath`

<details><summary>Code</summary>

```typescript
function (perc, time) {
      return this.vectorOnPath(perc, time, 'normal');
    }
```
</details>

### `initialize$1(): void`

**Returns:** `void`

**Calls:**

- `addPropertyDecorator`

<details><summary>Code</summary>

```typescript
function initialize$1() {
  addPropertyDecorator();
}
```
</details>

### `addDecorator(): void`

**Returns:** `void`

**Calls:**

- `complex_call_475948`
- `this.addEffect`
- `this.getExpressionValue.bind`
- `this.calculateExpression`
- `this.copyData`
- `newValue.toString`
- `this.searchKeyframes`
- `this.searchExpressions`

<details><summary>Code</summary>

```typescript
function addDecorator() {
  function searchExpressions() {
    if (this.data.d.x) {
      this.calculateExpression = ExpressionManager.initiateExpression.bind(this)(this.elem, this.data.d, this);
      this.addEffect(this.getExpressionValue.bind(this));
      return true;
    }
    return null;
  }

  TextProperty.prototype.getExpressionValue = function (currentValue, text) {
    var newValue = this.calculateExpression(text);
    if (currentValue.t !== newValue) {
      var newData = {};
      this.copyData(newData, currentValue);
      newData.t = newValue.toString();
      newData.__complete = false;
      return newData;
    }
    return currentValue;
  };

  TextProperty.prototype.searchProperty = function () {
    var isKeyframed = this.searchKeyframes();
    var hasExpressions = this.searchExpressions();
    this.kf = isKeyframed || hasExpressions;
    return this.kf;
  };

  TextProperty.prototype.searchExpressions = searchExpressions;
}
```
</details>

### `searchExpressions(): boolean`

**Returns:** `boolean`

**Calls:**

- `complex_call_475948`
- `this.addEffect`
- `this.getExpressionValue.bind`

<details><summary>Code</summary>

```typescript
function searchExpressions() {
    if (this.data.d.x) {
      this.calculateExpression = ExpressionManager.initiateExpression.bind(this)(this.elem, this.data.d, this);
      this.addEffect(this.getExpressionValue.bind(this));
      return true;
    }
    return null;
  }
```
</details>

### `initialize(): void`

**Returns:** `void`

**Calls:**

- `addDecorator`

<details><summary>Code</summary>

```typescript
function initialize() {
  addDecorator();
}
```
</details>


---