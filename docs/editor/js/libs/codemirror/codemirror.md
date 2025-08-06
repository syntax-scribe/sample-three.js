[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `codemirror.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 968 |
| 📊 Variables & Constants | 1070 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/codemirror/codemirror.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `userAgent` | `string` | let/var | `navigator.userAgent` | ✗ |
| `platform` | `string` | let/var | `navigator.platform` | ✗ |
| `ie` | `true \| RegExpExecArray` | let/var | `ie_upto10 \|\| ie_11up \|\| edge` | ✗ |
| `ie_version` | `any` | let/var | `ie && (ie_upto10 ? document.documentMode \|\| 6 : +(edge \|\| ie_11up)[1])` | ✗ |
| `webkit` | `boolean` | let/var | `!edge && /WebKit\//.test(userAgent)` | ✗ |
| `qtwebkit` | `boolean` | let/var | `webkit && /Qt\/\d+\.\d+/.test(userAgent)` | ✗ |
| `chrome` | `boolean` | let/var | `!edge && /Chrome\//.test(userAgent)` | ✗ |
| `ios` | `boolean` | let/var | `safari && (/Mobile\/\w+/.test(userAgent) \|\| navigator.maxTouchPoints > 2)` | ✗ |
| `mobile` | `boolean` | let/var | `ios \|\| android \|\| /webOS\|BlackBerry\|Opera Mini\|Opera Mobi\|IEMobile/i....` | ✗ |
| `mac` | `boolean` | let/var | `ios \|\| /Mac/.test(platform)` | ✗ |
| `presto_version` | `RegExpMatchArray` | let/var | `presto && userAgent.match(/Version\/(\d*\.\d*)/)` | ✗ |
| `flipCtrlCmd` | `boolean` | let/var | `mac && (qtwebkit \|\| presto && (presto_version == null \|\| presto_version <...` | ✗ |
| `captureRightClick` | `boolean` | let/var | `gecko \|\| (ie && ie_version >= 9)` | ✗ |
| `current` | `any` | let/var | `node.className` | ✗ |
| `range` | `any` | let/var | `*not shown*` | ✗ |
| `activeElement` | `any` | let/var | `*not shown*` | ✗ |
| `current` | `any` | let/var | `node.className` | ✗ |
| `time` | `any` | let/var | `+new Date + ms` | ✗ |
| `scrollerGap` | `number` | let/var | `50` | ✗ |
| `Pass` | `{ toString: () => string; }` | let/var | `{toString: function(){return "CodeMirror.Pass"}}` | ✗ |
| `sel_dontScroll` | `{ scroll: boolean; }` | let/var | `{scroll: false}` | ✗ |
| `sel_mouse` | `{ origin: string; }` | let/var | `{origin: "*mouse"}` | ✗ |
| `sel_move` | `{ origin: string; }` | let/var | `{origin: "+move"}` | ✗ |
| `skipped` | `number` | let/var | `nextTab - pos` | ✗ |
| `spaceStrs` | `string[]` | let/var | `[""]` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `inst` | `any` | let/var | `*not shown*` | ✗ |
| `nonASCIISingleCaseWordChar` | `RegExp` | let/var | `/[\u00df\u0587\u0590-\u05f4\u0600-\u06ff\u3040-\u309f\u30a0-\u30ff\u3400-\u4d...` | ✗ |
| `extendingChars` | `RegExp` | let/var | `/[\u0300-\u036f\u0483-\u0489\u0591-\u05bd\u05bf\u05c1\u05c2\u05c4\u05c5\u05c7...` | ✗ |
| `dir` | `number` | let/var | `from > to ? -1 : 1` | ✗ |
| `midF` | `number` | let/var | `(from + to) / 2` | ✗ |
| `mid` | `number` | let/var | `dir < 0 ? Math.ceil(midF) : Math.floor(midF)` | ✗ |
| `found` | `boolean` | let/var | `false` | ✗ |
| `part` | `any` | let/var | `order[i]` | ✗ |
| `bidiOther` | `any` | let/var | `null` | ✗ |
| `found` | `any` | let/var | `*not shown*` | ✗ |
| `cur` | `any` | let/var | `order[i]` | ✗ |
| `lowTypes` | `string` | let/var | `"bbbbbbbbbtstwsbbbbbbbbbbbbbbssstwNN%%%NNNNNN,N,N1111111111NNNNNNNLLLLLLLLLLL...` | ✗ |
| `arabicTypes` | `string` | let/var | `"nnnnnnNNr%%r,rNNmmmmmmmmmmmrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrm...` | ✗ |
| `bidiRE` | `RegExp` | let/var | `/[\u0590-\u05f4\u0600-\u06ff\u0700-\u08ac]/` | ✗ |
| `isNeutral` | `RegExp` | let/var | `/[stwN]/` | ✗ |
| `isStrong` | `RegExp` | let/var | `/[LRr]/` | ✗ |
| `countsAsLeft` | `RegExp` | let/var | `/[Lb1n]/` | ✗ |
| `countsAsNum` | `RegExp` | let/var | `/[1n]/` | ✗ |
| `outerType` | `string` | let/var | `direction == "ltr" ? "L" : "R"` | ✗ |
| `len` | `any` | let/var | `str.length` | ✗ |
| `types` | `any[]` | let/var | `[]` | ✗ |
| `type` | `string` | let/var | `types[i$1]` | ✗ |
| `type$1` | `string` | let/var | `types[i$2]` | ✗ |
| `type$2` | `string` | let/var | `types[i$3]` | ✗ |
| `type$3` | `any` | let/var | `types[i$4]` | ✗ |
| `end` | `any` | let/var | `(void 0)` | ✗ |
| `replace` | `any` | let/var | `(i$4 && types[i$4-1] == "!") \|\| (end < len && types[end] == "1") ? "1" : "N"` | ✗ |
| `type$4` | `any` | let/var | `types[i$5]` | ✗ |
| `end$1` | `any` | let/var | `(void 0)` | ✗ |
| `before` | `any` | let/var | `(i$6 ? types[i$6-1] : outerType) == "L"` | ✗ |
| `after` | `any` | let/var | `(end$1 < len ? types[end$1] : outerType) == "L"` | ✗ |
| `replace$1` | `any` | let/var | `before == after ? (before ? "L" : "R") : outerType` | ✗ |
| `order` | `any[]` | let/var | `[]` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `number` | let/var | `i$7` | ✗ |
| `pos` | `number` | let/var | `i$7` | ✗ |
| `at` | `number` | let/var | `order.length` | ✗ |
| `isRTL` | `number` | let/var | `direction == "rtl" ? 1 : 0` | ✗ |
| `nstart` | `number` | let/var | `j$2` | ✗ |
| `order` | `any` | let/var | `line.order` | ✗ |
| `noHandlers` | `any[]` | let/var | `[]` | ✗ |
| `map` | `any` | let/var | `emitter._handlers \|\| (emitter._handlers = {})` | ✗ |
| `map` | `any` | let/var | `emitter._handlers` | ✗ |
| `arr` | `any` | let/var | `map && map[type]` | ✗ |
| `arr` | `any` | let/var | `cm._handlers && cm._handlers.cursorActivity` | ✗ |
| `set` | `any` | let/var | `cm.curOp.cursorActivityHandlers \|\| (cm.curOp.cursorActivityHandlers = [])` | ✗ |
| `b` | `any` | let/var | `e.which` | ✗ |
| `zwspSupported` | `any` | let/var | `*not shown*` | ✗ |
| `node` | `any` | let/var | `zwspSupported ? elt("span", "\u200b") : elt("span", "\u00a0", null, "display:...` | ✗ |
| `badBidiRects` | `any` | let/var | `*not shown*` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `l` | `any` | let/var | `string.length` | ✗ |
| `splitLinesAuto` | `(string: any) => any` | let/var | `"\n\nb".split(/\n/).length != 3 ? function (string) { var pos = 0, result = [...` | ✗ |
| `range` | `any` | let/var | `*not shown*` | ✗ |
| `hasSelection` | `(te: any) => boolean` | let/var | `window.getSelection ? function (te) { try { return te.selectionStart != te.se...` | ✗ |
| `badZoomedRects` | `any` | let/var | `null` | ✗ |
| `modes` | `{}` | let/var | `{}` | ✗ |
| `mimeModes` | `{}` | let/var | `{}` | ✗ |
| `found` | `any` | let/var | `mimeModes[spec.name]` | ✗ |
| `mfactory` | `any` | let/var | `modes[spec.name]` | ✗ |
| `exts` | `any` | let/var | `modeExtensions[spec.name]` | ✗ |
| `modeExtensions` | `{}` | let/var | `{}` | ✗ |
| `exts` | `any` | let/var | `modeExtensions.hasOwnProperty(mode) ? modeExtensions[mode] : (modeExtensions[...` | ✗ |
| `nstate` | `{}` | let/var | `{}` | ✗ |
| `val` | `any` | let/var | `state[n]` | ✗ |
| `info` | `any` | let/var | `*not shown*` | ✗ |
| `ok` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `number` | let/var | `this.pos` | ✗ |
| `start` | `number` | let/var | `this.pos` | ✗ |
| `oracle` | `any` | let/var | `this.lineOracle` | ✗ |
| `oracle` | `any` | let/var | `this.lineOracle` | ✗ |
| `chunk` | `any` | let/var | `doc` | ✗ |
| `child` | `any` | let/var | `chunk.children[i]` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `n` | `any` | let/var | `start.line` | ✗ |
| `text` | `any` | let/var | `line.text` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `diff` | `number` | let/var | `height - line.height` | ✗ |
| `cur` | `any` | let/var | `line.parent` | ✗ |
| `n` | `any` | let/var | `chunk.first` | ✗ |
| `child` | `any` | let/var | `chunk.children[i$1]` | ✗ |
| `ch` | `any` | let/var | `child.height` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `line` | `any` | let/var | `chunk.lines[i]` | ✗ |
| `lh` | `any` | let/var | `line.height` | ✗ |
| `last` | `number` | let/var | `doc.first + doc.size - 1` | ✗ |
| `ch` | `any` | let/var | `pos.ch` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `type` | `any` | let/var | `this.baseTokens[this.baseTokenPos + 1]` | ✗ |
| `state` | `any` | let/var | `copy !== false ? copyState(this.doc.mode, this.state) : this.state` | ✗ |
| `st` | `any[]` | let/var | `[cm.state.modeGen]` | ✗ |
| `lineClasses` | `{}` | let/var | `{}` | ✗ |
| `state` | `any` | let/var | `context.state` | ✗ |
| `overlay` | `any` | let/var | `cm.state.overlays[o]` | ✗ |
| `i` | `number` | let/var | `1` | ✗ |
| `at` | `number` | let/var | `0` | ✗ |
| `start` | `number` | let/var | `i` | ✗ |
| `i_end` | `any` | let/var | `st[i]` | ✗ |
| `cur` | `any` | let/var | `st[start+1]` | ✗ |
| `resetState` | `any` | let/var | `line.text.length > cm.options.maxHighlightLength && copyState(cm.doc.mode, co...` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `saved` | `any` | let/var | `start > doc.first && getLine(doc, start - 1).stateAfter` | ✗ |
| `context` | `Context` | let/var | `saved ? Context.fromSaved(doc, saved, start) : new Context(doc, startState(do...` | ✗ |
| `pos` | `any` | let/var | `context.line` | ✗ |
| `mode` | `any` | let/var | `cm.doc.mode` | ✗ |
| `stream` | `StringStream` | let/var | `new StringStream(text, cm.options.tabSize, context)` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `mode` | `any` | let/var | `doc.mode` | ✗ |
| `style` | `any` | let/var | `*not shown*` | ✗ |
| `stream` | `StringStream` | let/var | `new StringStream(line.text, cm.options.tabSize, context)` | ✗ |
| `tokens` | `any` | let/var | `*not shown*` | ✗ |
| `prop` | `string` | let/var | `lineClass[1] ? "bgClass" : "textClass"` | ✗ |
| `flattenSpans` | `any` | let/var | `mode.flattenSpans` | ✗ |
| `curStart` | `number` | let/var | `0` | ✗ |
| `curStyle` | `any` | let/var | `null` | ✗ |
| `stream` | `StringStream` | let/var | `new StringStream(text, cm.options.tabSize, context)` | ✗ |
| `style` | `any` | let/var | `*not shown*` | ✗ |
| `inner` | `any[]` | let/var | `cm.options.addModeClass && [null]` | ✗ |
| `mName` | `any` | let/var | `inner[0].name` | ✗ |
| `minindent` | `any` | let/var | `*not shown*` | ✗ |
| `minline` | `any` | let/var | `*not shown*` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `lim` | `number` | let/var | `precise ? -1 : n - (cm.doc.mode.innerMode ? 1000 : 100)` | ✗ |
| `after` | `any` | let/var | `line.stateAfter` | ✗ |
| `start` | `any` | let/var | `doc.first` | ✗ |
| `saved` | `any` | let/var | `getLine(doc, line).stateAfter` | ✗ |
| `sawReadOnlySpans` | `boolean` | let/var | `false` | ✗ |
| `sawCollapsedSpans` | `boolean` | let/var | `false` | ✗ |
| `span` | `any` | let/var | `spans[i]` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `inThisOp` | `any` | let/var | `op && window.WeakSet && (op.markedSpans \|\| (op.markedSpans = new WeakSet))` | ✗ |
| `nw` | `any` | let/var | `*not shown*` | ✗ |
| `span` | `any` | let/var | `old[i]` | ✗ |
| `marker` | `any` | let/var | `span.marker` | ✗ |
| `startsBefore` | `boolean` | let/var | `span.from == null \|\| (marker.inclusiveLeft ? span.from <= startCh : span.fr...` | ✗ |
| `endsAfter` | `boolean` | let/var | `span.to == null \|\| (marker.inclusiveRight ? span.to >= startCh : span.to > ...` | ✗ |
| `nw` | `any` | let/var | `*not shown*` | ✗ |
| `span` | `any` | let/var | `old[i]` | ✗ |
| `marker` | `any` | let/var | `span.marker` | ✗ |
| `endsAfter` | `boolean` | let/var | `span.to == null \|\| (marker.inclusiveRight ? span.to >= endCh : span.to > en...` | ✗ |
| `startsBefore` | `boolean` | let/var | `span.from == null \|\| (marker.inclusiveLeft ? span.from <= endCh : span.from...` | ✗ |
| `oldFirst` | `any` | let/var | `isLine(doc, change.from.line) && getLine(doc, change.from.line).markedSpans` | ✗ |
| `oldLast` | `any` | let/var | `isLine(doc, change.to.line) && getLine(doc, change.to.line).markedSpans` | ✗ |
| `startCh` | `any` | let/var | `change.from.ch` | ✗ |
| `endCh` | `any` | let/var | `change.to.ch` | ✗ |
| `isInsert` | `boolean` | let/var | `cmp(change.from, change.to) == 0` | ✗ |
| `sameLine` | `boolean` | let/var | `change.text.length == 1` | ✗ |
| `offset` | `any` | let/var | `lst(change.text).length + (sameLine ? startCh : 0)` | ✗ |
| `span` | `any` | let/var | `first[i]` | ✗ |
| `span$1` | `any` | let/var | `last[i$1]` | ✗ |
| `newMarkers` | `any[][]` | let/var | `[first]` | ✗ |
| `gap` | `number` | let/var | `change.text.length - 2` | ✗ |
| `gapMarkers` | `any` | let/var | `*not shown*` | ✗ |
| `span` | `any` | let/var | `spans[i]` | ✗ |
| `markers` | `any` | let/var | `null` | ✗ |
| `mark` | `any` | let/var | `line.markedSpans[i].marker` | ✗ |
| `parts` | `{ from: any; to: any; }[]` | let/var | `[{from: from, to: to}]` | ✗ |
| `mk` | `never` | let/var | `markers[i]` | ✗ |
| `p` | `{ from: any; to: any; }` | let/var | `parts[j]` | ✗ |
| `newParts` | `number[]` | let/var | `[j, 1]` | ✗ |
| `spans` | `any` | let/var | `line.markedSpans` | ✗ |
| `lenDiff` | `number` | let/var | `a.lines.length - b.lines.length` | ✗ |
| `fromCmp` | `number` | let/var | `cmp(aPos.from, bPos.from) \|\| extraLeft(a) - extraLeft(b)` | ✗ |
| `toCmp` | `number` | let/var | `cmp(aPos.to, bPos.to) \|\| extraRight(a) - extraRight(b)` | ✗ |
| `sps` | `any` | let/var | `sawCollapsedSpans && line.markedSpans` | ✗ |
| `found` | `any` | let/var | `*not shown*` | ✗ |
| `sps` | `any` | let/var | `sawCollapsedSpans && line.markedSpans` | ✗ |
| `found` | `any` | let/var | `*not shown*` | ✗ |
| `sp` | `any` | let/var | `sps[i]` | ✗ |
| `sps` | `any` | let/var | `sawCollapsedSpans && line.markedSpans` | ✗ |
| `sp` | `any` | let/var | `sps[i]` | ✗ |
| `fromCmp` | `number` | let/var | `cmp(found.from, from) \|\| extraLeft(sp.marker) - extraLeft(marker)` | ✗ |
| `toCmp` | `number` | let/var | `cmp(found.to, to) \|\| extraRight(sp.marker) - extraRight(marker)` | ✗ |
| `merged` | `any` | let/var | `*not shown*` | ✗ |
| `merged` | `any` | let/var | `*not shown*` | ✗ |
| `merged` | `any` | let/var | `*not shown*` | ✗ |
| `lines` | `any` | let/var | `*not shown*` | ✗ |
| `merged` | `any` | let/var | `*not shown*` | ✗ |
| `sps` | `any` | let/var | `sawCollapsedSpans && line.markedSpans` | ✗ |
| `h` | `number` | let/var | `0` | ✗ |
| `chunk` | `any` | let/var | `lineObj.parent` | ✗ |
| `line` | `any` | let/var | `chunk.lines[i]` | ✗ |
| `cur` | `any` | let/var | `p.children[i$1]` | ✗ |
| `len` | `any` | let/var | `line.text.length` | ✗ |
| `merged` | `any` | let/var | `*not shown*` | ✗ |
| `cur` | `any` | let/var | `line` | ✗ |
| `d` | `any` | let/var | `cm.display` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `estHeight` | `any` | let/var | `estimateHeight ? estimateHeight(line) : 1` | ✗ |
| `styleToClassCache` | `{}` | let/var | `{}` | ✗ |
| `styleToClassCacheWithMode` | `{}` | let/var | `{}` | ✗ |
| `cache` | `{}` | let/var | `options.addModeClass ? styleToClassCacheWithMode : styleToClassCache` | ✗ |
| `builder` | `{ pre: any; content: any; col: number...` | let/var | `{pre: eltP("pre", [content], "CodeMirror-line"), content: content, col: 0, po...` | ✗ |
| `line` | `any` | let/var | `i ? lineView.rest[i - 1] : lineView.line` | ✗ |
| `order` | `any` | let/var | `(void 0)` | ✗ |
| `allowFrontierUpdate` | `any` | let/var | `lineView != cm.display.externalMeasured && lineNo(line)` | ✗ |
| `last` | `any` | let/var | `builder.content.lastChild` | ✗ |
| `displayText` | `any` | let/var | `builder.splitSpaces ? splitSpaces(text, builder.trailingSpace) : text` | ✗ |
| `special` | `any` | let/var | `builder.cm.state.specialChars` | ✗ |
| `mustWrap` | `boolean` | let/var | `false` | ✗ |
| `content` | `any` | let/var | `*not shown*` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `skipped` | `number` | let/var | `m ? m.index - pos : text.length - pos` | ✗ |
| `txt$1` | `any` | let/var | `(void 0)` | ✗ |
| `tabSize` | `any` | let/var | `builder.cm.options.tabSize` | ✗ |
| `tabWidth` | `number` | let/var | `tabSize - builder.col % tabSize` | ✗ |
| `fullStyle` | `any` | let/var | `style \|\| ""` | ✗ |
| `spaceBefore` | `any` | let/var | `trailingBefore` | ✗ |
| `result` | `string` | let/var | `""` | ✗ |
| `start` | `any` | let/var | `builder.pos` | ✗ |
| `end` | `any` | let/var | `start + text.length` | ✗ |
| `part` | `any` | let/var | `(void 0)` | ✗ |
| `widget` | `any` | let/var | `!ignoreWidget && marker.widgetNode` | ✗ |
| `spans` | `any` | let/var | `line.markedSpans` | ✗ |
| `allText` | `any` | let/var | `line.text` | ✗ |
| `at` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `allText.length` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `i` | `number` | let/var | `1` | ✗ |
| `text` | `string` | let/var | `""` | ✗ |
| `style` | `any` | let/var | `*not shown*` | ✗ |
| `css` | `any` | let/var | `*not shown*` | ✗ |
| `nextChange` | `number` | let/var | `0` | ✗ |
| `spanStyle` | `any` | let/var | `*not shown*` | ✗ |
| `spanEndStyle` | `any` | let/var | `*not shown*` | ✗ |
| `spanStartStyle` | `any` | let/var | `*not shown*` | ✗ |
| `collapsed` | `any` | let/var | `*not shown*` | ✗ |
| `attributes` | `any` | let/var | `*not shown*` | ✗ |
| `foundBookmarks` | `any[]` | let/var | `[]` | ✗ |
| `endStyles` | `any` | let/var | `(void 0)` | ✗ |
| `sp` | `any` | let/var | `spans[j]` | ✗ |
| `m` | `any` | let/var | `sp.marker` | ✗ |
| `end` | `number` | let/var | `pos + text.length` | ✗ |
| `tokenText` | `string` | let/var | `end > upto ? text.slice(0, upto - pos) : text` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `nextPos` | `any` | let/var | `*not shown*` | ✗ |
| `view` | `LineView` | let/var | `new LineView(cm.doc, getLine(cm.doc, pos), pos)` | ✗ |
| `operationGroup` | `any` | let/var | `null` | ✗ |
| `callbacks` | `any` | let/var | `group.delayedCallbacks` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `op` | `any` | let/var | `group.ops[j]` | ✗ |
| `group` | `any` | let/var | `op.ownsGroup` | ✗ |
| `orphanDelayedCallbacks` | `any` | let/var | `null` | ✗ |
| `list` | `any` | let/var | `*not shown*` | ✗ |
| `delayed` | `any` | let/var | `orphanDelayedCallbacks` | ✗ |
| `type` | `any` | let/var | `lineView.changes[j]` | ✗ |
| `cls` | `any` | let/var | `lineView.bgClass ? lineView.bgClass + " " + (lineView.line.bgClass \|\| "") :...` | ✗ |
| `ext` | `any` | let/var | `cm.display.externalMeasured` | ✗ |
| `cls` | `any` | let/var | `lineView.text.className` | ✗ |
| `textClass` | `any` | let/var | `lineView.textClass ? lineView.textClass + " " + (lineView.line.textClass \|\|...` | ✗ |
| `markers` | `any` | let/var | `lineView.line.gutterMarkers` | ✗ |
| `gutterWrap` | `any` | let/var | `lineView.gutter = elt("div", null, "CodeMirror-gutter-wrapper", ("left: " + (...` | ✗ |
| `id` | `any` | let/var | `cm.display.gutterSpecs[k].className` | ✗ |
| `found` | `any` | let/var | `markers.hasOwnProperty(id) && markers[id]` | ✗ |
| `widget` | `any` | let/var | `ws[i]` | ✗ |
| `width` | `any` | let/var | `dims.wrapperWidth` | ✗ |
| `cm` | `any` | let/var | `widget.doc.cm` | ✗ |
| `parentStyle` | `string` | let/var | `"position: relative;"` | ✗ |
| `style` | `any` | let/var | `window.getComputedStyle ? window.getComputedStyle(e) : e.currentStyle` | ✗ |
| `data` | `{ left: number; right: number; }` | let/var | `{left: parseInt(style.paddingLeft), right: parseInt(style.paddingRight)}` | ✗ |
| `wrapping` | `any` | let/var | `cm.options.lineWrapping` | ✗ |
| `curWidth` | `number` | let/var | `wrapping && displayWidth(cm)` | ✗ |
| `heights` | `any[]` | let/var | `lineView.measure.heights = []` | ✗ |
| `cur` | `any` | let/var | `rects[i]` | ✗ |
| `next` | `any` | let/var | `rects[i + 1]` | ✗ |
| `view` | `LineView` | let/var | `cm.display.externalMeasured = new LineView(cm.doc, line, lineN)` | ✗ |
| `built` | `{ pre: any; content: any; col: number...` | let/var | `view.built = buildLineContent(cm, view)` | ✗ |
| `ext` | `any` | let/var | `cm.display.externalMeasured` | ✗ |
| `key` | `any` | let/var | `ch + (bias \|\| "")` | ✗ |
| `found` | `any` | let/var | `*not shown*` | ✗ |
| `nullRect` | `{ left: number; right: number; top: n...` | let/var | `{left: 0, right: 0, top: 0, bottom: 0}` | ✗ |
| `node` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `any` | let/var | `*not shown*` | ✗ |
| `end` | `any` | let/var | `*not shown*` | ✗ |
| `collapse` | `any` | let/var | `*not shown*` | ✗ |
| `mStart` | `any` | let/var | `*not shown*` | ✗ |
| `mEnd` | `any` | let/var | `*not shown*` | ✗ |
| `rect` | `{ left: number; right: number; top: n...` | let/var | `nullRect` | ✗ |
| `node` | `any` | let/var | `place.node` | ✗ |
| `start` | `number` | let/var | `place.start` | ✗ |
| `end` | `number` | let/var | `place.end` | ✗ |
| `collapse` | `any` | let/var | `place.collapse` | ✗ |
| `rect` | `any` | let/var | `*not shown*` | ✗ |
| `rects` | `any` | let/var | `*not shown*` | ✗ |
| `rSpan` | `any` | let/var | `node.parentNode.getClientRects()[0]` | ✗ |
| `rtop` | `number` | let/var | `rect.top - prepared.rect.top` | ✗ |
| `rbot` | `number` | let/var | `rect.bottom - prepared.rect.top` | ✗ |
| `mid` | `number` | let/var | `(rtop + rbot) / 2` | ✗ |
| `heights` | `any` | let/var | `prepared.view.measure.heights` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `top` | `any` | let/var | `i ? heights[i - 1] : 0` | ✗ |
| `bot` | `any` | let/var | `heights[i]` | ✗ |
| `result` | `{ left: number; right: number; top: a...` | let/var | `{left: (collapse == "right" ? rect.right : rect.left) - prepared.rect.left, r...` | ✗ |
| `scaleX` | `number` | let/var | `screen.logicalXDPI / screen.deviceXDPI` | ✗ |
| `scaleY` | `number` | let/var | `screen.logicalYDPI / screen.deviceYDPI` | ✗ |
| `widgets` | `any` | let/var | `ref.widgets` | ✗ |
| `height` | `number` | let/var | `0` | ✗ |
| `xOff` | `any` | let/var | `lOff.left + (context == "window" ? 0 : pageScrollX())` | ✗ |
| `left` | `any` | let/var | `coords.left` | ✗ |
| `top` | `any` | let/var | `coords.top` | ✗ |
| `ch` | `any` | let/var | `pos.ch` | ✗ |
| `sticky` | `any` | let/var | `pos.sticky` | ✗ |
| `part` | `any` | let/var | `order[partPos]` | ✗ |
| `right` | `boolean` | let/var | `part.level == 1` | ✗ |
| `other` | `any` | let/var | `bidiOther` | ✗ |
| `left` | `number` | let/var | `0` | ✗ |
| `top` | `any` | let/var | `heightAtLine(lineObj) + paddingTop(cm.display)` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `last` | `number` | let/var | `doc.first + doc.size - 1` | ✗ |
| `end` | `any` | let/var | `lineObj.text.length` | ✗ |
| `targetTop` | `any` | let/var | `intoCoordSystem(cm, lineObj, measureCharPrepared(cm, preparedMeasure, target)...` | ✗ |
| `begin` | `number` | let/var | `0` | ✗ |
| `end` | `any` | let/var | `lineObj.text.length` | ✗ |
| `ltr` | `boolean` | let/var | `true` | ✗ |
| `chAround` | `any` | let/var | `null` | ✗ |
| `boxAround` | `any` | let/var | `null` | ✗ |
| `baseX` | `any` | let/var | `*not shown*` | ✗ |
| `sticky` | `any` | let/var | `*not shown*` | ✗ |
| `outside` | `boolean` | let/var | `false` | ✗ |
| `atLeft` | `boolean` | let/var | `x - boxAround.left < boxAround.right - x` | ✗ |
| `atStart` | `boolean` | let/var | `atLeft == ltr` | ✗ |
| `part` | `any` | let/var | `order[i]` | ✗ |
| `ltr` | `boolean` | let/var | `part.level != 1` | ✗ |
| `part` | `any` | let/var | `order[index]` | ✗ |
| `ltr` | `boolean` | let/var | `part.level != 1` | ✗ |
| `begin` | `any` | let/var | `ref.begin` | ✗ |
| `end` | `any` | let/var | `ref.end` | ✗ |
| `part` | `any` | let/var | `null` | ✗ |
| `closestDist` | `any` | let/var | `null` | ✗ |
| `p` | `any` | let/var | `order[i]` | ✗ |
| `ltr` | `boolean` | let/var | `p.level != 1` | ✗ |
| `endX` | `any` | let/var | `measureCharPrepared(cm, preparedMeasure, ltr ? Math.min(end, p.to) - 1 : Math...` | ✗ |
| `dist` | `number` | let/var | `endX < x ? x - endX + 1e9 : endX - x` | ✗ |
| `measureText` | `any` | let/var | `*not shown*` | ✗ |
| `height` | `number` | let/var | `measureText.offsetHeight / 50` | ✗ |
| `width` | `number` | let/var | `(rect.right - rect.left) / 10` | ✗ |
| `d` | `any` | let/var | `cm.display` | ✗ |
| `left` | `{}` | let/var | `{}` | ✗ |
| `width` | `{}` | let/var | `{}` | ✗ |
| `gutterLeft` | `any` | let/var | `d.gutters.clientLeft` | ✗ |
| `id` | `any` | let/var | `cm.display.gutterSpecs[i].className` | ✗ |
| `wrapping` | `any` | let/var | `cm.options.lineWrapping` | ✗ |
| `perLine` | `number` | let/var | `wrapping && Math.max(5, cm.display.scroller.clientWidth / charWidth(cm.displa...` | ✗ |
| `widgetsHeight` | `number` | let/var | `0` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `line` | `any` | let/var | `*not shown*` | ✗ |
| `colDiff` | `number` | let/var | `countColumn(line, line.length, cm.options.tabSize) - line.length` | ✗ |
| `view` | `any` | let/var | `cm.display.view` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `ext` | `any` | let/var | `display.externalMeasured` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `ext` | `any` | let/var | `cm.display.externalMeasured` | ✗ |
| `lineView` | `any` | let/var | `display.view[findViewIndex(cm, line)]` | ✗ |
| `arr` | `any` | let/var | `lineView.changes \|\| (lineView.changes = [])` | ✗ |
| `diff` | `any` | let/var | `*not shown*` | ✗ |
| `view` | `any` | let/var | `cm.display.view` | ✗ |
| `n` | `any` | let/var | `cm.display.viewFrom` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `view` | `any` | let/var | `display.view` | ✗ |
| `view` | `any` | let/var | `cm.display.view` | ✗ |
| `dirty` | `number` | let/var | `0` | ✗ |
| `lineView` | `any` | let/var | `view[i]` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `result` | `{ cursors: DocumentFragment; selectio...` | let/var | `{}` | ✗ |
| `curFragment` | `DocumentFragment` | let/var | `result.cursors = document.createDocumentFragment()` | ✗ |
| `selFragment` | `DocumentFragment` | let/var | `result.selection = document.createDocumentFragment()` | ✗ |
| `customCursor` | `any` | let/var | `cm.options.$customCursor` | ✗ |
| `range` | `any` | let/var | `doc.sel.ranges[i]` | ✗ |
| `width` | `number` | let/var | `charPos.right - charPos.left` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `leftSide` | `any` | let/var | `padding.left` | ✗ |
| `rightSide` | `number` | let/var | `Math.max(display.sizerWidth, displayWidth(cm) - display.sizer.offsetLeft) - p...` | ✗ |
| `docLTR` | `boolean` | let/var | `doc.direction == "ltr"` | ✗ |
| `lineLen` | `any` | let/var | `lineObj.text.length` | ✗ |
| `start` | `any` | let/var | `*not shown*` | ✗ |
| `end` | `any` | let/var | `*not shown*` | ✗ |
| `prop` | `string` | let/var | `(dir == "ltr") == (side == "after") ? "left" : "right"` | ✗ |
| `ch` | `any` | let/var | `side == "after" ? extent.begin : extent.end - (/\s/.test(lineObj.text.charAt(...` | ✗ |
| `ltr` | `boolean` | let/var | `dir == "ltr"` | ✗ |
| `openStart` | `boolean` | let/var | `fromArg == null && from == 0` | ✗ |
| `openEnd` | `boolean` | let/var | `toArg == null && to == lineLen` | ✗ |
| `first` | `boolean` | let/var | `i == 0` | ✗ |
| `last` | `boolean` | let/var | `!order \|\| i == order.length - 1` | ✗ |
| `openLeft` | `boolean` | let/var | `(docLTR ? openStart : openEnd) && first` | ✗ |
| `openRight` | `boolean` | let/var | `(docLTR ? openEnd : openStart) && last` | ✗ |
| `left` | `any` | let/var | `openLeft ? leftSide : (ltr ? fromPos : toPos).left` | ✗ |
| `right` | `any` | let/var | `openRight ? rightSide : (ltr ? toPos : fromPos).right` | ✗ |
| `topLeft` | `any` | let/var | `*not shown*` | ✗ |
| `topRight` | `any` | let/var | `*not shown*` | ✗ |
| `botLeft` | `any` | let/var | `*not shown*` | ✗ |
| `botRight` | `any` | let/var | `*not shown*` | ✗ |
| `singleVLine` | `boolean` | let/var | `visualLine(fromLine) == visualLine(toLine)` | ✗ |
| `leftEnd` | `undefined` | let/var | `drawForLine(sFrom.line, sFrom.ch, singleVLine ? fromLine.text.length + 1 : nu...` | ✗ |
| `rightStart` | `undefined` | let/var | `drawForLine(sTo.line, singleVLine ? 0 : null, sTo.ch).start` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `on` | `boolean` | let/var | `true` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `prevBottom` | `any` | let/var | `display.lineDiv.offsetTop` | ✗ |
| `oldHeight` | `any` | let/var | `display.lineDiv.getBoundingClientRect().top` | ✗ |
| `mustScroll` | `number` | let/var | `0` | ✗ |
| `cur` | `any` | let/var | `display.view[i]` | ✗ |
| `wrapping` | `any` | let/var | `cm.options.lineWrapping` | ✗ |
| `height` | `any` | let/var | `(void 0)` | ✗ |
| `width` | `number` | let/var | `0` | ✗ |
| `bot` | `any` | let/var | `cur.node.offsetTop + cur.node.offsetHeight` | ✗ |
| `diff` | `number` | let/var | `cur.line.height - height` | ✗ |
| `w` | `any` | let/var | `line.widgets[i]` | ✗ |
| `parent` | `any` | let/var | `w.node.parentNode` | ✗ |
| `top` | `any` | let/var | `viewport && viewport.top != null ? Math.max(0, viewport.top) : display.scroll...` | ✗ |
| `bottom` | `any` | let/var | `viewport && viewport.bottom != null ? viewport.bottom : top + display.wrapper...` | ✗ |
| `ensureFrom` | `any` | let/var | `viewport.ensure.from.line` | ✗ |
| `ensureTo` | `any` | let/var | `viewport.ensure.to.line` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `doScroll` | `any` | let/var | `null` | ✗ |
| `rect` | `any` | let/var | `*not shown*` | ✗ |
| `changed` | `boolean` | let/var | `false` | ✗ |
| `endCoords` | `any` | let/var | `!end \|\| end == pos ? coords : cursorCoords(cm, end)` | ✗ |
| `startTop` | `any` | let/var | `cm.doc.scrollTop` | ✗ |
| `startLeft` | `any` | let/var | `cm.doc.scrollLeft` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `screentop` | `any` | let/var | `cm.curOp && cm.curOp.scrollTop != null ? cm.curOp.scrollTop : display.scrolle...` | ✗ |
| `result` | `{ scrollTop: any; scrollLeft: number; }` | let/var | `{}` | ✗ |
| `docBottom` | `any` | let/var | `cm.doc.height + paddingVert(display)` | ✗ |
| `atTop` | `boolean` | let/var | `rect.top < snapMargin` | ✗ |
| `atBottom` | `boolean` | let/var | `rect.bottom > docBottom - snapMargin` | ✗ |
| `gutterSpace` | `any` | let/var | `cm.options.fixedGutter ? 0 : display.gutters.offsetWidth` | ✗ |
| `screenleft` | `any` | let/var | `cm.curOp && cm.curOp.scrollLeft != null ? cm.curOp.scrollLeft : display.scrol...` | ✗ |
| `screenw` | `number` | let/var | `displayWidth(cm) - display.gutters.offsetWidth` | ✗ |
| `tooWide` | `boolean` | let/var | `rect.right - rect.left > screenw` | ✗ |
| `range` | `any` | let/var | `cm.curOp.scrollToPos` | ✗ |
| `d` | `any` | let/var | `cm.display` | ✗ |
| `gutterW` | `any` | let/var | `d.gutters.offsetWidth` | ✗ |
| `vert` | `any` | let/var | `this.vert = elt("div", [elt("div", null, null, "min-width: 1px")], "CodeMirro...` | ✗ |
| `horiz` | `any` | let/var | `this.horiz = elt("div", [elt("div", null, null, "height: 100%; min-height: 1p...` | ✗ |
| `needsH` | `boolean` | let/var | `measure.scrollWidth > measure.clientWidth + 1` | ✗ |
| `needsV` | `boolean` | let/var | `measure.scrollHeight > measure.clientHeight + 1` | ✗ |
| `sWidth` | `any` | let/var | `measure.nativeBarWidth` | ✗ |
| `totalHeight` | `number` | let/var | `measure.viewHeight - (needsH ? sWidth : 0)` | ✗ |
| `totalWidth` | `number` | let/var | `measure.viewWidth - measure.barLeft - (needsV ? sWidth : 0)` | ✗ |
| `w` | `string` | let/var | `mac && !mac_geMountainLion ? "12px" : "18px"` | ✗ |
| `elt` | `Element` | let/var | `type == "vert" ? document.elementFromPoint(box.right - 1, (box.top + box.bott...` | ✗ |
| `parent` | `any` | let/var | `this.horiz.parentNode` | ✗ |
| `startWidth` | `any` | let/var | `cm.display.barWidth` | ✗ |
| `startHeight` | `any` | let/var | `cm.display.barHeight` | ✗ |
| `d` | `any` | let/var | `cm.display` | ✗ |
| `scrollbarModel` | `{ native: typeof NativeScrollbars; nu...` | let/var | `{"native": NativeScrollbars, "null": NullScrollbars}` | ✗ |
| `nextOpId` | `number` | let/var | `0` | ✗ |
| `op` | `any` | let/var | `cm.curOp` | ✗ |
| `ops` | `any` | let/var | `group.ops` | ✗ |
| `cm` | `any` | let/var | `op.cm` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `cm` | `any` | let/var | `op.cm` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `cm` | `any` | let/var | `op.cm` | ✗ |
| `takeFocus` | `boolean` | let/var | `op.focus && op.focus == activeElt()` | ✗ |
| `cm` | `any` | let/var | `op.cm` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `hidden` | `any` | let/var | `op.maybeHiddenMarkers` | ✗ |
| `unhidden` | `any` | let/var | `op.maybeUnhiddenMarkers` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `end` | `any` | let/var | `+new Date + cm.options.workTime` | ✗ |
| `changedLines` | `any[]` | let/var | `[]` | ✗ |
| `oldStyles` | `any` | let/var | `line.styles` | ✗ |
| `resetState` | `any` | let/var | `line.text.length > cm.options.maxHighlightLength ? copyState(doc.mode, contex...` | ✗ |
| `oldCls` | `any` | let/var | `line.styleClasses` | ✗ |
| `newCls` | `{}` | let/var | `highlighted.classes` | ✗ |
| `ischange` | `boolean` | let/var | `!oldStyles \|\| oldStyles.length != line.styles.length \|\| oldCls != newCls ...` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `result` | `{ activeElt: Element; }` | let/var | `{activeElt: active}` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `end` | `any` | let/var | `doc.first + doc.size` | ✗ |
| `different` | `boolean` | let/var | `from != display.viewFrom \|\| to != display.viewTo \|\| display.lastWrapHeigh...` | ✗ |
| `viewport` | `any` | let/var | `update.viewport` | ✗ |
| `update` | `DisplayUpdate` | let/var | `new DisplayUpdate(cm, viewport)` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `lineNumbers` | `any` | let/var | `cm.options.lineNumbers` | ✗ |
| `container` | `any` | let/var | `display.lineDiv` | ✗ |
| `cur` | `any` | let/var | `container.firstChild` | ✗ |
| `next` | `any` | let/var | `node.nextSibling` | ✗ |
| `view` | `any` | let/var | `display.view` | ✗ |
| `lineN` | `any` | let/var | `display.viewFrom` | ✗ |
| `lineView` | `any` | let/var | `view[i]` | ✗ |
| `updateNumber` | `any` | let/var | `lineNumbers && updateNumbersFrom != null && updateNumbersFrom <= lineN && lin...` | ✗ |
| `width` | `any` | let/var | `display.gutters.offsetWidth` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `view` | `any` | let/var | `display.view` | ✗ |
| `comp` | `any` | let/var | `compensateForHScroll(display) - display.scroller.scrollLeft + cm.doc.scrollLeft` | ✗ |
| `gutterW` | `any` | let/var | `display.gutters.offsetWidth` | ✗ |
| `left` | `string` | let/var | `comp + "px"` | ✗ |
| `align` | `any` | let/var | `view[i].alignable` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `innerW` | `any` | let/var | `test.firstChild.offsetWidth` | ✗ |
| `padding` | `number` | let/var | `test.offsetWidth - innerW` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `sawLineNumbers` | `boolean` | let/var | `false` | ✗ |
| `name` | `any` | let/var | `gutters[i]` | ✗ |
| `style` | `any` | let/var | `null` | ✗ |
| `gutters` | `any` | let/var | `display.gutters` | ✗ |
| `specs` | `any` | let/var | `display.gutterSpecs` | ✗ |
| `ref` | `any` | let/var | `specs[i]` | ✗ |
| `className` | `any` | let/var | `ref.className` | ✗ |
| `style` | `any` | let/var | `ref.style` | ✗ |
| `d` | `this` | let/var | `this` | ✗ |
| `wheelSamples` | `number` | let/var | `0` | ✗ |
| `wheelPixelsPerUnit` | `any` | let/var | `null` | ✗ |
| `dx` | `any` | let/var | `e.wheelDeltaX` | ✗ |
| `dy` | `any` | let/var | `e.wheelDeltaY` | ✗ |
| `dx` | `any` | let/var | `delta.x` | ✗ |
| `dy` | `any` | let/var | `delta.y` | ✗ |
| `pixelsPerUnit` | `any` | let/var | `wheelPixelsPerUnit` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `scroll` | `any` | let/var | `display.scroller` | ✗ |
| `canScrollX` | `boolean` | let/var | `scroll.scrollWidth > scroll.clientWidth` | ✗ |
| `canScrollY` | `boolean` | let/var | `scroll.scrollHeight > scroll.clientHeight` | ✗ |
| `pixels` | `number` | let/var | `dy * pixelsPerUnit` | ✗ |
| `top` | `any` | let/var | `cm.doc.scrollTop` | ✗ |
| `bot` | `any` | let/var | `top + display.wrapper.clientHeight` | ✗ |
| `movedX` | `number` | let/var | `scroll.scrollLeft - display.wheelStartX` | ✗ |
| `movedY` | `number` | let/var | `scroll.scrollTop - display.wheelStartY` | ✗ |
| `sample` | `number` | let/var | `(movedY && display.wheelDY && movedY / display.wheelDY) \|\| (movedX && displ...` | ✗ |
| `here` | `any` | let/var | `this.ranges[i]` | ✗ |
| `there` | `any` | let/var | `other.ranges[i]` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `range` | `any` | let/var | `this.ranges[i]` | ✗ |
| `mayTouch` | `any` | let/var | `cm && cm.options.selectionsMayTouch` | ✗ |
| `prim` | `any` | let/var | `ranges[primIndex]` | ✗ |
| `cur` | `any` | let/var | `ranges[i]` | ✗ |
| `prev` | `any` | let/var | `ranges[i - 1]` | ✗ |
| `inv` | `boolean` | let/var | `prev.empty() ? cur.from() == cur.head : prev.from() == prev.head` | ✗ |
| `line` | `number` | let/var | `pos.line + change.text.length - (change.to.line - change.from.line) - 1` | ✗ |
| `ch` | `any` | let/var | `pos.ch` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `range` | `any` | let/var | `doc.sel.ranges[i]` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `newPrev` | `Pos` | let/var | `oldPrev` | ✗ |
| `change` | `any` | let/var | `changes[i]` | ✗ |
| `range` | `any` | let/var | `doc.sel.ranges[i]` | ✗ |
| `inv` | `boolean` | let/var | `cmp(range.head, range.anchor) < 0` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `from` | `any` | let/var | `change.from` | ✗ |
| `to` | `any` | let/var | `change.to` | ✗ |
| `text` | `any` | let/var | `change.text` | ✗ |
| `nlines` | `number` | let/var | `to.line - from.line` | ✗ |
| `rel` | `any` | let/var | `doc.linked[i]` | ✗ |
| `shared` | `any` | let/var | `sharedHist && rel.sharedHist` | ✗ |
| `histChange` | `{ from: Pos; to: any; text: any[]; }` | let/var | `{from: copyPos(change.from), to: changeEnd(change), text: getBetween(doc, cha...` | ✗ |
| `hist` | `any` | let/var | `doc.history` | ✗ |
| `time` | `number` | let/var | `+new Date` | ✗ |
| `cur` | `any` | let/var | `*not shown*` | ✗ |
| `last` | `any` | let/var | `*not shown*` | ✗ |
| `hist` | `any` | let/var | `doc.history` | ✗ |
| `origin` | `any` | let/var | `options && options.origin` | ✗ |
| `existing` | `any` | let/var | `change["spans_" + doc.id]` | ✗ |
| `n` | `number` | let/var | `0` | ✗ |
| `out` | `any` | let/var | `*not shown*` | ✗ |
| `found` | `any` | let/var | `change["spans_" + doc.id]` | ✗ |
| `nw` | `any[]` | let/var | `[]` | ✗ |
| `oldCur` | `any` | let/var | `old[i]` | ✗ |
| `stretchCur` | `any[]` | let/var | `stretched[i]` | ✗ |
| `span` | `any` | let/var | `stretchCur[j]` | ✗ |
| `copy` | `any[]` | let/var | `[]` | ✗ |
| `event` | `any` | let/var | `events[i]` | ✗ |
| `changes` | `any` | let/var | `event.changes` | ✗ |
| `newChanges` | `any[]` | let/var | `[]` | ✗ |
| `change` | `any` | let/var | `changes[j]` | ✗ |
| `m` | `any` | let/var | `(void 0)` | ✗ |
| `anchor` | `any` | let/var | `range.anchor` | ✗ |
| `posBefore` | `boolean` | let/var | `cmp(head, anchor) < 0` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `extend` | `any` | let/var | `doc.cm && (doc.cm.display.shift \|\| doc.extend)` | ✗ |
| `obj` | `{ ranges: any; update: typeof update;...` | let/var | `{ ranges: sel.ranges, update: function(ranges) { this.ranges = []; for (var i...` | ✗ |
| `done` | `any` | let/var | `doc.history.done` | ✗ |
| `bias` | `any` | let/var | `options && options.bias \|\| (cmp(sel.primary().head, doc.sel.primary().head)...` | ✗ |
| `out` | `any` | let/var | `*not shown*` | ✗ |
| `range` | `any` | let/var | `sel.ranges[i]` | ✗ |
| `old` | `any` | let/var | `sel.ranges.length == doc.sel.ranges.length && doc.sel.ranges[i]` | ✗ |
| `sp` | `any` | let/var | `line.markedSpans[i]` | ✗ |
| `m` | `any` | let/var | `sp.marker` | ✗ |
| `preventCursorLeft` | `any` | let/var | `("selectLeft" in m) ? !m.selectLeft : m.inclusiveLeft` | ✗ |
| `preventCursorRight` | `any` | let/var | `("selectRight" in m) ? !m.selectRight : m.inclusiveRight` | ✗ |
| `diff` | `any` | let/var | `(void 0)` | ✗ |
| `dir` | `any` | let/var | `bias \|\| 1` | ✗ |
| `found` | `any` | let/var | `skipAtomicInner(doc, pos, oldPos, dir, mayClear) \|\| (!mayClear && skipAtomi...` | ✗ |
| `obj` | `{ canceled: boolean; from: any; to: a...` | let/var | `{ canceled: false, from: change.from, to: change.to, text: change.text, origi...` | ✗ |
| `split` | `{ from: any; to: any; }[]` | let/var | `sawReadOnlySpans && !ignoreReadOnly && removeReadOnlyRanges(doc, change.from,...` | ✗ |
| `rebased` | `any[]` | let/var | `[]` | ✗ |
| `suppress` | `any` | let/var | `doc.cm && doc.cm.state.suppressEdits` | ✗ |
| `hist` | `any` | let/var | `doc.history` | ✗ |
| `event` | `any` | let/var | `*not shown*` | ✗ |
| `selAfter` | `any` | let/var | `doc.sel` | ✗ |
| `source` | `any` | let/var | `type == "undo" ? hist.done : hist.undone` | ✗ |
| `dest` | `any` | let/var | `type == "undo" ? hist.undone : hist.done` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `antiChanges` | `any[]` | let/var | `[]` | ✗ |
| `filter` | `boolean` | let/var | `hasHandler(doc, "beforeChange") \|\| doc.cm && hasHandler(doc.cm, "beforeChan...` | ✗ |
| `change` | `any` | let/var | `event.changes[i]` | ✗ |
| `after` | `any` | let/var | `i ? computeSelAfterChange(doc, change) : lst(source)` | ✗ |
| `rebased` | `any[]` | let/var | `[]` | ✗ |
| `shift` | `number` | let/var | `change.text.length - 1 - (doc.first - change.from.line)` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `from` | `any` | let/var | `change.from` | ✗ |
| `to` | `any` | let/var | `change.to` | ✗ |
| `recomputeMaxLength` | `boolean` | let/var | `false` | ✗ |
| `checkWidthStart` | `any` | let/var | `from.line` | ✗ |
| `lendiff` | `number` | let/var | `change.text.length - (to.line - from.line) - 1` | ✗ |
| `obj` | `{ from: any; to: any; text: any; remo...` | let/var | `{ from: from, to: to, text: change.text, removed: change.removed, origin: cha...` | ✗ |
| `assign` | `any` | let/var | `*not shown*` | ✗ |
| `sub` | `any` | let/var | `array[i]` | ✗ |
| `ok` | `boolean` | let/var | `true` | ✗ |
| `cur` | `any` | let/var | `sub.changes[j$1]` | ✗ |
| `from` | `any` | let/var | `change.from.line` | ✗ |
| `to` | `any` | let/var | `change.to.line` | ✗ |
| `diff` | `number` | let/var | `change.text.length - (to - from) - 1` | ✗ |
| `no` | `any` | let/var | `handle` | ✗ |
| `line` | `any` | let/var | `handle` | ✗ |
| `height` | `number` | let/var | `0` | ✗ |
| `line` | `any` | let/var | `this.lines[i]` | ✗ |
| `size` | `number` | let/var | `0` | ✗ |
| `height` | `number` | let/var | `0` | ✗ |
| `ch` | `any` | let/var | `children[i]` | ✗ |
| `child` | `any` | let/var | `this.children[i]` | ✗ |
| `oldHeight` | `any` | let/var | `child.height` | ✗ |
| `lines` | `any[]` | let/var | `[]` | ✗ |
| `child` | `any` | let/var | `this.children[i]` | ✗ |
| `remaining` | `number` | let/var | `child.lines.length % 25 + 25` | ✗ |
| `leaf` | `LeafChunk` | let/var | `new LeafChunk(child.lines.slice(pos, pos += 25))` | ✗ |
| `me` | `this` | let/var | `this` | ✗ |
| `sibling` | `BranchChunk` | let/var | `new BranchChunk(spilled)` | ✗ |
| `copy` | `BranchChunk` | let/var | `new BranchChunk(me.children)` | ✗ |
| `child` | `any` | let/var | `this.children[i]` | ✗ |
| `cm` | `any` | let/var | `this.doc.cm` | ✗ |
| `ws` | `any` | let/var | `this.line.widgets` | ✗ |
| `line` | `any` | let/var | `this.line` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `oldH` | `any` | let/var | `this.height` | ✗ |
| `cm` | `any` | let/var | `this.doc.cm` | ✗ |
| `line` | `any` | let/var | `this.line` | ✗ |
| `diff` | `number` | let/var | `widgetHeight(this) - oldH` | ✗ |
| `widget` | `LineWidget` | let/var | `new LineWidget(doc, node, options)` | ✗ |
| `cm` | `any` | let/var | `doc.cm` | ✗ |
| `widgets` | `any` | let/var | `line.widgets \|\| (line.widgets = [])` | ✗ |
| `aboveVisible` | `boolean` | let/var | `heightAtLine(line) < doc.scrollTop` | ✗ |
| `nextMarkerId` | `number` | let/var | `0` | ✗ |
| `cm` | `any` | let/var | `this.doc.cm` | ✗ |
| `withOp` | `boolean` | let/var | `cm && !cm.curOp` | ✗ |
| `min` | `any` | let/var | `null` | ✗ |
| `max` | `any` | let/var | `null` | ✗ |
| `line` | `any` | let/var | `this.lines[i]` | ✗ |
| `from` | `any` | let/var | `*not shown*` | ✗ |
| `to` | `any` | let/var | `*not shown*` | ✗ |
| `line` | `any` | let/var | `this.lines[i]` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `widget` | `this` | let/var | `this` | ✗ |
| `cm` | `any` | let/var | `this.doc.cm` | ✗ |
| `line` | `any` | let/var | `pos.line` | ✗ |
| `oldHeight` | `any` | let/var | `widget.height` | ✗ |
| `dHeight` | `number` | let/var | `widgetHeight(widget) - oldHeight` | ✗ |
| `op` | `any` | let/var | `this.doc.cm.curOp` | ✗ |
| `op` | `any` | let/var | `this.doc.cm.curOp` | ✗ |
| `marker` | `TextMarker` | let/var | `new TextMarker(doc, type)` | ✗ |
| `curLine` | `any` | let/var | `from.line` | ✗ |
| `cm` | `any` | let/var | `doc.cm` | ✗ |
| `updateMaxLine` | `any` | let/var | `*not shown*` | ✗ |
| `markers` | `any` | let/var | `[markText(doc, from, to, options, type)]` | ✗ |
| `primary` | `any` | let/var | `markers[0]` | ✗ |
| `widget` | `any` | let/var | `options.widgetNode` | ✗ |
| `marker` | `any` | let/var | `markers[i]` | ✗ |
| `marker` | `any` | let/var | `markers[i]` | ✗ |
| `linked` | `any[]` | let/var | `[marker.primary.doc]` | ✗ |
| `subMarker` | `any` | let/var | `marker.markers[j]` | ✗ |
| `nextDocId` | `number` | let/var | `0` | ✗ |
| `height` | `number` | let/var | `0` | ✗ |
| `last` | `number` | let/var | `this.first + this.size - 1` | ✗ |
| `pos` | `any` | let/var | `*not shown*` | ✗ |
| `out` | `any[]` | let/var | `[]` | ✗ |
| `ranges` | `any` | let/var | `this.sel.ranges` | ✗ |
| `lines` | `any` | let/var | `*not shown*` | ✗ |
| `parts` | `any[]` | let/var | `[]` | ✗ |
| `ranges` | `any` | let/var | `this.sel.ranges` | ✗ |
| `dup` | `any[]` | let/var | `[]` | ✗ |
| `changes` | `any[]` | let/var | `[]` | ✗ |
| `sel` | `any` | let/var | `this.sel` | ✗ |
| `range` | `any` | let/var | `sel.ranges[i]` | ✗ |
| `newSel` | `Selection` | let/var | `collapse && collapse != "end" && computeReplacedSel(this, changes, collapse)` | ✗ |
| `hist` | `any` | let/var | `this.history` | ✗ |
| `done` | `number` | let/var | `0` | ✗ |
| `undone` | `number` | let/var | `0` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `hist` | `History` | let/var | `this.history = new History(this.history)` | ✗ |
| `markers` | `any` | let/var | `line.gutterMarkers \|\| (line.gutterMarkers = {})` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `prop` | `string` | let/var | `where == "text" ? "textClass" : where == "background" ? "bgClass" : where == ...` | ✗ |
| `prop` | `string` | let/var | `where == "text" ? "textClass" : where == "background" ? "bgClass" : where == ...` | ✗ |
| `cur` | `any` | let/var | `line[prop]` | ✗ |
| `end` | `any` | let/var | `found.index + found[0].length` | ✗ |
| `realOpts` | `{ replacedWith: any; insertLeft: any;...` | let/var | `{replacedWith: options && (options.nodeType == null ? options.widget : option...` | ✗ |
| `markers` | `any[]` | let/var | `[]` | ✗ |
| `spans` | `any` | let/var | `getLine(this, pos.line).markedSpans` | ✗ |
| `span` | `any` | let/var | `spans[i]` | ✗ |
| `found` | `any[]` | let/var | `[]` | ✗ |
| `lineNo` | `any` | let/var | `from.line` | ✗ |
| `spans` | `any` | let/var | `line.markedSpans` | ✗ |
| `span` | `any` | let/var | `spans[i]` | ✗ |
| `markers` | `any[]` | let/var | `[]` | ✗ |
| `sps` | `any` | let/var | `line.markedSpans` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `lineNo` | `any` | let/var | `this.first` | ✗ |
| `sepSize` | `any` | let/var | `this.lineSeparator().length` | ✗ |
| `sz` | `any` | let/var | `line.text.length + sepSize` | ✗ |
| `index` | `any` | let/var | `coords.ch` | ✗ |
| `sepSize` | `any` | let/var | `this.lineSeparator().length` | ✗ |
| `doc` | `Doc` | let/var | `new Doc(getLines(this, this.first, this.first + this.size), this.modeOption, ...` | ✗ |
| `from` | `any` | let/var | `this.first` | ✗ |
| `to` | `any` | let/var | `this.first + this.size` | ✗ |
| `copy` | `Doc` | let/var | `new Doc(getLines(this, from, to), options.mode \|\| this.modeOption, from, th...` | ✗ |
| `link` | `any` | let/var | `this.linked[i]` | ✗ |
| `splitIds` | `any[]` | let/var | `[other.id]` | ✗ |
| `lastDrop` | `number` | let/var | `0` | ✗ |
| `cm` | `any` | let/var | `this` | ✗ |
| `files` | `any` | let/var | `e.dataTransfer.files` | ✗ |
| `n` | `any` | let/var | `files.length` | ✗ |
| `read` | `number` | let/var | `0` | ✗ |
| `change` | `{ from: any; to: any; text: any; orig...` | let/var | `{from: pos, to: pos, text: cm.doc.splitLines( text.filter(function (t) { retu...` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader` | ✗ |
| `content` | `string \| ArrayBuffer` | let/var | `reader.result` | ✗ |
| `selected` | `any` | let/var | `*not shown*` | ✗ |
| `editors` | `any[]` | let/var | `[]` | ✗ |
| `cm` | `any` | let/var | `byClass[i].CodeMirror` | ✗ |
| `globalsRegistered` | `boolean` | let/var | `false` | ✗ |
| `resizeTimer` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `any` | let/var | `cm.display` | ✗ |
| `keyNames` | `{ 3: string; 8: string; 9: string; 13...` | let/var | `{ 3: "Pause", 8: "Backspace", 9: "Tab", 13: "Enter", 16: "Shift", 17: "Ctrl",...` | ✗ |
| `keyMap` | `{ basic: { Left: string; Right: strin...` | let/var | `{}` | ✗ |
| `alt` | `any` | let/var | `*not shown*` | ✗ |
| `ctrl` | `any` | let/var | `*not shown*` | ✗ |
| `shift` | `any` | let/var | `*not shown*` | ✗ |
| `cmd` | `any` | let/var | `*not shown*` | ✗ |
| `mod` | `any` | let/var | `parts[i]` | ✗ |
| `copy` | `{}` | let/var | `{}` | ✗ |
| `value` | `any` | let/var | `keymap[keyname]` | ✗ |
| `val` | `any` | let/var | `(void 0)` | ✗ |
| `name` | `any` | let/var | `(void 0)` | ✗ |
| `prev` | `any` | let/var | `copy[name]` | ✗ |
| `found` | `any` | let/var | `map.call ? map.call(key, context) : map[key]` | ✗ |
| `name` | `any` | let/var | `typeof value == "string" ? value : keyNames[value.keyCode]` | ✗ |
| `base` | `any` | let/var | `name` | ✗ |
| `name` | `any` | let/var | `keyNames[event.keyCode]` | ✗ |
| `ranges` | `any` | let/var | `cm.doc.sel.ranges` | ✗ |
| `kill` | `any[]` | let/var | `[]` | ✗ |
| `part` | `any` | let/var | `dir < 0 ? lst(order) : order[0]` | ✗ |
| `moveInStorageOrder` | `boolean` | let/var | `(dir < 0) == (part.level == 1)` | ✗ |
| `sticky` | `string` | let/var | `moveInStorageOrder ? "after" : "before"` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `targetTop` | `any` | let/var | `measureCharPrepared(cm, prep, ch).top` | ✗ |
| `part` | `any` | let/var | `bidi[partPos]` | ✗ |
| `prep` | `any` | let/var | `*not shown*` | ✗ |
| `moveInStorageOrder` | `boolean` | let/var | `(part.level == 1) == (dir < 0)` | ✗ |
| `sticky` | `string` | let/var | `moveInStorageOrder ? "before" : "after"` | ✗ |
| `part` | `any` | let/var | `bidi[partPos]` | ✗ |
| `moveInStorageOrder` | `boolean` | let/var | `(dir > 0) == (part.level != 1)` | ✗ |
| `ch` | `any` | let/var | `moveInStorageOrder ? wrappedLineExtent.begin : mv(wrappedLineExtent.end, -1)` | ✗ |
| `nextCh` | `any` | let/var | `dir > 0 ? wrappedLineExtent.end : mv(wrappedLineExtent.begin, -1)` | ✗ |
| `len` | `any` | let/var | `getLine(cm.doc, range.head.line).text.length` | ✗ |
| `top` | `any` | let/var | `cm.charCoords(range.head, "div").top + 5` | ✗ |
| `top` | `any` | let/var | `cm.charCoords(range.head, "div").top + 5` | ✗ |
| `top` | `any` | let/var | `cm.cursorCoords(range.head, "div").top + 5` | ✗ |
| `top` | `any` | let/var | `cm.cursorCoords(range.head, "div").top + 5` | ✗ |
| `top` | `any` | let/var | `cm.cursorCoords(range.head, "div").top + 5` | ✗ |
| `spaces` | `any[]` | let/var | `[]` | ✗ |
| `tabSize` | `any` | let/var | `cm.options.tabSize` | ✗ |
| `newSel` | `any[]` | let/var | `[]` | ✗ |
| `cur` | `any` | let/var | `ranges[i].head` | ✗ |
| `line` | `any` | let/var | `getLine(cm.doc, cur.line).text` | ✗ |
| `prev` | `any` | let/var | `getLine(cm.doc, cur.line - 1).text` | ✗ |
| `commands` | `{ selectAll: (cm: any) => void; singl...` | let/var | `{ selectAll: selectAll, singleSelection: function (cm) { return cm.setSelecti...` | ✗ |
| `inWS` | `any` | let/var | `pos.line == start.line && pos.ch <= firstNonWS && pos.ch` | ✗ |
| `prevShift` | `any` | let/var | `cm.display.shift` | ✗ |
| `done` | `boolean` | let/var | `false` | ✗ |
| `stopSeq` | `Delayed` | let/var | `new Delayed` | ✗ |
| `seq` | `any` | let/var | `cm.state.keySeq` | ✗ |
| `lastStoppedKey` | `any` | let/var | `null` | ✗ |
| `cm` | `any` | let/var | `this` | ✗ |
| `code` | `any` | let/var | `e.keyCode` | ✗ |
| `lineDiv` | `any` | let/var | `cm.display.lineDiv` | ✗ |
| `cm` | `any` | let/var | `this` | ✗ |
| `keyCode` | `any` | let/var | `e.keyCode` | ✗ |
| `charCode` | `any` | let/var | `e.charCode` | ✗ |
| `DOUBLECLICK_DELAY` | `number` | let/var | `400` | ✗ |
| `lastClick` | `any` | let/var | `*not shown*` | ✗ |
| `lastDoubleClick` | `any` | let/var | `*not shown*` | ✗ |
| `now` | `number` | let/var | `+new Date` | ✗ |
| `cm` | `any` | let/var | `this` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `repeat` | `string` | let/var | `pos ? clickRepeat(pos, button) : "single"` | ✗ |
| `name` | `string` | let/var | `"Click"` | ✗ |
| `done` | `boolean` | let/var | `false` | ✗ |
| `value` | `any` | let/var | `option ? option(cm, repeat, event) : {}` | ✗ |
| `rect` | `any` | let/var | `chromeOS ? event.shiftKey && event.metaKey : event.altKey` | ✗ |
| `sel` | `any` | let/var | `cm.doc.sel` | ✗ |
| `contained` | `any` | let/var | `*not shown*` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `moved` | `boolean` | let/var | `false` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `ourRange` | `any` | let/var | `*not shown*` | ✗ |
| `ourIndex` | `any` | let/var | `*not shown*` | ✗ |
| `startSel` | `any` | let/var | `doc.sel` | ✗ |
| `ranges` | `any` | let/var | `startSel.ranges` | ✗ |
| `lastPos` | `any` | let/var | `start` | ✗ |
| `ranges` | `any[]` | let/var | `[]` | ✗ |
| `tabSize` | `any` | let/var | `cm.options.tabSize` | ✗ |
| `text` | `any` | let/var | `getLine(doc, line).text` | ✗ |
| `oldRange` | `any` | let/var | `ourRange` | ✗ |
| `anchor` | `any` | let/var | `oldRange.anchor` | ✗ |
| `head` | `any` | let/var | `*not shown*` | ✗ |
| `counter` | `number` | let/var | `0` | ✗ |
| `curCount` | `number` | let/var | `++counter` | ✗ |
| `outside` | `number` | let/var | `e.clientY < editorSize.top ? -20 : e.clientY > editorSize.bottom ? 20 : 0` | ✗ |
| `anchor` | `any` | let/var | `range.anchor` | ✗ |
| `head` | `any` | let/var | `range.head` | ✗ |
| `part` | `any` | let/var | `order[index]` | ✗ |
| `boundary` | `number` | let/var | `index + ((part.from == anchor.ch) == (part.level != 1) ? 0 : 1)` | ✗ |
| `leftSide` | `any` | let/var | `*not shown*` | ✗ |
| `dir` | `number` | let/var | `headIndex - index \|\| (head.ch - anchor.ch) * (part.level == 1 ? -1 : 1)` | ✗ |
| `usePart` | `any` | let/var | `order[boundary + (leftSide ? -1 : 0)]` | ✗ |
| `from` | `boolean` | let/var | `leftSide == (usePart.level == 1)` | ✗ |
| `ch` | `any` | let/var | `from ? usePart.from : usePart.to` | ✗ |
| `sticky` | `string` | let/var | `from ? "after" : "before"` | ✗ |
| `mX` | `any` | let/var | `*not shown*` | ✗ |
| `mY` | `any` | let/var | `*not shown*` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `g` | `any` | let/var | `display.gutters.childNodes[i]` | ✗ |
| `gutter` | `any` | let/var | `cm.display.gutterSpecs[i]` | ✗ |
| `Init` | `{ toString: () => string; }` | let/var | `{toString: function(){return "CodeMirror.Init"}}` | ✗ |
| `defaults` | `{}` | let/var | `{}` | ✗ |
| `optionHandlers` | `{}` | let/var | `{}` | ✗ |
| `optionHandlers` | `any` | let/var | `CodeMirror.optionHandlers` | ✗ |
| `newBreaks` | `any[]` | let/var | `[]` | ✗ |
| `lineNo` | `any` | let/var | `cm.doc.first` | ✗ |
| `prev` | `any` | let/var | `old != Init && getKeyMap(old)` | ✗ |
| `wasOn` | `boolean` | let/var | `old && old != Init` | ✗ |
| `funcs` | `any` | let/var | `cm.display.dragFunctions` | ✗ |
| `toggle` | `(emitter: any, type: any, f: any) => ...` | let/var | `value ? on : off` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `doc` | `any` | let/var | `options.value` | ✗ |
| `input` | `any` | let/var | `new CodeMirror.inputStyles[options.inputStyle](this)` | ✗ |
| `display` | `Display` | let/var | `this.display = new Display(place, doc, input, options)` | ✗ |
| `d` | `any` | let/var | `cm.display` | ✗ |
| `touchFinished` | `any` | let/var | `*not shown*` | ✗ |
| `prevTouch` | `{ end: number; }` | let/var | `{end: 0}` | ✗ |
| `touch` | `any` | let/var | `e.touches[0]` | ✗ |
| `dx` | `number` | let/var | `other.left - touch.left` | ✗ |
| `dy` | `number` | let/var | `other.top - touch.top` | ✗ |
| `now` | `number` | let/var | `+new Date` | ✗ |
| `touch` | `any` | let/var | `d.activeTouch` | ✗ |
| `range` | `any` | let/var | `*not shown*` | ✗ |
| `initHooks` | `any[]` | let/var | `[]` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `state` | `any` | let/var | `*not shown*` | ✗ |
| `tabSize` | `any` | let/var | `cm.options.tabSize` | ✗ |
| `curSpaceString` | `any` | let/var | `line.text.match(/^\s*/)[0]` | ✗ |
| `indentation` | `any` | let/var | `*not shown*` | ✗ |
| `indentString` | `string` | let/var | `""` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `range` | `any` | let/var | `doc.sel.ranges[i$1]` | ✗ |
| `lastCopied` | `any` | let/var | `null` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `recent` | `number` | let/var | `+new Date - 200` | ✗ |
| `paste` | `boolean` | let/var | `origin == "paste" \|\| cm.state.pasteIncoming > recent` | ✗ |
| `multiPaste` | `any` | let/var | `null` | ✗ |
| `updateInput` | `any` | let/var | `cm.curOp.updateInput` | ✗ |
| `range` | `any` | let/var | `sel.ranges[i$1]` | ✗ |
| `changeEvent` | `{ from: any; to: any; text: any; orig...` | let/var | `{from: from, to: to, text: multiPaste ? multiPaste[i$1 % multiPaste.length] :...` | ✗ |
| `pasted` | `any` | let/var | `e.clipboardData && e.clipboardData.getData("Text")` | ✗ |
| `sel` | `any` | let/var | `cm.doc.sel` | ✗ |
| `range` | `any` | let/var | `sel.ranges[i]` | ✗ |
| `indented` | `boolean` | let/var | `false` | ✗ |
| `text` | `any[]` | let/var | `[]` | ✗ |
| `ranges` | `any[]` | let/var | `[]` | ✗ |
| `line` | `any` | let/var | `cm.doc.sel.ranges[i].head.line` | ✗ |
| `lineRange` | `{ anchor: Pos; head: Pos; }` | let/var | `{anchor: Pos(line, 0), head: Pos(line + 1, 0)}` | ✗ |
| `optionHandlers` | `any` | let/var | `CodeMirror.optionHandlers` | ✗ |
| `helpers` | `{}` | let/var | `CodeMirror.helpers = {}` | ✗ |
| `options` | `any` | let/var | `this.options` | ✗ |
| `old` | `any` | let/var | `options[option]` | ✗ |
| `maps` | `any` | let/var | `this.state.keyMaps` | ✗ |
| `mode` | `any` | let/var | `spec.token ? spec : CodeMirror.getMode(this.options, spec)` | ✗ |
| `overlays` | `any` | let/var | `this.state.overlays` | ✗ |
| `cur` | `any` | let/var | `overlays[i].modeSpec` | ✗ |
| `ranges` | `any` | let/var | `this.doc.sel.ranges` | ✗ |
| `end` | `number` | let/var | `-1` | ✗ |
| `range` | `any` | let/var | `ranges[i]` | ✗ |
| `newRanges` | `any` | let/var | `this.doc.sel.ranges` | ✗ |
| `before` | `number` | let/var | `0` | ✗ |
| `after` | `number` | let/var | `(styles.length - 1) / 2` | ✗ |
| `ch` | `any` | let/var | `pos.ch` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `mid` | `number` | let/var | `(before + after) >> 1` | ✗ |
| `cut` | `any` | let/var | `type ? type.indexOf("overlay ") : -1` | ✗ |
| `mode` | `any` | let/var | `this.doc.mode` | ✗ |
| `found` | `any[]` | let/var | `[]` | ✗ |
| `help` | `any` | let/var | `helpers[type]` | ✗ |
| `val` | `any` | let/var | `help[mode[type][i]]` | ✗ |
| `cur` | `any` | let/var | `help._global[i$1]` | ✗ |
| `doc` | `any` | let/var | `this.doc` | ✗ |
| `pos` | `any` | let/var | `*not shown*` | ✗ |
| `end` | `boolean` | let/var | `false` | ✗ |
| `lineObj` | `any` | let/var | `*not shown*` | ✗ |
| `last` | `number` | let/var | `this.doc.first + this.doc.size - 1` | ✗ |
| `display` | `any` | let/var | `this.display` | ✗ |
| `top` | `any` | let/var | `pos.bottom` | ✗ |
| `left` | `any` | let/var | `pos.left` | ✗ |
| `dir` | `number` | let/var | `1` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `sel` | `any` | let/var | `this.doc.sel` | ✗ |
| `doc` | `any` | let/var | `this.doc` | ✗ |
| `dir` | `number` | let/var | `1` | ✗ |
| `x` | `any` | let/var | `goalColumn` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `doc` | `any` | let/var | `this.doc` | ✗ |
| `goals` | `any[]` | let/var | `[]` | ✗ |
| `collapse` | `any` | let/var | `!this.display.shift && !doc.extend && doc.sel.somethingSelected()` | ✗ |
| `doc` | `any` | let/var | `this.doc` | ✗ |
| `line` | `any` | let/var | `getLine(doc, pos.line).text` | ✗ |
| `start` | `any` | let/var | `pos.ch` | ✗ |
| `end` | `any` | let/var | `pos.ch` | ✗ |
| `check` | `(ch: any) => any` | let/var | `isWordChar(startChar, helper) ? function (ch) { return isWordChar(ch, helper)...` | ✗ |
| `scroller` | `any` | let/var | `this.display.scroller` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `lineNo` | `any` | let/var | `this.display.viewFrom` | ✗ |
| `oldHeight` | `any` | let/var | `this.display.cachedTextHeight` | ✗ |
| `old` | `any` | let/var | `this.doc` | ✗ |
| `phrases` | `any` | let/var | `this.options.phrases` | ✗ |
| `oldPos` | `any` | let/var | `pos` | ✗ |
| `origDir` | `any` | let/var | `dir` | ✗ |
| `lineDir` | `any` | let/var | `visually && doc.direction == "rtl" ? -dir : dir` | ✗ |
| `l` | `any` | let/var | `pos.line + lineDir` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `astral` | `boolean` | let/var | `dir > 0 ? ch >= 0xD800 && ch < 0xDC00 : ch >= 0xDC00 && ch < 0xDFFF` | ✗ |
| `sawType` | `any` | let/var | `null` | ✗ |
| `group` | `boolean` | let/var | `unit == "group"` | ✗ |
| `helper` | `any` | let/var | `doc.cm && doc.cm.getHelper(pos, "wordChars")` | ✗ |
| `cur` | `any` | let/var | `lineObj.text.charAt(pos.ch) \|\| "\n"` | ✗ |
| `type` | `string` | let/var | `isWordChar(cur, helper) ? "w" : group && cur == "\n" ? "n" : !group \|\| /\s/...` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `x` | `any` | let/var | `pos.left` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `target` | `any` | let/var | `*not shown*` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `input` | `this` | let/var | `this` | ✗ |
| `cm` | `any` | let/var | `input.cm` | ✗ |
| `div` | `any` | let/var | `input.div = display.lineDiv` | ✗ |
| `te` | `any` | let/var | `kludge.firstChild` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `view` | `any` | let/var | `cm.display.view` | ✗ |
| `start` | `{ node: any; start: number; end: numb...` | let/var | `(from.line >= cm.display.viewFrom && posToDOM(cm, from)) \|\| {node: view[0]....` | ✗ |
| `end` | `{ node: any; start: number; end: numb...` | let/var | `to.line < cm.display.viewTo && posToDOM(cm, to)` | ✗ |
| `measure` | `any` | let/var | `view[view.length - 1].measure` | ✗ |
| `map` | `any` | let/var | `measure.maps ? measure.maps[measure.maps.length - 1] : measure.map` | ✗ |
| `old` | `any` | let/var | `sel.rangeCount && sel.getRangeAt(0)` | ✗ |
| `rng` | `any` | let/var | `*not shown*` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `node` | `any` | let/var | `sel.getRangeAt(0).commonAncestorContainer` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `input` | `this` | let/var | `this` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `fromIndex` | `any` | let/var | `*not shown*` | ✗ |
| `fromLine` | `any` | let/var | `*not shown*` | ✗ |
| `fromNode` | `any` | let/var | `*not shown*` | ✗ |
| `toLine` | `any` | let/var | `*not shown*` | ✗ |
| `toNode` | `any` | let/var | `*not shown*` | ✗ |
| `cutFront` | `number` | let/var | `0` | ✗ |
| `cutEnd` | `number` | let/var | `0` | ✗ |
| `newTop` | `any` | let/var | `newText[0]` | ✗ |
| `oldTop` | `any` | let/var | `oldText[0]` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `side` | `string` | let/var | `"left"` | ✗ |
| `text` | `string` | let/var | `""` | ✗ |
| `closing` | `boolean` | let/var | `false` | ✗ |
| `extraLinebreak` | `boolean` | let/var | `false` | ✗ |
| `range` | `any` | let/var | `*not shown*` | ✗ |
| `lineNode` | `any` | let/var | `*not shown*` | ✗ |
| `lineView` | `any` | let/var | `cm.display.view[i]` | ✗ |
| `wrapper` | `any` | let/var | `lineView.text.firstChild` | ✗ |
| `bad` | `boolean` | let/var | `false` | ✗ |
| `line` | `any` | let/var | `lineView.rest ? lst(lineView.rest) : lineView.line` | ✗ |
| `textNode` | `any` | let/var | `node.nodeType == 3 ? node : null` | ✗ |
| `topNode` | `any` | let/var | `node` | ✗ |
| `measure` | `any` | let/var | `lineView.measure` | ✗ |
| `maps` | `any` | let/var | `measure.maps` | ✗ |
| `map` | `any` | let/var | `i < 0 ? measure.map : maps[i]` | ✗ |
| `curNode` | `any` | let/var | `map[j + 2]` | ✗ |
| `ch` | `any` | let/var | `map[j] + offset` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `input` | `this` | let/var | `this` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `te` | `any` | let/var | `this.textarea` | ✗ |
| `event` | `Event` | let/var | `new Event("paste")` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `doc` | `any` | let/var | `cm.doc` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `missed` | `boolean` | let/var | `false` | ✗ |
| `input` | `this` | let/var | `this` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `cm` | `any` | let/var | `this.cm` | ✗ |
| `input` | `any` | let/var | `this.textarea` | ✗ |
| `prevInput` | `string` | let/var | `this.prevInput` | ✗ |
| `text` | `any` | let/var | `input.value` | ✗ |
| `same` | `number` | let/var | `0` | ✗ |
| `input` | `this` | let/var | `this` | ✗ |
| `cm` | `any` | let/var | `input.cm` | ✗ |
| `display` | `any` | let/var | `cm.display` | ✗ |
| `te` | `any` | let/var | `input.textarea` | ✗ |
| `scrollPos` | `any` | let/var | `display.scroller.scrollTop` | ✗ |
| `reset` | `any` | let/var | `cm.options.resetSelectionOnContextMenu` | ✗ |
| `oldCSS` | `any` | let/var | `te.style.cssText` | ✗ |
| `oldWrapperCSS` | `any` | let/var | `input.wrapper.style.cssText` | ✗ |
| `oldScrollY` | `any` | let/var | `*not shown*` | ✗ |
| `extval` | `string` | let/var | `"\u200b" + (selected ? te.value : "")` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `realSubmit` | `any` | let/var | `*not shown*` | ✗ |
| `form` | `any` | let/var | `textarea.form` | ✗ |
| `wrappedSubmit` | `() => void` | let/var | `form.submit = function () { save(); form.submit = realSubmit; form.submit(); ...` | ✗ |


---

## Functions

### `classTest(cls: any): RegExp`

**Parameters:**

- **`cls`** `any`

**Returns:** `RegExp`

<details><summary>Code</summary>

```typescript
function classTest(cls) { return new RegExp("(^|\\s)" + cls + "(?:$|\\s)\\s*") }
```
</details>

### `rmClass(node: any, cls: any): void`

**Parameters:**

- **`node`** `any`
- **`cls`** `any`

**Returns:** `void`

**Calls:**

- `classTest(cls).exec`
- `current.slice`

<details><summary>Code</summary>

```typescript
function(node, cls) {
    var current = node.className;
    var match = classTest(cls).exec(current);
    if (match) {
      var after = current.slice(match.index + match[0].length);
      node.className = current.slice(0, match.index) + (after ? match[1] + after : "");
    }
  }
```
</details>

### `removeChildren(e: any): any`

**Parameters:**

- **`e`** `any`

**Returns:** `any`

**Calls:**

- `e.removeChild`

<details><summary>Code</summary>

```typescript
function removeChildren(e) {
    for (var count = e.childNodes.length; count > 0; --count)
      { e.removeChild(e.firstChild); }
    return e
  }
```
</details>

### `removeChildrenAndAdd(parent: any, e: any): any`

**Parameters:**

- **`parent`** `any`
- **`e`** `any`

**Returns:** `any`

**Calls:**

- `removeChildren(parent).appendChild`

<details><summary>Code</summary>

```typescript
function removeChildrenAndAdd(parent, e) {
    return removeChildren(parent).appendChild(e)
  }
```
</details>

### `elt(tag: any, content: any, className: any, style: any): any`

**Parameters:**

- **`tag`** `any`
- **`content`** `any`
- **`className`** `any`
- **`style`** `any`

**Returns:** `any`

**Calls:**

- `document.createElement`
- `e.appendChild`
- `document.createTextNode`

<details><summary>Code</summary>

```typescript
function elt(tag, content, className, style) {
    var e = document.createElement(tag);
    if (className) { e.className = className; }
    if (style) { e.style.cssText = style; }
    if (typeof content == "string") { e.appendChild(document.createTextNode(content)); }
    else if (content) { for (var i = 0; i < content.length; ++i) { e.appendChild(content[i]); } }
    return e
  }
```
</details>

### `eltP(tag: any, content: any, className: any, style: any): any`

**Parameters:**

- **`tag`** `any`
- **`content`** `any`
- **`className`** `any`
- **`style`** `any`

**Returns:** `any`

**Calls:**

- `elt`
- `e.setAttribute`

<details><summary>Code</summary>

```typescript
function eltP(tag, content, className, style) {
    var e = elt(tag, content, className, style);
    e.setAttribute("role", "presentation");
    return e
  }
```
</details>

### `contains(parent: any, child: any): any`

**Parameters:**

- **`parent`** `any`
- **`child`** `any`

**Returns:** `any`

**Calls:**

- `parent.contains`

<details><summary>Code</summary>

```typescript
function contains(parent, child) {
    if (child.nodeType == 3) // Android browser always returns false when child is a textnode
      { child = child.parentNode; }
    if (parent.contains)
      { return parent.contains(child) }
    do {
      if (child.nodeType == 11) { child = child.host; }
      if (child == parent) { return true }
    } while (child = child.parentNode)
  }
```
</details>

### `activeElt(): Element`

**Returns:** `Element`

**Internal Comments:**
```
// IE and Edge may throw an "Unspecified Error" when accessing document.activeElement. (x2)
// IE < 10 will throw when accessed while the page is loading or in an iframe. (x2)
// IE > 9 and Edge will throw when accessed in an iframe if document.body is unavailable. (x2)
```

<details><summary>Code</summary>

```typescript
function activeElt() {
    // IE and Edge may throw an "Unspecified Error" when accessing document.activeElement.
    // IE < 10 will throw when accessed while the page is loading or in an iframe.
    // IE > 9 and Edge will throw when accessed in an iframe if document.body is unavailable.
    var activeElement;
    try {
      activeElement = document.activeElement;
    } catch(e) {
      activeElement = document.body || null;
    }
    while (activeElement && activeElement.shadowRoot && activeElement.shadowRoot.activeElement)
      { activeElement = activeElement.shadowRoot.activeElement; }
    return activeElement
  }
```
</details>

### `addClass(node: any, cls: any): void`

**Parameters:**

- **`node`** `any`
- **`cls`** `any`

**Returns:** `void`

**Calls:**

- `classTest(cls).test`

<details><summary>Code</summary>

```typescript
function addClass(node, cls) {
    var current = node.className;
    if (!classTest(cls).test(current)) { node.className += (current ? " " : "") + cls; }
  }
```
</details>

### `joinClasses(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `a.split`
- `classTest(as[i]).test`

<details><summary>Code</summary>

```typescript
function joinClasses(a, b) {
    var as = a.split(" ");
    for (var i = 0; i < as.length; i++)
      { if (as[i] && !classTest(as[i]).test(b)) { b += " " + as[i]; } }
    return b
  }
```
</details>

### `selectInput(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `node.select`

<details><summary>Code</summary>

```typescript
function(node) { node.select(); }
```
</details>

### `bind(f: any): () => any`

**Parameters:**

- **`f`** `any`

**Returns:** `() => any`

**Calls:**

- `Array.prototype.slice.call`
- `f.apply`

<details><summary>Code</summary>

```typescript
function bind(f) {
    var args = Array.prototype.slice.call(arguments, 1);
    return function(){return f.apply(null, args)}
  }
```
</details>

### `copyObj(obj: any, target: any, overwrite: any): any`

**Parameters:**

- **`obj`** `any`
- **`target`** `any`
- **`overwrite`** `any`

**Returns:** `any`

**Calls:**

- `obj.hasOwnProperty`
- `target.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function copyObj(obj, target, overwrite) {
    if (!target) { target = {}; }
    for (var prop in obj)
      { if (obj.hasOwnProperty(prop) && (overwrite !== false || !target.hasOwnProperty(prop)))
        { target[prop] = obj[prop]; } }
    return target
  }
```
</details>

### `countColumn(string: any, end: any, tabSize: any, startIndex: any, startValue: any): any`

**Parameters:**

- **`string`** `any`
- **`end`** `any`
- **`tabSize`** `any`
- **`startIndex`** `any`
- **`startValue`** `any`

**Returns:** `any`

**Calls:**

- `string.search`
- `string.indexOf`

<details><summary>Code</summary>

```typescript
function countColumn(string, end, tabSize, startIndex, startValue) {
    if (end == null) {
      end = string.search(/[^\s\u00a0]/);
      if (end == -1) { end = string.length; }
    }
    for (var i = startIndex || 0, n = startValue || 0;;) {
      var nextTab = string.indexOf("\t", i);
      if (nextTab < 0 || nextTab >= end)
        { return n + (end - i) }
      n += nextTab - i;
      n += tabSize - (n % tabSize);
      i = nextTab + 1;
    }
  }
```
</details>

### `Delayed(): void`

**Returns:** `void`

**Calls:**

- `bind`

<details><summary>Code</summary>

```typescript
function() {
    this.id = null;
    this.f = null;
    this.time = 0;
    this.handler = bind(this.onTimeout, this);
  }
```
</details>

### `indexOf(array: any, elt: any): number`

**Parameters:**

- **`array`** `any`
- **`elt`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function indexOf(array, elt) {
    for (var i = 0; i < array.length; ++i)
      { if (array[i] == elt) { return i } }
    return -1
  }
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Pass"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Pass"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Pass"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Pass"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Pass"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Pass"}
```
</details>

### `findColumn(string: any, goal: any, tabSize: any): number`

**Parameters:**

- **`string`** `any`
- **`goal`** `any`
- **`tabSize`** `any`

**Returns:** `number`

**Calls:**

- `string.indexOf`
- `Math.min`

<details><summary>Code</summary>

```typescript
function findColumn(string, goal, tabSize) {
    for (var pos = 0, col = 0;;) {
      var nextTab = string.indexOf("\t", pos);
      if (nextTab == -1) { nextTab = string.length; }
      var skipped = nextTab - pos;
      if (nextTab == string.length || col + skipped >= goal)
        { return pos + Math.min(skipped, goal - col) }
      col += nextTab - pos;
      col += tabSize - (col % tabSize);
      pos = nextTab + 1;
      if (col >= goal) { return pos }
    }
  }
```
</details>

### `spaceStr(n: any): string`

**Parameters:**

- **`n`** `any`

**Returns:** `string`

**Calls:**

- `spaceStrs.push`
- `lst`

<details><summary>Code</summary>

```typescript
function spaceStr(n) {
    while (spaceStrs.length <= n)
      { spaceStrs.push(lst(spaceStrs) + " "); }
    return spaceStrs[n]
  }
```
</details>

### `lst(arr: any): any`

**Parameters:**

- **`arr`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function lst(arr) { return arr[arr.length-1] }
```
</details>

### `map(array: any, f: any): any[]`

**Parameters:**

- **`array`** `any`
- **`f`** `any`

**Returns:** `any[]`

**Calls:**

- `f`

<details><summary>Code</summary>

```typescript
function map(array, f) {
    var out = [];
    for (var i = 0; i < array.length; i++) { out[i] = f(array[i], i); }
    return out
  }
```
</details>

### `insertSorted(array: any, value: any, score: any): void`

**Parameters:**

- **`array`** `any`
- **`value`** `any`
- **`score`** `any`

**Returns:** `void`

**Calls:**

- `score`
- `array.splice`

<details><summary>Code</summary>

```typescript
function insertSorted(array, value, score) {
    var pos = 0, priority = score(value);
    while (pos < array.length && score(array[pos]) <= priority) { pos++; }
    array.splice(pos, 0, value);
  }
```
</details>

### `nothing(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function nothing() {}
```
</details>

### `createObj(base: any, props: any): any`

**Parameters:**

- **`base`** `any`
- **`props`** `any`

**Returns:** `any`

**Calls:**

- `Object.create`
- `copyObj`

<details><summary>Code</summary>

```typescript
function createObj(base, props) {
    var inst;
    if (Object.create) {
      inst = Object.create(base);
    } else {
      nothing.prototype = base;
      inst = new nothing();
    }
    if (props) { copyObj(props, inst); }
    return inst
  }
```
</details>

### `isWordCharBasic(ch: any): boolean`

**Parameters:**

- **`ch`** `any`

**Returns:** `boolean`

**Calls:**

- `/\w/.test`
- `ch.toUpperCase`
- `ch.toLowerCase`
- `nonASCIISingleCaseWordChar.test`

<details><summary>Code</summary>

```typescript
function isWordCharBasic(ch) {
    return /\w/.test(ch) || ch > "\x80" &&
      (ch.toUpperCase() != ch.toLowerCase() || nonASCIISingleCaseWordChar.test(ch))
  }
```
</details>

### `isWordChar(ch: any, helper: any): any`

**Parameters:**

- **`ch`** `any`
- **`helper`** `any`

**Returns:** `any`

**Calls:**

- `isWordCharBasic`
- `helper.source.indexOf`
- `helper.test`

<details><summary>Code</summary>

```typescript
function isWordChar(ch, helper) {
    if (!helper) { return isWordCharBasic(ch) }
    if (helper.source.indexOf("\\w") > -1 && isWordCharBasic(ch)) { return true }
    return helper.test(ch)
  }
```
</details>

### `isEmpty(obj: any): boolean`

**Parameters:**

- **`obj`** `any`

**Returns:** `boolean`

**Calls:**

- `obj.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function isEmpty(obj) {
    for (var n in obj) { if (obj.hasOwnProperty(n) && obj[n]) { return false } }
    return true
  }
```
</details>

### `isExtendingChar(ch: any): boolean`

**Parameters:**

- **`ch`** `any`

**Returns:** `boolean`

**Calls:**

- `ch.charCodeAt`
- `extendingChars.test`

<details><summary>Code</summary>

```typescript
function isExtendingChar(ch) { return ch.charCodeAt(0) >= 768 && extendingChars.test(ch) }
```
</details>

### `skipExtendingChars(str: any, pos: any, dir: any): any`

**Parameters:**

- **`str`** `any`
- **`pos`** `any`
- **`dir`** `any`

**Returns:** `any`

**Calls:**

- `isExtendingChar`
- `str.charAt`

<details><summary>Code</summary>

```typescript
function skipExtendingChars(str, pos, dir) {
    while ((dir < 0 ? pos > 0 : pos < str.length) && isExtendingChar(str.charAt(pos))) { pos += dir; }
    return pos
  }
```
</details>

### `findFirst(pred: any, from: any, to: any): any`

**Parameters:**

- **`pred`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `any`

**Calls:**

- `Math.ceil`
- `Math.floor`
- `pred`

**Internal Comments:**
```
// At any point we are certain `to` satisfies `pred`, don't know (x2)
// whether `from` does. (x2)
```

<details><summary>Code</summary>

```typescript
function findFirst(pred, from, to) {
    // At any point we are certain `to` satisfies `pred`, don't know
    // whether `from` does.
    var dir = from > to ? -1 : 1;
    for (;;) {
      if (from == to) { return from }
      var midF = (from + to) / 2, mid = dir < 0 ? Math.ceil(midF) : Math.floor(midF);
      if (mid == from) { return pred(mid) ? from : to }
      if (pred(mid)) { to = mid; }
      else { from = mid + dir; }
    }
  }
```
</details>

### `iterateBidiSections(order: any, from: any, to: any, f: any): any`

**Parameters:**

- **`order`** `any`
- **`from`** `any`
- **`to`** `any`
- **`f`** `any`

**Returns:** `any`

**Calls:**

- `f`
- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function iterateBidiSections(order, from, to, f) {
    if (!order) { return f(from, to, "ltr", 0) }
    var found = false;
    for (var i = 0; i < order.length; ++i) {
      var part = order[i];
      if (part.from < to && part.to > from || from == to && part.to == from) {
        f(Math.max(part.from, from), Math.min(part.to, to), part.level == 1 ? "rtl" : "ltr", i);
        found = true;
      }
    }
    if (!found) { f(from, to, "ltr"); }
  }
```
</details>

### `getBidiPartAt(order: any, ch: any, sticky: any): number`

**Parameters:**

- **`order`** `any`
- **`ch`** `any`
- **`sticky`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function getBidiPartAt(order, ch, sticky) {
    var found;
    bidiOther = null;
    for (var i = 0; i < order.length; ++i) {
      var cur = order[i];
      if (cur.from < ch && cur.to > ch) { return i }
      if (cur.to == ch) {
        if (cur.from != cur.to && sticky == "before") { found = i; }
        else { bidiOther = i; }
      }
      if (cur.from == ch) {
        if (cur.from != cur.to && sticky != "before") { found = i; }
        else { bidiOther = i; }
      }
    }
    return found != null ? found : bidiOther
  }
```
</details>

### `charType(code: any): string`

**Parameters:**

- **`code`** `any`

**Returns:** `string`

**Calls:**

- `lowTypes.charAt`
- `arabicTypes.charAt`

<details><summary>Code</summary>

```typescript
function charType(code) {
      if (code <= 0xf7) { return lowTypes.charAt(code) }
      else if (0x590 <= code && code <= 0x5f4) { return "R" }
      else if (0x600 <= code && code <= 0x6f9) { return arabicTypes.charAt(code - 0x600) }
      else if (0x6ee <= code && code <= 0x8ac) { return "r" }
      else if (0x2000 <= code && code <= 0x200b) { return "w" }
      else if (code == 0x200c) { return "b" }
      else { return "L" }
    }
```
</details>

### `BidiSpan(level: any, from: any, to: any): void`

**Parameters:**

- **`level`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BidiSpan(level, from, to) {
      this.level = level;
      this.from = from; this.to = to;
    }
```
</details>

### `getOrder(line: any, direction: any): any`

**Parameters:**

- **`line`** `any`
- **`direction`** `any`

**Returns:** `any`

**Calls:**

- `bidiOrdering`

<details><summary>Code</summary>

```typescript
function getOrder(line, direction) {
    var order = line.order;
    if (order == null) { order = line.order = bidiOrdering(line.text, direction); }
    return order
  }
```
</details>

### `on(emitter: any, type: any, f: any): void`

**Parameters:**

- **`emitter`** `any`
- **`type`** `any`
- **`f`** `any`

**Returns:** `void`

**Calls:**

- `emitter.addEventListener`
- `emitter.attachEvent`
- `(map[type] || noHandlers).concat`

<details><summary>Code</summary>

```typescript
function(emitter, type, f) {
    if (emitter.addEventListener) {
      emitter.addEventListener(type, f, { passive: false });
    } else if (emitter.attachEvent) {
      emitter.attachEvent("on" + type, f);
    } else {
      var map = emitter._handlers || (emitter._handlers = {});
      map[type] = (map[type] || noHandlers).concat(f);
    }
  }
```
</details>

### `getHandlers(emitter: any, type: any): any`

**Parameters:**

- **`emitter`** `any`
- **`type`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getHandlers(emitter, type) {
    return emitter._handlers && emitter._handlers[type] || noHandlers
  }
```
</details>

### `off(emitter: any, type: any, f: any): void`

**Parameters:**

- **`emitter`** `any`
- **`type`** `any`
- **`f`** `any`

**Returns:** `void`

**Calls:**

- `emitter.removeEventListener`
- `emitter.detachEvent`
- `indexOf`
- `arr.slice(0, index).concat`
- `arr.slice`

<details><summary>Code</summary>

```typescript
function off(emitter, type, f) {
    if (emitter.removeEventListener) {
      emitter.removeEventListener(type, f, false);
    } else if (emitter.detachEvent) {
      emitter.detachEvent("on" + type, f);
    } else {
      var map = emitter._handlers, arr = map && map[type];
      if (arr) {
        var index = indexOf(arr, f);
        if (index > -1)
          { map[type] = arr.slice(0, index).concat(arr.slice(index + 1)); }
      }
    }
  }
```
</details>

### `signal(emitter: any, type: any): void`

**Parameters:**

- **`emitter`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `getHandlers`
- `Array.prototype.slice.call`
- `handlers[i].apply`

<details><summary>Code</summary>

```typescript
function signal(emitter, type /*, values...*/) {
    var handlers = getHandlers(emitter, type);
    if (!handlers.length) { return }
    var args = Array.prototype.slice.call(arguments, 2);
    for (var i = 0; i < handlers.length; ++i) { handlers[i].apply(null, args); }
  }
```
</details>

### `signalDOMEvent(cm: any, e: any, override: any): any`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`
- **`override`** `any`

**Returns:** `any`

**Calls:**

- `signal`
- `e_defaultPrevented`

<details><summary>Code</summary>

```typescript
function signalDOMEvent(cm, e, override) {
    if (typeof e == "string")
      { e = {type: e, preventDefault: function() { this.defaultPrevented = true; }}; }
    signal(cm, override || e.type, cm, e);
    return e_defaultPrevented(e) || e.codemirrorIgnore
  }
```
</details>

### `preventDefault(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { this.defaultPrevented = true; }
```
</details>

### `preventDefault(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { this.defaultPrevented = true; }
```
</details>

### `signalCursorActivity(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `indexOf`
- `set.push`

<details><summary>Code</summary>

```typescript
function signalCursorActivity(cm) {
    var arr = cm._handlers && cm._handlers.cursorActivity;
    if (!arr) { return }
    var set = cm.curOp.cursorActivityHandlers || (cm.curOp.cursorActivityHandlers = []);
    for (var i = 0; i < arr.length; ++i) { if (indexOf(set, arr[i]) == -1)
      { set.push(arr[i]); } }
  }
```
</details>

### `hasHandler(emitter: any, type: any): boolean`

**Parameters:**

- **`emitter`** `any`
- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `getHandlers`

<details><summary>Code</summary>

```typescript
function hasHandler(emitter, type) {
    return getHandlers(emitter, type).length > 0
  }
```
</details>

### `eventMixin(ctor: any): void`

**Parameters:**

- **`ctor`** `any`

**Returns:** `void`

**Calls:**

- `on`
- `off`

<details><summary>Code</summary>

```typescript
function eventMixin(ctor) {
    ctor.prototype.on = function(type, f) {on(this, type, f);};
    ctor.prototype.off = function(type, f) {off(this, type, f);};
  }
```
</details>

### `e_preventDefault(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.preventDefault`

<details><summary>Code</summary>

```typescript
function e_preventDefault(e) {
    if (e.preventDefault) { e.preventDefault(); }
    else { e.returnValue = false; }
  }
```
</details>

### `e_stopPropagation(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.stopPropagation`

<details><summary>Code</summary>

```typescript
function e_stopPropagation(e) {
    if (e.stopPropagation) { e.stopPropagation(); }
    else { e.cancelBubble = true; }
  }
```
</details>

### `e_defaultPrevented(e: any): any`

**Parameters:**

- **`e`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function e_defaultPrevented(e) {
    return e.defaultPrevented != null ? e.defaultPrevented : e.returnValue == false
  }
```
</details>

### `e_stop(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e_preventDefault`
- `e_stopPropagation`

<details><summary>Code</summary>

```typescript
function e_stop(e) {e_preventDefault(e); e_stopPropagation(e);}
```
</details>

### `e_target(e: any): any`

**Parameters:**

- **`e`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function e_target(e) {return e.target || e.srcElement}
```
</details>

### `e_button(e: any): any`

**Parameters:**

- **`e`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function e_button(e) {
    var b = e.which;
    if (b == null) {
      if (e.button & 1) { b = 1; }
      else if (e.button & 2) { b = 3; }
      else if (e.button & 4) { b = 2; }
    }
    if (mac && e.ctrlKey && b == 1) { b = 3; }
    return b
  }
```
</details>

### `zeroWidthElement(measure: any): any`

**Parameters:**

- **`measure`** `any`

**Returns:** `any`

**Calls:**

- `elt`
- `removeChildrenAndAdd`
- `document.createTextNode`
- `node.setAttribute`

<details><summary>Code</summary>

```typescript
function zeroWidthElement(measure) {
    if (zwspSupported == null) {
      var test = elt("span", "\u200b");
      removeChildrenAndAdd(measure, elt("span", [test, document.createTextNode("x")]));
      if (measure.firstChild.offsetHeight != 0)
        { zwspSupported = test.offsetWidth <= 1 && test.offsetHeight > 2 && !(ie && ie_version < 8); }
    }
    var node = zwspSupported ? elt("span", "\u200b") :
      elt("span", "\u00a0", null, "display: inline-block; width: 1px; margin-right: -1px");
    node.setAttribute("cm-text", "");
    return node
  }
```
</details>

### `hasBadBidiRects(measure: any): any`

**Parameters:**

- **`measure`** `any`

**Returns:** `any`

**Calls:**

- `removeChildrenAndAdd`
- `document.createTextNode`
- `range(txt, 0, 1).getBoundingClientRect`
- `range(txt, 1, 2).getBoundingClientRect`
- `removeChildren`

<details><summary>Code</summary>

```typescript
function hasBadBidiRects(measure) {
    if (badBidiRects != null) { return badBidiRects }
    var txt = removeChildrenAndAdd(measure, document.createTextNode("A\u062eA"));
    var r0 = range(txt, 0, 1).getBoundingClientRect();
    var r1 = range(txt, 1, 2).getBoundingClientRect();
    removeChildren(measure);
    if (!r0 || r0.left == r0.right) { return false } // Safari returns null in some cases (#2780)
    return badBidiRects = (r1.right - r0.right < 3)
  }
```
</details>

### `hasBadZoomedRects(measure: any): any`

**Parameters:**

- **`measure`** `any`

**Returns:** `any`

**Calls:**

- `removeChildrenAndAdd`
- `elt`
- `node.getBoundingClientRect`
- `range(node, 0, 1).getBoundingClientRect`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function hasBadZoomedRects(measure) {
    if (badZoomedRects != null) { return badZoomedRects }
    var node = removeChildrenAndAdd(measure, elt("span", "x"));
    var normal = node.getBoundingClientRect();
    var fromRange = range(node, 0, 1).getBoundingClientRect();
    return badZoomedRects = Math.abs(normal.left - fromRange.left) > 1
  }
```
</details>

### `defineMode(name: any, mode: any): void`

**Parameters:**

- **`name`** `any`
- **`mode`** `any`

**Returns:** `void`

**Calls:**

- `Array.prototype.slice.call`

<details><summary>Code</summary>

```typescript
function defineMode(name, mode) {
    if (arguments.length > 2)
      { mode.dependencies = Array.prototype.slice.call(arguments, 2); }
    modes[name] = mode;
  }
```
</details>

### `defineMIME(mime: any, spec: any): void`

**Parameters:**

- **`mime`** `any`
- **`spec`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function defineMIME(mime, spec) {
    mimeModes[mime] = spec;
  }
```
</details>

### `resolveMode(spec: any): any`

**Parameters:**

- **`spec`** `any`

**Returns:** `any`

**Calls:**

- `mimeModes.hasOwnProperty`
- `createObj`
- `/^[\w\-]+\/[\w\-]+\+xml$/.test`
- `resolveMode`
- `/^[\w\-]+\/[\w\-]+\+json$/.test`

<details><summary>Code</summary>

```typescript
function resolveMode(spec) {
    if (typeof spec == "string" && mimeModes.hasOwnProperty(spec)) {
      spec = mimeModes[spec];
    } else if (spec && typeof spec.name == "string" && mimeModes.hasOwnProperty(spec.name)) {
      var found = mimeModes[spec.name];
      if (typeof found == "string") { found = {name: found}; }
      spec = createObj(found, spec);
      spec.name = found.name;
    } else if (typeof spec == "string" && /^[\w\-]+\/[\w\-]+\+xml$/.test(spec)) {
      return resolveMode("application/xml")
    } else if (typeof spec == "string" && /^[\w\-]+\/[\w\-]+\+json$/.test(spec)) {
      return resolveMode("application/json")
    }
    if (typeof spec == "string") { return {name: spec} }
    else { return spec || {name: "null"} }
  }
```
</details>

### `getMode(options: any, spec: any): any`

**Parameters:**

- **`options`** `any`
- **`spec`** `any`

**Returns:** `any`

**Calls:**

- `resolveMode`
- `getMode`
- `mfactory`
- `modeExtensions.hasOwnProperty`
- `exts.hasOwnProperty`
- `modeObj.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function getMode(options, spec) {
    spec = resolveMode(spec);
    var mfactory = modes[spec.name];
    if (!mfactory) { return getMode(options, "text/plain") }
    var modeObj = mfactory(options, spec);
    if (modeExtensions.hasOwnProperty(spec.name)) {
      var exts = modeExtensions[spec.name];
      for (var prop in exts) {
        if (!exts.hasOwnProperty(prop)) { continue }
        if (modeObj.hasOwnProperty(prop)) { modeObj["_" + prop] = modeObj[prop]; }
        modeObj[prop] = exts[prop];
      }
    }
    modeObj.name = spec.name;
    if (spec.helperType) { modeObj.helperType = spec.helperType; }
    if (spec.modeProps) { for (var prop$1 in spec.modeProps)
      { modeObj[prop$1] = spec.modeProps[prop$1]; } }

    return modeObj
  }
```
</details>

### `extendMode(mode: any, properties: any): void`

**Parameters:**

- **`mode`** `any`
- **`properties`** `any`

**Returns:** `void`

**Calls:**

- `modeExtensions.hasOwnProperty`
- `copyObj`

<details><summary>Code</summary>

```typescript
function extendMode(mode, properties) {
    var exts = modeExtensions.hasOwnProperty(mode) ? modeExtensions[mode] : (modeExtensions[mode] = {});
    copyObj(properties, exts);
  }
```
</details>

### `copyState(mode: any, state: any): any`

**Parameters:**

- **`mode`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `mode.copyState`
- `val.concat`

<details><summary>Code</summary>

```typescript
function copyState(mode, state) {
    if (state === true) { return state }
    if (mode.copyState) { return mode.copyState(state) }
    var nstate = {};
    for (var n in state) {
      var val = state[n];
      if (val instanceof Array) { val = val.concat([]); }
      nstate[n] = val;
    }
    return nstate
  }
```
</details>

### `innerMode(mode: any, state: any): any`

**Parameters:**

- **`mode`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `mode.innerMode`

<details><summary>Code</summary>

```typescript
function innerMode(mode, state) {
    var info;
    while (mode.innerMode) {
      info = mode.innerMode(state);
      if (!info || info.mode == mode) { break }
      state = info.state;
      mode = info.mode;
    }
    return info || {mode: mode, state: state}
  }
```
</details>

### `startState(mode: any, a1: any, a2: any): any`

**Parameters:**

- **`mode`** `any`
- **`a1`** `any`
- **`a2`** `any`

**Returns:** `any`

**Calls:**

- `mode.startState`

<details><summary>Code</summary>

```typescript
function startState(mode, a1, a2) {
    return mode.startState ? mode.startState(a1, a2) : true
  }
```
</details>

### `StringStream(string: any, tabSize: any, lineOracle: any): void`

**Parameters:**

- **`string`** `any`
- **`tabSize`** `any`
- **`lineOracle`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(string, tabSize, lineOracle) {
    this.pos = this.start = 0;
    this.string = string;
    this.tabSize = tabSize || 8;
    this.lastColumnPos = this.lastColumnValue = 0;
    this.lineStart = 0;
    this.lineOracle = lineOracle;
  }
```
</details>

### `cased(str: any): any`

**Parameters:**

- **`str`** `any`

**Returns:** `any`

**Calls:**

- `str.toLowerCase`

<details><summary>Code</summary>

```typescript
function (str) { return caseInsensitive ? str.toLowerCase() : str; }
```
</details>

### `getLine(doc: any, n: any): any`

**Parameters:**

- **`doc`** `any`
- **`n`** `any`

**Returns:** `any`

**Calls:**

- `child.chunkSize`

<details><summary>Code</summary>

```typescript
function getLine(doc, n) {
    n -= doc.first;
    if (n < 0 || n >= doc.size) { throw new Error("There is no line " + (n + doc.first) + " in the document.") }
    var chunk = doc;
    while (!chunk.lines) {
      for (var i = 0;; ++i) {
        var child = chunk.children[i], sz = child.chunkSize();
        if (n < sz) { chunk = child; break }
        n -= sz;
      }
    }
    return chunk.lines[n]
  }
```
</details>

### `getBetween(doc: any, start: any, end: any): any[]`

**Parameters:**

- **`doc`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `any[]`

**Calls:**

- `doc.iter`
- `text.slice`
- `out.push`

<details><summary>Code</summary>

```typescript
function getBetween(doc, start, end) {
    var out = [], n = start.line;
    doc.iter(start.line, end.line + 1, function (line) {
      var text = line.text;
      if (n == end.line) { text = text.slice(0, end.ch); }
      if (n == start.line) { text = text.slice(start.ch); }
      out.push(text);
      ++n;
    });
    return out
  }
```
</details>

### `getLines(doc: any, from: any, to: any): any[]`

**Parameters:**

- **`doc`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `any[]`

**Calls:**

- `doc.iter`
- `out.push`

<details><summary>Code</summary>

```typescript
function getLines(doc, from, to) {
    var out = [];
    doc.iter(from, to, function (line) { out.push(line.text); }); // iter aborts when callback returns truthy value
    return out
  }
```
</details>

### `updateLineHeight(line: any, height: any): void`

**Parameters:**

- **`line`** `any`
- **`height`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function updateLineHeight(line, height) {
    var diff = height - line.height;
    if (diff) { for (var n = line; n; n = n.parent) { n.height += diff; } }
  }
```
</details>

### `lineNo(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `indexOf`
- `chunk.children[i].chunkSize`

<details><summary>Code</summary>

```typescript
function lineNo(line) {
    if (line.parent == null) { return null }
    var cur = line.parent, no = indexOf(cur.lines, line);
    for (var chunk = cur.parent; chunk; cur = chunk, chunk = chunk.parent) {
      for (var i = 0;; ++i) {
        if (chunk.children[i] == cur) { break }
        no += chunk.children[i].chunkSize();
      }
    }
    return no + cur.first
  }
```
</details>

### `lineAtHeight(chunk: any, h: any): any`

**Parameters:**

- **`chunk`** `any`
- **`h`** `any`

**Returns:** `any`

**Calls:**

- `child.chunkSize`

<details><summary>Code</summary>

```typescript
function lineAtHeight(chunk, h) {
    var n = chunk.first;
    outer: do {
      for (var i$1 = 0; i$1 < chunk.children.length; ++i$1) {
        var child = chunk.children[i$1], ch = child.height;
        if (h < ch) { chunk = child; continue outer }
        h -= ch;
        n += child.chunkSize();
      }
      return n
    } while (!chunk.lines)
    var i = 0;
    for (; i < chunk.lines.length; ++i) {
      var line = chunk.lines[i], lh = line.height;
      if (h < lh) { break }
      h -= lh;
    }
    return n + i
  }
```
</details>

### `isLine(doc: any, l: any): boolean`

**Parameters:**

- **`doc`** `any`
- **`l`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isLine(doc, l) {return l >= doc.first && l < doc.first + doc.size}
```
</details>

### `lineNumberFor(options: any, i: any): string`

**Parameters:**

- **`options`** `any`
- **`i`** `any`

**Returns:** `string`

**Calls:**

- `String`
- `options.lineNumberFormatter`

<details><summary>Code</summary>

```typescript
function lineNumberFor(options, i) {
    return String(options.lineNumberFormatter(i + options.firstLineNumber))
  }
```
</details>

### `Pos(line: any, ch: any, sticky: any): Pos`

**Parameters:**

- **`line`** `any`
- **`ch`** `any`
- **`sticky`** `any`

**Returns:** `Pos`

<details><summary>Code</summary>

```typescript
function Pos(line, ch, sticky) {
    if ( sticky === void 0 ) sticky = null;

    if (!(this instanceof Pos)) { return new Pos(line, ch, sticky) }
    this.line = line;
    this.ch = ch;
    this.sticky = sticky;
  }
```
</details>

### `cmp(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function cmp(a, b) { return a.line - b.line || a.ch - b.ch }
```
</details>

### `equalCursorPos(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

**Calls:**

- `cmp`

<details><summary>Code</summary>

```typescript
function equalCursorPos(a, b) { return a.sticky == b.sticky && cmp(a, b) == 0 }
```
</details>

### `copyPos(x: any): Pos`

**Parameters:**

- **`x`** `any`

**Returns:** `Pos`

**Calls:**

- `Pos`

<details><summary>Code</summary>

```typescript
function copyPos(x) {return Pos(x.line, x.ch)}
```
</details>

### `maxPos(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `cmp`

<details><summary>Code</summary>

```typescript
function maxPos(a, b) { return cmp(a, b) < 0 ? b : a }
```
</details>

### `minPos(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `cmp`

<details><summary>Code</summary>

```typescript
function minPos(a, b) { return cmp(a, b) < 0 ? a : b }
```
</details>

### `clipLine(doc: any, n: any): number`

**Parameters:**

- **`doc`** `any`
- **`n`** `any`

**Returns:** `number`

**Calls:**

- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function clipLine(doc, n) {return Math.max(doc.first, Math.min(n, doc.first + doc.size - 1))}
```
</details>

### `clipPos(doc: any, pos: any): any`

**Parameters:**

- **`doc`** `any`
- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `Pos`
- `getLine`
- `clipToLen`

<details><summary>Code</summary>

```typescript
function clipPos(doc, pos) {
    if (pos.line < doc.first) { return Pos(doc.first, 0) }
    var last = doc.first + doc.size - 1;
    if (pos.line > last) { return Pos(last, getLine(doc, last).text.length) }
    return clipToLen(pos, getLine(doc, pos.line).text.length)
  }
```
</details>

### `clipToLen(pos: any, linelen: any): any`

**Parameters:**

- **`pos`** `any`
- **`linelen`** `any`

**Returns:** `any`

**Calls:**

- `Pos`

<details><summary>Code</summary>

```typescript
function clipToLen(pos, linelen) {
    var ch = pos.ch;
    if (ch == null || ch > linelen) { return Pos(pos.line, linelen) }
    else if (ch < 0) { return Pos(pos.line, 0) }
    else { return pos }
  }
```
</details>

### `clipPosArray(doc: any, array: any): any[]`

**Parameters:**

- **`doc`** `any`
- **`array`** `any`

**Returns:** `any[]`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function clipPosArray(doc, array) {
    var out = [];
    for (var i = 0; i < array.length; i++) { out[i] = clipPos(doc, array[i]); }
    return out
  }
```
</details>

### `SavedContext(state: any, lookAhead: any): void`

**Parameters:**

- **`state`** `any`
- **`lookAhead`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(state, lookAhead) {
    this.state = state;
    this.lookAhead = lookAhead;
  }
```
</details>

### `Context(doc: any, state: any, line: any, lookAhead: any): void`

**Parameters:**

- **`doc`** `any`
- **`state`** `any`
- **`line`** `any`
- **`lookAhead`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(doc, state, line, lookAhead) {
    this.state = state;
    this.doc = doc;
    this.line = line;
    this.maxLookAhead = lookAhead || 0;
    this.baseTokens = null;
    this.baseTokenPos = 1;
  }
```
</details>

### `highlightLine(cm: any, line: any, context: any, forceToEnd: any): { styles: any[]; classes: {}; }`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`
- **`context`** `any`
- **`forceToEnd`** `any`

**Returns:** `{ styles: any[]; classes: {}; }`

**Calls:**

- `runMode`
- `st.push`
- `st.splice`
- `Math.min`
- `loop`

**Internal Comments:**
```
// A styles array always starts with a number identifying the (x2)
// mode/overlays that it is based on (for easy invalidation). (x2)
// Compute the base array of styles (x3)
// Run overlays, adjust style array. (x2)
// Ensure there's a token end at the current position, and that i points at it
```

<details><summary>Code</summary>

```typescript
function highlightLine(cm, line, context, forceToEnd) {
    // A styles array always starts with a number identifying the
    // mode/overlays that it is based on (for easy invalidation).
    var st = [cm.state.modeGen], lineClasses = {};
    // Compute the base array of styles
    runMode(cm, line.text, cm.doc.mode, context, function (end, style) { return st.push(end, style); },
            lineClasses, forceToEnd);
    var state = context.state;

    // Run overlays, adjust style array.
    var loop = function ( o ) {
      context.baseTokens = st;
      var overlay = cm.state.overlays[o], i = 1, at = 0;
      context.state = true;
      runMode(cm, line.text, overlay.mode, context, function (end, style) {
        var start = i;
        // Ensure there's a token end at the current position, and that i points at it
        while (at < end) {
          var i_end = st[i];
          if (i_end > end)
            { st.splice(i, 1, end, st[i+1], i_end); }
          i += 2;
          at = Math.min(end, i_end);
        }
        if (!style) { return }
        if (overlay.opaque) {
          st.splice(start, i - start, end, "overlay " + style);
          i = start + 2;
        } else {
          for (; start < i; start += 2) {
            var cur = st[start+1];
            st[start+1] = (cur ? cur + " " : "") + "overlay " + style;
          }
        }
      }, lineClasses);
      context.state = state;
      context.baseTokens = null;
      context.baseTokenPos = 1;
    };

    for (var o = 0; o < cm.state.overlays.length; ++o) loop( o );

    return {styles: st, classes: lineClasses.bgClass || lineClasses.textClass ? lineClasses : null}
  }
```
</details>

### `loop(o: any): void`

**Parameters:**

- **`o`** `any`

**Returns:** `void`

**Calls:**

- `runMode`
- `st.splice`
- `Math.min`

**Internal Comments:**
```
// Ensure there's a token end at the current position, and that i points at it
```

<details><summary>Code</summary>

```typescript
function ( o ) {
      context.baseTokens = st;
      var overlay = cm.state.overlays[o], i = 1, at = 0;
      context.state = true;
      runMode(cm, line.text, overlay.mode, context, function (end, style) {
        var start = i;
        // Ensure there's a token end at the current position, and that i points at it
        while (at < end) {
          var i_end = st[i];
          if (i_end > end)
            { st.splice(i, 1, end, st[i+1], i_end); }
          i += 2;
          at = Math.min(end, i_end);
        }
        if (!style) { return }
        if (overlay.opaque) {
          st.splice(start, i - start, end, "overlay " + style);
          i = start + 2;
        } else {
          for (; start < i; start += 2) {
            var cur = st[start+1];
            st[start+1] = (cur ? cur + " " : "") + "overlay " + style;
          }
        }
      }, lineClasses);
      context.state = state;
      context.baseTokens = null;
      context.baseTokenPos = 1;
    }
```
</details>

### `getLineStyles(cm: any, line: any, updateFrontier: any): any`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`
- **`updateFrontier`** `any`

**Returns:** `any`

**Calls:**

- `getContextBefore`
- `lineNo`
- `copyState`
- `highlightLine`
- `context.save`
- `Math.max`

<details><summary>Code</summary>

```typescript
function getLineStyles(cm, line, updateFrontier) {
    if (!line.styles || line.styles[0] != cm.state.modeGen) {
      var context = getContextBefore(cm, lineNo(line));
      var resetState = line.text.length > cm.options.maxHighlightLength && copyState(cm.doc.mode, context.state);
      var result = highlightLine(cm, line, context);
      if (resetState) { context.state = resetState; }
      line.stateAfter = context.save(!resetState);
      line.styles = result.styles;
      if (result.classes) { line.styleClasses = result.classes; }
      else if (line.styleClasses) { line.styleClasses = null; }
      if (updateFrontier === cm.doc.highlightFrontier)
        { cm.doc.modeFrontier = Math.max(cm.doc.modeFrontier, ++cm.doc.highlightFrontier); }
    }
    return line.styles
  }
```
</details>

### `getContextBefore(cm: any, n: any, precise: any): Context`

**Parameters:**

- **`cm`** `any`
- **`n`** `any`
- **`precise`** `any`

**Returns:** `Context`

**Calls:**

- `findStartLine`
- `getLine`
- `Context.fromSaved`
- `startState`
- `doc.iter`
- `processLine`
- `context.save`
- `context.nextLine`

<details><summary>Code</summary>

```typescript
function getContextBefore(cm, n, precise) {
    var doc = cm.doc, display = cm.display;
    if (!doc.mode.startState) { return new Context(doc, true, n) }
    var start = findStartLine(cm, n, precise);
    var saved = start > doc.first && getLine(doc, start - 1).stateAfter;
    var context = saved ? Context.fromSaved(doc, saved, start) : new Context(doc, startState(doc.mode), start);

    doc.iter(start, n, function (line) {
      processLine(cm, line.text, context);
      var pos = context.line;
      line.stateAfter = pos == n - 1 || pos % 5 == 0 || pos >= display.viewFrom && pos < display.viewTo ? context.save() : null;
      context.nextLine();
    });
    if (precise) { doc.modeFrontier = context.line; }
    return context
  }
```
</details>

### `processLine(cm: any, text: any, context: any, startAt: any): void`

**Parameters:**

- **`cm`** `any`
- **`text`** `any`
- **`context`** `any`
- **`startAt`** `any`

**Returns:** `void`

**Calls:**

- `callBlankLine`
- `stream.eol`
- `readToken`

<details><summary>Code</summary>

```typescript
function processLine(cm, text, context, startAt) {
    var mode = cm.doc.mode;
    var stream = new StringStream(text, cm.options.tabSize, context);
    stream.start = stream.pos = startAt || 0;
    if (text == "") { callBlankLine(mode, context.state); }
    while (!stream.eol()) {
      readToken(mode, stream, context.state);
      stream.start = stream.pos;
    }
  }
```
</details>

### `callBlankLine(mode: any, state: any): any`

**Parameters:**

- **`mode`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `mode.blankLine`
- `innerMode`
- `inner.mode.blankLine`

<details><summary>Code</summary>

```typescript
function callBlankLine(mode, state) {
    if (mode.blankLine) { return mode.blankLine(state) }
    if (!mode.innerMode) { return }
    var inner = innerMode(mode, state);
    if (inner.mode.blankLine) { return inner.mode.blankLine(inner.state) }
  }
```
</details>

### `readToken(mode: any, stream: any, state: any, inner: any): any`

**Parameters:**

- **`mode`** `any`
- **`stream`** `any`
- **`state`** `any`
- **`inner`** `any`

**Returns:** `any`

**Calls:**

- `innerMode`
- `mode.token`

<details><summary>Code</summary>

```typescript
function readToken(mode, stream, state, inner) {
    for (var i = 0; i < 10; i++) {
      if (inner) { inner[0] = innerMode(mode, state).mode; }
      var style = mode.token(stream, state);
      if (stream.pos > stream.start) { return style }
    }
    throw new Error("Mode " + mode.name + " failed to advance stream.")
  }
```
</details>

### `Token(stream: any, type: any, state: any): void`

**Parameters:**

- **`stream`** `any`
- **`type`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stream.current`

<details><summary>Code</summary>

```typescript
function(stream, type, state) {
    this.start = stream.start; this.end = stream.pos;
    this.string = stream.current();
    this.type = type || null;
    this.state = state;
  }
```
</details>

### `takeToken(cm: any, pos: any, precise: any, asArray: any): any[] | Token`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`precise`** `any`
- **`asArray`** `any`

**Returns:** `any[] | Token`

**Calls:**

- `clipPos`
- `getLine`
- `getContextBefore`
- `stream.eol`
- `readToken`
- `tokens.push`
- `copyState`

<details><summary>Code</summary>

```typescript
function takeToken(cm, pos, precise, asArray) {
    var doc = cm.doc, mode = doc.mode, style;
    pos = clipPos(doc, pos);
    var line = getLine(doc, pos.line), context = getContextBefore(cm, pos.line, precise);
    var stream = new StringStream(line.text, cm.options.tabSize, context), tokens;
    if (asArray) { tokens = []; }
    while ((asArray || stream.pos < pos.ch) && !stream.eol()) {
      stream.start = stream.pos;
      style = readToken(mode, stream, context.state);
      if (asArray) { tokens.push(new Token(stream, style, copyState(doc.mode, context.state))); }
    }
    return asArray ? tokens : new Token(stream, style, context.state)
  }
```
</details>

### `extractLineClasses(type: any, output: any): any`

**Parameters:**

- **`type`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `type.match`
- `type.slice`
- `(new RegExp("(?:^|\\s)" + lineClass[2] + "(?:$|\\s)")).test`

<details><summary>Code</summary>

```typescript
function extractLineClasses(type, output) {
    if (type) { for (;;) {
      var lineClass = type.match(/(?:^|\s+)line-(background-)?(\S+)/);
      if (!lineClass) { break }
      type = type.slice(0, lineClass.index) + type.slice(lineClass.index + lineClass[0].length);
      var prop = lineClass[1] ? "bgClass" : "textClass";
      if (output[prop] == null)
        { output[prop] = lineClass[2]; }
      else if (!(new RegExp("(?:^|\\s)" + lineClass[2] + "(?:$|\\s)")).test(output[prop]))
        { output[prop] += " " + lineClass[2]; }
    } }
    return type
  }
```
</details>

### `runMode(cm: any, text: any, mode: any, context: any, f: any, lineClasses: any, forceToEnd: any): void`

**Parameters:**

- **`cm`** `any`
- **`text`** `any`
- **`mode`** `any`
- **`context`** `any`
- **`f`** `any`
- **`lineClasses`** `any`
- **`forceToEnd`** `any`

**Returns:** `void`

**Calls:**

- `extractLineClasses`
- `callBlankLine`
- `stream.eol`
- `processLine`
- `readToken`
- `Math.min`
- `f`

**Internal Comments:**
```
// Webkit seems to refuse to render text nodes longer than 57444 (x2)
// characters, and returns inaccurate measurements in nodes (x2)
// starting around 5000 chars. (x2)
```

<details><summary>Code</summary>

```typescript
function runMode(cm, text, mode, context, f, lineClasses, forceToEnd) {
    var flattenSpans = mode.flattenSpans;
    if (flattenSpans == null) { flattenSpans = cm.options.flattenSpans; }
    var curStart = 0, curStyle = null;
    var stream = new StringStream(text, cm.options.tabSize, context), style;
    var inner = cm.options.addModeClass && [null];
    if (text == "") { extractLineClasses(callBlankLine(mode, context.state), lineClasses); }
    while (!stream.eol()) {
      if (stream.pos > cm.options.maxHighlightLength) {
        flattenSpans = false;
        if (forceToEnd) { processLine(cm, text, context, stream.pos); }
        stream.pos = text.length;
        style = null;
      } else {
        style = extractLineClasses(readToken(mode, stream, context.state, inner), lineClasses);
      }
      if (inner) {
        var mName = inner[0].name;
        if (mName) { style = "m-" + (style ? mName + " " + style : mName); }
      }
      if (!flattenSpans || curStyle != style) {
        while (curStart < stream.start) {
          curStart = Math.min(stream.start, curStart + 5000);
          f(curStart, curStyle);
        }
        curStyle = style;
      }
      stream.start = stream.pos;
    }
    while (curStart < stream.pos) {
      // Webkit seems to refuse to render text nodes longer than 57444
      // characters, and returns inaccurate measurements in nodes
      // starting around 5000 chars.
      var pos = Math.min(stream.pos, curStart + 5000);
      f(pos, curStyle);
      curStart = pos;
    }
  }
```
</details>

### `findStartLine(cm: any, n: any, precise: any): any`

**Parameters:**

- **`cm`** `any`
- **`n`** `any`
- **`precise`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `countColumn`

<details><summary>Code</summary>

```typescript
function findStartLine(cm, n, precise) {
    var minindent, minline, doc = cm.doc;
    var lim = precise ? -1 : n - (cm.doc.mode.innerMode ? 1000 : 100);
    for (var search = n; search > lim; --search) {
      if (search <= doc.first) { return doc.first }
      var line = getLine(doc, search - 1), after = line.stateAfter;
      if (after && (!precise || search + (after instanceof SavedContext ? after.lookAhead : 0) <= doc.modeFrontier))
        { return search }
      var indented = countColumn(line.text, null, cm.options.tabSize);
      if (minline == null || minindent > indented) {
        minline = search - 1;
        minindent = indented;
      }
    }
    return minline
  }
```
</details>

### `retreatFrontier(doc: any, n: any): void`

**Parameters:**

- **`doc`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `getLine`

**Internal Comments:**
```
// change is on 3
// state on line 1 looked ahead 2 -- so saw 3
// test 1 + 2 < 3 should cover this
```

<details><summary>Code</summary>

```typescript
function retreatFrontier(doc, n) {
    doc.modeFrontier = Math.min(doc.modeFrontier, n);
    if (doc.highlightFrontier < n - 10) { return }
    var start = doc.first;
    for (var line = n - 1; line > start; line--) {
      var saved = getLine(doc, line).stateAfter;
      // change is on 3
      // state on line 1 looked ahead 2 -- so saw 3
      // test 1 + 2 < 3 should cover this
      if (saved && (!(saved instanceof SavedContext) || line + saved.lookAhead < n)) {
        start = line + 1;
        break
      }
    }
    doc.highlightFrontier = Math.min(doc.highlightFrontier, start);
  }
```
</details>

### `seeReadOnlySpans(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function seeReadOnlySpans() {
    sawReadOnlySpans = true;
  }
```
</details>

### `seeCollapsedSpans(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function seeCollapsedSpans() {
    sawCollapsedSpans = true;
  }
```
</details>

### `MarkedSpan(marker: any, from: any, to: any): void`

**Parameters:**

- **`marker`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function MarkedSpan(marker, from, to) {
    this.marker = marker;
    this.from = from; this.to = to;
  }
```
</details>

### `getMarkedSpanFor(spans: any, marker: any): any`

**Parameters:**

- **`spans`** `any`
- **`marker`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getMarkedSpanFor(spans, marker) {
    if (spans) { for (var i = 0; i < spans.length; ++i) {
      var span = spans[i];
      if (span.marker == marker) { return span }
    } }
  }
```
</details>

### `removeMarkedSpan(spans: any, span: any): any[]`

**Parameters:**

- **`spans`** `any`
- **`span`** `any`

**Returns:** `any[]`

**Calls:**

- `(r || (r = [])).push`

<details><summary>Code</summary>

```typescript
function removeMarkedSpan(spans, span) {
    var r;
    for (var i = 0; i < spans.length; ++i)
      { if (spans[i] != span) { (r || (r = [])).push(spans[i]); } }
    return r
  }
```
</details>

### `addMarkedSpan(line: any, span: any, op: any): void`

**Parameters:**

- **`line`** `any`
- **`span`** `any`
- **`op`** `any`

**Returns:** `void`

**Calls:**

- `inThisOp.has`
- `line.markedSpans.push`
- `line.markedSpans.concat`
- `inThisOp.add`
- `span.marker.attachLine`

<details><summary>Code</summary>

```typescript
function addMarkedSpan(line, span, op) {
    var inThisOp = op && window.WeakSet && (op.markedSpans || (op.markedSpans = new WeakSet));
    if (inThisOp && inThisOp.has(line.markedSpans)) {
      line.markedSpans.push(span);
    } else {
      line.markedSpans = line.markedSpans ? line.markedSpans.concat([span]) : [span];
      if (inThisOp) { inThisOp.add(line.markedSpans); }
    }
    span.marker.attachLine(line);
  }
```
</details>

### `markedSpansBefore(old: any, startCh: any, isInsert: any): any[]`

**Parameters:**

- **`old`** `any`
- **`startCh`** `any`
- **`isInsert`** `any`

**Returns:** `any[]`

**Calls:**

- `(nw || (nw = [])).push`

<details><summary>Code</summary>

```typescript
function markedSpansBefore(old, startCh, isInsert) {
    var nw;
    if (old) { for (var i = 0; i < old.length; ++i) {
      var span = old[i], marker = span.marker;
      var startsBefore = span.from == null || (marker.inclusiveLeft ? span.from <= startCh : span.from < startCh);
      if (startsBefore || span.from == startCh && marker.type == "bookmark" && (!isInsert || !span.marker.insertLeft)) {
        var endsAfter = span.to == null || (marker.inclusiveRight ? span.to >= startCh : span.to > startCh)
        ;(nw || (nw = [])).push(new MarkedSpan(marker, span.from, endsAfter ? null : span.to));
      }
    } }
    return nw
  }
```
</details>

### `markedSpansAfter(old: any, endCh: any, isInsert: any): any[]`

**Parameters:**

- **`old`** `any`
- **`endCh`** `any`
- **`isInsert`** `any`

**Returns:** `any[]`

**Calls:**

- `(nw || (nw = [])).push`

<details><summary>Code</summary>

```typescript
function markedSpansAfter(old, endCh, isInsert) {
    var nw;
    if (old) { for (var i = 0; i < old.length; ++i) {
      var span = old[i], marker = span.marker;
      var endsAfter = span.to == null || (marker.inclusiveRight ? span.to >= endCh : span.to > endCh);
      if (endsAfter || span.from == endCh && marker.type == "bookmark" && (!isInsert || span.marker.insertLeft)) {
        var startsBefore = span.from == null || (marker.inclusiveLeft ? span.from <= endCh : span.from < endCh)
        ;(nw || (nw = [])).push(new MarkedSpan(marker, startsBefore ? null : span.from - endCh,
                                              span.to == null ? null : span.to - endCh));
      }
    } }
    return nw
  }
```
</details>

### `stretchSpansOverChange(doc: any, change: any): any[][]`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`

**Returns:** `any[][]`

**Calls:**

- `isLine`
- `getLine`
- `cmp`
- `markedSpansBefore`
- `markedSpansAfter`
- `lst`
- `getMarkedSpanFor`
- `(first || (first = [])).push`
- `clearEmptySpans`
- `(gapMarkers || (gapMarkers = [])).push`
- `newMarkers.push`

**Internal Comments:**
```
// Get the spans that 'stick out' on both sides (x2)
// Next, merge those two ends (x2)
// Fix up .to properties of first
// Fix up .from in last (or move them into first in case of sameLine)
// Make sure we didn't create any zero-length spans
// Fill gap with whole-line-spans (x2)
```

<details><summary>Code</summary>

```typescript
function stretchSpansOverChange(doc, change) {
    if (change.full) { return null }
    var oldFirst = isLine(doc, change.from.line) && getLine(doc, change.from.line).markedSpans;
    var oldLast = isLine(doc, change.to.line) && getLine(doc, change.to.line).markedSpans;
    if (!oldFirst && !oldLast) { return null }

    var startCh = change.from.ch, endCh = change.to.ch, isInsert = cmp(change.from, change.to) == 0;
    // Get the spans that 'stick out' on both sides
    var first = markedSpansBefore(oldFirst, startCh, isInsert);
    var last = markedSpansAfter(oldLast, endCh, isInsert);

    // Next, merge those two ends
    var sameLine = change.text.length == 1, offset = lst(change.text).length + (sameLine ? startCh : 0);
    if (first) {
      // Fix up .to properties of first
      for (var i = 0; i < first.length; ++i) {
        var span = first[i];
        if (span.to == null) {
          var found = getMarkedSpanFor(last, span.marker);
          if (!found) { span.to = startCh; }
          else if (sameLine) { span.to = found.to == null ? null : found.to + offset; }
        }
      }
    }
    if (last) {
      // Fix up .from in last (or move them into first in case of sameLine)
      for (var i$1 = 0; i$1 < last.length; ++i$1) {
        var span$1 = last[i$1];
        if (span$1.to != null) { span$1.to += offset; }
        if (span$1.from == null) {
          var found$1 = getMarkedSpanFor(first, span$1.marker);
          if (!found$1) {
            span$1.from = offset;
            if (sameLine) { (first || (first = [])).push(span$1); }
          }
        } else {
          span$1.from += offset;
          if (sameLine) { (first || (first = [])).push(span$1); }
        }
      }
    }
    // Make sure we didn't create any zero-length spans
    if (first) { first = clearEmptySpans(first); }
    if (last && last != first) { last = clearEmptySpans(last); }

    var newMarkers = [first];
    if (!sameLine) {
      // Fill gap with whole-line-spans
      var gap = change.text.length - 2, gapMarkers;
      if (gap > 0 && first)
        { for (var i$2 = 0; i$2 < first.length; ++i$2)
          { if (first[i$2].to == null)
            { (gapMarkers || (gapMarkers = [])).push(new MarkedSpan(first[i$2].marker, null, null)); } } }
      for (var i$3 = 0; i$3 < gap; ++i$3)
        { newMarkers.push(gapMarkers); }
      newMarkers.push(last);
    }
    return newMarkers
  }
```
</details>

### `clearEmptySpans(spans: any): any`

**Parameters:**

- **`spans`** `any`

**Returns:** `any`

**Calls:**

- `spans.splice`

<details><summary>Code</summary>

```typescript
function clearEmptySpans(spans) {
    for (var i = 0; i < spans.length; ++i) {
      var span = spans[i];
      if (span.from != null && span.from == span.to && span.marker.clearWhenEmpty !== false)
        { spans.splice(i--, 1); }
    }
    if (!spans.length) { return null }
    return spans
  }
```
</details>

### `removeReadOnlyRanges(doc: any, from: any, to: any): { from: any; to: any; }[]`

**Parameters:**

- **`doc`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `{ from: any; to: any; }[]`

**Calls:**

- `doc.iter`
- `indexOf`
- `(markers || (markers = [])).push`
- `mk.find`
- `cmp`
- `newParts.push`
- `parts.splice.apply`

<details><summary>Code</summary>

```typescript
function removeReadOnlyRanges(doc, from, to) {
    var markers = null;
    doc.iter(from.line, to.line + 1, function (line) {
      if (line.markedSpans) { for (var i = 0; i < line.markedSpans.length; ++i) {
        var mark = line.markedSpans[i].marker;
        if (mark.readOnly && (!markers || indexOf(markers, mark) == -1))
          { (markers || (markers = [])).push(mark); }
      } }
    });
    if (!markers) { return null }
    var parts = [{from: from, to: to}];
    for (var i = 0; i < markers.length; ++i) {
      var mk = markers[i], m = mk.find(0);
      for (var j = 0; j < parts.length; ++j) {
        var p = parts[j];
        if (cmp(p.to, m.from) < 0 || cmp(p.from, m.to) > 0) { continue }
        var newParts = [j, 1], dfrom = cmp(p.from, m.from), dto = cmp(p.to, m.to);
        if (dfrom < 0 || !mk.inclusiveLeft && !dfrom)
          { newParts.push({from: p.from, to: m.from}); }
        if (dto > 0 || !mk.inclusiveRight && !dto)
          { newParts.push({from: m.to, to: p.to}); }
        parts.splice.apply(parts, newParts);
        j += newParts.length - 3;
      }
    }
    return parts
  }
```
</details>

### `detachMarkedSpans(line: any): void`

**Parameters:**

- **`line`** `any`

**Returns:** `void`

**Calls:**

- `spans[i].marker.detachLine`

<details><summary>Code</summary>

```typescript
function detachMarkedSpans(line) {
    var spans = line.markedSpans;
    if (!spans) { return }
    for (var i = 0; i < spans.length; ++i)
      { spans[i].marker.detachLine(line); }
    line.markedSpans = null;
  }
```
</details>

### `attachMarkedSpans(line: any, spans: any): void`

**Parameters:**

- **`line`** `any`
- **`spans`** `any`

**Returns:** `void`

**Calls:**

- `spans[i].marker.attachLine`

<details><summary>Code</summary>

```typescript
function attachMarkedSpans(line, spans) {
    if (!spans) { return }
    for (var i = 0; i < spans.length; ++i)
      { spans[i].marker.attachLine(line); }
    line.markedSpans = spans;
  }
```
</details>

### `extraLeft(marker: any): 0 | -1`

**Parameters:**

- **`marker`** `any`

**Returns:** `0 | -1`

<details><summary>Code</summary>

```typescript
function extraLeft(marker) { return marker.inclusiveLeft ? -1 : 0 }
```
</details>

### `extraRight(marker: any): 1 | 0`

**Parameters:**

- **`marker`** `any`

**Returns:** `1 | 0`

<details><summary>Code</summary>

```typescript
function extraRight(marker) { return marker.inclusiveRight ? 1 : 0 }
```
</details>

### `compareCollapsedMarkers(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

**Calls:**

- `a.find`
- `b.find`
- `cmp`
- `extraLeft`
- `extraRight`

<details><summary>Code</summary>

```typescript
function compareCollapsedMarkers(a, b) {
    var lenDiff = a.lines.length - b.lines.length;
    if (lenDiff != 0) { return lenDiff }
    var aPos = a.find(), bPos = b.find();
    var fromCmp = cmp(aPos.from, bPos.from) || extraLeft(a) - extraLeft(b);
    if (fromCmp) { return -fromCmp }
    var toCmp = cmp(aPos.to, bPos.to) || extraRight(a) - extraRight(b);
    if (toCmp) { return toCmp }
    return b.id - a.id
  }
```
</details>

### `collapsedSpanAtSide(line: any, start: any): any`

**Parameters:**

- **`line`** `any`
- **`start`** `any`

**Returns:** `any`

**Calls:**

- `compareCollapsedMarkers`

<details><summary>Code</summary>

```typescript
function collapsedSpanAtSide(line, start) {
    var sps = sawCollapsedSpans && line.markedSpans, found;
    if (sps) { for (var sp = (void 0), i = 0; i < sps.length; ++i) {
      sp = sps[i];
      if (sp.marker.collapsed && (start ? sp.from : sp.to) == null &&
          (!found || compareCollapsedMarkers(found, sp.marker) < 0))
        { found = sp.marker; }
    } }
    return found
  }
```
</details>

### `collapsedSpanAtStart(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `collapsedSpanAtSide`

<details><summary>Code</summary>

```typescript
function collapsedSpanAtStart(line) { return collapsedSpanAtSide(line, true) }
```
</details>

### `collapsedSpanAtEnd(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `collapsedSpanAtSide`

<details><summary>Code</summary>

```typescript
function collapsedSpanAtEnd(line) { return collapsedSpanAtSide(line, false) }
```
</details>

### `collapsedSpanAround(line: any, ch: any): any`

**Parameters:**

- **`line`** `any`
- **`ch`** `any`

**Returns:** `any`

**Calls:**

- `compareCollapsedMarkers`

<details><summary>Code</summary>

```typescript
function collapsedSpanAround(line, ch) {
    var sps = sawCollapsedSpans && line.markedSpans, found;
    if (sps) { for (var i = 0; i < sps.length; ++i) {
      var sp = sps[i];
      if (sp.marker.collapsed && (sp.from == null || sp.from < ch) && (sp.to == null || sp.to > ch) &&
          (!found || compareCollapsedMarkers(found, sp.marker) < 0)) { found = sp.marker; }
    } }
    return found
  }
```
</details>

### `conflictingCollapsedRange(doc: any, lineNo: any, from: any, to: any, marker: any): boolean`

**Parameters:**

- **`doc`** `any`
- **`lineNo`** `any`
- **`from`** `any`
- **`to`** `any`
- **`marker`** `any`

**Returns:** `boolean`

**Calls:**

- `getLine`
- `sp.marker.find`
- `cmp`
- `extraLeft`
- `extraRight`

<details><summary>Code</summary>

```typescript
function conflictingCollapsedRange(doc, lineNo, from, to, marker) {
    var line = getLine(doc, lineNo);
    var sps = sawCollapsedSpans && line.markedSpans;
    if (sps) { for (var i = 0; i < sps.length; ++i) {
      var sp = sps[i];
      if (!sp.marker.collapsed) { continue }
      var found = sp.marker.find(0);
      var fromCmp = cmp(found.from, from) || extraLeft(sp.marker) - extraLeft(marker);
      var toCmp = cmp(found.to, to) || extraRight(sp.marker) - extraRight(marker);
      if (fromCmp >= 0 && toCmp <= 0 || fromCmp <= 0 && toCmp >= 0) { continue }
      if (fromCmp <= 0 && (sp.marker.inclusiveRight && marker.inclusiveLeft ? cmp(found.to, from) >= 0 : cmp(found.to, from) > 0) ||
          fromCmp >= 0 && (sp.marker.inclusiveRight && marker.inclusiveLeft ? cmp(found.from, to) <= 0 : cmp(found.from, to) < 0))
        { return true }
    } }
  }
```
</details>

### `visualLine(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `collapsedSpanAtStart`
- `merged.find`

<details><summary>Code</summary>

```typescript
function visualLine(line) {
    var merged;
    while (merged = collapsedSpanAtStart(line))
      { line = merged.find(-1, true).line; }
    return line
  }
```
</details>

### `visualLineEnd(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `collapsedSpanAtEnd`
- `merged.find`

<details><summary>Code</summary>

```typescript
function visualLineEnd(line) {
    var merged;
    while (merged = collapsedSpanAtEnd(line))
      { line = merged.find(1, true).line; }
    return line
  }
```
</details>

### `visualLineContinued(line: any): any[]`

**Parameters:**

- **`line`** `any`

**Returns:** `any[]`

**Calls:**

- `collapsedSpanAtEnd`
- `merged.find`
- `(lines || (lines = [])).push`

<details><summary>Code</summary>

```typescript
function visualLineContinued(line) {
    var merged, lines;
    while (merged = collapsedSpanAtEnd(line)) {
      line = merged.find(1, true).line
      ;(lines || (lines = [])).push(line);
    }
    return lines
  }
```
</details>

### `visualLineNo(doc: any, lineN: any): any`

**Parameters:**

- **`doc`** `any`
- **`lineN`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `visualLine`
- `lineNo`

<details><summary>Code</summary>

```typescript
function visualLineNo(doc, lineN) {
    var line = getLine(doc, lineN), vis = visualLine(line);
    if (line == vis) { return lineN }
    return lineNo(vis)
  }
```
</details>

### `visualLineEndNo(doc: any, lineN: any): any`

**Parameters:**

- **`doc`** `any`
- **`lineN`** `any`

**Returns:** `any`

**Calls:**

- `doc.lastLine`
- `getLine`
- `lineIsHidden`
- `collapsedSpanAtEnd`
- `merged.find`
- `lineNo`

<details><summary>Code</summary>

```typescript
function visualLineEndNo(doc, lineN) {
    if (lineN > doc.lastLine()) { return lineN }
    var line = getLine(doc, lineN), merged;
    if (!lineIsHidden(doc, line)) { return lineN }
    while (merged = collapsedSpanAtEnd(line))
      { line = merged.find(1, true).line; }
    return lineNo(line) + 1
  }
```
</details>

### `lineIsHidden(doc: any, line: any): boolean`

**Parameters:**

- **`doc`** `any`
- **`line`** `any`

**Returns:** `boolean`

**Calls:**

- `lineIsHiddenInner`

<details><summary>Code</summary>

```typescript
function lineIsHidden(doc, line) {
    var sps = sawCollapsedSpans && line.markedSpans;
    if (sps) { for (var sp = (void 0), i = 0; i < sps.length; ++i) {
      sp = sps[i];
      if (!sp.marker.collapsed) { continue }
      if (sp.from == null) { return true }
      if (sp.marker.widgetNode) { continue }
      if (sp.from == 0 && sp.marker.inclusiveLeft && lineIsHiddenInner(doc, line, sp))
        { return true }
    } }
  }
```
</details>

### `lineIsHiddenInner(doc: any, line: any, span: any): boolean`

**Parameters:**

- **`doc`** `any`
- **`line`** `any`
- **`span`** `any`

**Returns:** `boolean`

**Calls:**

- `span.marker.find`
- `lineIsHiddenInner`
- `getMarkedSpanFor`

<details><summary>Code</summary>

```typescript
function lineIsHiddenInner(doc, line, span) {
    if (span.to == null) {
      var end = span.marker.find(1, true);
      return lineIsHiddenInner(doc, end.line, getMarkedSpanFor(end.line.markedSpans, span.marker))
    }
    if (span.marker.inclusiveRight && span.to == line.text.length)
      { return true }
    for (var sp = (void 0), i = 0; i < line.markedSpans.length; ++i) {
      sp = line.markedSpans[i];
      if (sp.marker.collapsed && !sp.marker.widgetNode && sp.from == span.to &&
          (sp.to == null || sp.to != span.from) &&
          (sp.marker.inclusiveLeft || span.marker.inclusiveRight) &&
          lineIsHiddenInner(doc, line, sp)) { return true }
    }
  }
```
</details>

### `heightAtLine(lineObj: any): number`

**Parameters:**

- **`lineObj`** `any`

**Returns:** `number`

**Calls:**

- `visualLine`

<details><summary>Code</summary>

```typescript
function heightAtLine(lineObj) {
    lineObj = visualLine(lineObj);

    var h = 0, chunk = lineObj.parent;
    for (var i = 0; i < chunk.lines.length; ++i) {
      var line = chunk.lines[i];
      if (line == lineObj) { break }
      else { h += line.height; }
    }
    for (var p = chunk.parent; p; chunk = p, p = chunk.parent) {
      for (var i$1 = 0; i$1 < p.children.length; ++i$1) {
        var cur = p.children[i$1];
        if (cur == chunk) { break }
        else { h += cur.height; }
      }
    }
    return h
  }
```
</details>

### `lineLength(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `collapsedSpanAtStart`
- `merged.find`
- `collapsedSpanAtEnd`

<details><summary>Code</summary>

```typescript
function lineLength(line) {
    if (line.height == 0) { return 0 }
    var len = line.text.length, merged, cur = line;
    while (merged = collapsedSpanAtStart(cur)) {
      var found = merged.find(0, true);
      cur = found.from.line;
      len += found.from.ch - found.to.ch;
    }
    cur = line;
    while (merged = collapsedSpanAtEnd(cur)) {
      var found$1 = merged.find(0, true);
      len -= cur.text.length - found$1.from.ch;
      cur = found$1.to.line;
      len += cur.text.length - found$1.to.ch;
    }
    return len
  }
```
</details>

### `findMaxLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `getLine`
- `lineLength`
- `doc.iter`

<details><summary>Code</summary>

```typescript
function findMaxLine(cm) {
    var d = cm.display, doc = cm.doc;
    d.maxLine = getLine(doc, doc.first);
    d.maxLineLength = lineLength(d.maxLine);
    d.maxLineChanged = true;
    doc.iter(function (line) {
      var len = lineLength(line);
      if (len > d.maxLineLength) {
        d.maxLineLength = len;
        d.maxLine = line;
      }
    });
  }
```
</details>

### `Line(text: any, markedSpans: any, estimateHeight: any): void`

**Parameters:**

- **`text`** `any`
- **`markedSpans`** `any`
- **`estimateHeight`** `any`

**Returns:** `void`

**Calls:**

- `attachMarkedSpans`
- `estimateHeight`

<details><summary>Code</summary>

```typescript
function(text, markedSpans, estimateHeight) {
    this.text = text;
    attachMarkedSpans(this, markedSpans);
    this.height = estimateHeight ? estimateHeight(this) : 1;
  }
```
</details>

### `updateLine(line: any, text: any, markedSpans: any, estimateHeight: any): void`

**Parameters:**

- **`line`** `any`
- **`text`** `any`
- **`markedSpans`** `any`
- **`estimateHeight`** `any`

**Returns:** `void`

**Calls:**

- `detachMarkedSpans`
- `attachMarkedSpans`
- `estimateHeight`
- `updateLineHeight`

<details><summary>Code</summary>

```typescript
function updateLine(line, text, markedSpans, estimateHeight) {
    line.text = text;
    if (line.stateAfter) { line.stateAfter = null; }
    if (line.styles) { line.styles = null; }
    if (line.order != null) { line.order = null; }
    detachMarkedSpans(line);
    attachMarkedSpans(line, markedSpans);
    var estHeight = estimateHeight ? estimateHeight(line) : 1;
    if (estHeight != line.height) { updateLineHeight(line, estHeight); }
  }
```
</details>

### `cleanUpLine(line: any): void`

**Parameters:**

- **`line`** `any`

**Returns:** `void`

**Calls:**

- `detachMarkedSpans`

<details><summary>Code</summary>

```typescript
function cleanUpLine(line) {
    line.parent = null;
    detachMarkedSpans(line);
  }
```
</details>

### `interpretTokenStyle(style: any, options: any): any`

**Parameters:**

- **`style`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `/^\s*$/.test`
- `style.replace`

<details><summary>Code</summary>

```typescript
function interpretTokenStyle(style, options) {
    if (!style || /^\s*$/.test(style)) { return null }
    var cache = options.addModeClass ? styleToClassCacheWithMode : styleToClassCache;
    return cache[style] ||
      (cache[style] = style.replace(/\S+/g, "cm-$&"))
  }
```
</details>

### `buildLineContent(cm: any, lineView: any): { pre: any; content: any; col: number; pos: number; cm: any; trailingSpace: boolean; splitSpaces: any; }`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`

**Returns:** `{ pre: any; content: any; col: number; pos: number; cm: any; trailingSpace: boolean; splitSpaces: any; }`

**Calls:**

- `eltP`
- `cm.getOption`
- `hasBadBidiRects`
- `getOrder`
- `buildTokenBadBidi`
- `lineNo`
- `insertLineContent`
- `getLineStyles`
- `joinClasses`
- `builder.map.push`
- `builder.content.appendChild`
- `zeroWidthElement`
- `(lineView.measure.maps || (lineView.measure.maps = [])).push`
- `(lineView.measure.caches || (lineView.measure.caches = [])).push`
- `/\bcm-tab\b/.test`
- `last.querySelector`
- `signal`

**Internal Comments:**
```
// The padding-right forces the element to have a 'border', which (x2)
// is needed on Webkit to be able to get line-level bounding (x2)
// rectangles for it (in measureChar). (x2)
// Iterate over the logical lines that make up this visual line.
// Optionally wire in some hacks into the token-rendering
// algorithm, to deal with browser quirks.
// Ensure at least a single node is present, for measuring.
// Store the map and a cache object for the current logical line
// See issue #2901
```

<details><summary>Code</summary>

```typescript
function buildLineContent(cm, lineView) {
    // The padding-right forces the element to have a 'border', which
    // is needed on Webkit to be able to get line-level bounding
    // rectangles for it (in measureChar).
    var content = eltP("span", null, null, webkit ? "padding-right: .1px" : null);
    var builder = {pre: eltP("pre", [content], "CodeMirror-line"), content: content,
                   col: 0, pos: 0, cm: cm,
                   trailingSpace: false,
                   splitSpaces: cm.getOption("lineWrapping")};
    lineView.measure = {};

    // Iterate over the logical lines that make up this visual line.
    for (var i = 0; i <= (lineView.rest ? lineView.rest.length : 0); i++) {
      var line = i ? lineView.rest[i - 1] : lineView.line, order = (void 0);
      builder.pos = 0;
      builder.addToken = buildToken;
      // Optionally wire in some hacks into the token-rendering
      // algorithm, to deal with browser quirks.
      if (hasBadBidiRects(cm.display.measure) && (order = getOrder(line, cm.doc.direction)))
        { builder.addToken = buildTokenBadBidi(builder.addToken, order); }
      builder.map = [];
      var allowFrontierUpdate = lineView != cm.display.externalMeasured && lineNo(line);
      insertLineContent(line, builder, getLineStyles(cm, line, allowFrontierUpdate));
      if (line.styleClasses) {
        if (line.styleClasses.bgClass)
          { builder.bgClass = joinClasses(line.styleClasses.bgClass, builder.bgClass || ""); }
        if (line.styleClasses.textClass)
          { builder.textClass = joinClasses(line.styleClasses.textClass, builder.textClass || ""); }
      }

      // Ensure at least a single node is present, for measuring.
      if (builder.map.length == 0)
        { builder.map.push(0, 0, builder.content.appendChild(zeroWidthElement(cm.display.measure))); }

      // Store the map and a cache object for the current logical line
      if (i == 0) {
        lineView.measure.map = builder.map;
        lineView.measure.cache = {};
      } else {
  (lineView.measure.maps || (lineView.measure.maps = [])).push(builder.map)
        ;(lineView.measure.caches || (lineView.measure.caches = [])).push({});
      }
    }

    // See issue #2901
    if (webkit) {
      var last = builder.content.lastChild;
      if (/\bcm-tab\b/.test(last.className) || (last.querySelector && last.querySelector(".cm-tab")))
        { builder.content.className = "cm-tab-wrap-hack"; }
    }

    signal(cm, "renderLine", cm, lineView.line, builder.pre);
    if (builder.pre.className)
      { builder.textClass = joinClasses(builder.pre.className, builder.textClass || ""); }

    return builder
  }
```
</details>

### `defaultSpecialCharPlaceholder(ch: any): any`

**Parameters:**

- **`ch`** `any`

**Returns:** `any`

**Calls:**

- `elt`
- `ch.charCodeAt(0).toString`
- `token.setAttribute`

<details><summary>Code</summary>

```typescript
function defaultSpecialCharPlaceholder(ch) {
    var token = elt("span", "\u2022", "cm-invalidchar");
    token.title = "\\u" + ch.charCodeAt(0).toString(16);
    token.setAttribute("aria-label", token.title);
    return token
  }
```
</details>

### `buildToken(builder: any, text: any, style: any, startStyle: any, endStyle: any, css: any, attributes: any): any`

**Parameters:**

- **`builder`** `any`
- **`text`** `any`
- **`style`** `any`
- **`startStyle`** `any`
- **`endStyle`** `any`
- **`css`** `any`
- **`attributes`** `any`

**Returns:** `any`

**Calls:**

- `splitSpaces`
- `special.test`
- `document.createTextNode`
- `builder.map.push`
- `document.createDocumentFragment`
- `special.exec`
- `displayText.slice`
- `content.appendChild`
- `elt`
- `spaceStr`
- `txt$1.setAttribute`
- `builder.cm.options.specialCharPlaceholder`
- `displayText.charCodeAt`
- `attributes.hasOwnProperty`
- `token.setAttribute`
- `builder.content.appendChild`

<details><summary>Code</summary>

```typescript
function buildToken(builder, text, style, startStyle, endStyle, css, attributes) {
    if (!text) { return }
    var displayText = builder.splitSpaces ? splitSpaces(text, builder.trailingSpace) : text;
    var special = builder.cm.state.specialChars, mustWrap = false;
    var content;
    if (!special.test(text)) {
      builder.col += text.length;
      content = document.createTextNode(displayText);
      builder.map.push(builder.pos, builder.pos + text.length, content);
      if (ie && ie_version < 9) { mustWrap = true; }
      builder.pos += text.length;
    } else {
      content = document.createDocumentFragment();
      var pos = 0;
      while (true) {
        special.lastIndex = pos;
        var m = special.exec(text);
        var skipped = m ? m.index - pos : text.length - pos;
        if (skipped) {
          var txt = document.createTextNode(displayText.slice(pos, pos + skipped));
          if (ie && ie_version < 9) { content.appendChild(elt("span", [txt])); }
          else { content.appendChild(txt); }
          builder.map.push(builder.pos, builder.pos + skipped, txt);
          builder.col += skipped;
          builder.pos += skipped;
        }
        if (!m) { break }
        pos += skipped + 1;
        var txt$1 = (void 0);
        if (m[0] == "\t") {
          var tabSize = builder.cm.options.tabSize, tabWidth = tabSize - builder.col % tabSize;
          txt$1 = content.appendChild(elt("span", spaceStr(tabWidth), "cm-tab"));
          txt$1.setAttribute("role", "presentation");
          txt$1.setAttribute("cm-text", "\t");
          builder.col += tabWidth;
        } else if (m[0] == "\r" || m[0] == "\n") {
          txt$1 = content.appendChild(elt("span", m[0] == "\r" ? "\u240d" : "\u2424", "cm-invalidchar"));
          txt$1.setAttribute("cm-text", m[0]);
          builder.col += 1;
        } else {
          txt$1 = builder.cm.options.specialCharPlaceholder(m[0]);
          txt$1.setAttribute("cm-text", m[0]);
          if (ie && ie_version < 9) { content.appendChild(elt("span", [txt$1])); }
          else { content.appendChild(txt$1); }
          builder.col += 1;
        }
        builder.map.push(builder.pos, builder.pos + 1, txt$1);
        builder.pos++;
      }
    }
    builder.trailingSpace = displayText.charCodeAt(text.length - 1) == 32;
    if (style || startStyle || endStyle || mustWrap || css || attributes) {
      var fullStyle = style || "";
      if (startStyle) { fullStyle += startStyle; }
      if (endStyle) { fullStyle += endStyle; }
      var token = elt("span", [content], fullStyle, css);
      if (attributes) {
        for (var attr in attributes) { if (attributes.hasOwnProperty(attr) && attr != "style" && attr != "class")
          { token.setAttribute(attr, attributes[attr]); } }
      }
      return builder.content.appendChild(token)
    }
    builder.content.appendChild(content);
  }
```
</details>

### `splitSpaces(text: any, trailingBefore: any): any`

**Parameters:**

- **`text`** `any`
- **`trailingBefore`** `any`

**Returns:** `any`

**Calls:**

- `/  /.test`
- `text.charAt`
- `text.charCodeAt`

<details><summary>Code</summary>

```typescript
function splitSpaces(text, trailingBefore) {
    if (text.length > 1 && !/  /.test(text)) { return text }
    var spaceBefore = trailingBefore, result = "";
    for (var i = 0; i < text.length; i++) {
      var ch = text.charAt(i);
      if (ch == " " && spaceBefore && (i == text.length - 1 || text.charCodeAt(i + 1) == 32))
        { ch = "\u00a0"; }
      result += ch;
      spaceBefore = ch == " ";
    }
    return result
  }
```
</details>

### `buildTokenBadBidi(inner: any, order: any): (builder: any, text: any, style: any, startStyle: any, endStyle: any, css: any, attributes: any) => any`

**Parameters:**

- **`inner`** `any`
- **`order`** `any`

**Returns:** `(builder: any, text: any, style: any, startStyle: any, endStyle: any, css: any, attributes: any) => any`

**Calls:**

- `inner`
- `text.slice`

**Internal Comments:**
```
// Find the part that overlaps with the start of this text (x2)
```

<details><summary>Code</summary>

```typescript
function buildTokenBadBidi(inner, order) {
    return function (builder, text, style, startStyle, endStyle, css, attributes) {
      style = style ? style + " cm-force-border" : "cm-force-border";
      var start = builder.pos, end = start + text.length;
      for (;;) {
        // Find the part that overlaps with the start of this text
        var part = (void 0);
        for (var i = 0; i < order.length; i++) {
          part = order[i];
          if (part.to > start && part.from <= start) { break }
        }
        if (part.to >= end) { return inner(builder, text, style, startStyle, endStyle, css, attributes) }
        inner(builder, text.slice(0, part.to - start), style, startStyle, null, css, attributes);
        startStyle = null;
        text = text.slice(part.to - start);
        start = part.to;
      }
    }
  }
```
</details>

### `buildCollapsedSpan(builder: any, size: any, marker: any, ignoreWidget: any): void`

**Parameters:**

- **`builder`** `any`
- **`size`** `any`
- **`marker`** `any`
- **`ignoreWidget`** `any`

**Returns:** `void`

**Calls:**

- `builder.map.push`
- `builder.content.appendChild`
- `document.createElement`
- `widget.setAttribute`
- `builder.cm.display.input.setUneditable`

<details><summary>Code</summary>

```typescript
function buildCollapsedSpan(builder, size, marker, ignoreWidget) {
    var widget = !ignoreWidget && marker.widgetNode;
    if (widget) { builder.map.push(builder.pos, builder.pos + size, widget); }
    if (!ignoreWidget && builder.cm.display.input.needsContentAttribute) {
      if (!widget)
        { widget = builder.content.appendChild(document.createElement("span")); }
      widget.setAttribute("cm-marker", marker.id);
    }
    if (widget) {
      builder.cm.display.input.setUneditable(widget);
      builder.content.appendChild(widget);
    }
    builder.pos += size;
    builder.trailingSpace = false;
  }
```
</details>

### `insertLineContent(line: any, builder: any, styles: any): void`

**Parameters:**

- **`line`** `any`
- **`builder`** `any`
- **`styles`** `any`

**Returns:** `void`

**Calls:**

- `builder.addToken`
- `allText.slice`
- `interpretTokenStyle`
- `foundBookmarks.push`
- `(endStyles || (endStyles = [])).push`
- `compareCollapsedMarkers`
- `buildCollapsedSpan`
- `Math.min`
- `text.slice`

**Internal Comments:**
```
// support for the old title property
// https://github.com/codemirror/CodeMirror/pull/5673
```

<details><summary>Code</summary>

```typescript
function insertLineContent(line, builder, styles) {
    var spans = line.markedSpans, allText = line.text, at = 0;
    if (!spans) {
      for (var i$1 = 1; i$1 < styles.length; i$1+=2)
        { builder.addToken(builder, allText.slice(at, at = styles[i$1]), interpretTokenStyle(styles[i$1+1], builder.cm.options)); }
      return
    }

    var len = allText.length, pos = 0, i = 1, text = "", style, css;
    var nextChange = 0, spanStyle, spanEndStyle, spanStartStyle, collapsed, attributes;
    for (;;) {
      if (nextChange == pos) { // Update current marker set
        spanStyle = spanEndStyle = spanStartStyle = css = "";
        attributes = null;
        collapsed = null; nextChange = Infinity;
        var foundBookmarks = [], endStyles = (void 0);
        for (var j = 0; j < spans.length; ++j) {
          var sp = spans[j], m = sp.marker;
          if (m.type == "bookmark" && sp.from == pos && m.widgetNode) {
            foundBookmarks.push(m);
          } else if (sp.from <= pos && (sp.to == null || sp.to > pos || m.collapsed && sp.to == pos && sp.from == pos)) {
            if (sp.to != null && sp.to != pos && nextChange > sp.to) {
              nextChange = sp.to;
              spanEndStyle = "";
            }
            if (m.className) { spanStyle += " " + m.className; }
            if (m.css) { css = (css ? css + ";" : "") + m.css; }
            if (m.startStyle && sp.from == pos) { spanStartStyle += " " + m.startStyle; }
            if (m.endStyle && sp.to == nextChange) { (endStyles || (endStyles = [])).push(m.endStyle, sp.to); }
            // support for the old title property
            // https://github.com/codemirror/CodeMirror/pull/5673
            if (m.title) { (attributes || (attributes = {})).title = m.title; }
            if (m.attributes) {
              for (var attr in m.attributes)
                { (attributes || (attributes = {}))[attr] = m.attributes[attr]; }
            }
            if (m.collapsed && (!collapsed || compareCollapsedMarkers(collapsed.marker, m) < 0))
              { collapsed = sp; }
          } else if (sp.from > pos && nextChange > sp.from) {
            nextChange = sp.from;
          }
        }
        if (endStyles) { for (var j$1 = 0; j$1 < endStyles.length; j$1 += 2)
          { if (endStyles[j$1 + 1] == nextChange) { spanEndStyle += " " + endStyles[j$1]; } } }

        if (!collapsed || collapsed.from == pos) { for (var j$2 = 0; j$2 < foundBookmarks.length; ++j$2)
          { buildCollapsedSpan(builder, 0, foundBookmarks[j$2]); } }
        if (collapsed && (collapsed.from || 0) == pos) {
          buildCollapsedSpan(builder, (collapsed.to == null ? len + 1 : collapsed.to) - pos,
                             collapsed.marker, collapsed.from == null);
          if (collapsed.to == null) { return }
          if (collapsed.to == pos) { collapsed = false; }
        }
      }
      if (pos >= len) { break }

      var upto = Math.min(len, nextChange);
      while (true) {
        if (text) {
          var end = pos + text.length;
          if (!collapsed) {
            var tokenText = end > upto ? text.slice(0, upto - pos) : text;
            builder.addToken(builder, tokenText, style ? style + spanStyle : spanStyle,
                             spanStartStyle, pos + tokenText.length == nextChange ? spanEndStyle : "", css, attributes);
          }
          if (end >= upto) {text = text.slice(upto - pos); pos = upto; break}
          pos = end;
          spanStartStyle = "";
        }
        text = allText.slice(at, at = styles[i++]);
        style = interpretTokenStyle(styles[i++], builder.cm.options);
      }
    }
  }
```
</details>

### `LineView(doc: any, line: any, lineN: any): void`

**Parameters:**

- **`doc`** `any`
- **`line`** `any`
- **`lineN`** `any`

**Returns:** `void`

**Calls:**

- `visualLineContinued`
- `lineNo`
- `lst`
- `lineIsHidden`

**Internal Comments:**
```
// The starting line (x4)
// Continuing lines, if any (x4)
// Number of logical lines in this visual line (x4)
```

<details><summary>Code</summary>

```typescript
function LineView(doc, line, lineN) {
    // The starting line
    this.line = line;
    // Continuing lines, if any
    this.rest = visualLineContinued(line);
    // Number of logical lines in this visual line
    this.size = this.rest ? lineNo(lst(this.rest)) - lineN + 1 : 1;
    this.node = this.text = null;
    this.hidden = lineIsHidden(doc, line);
  }
```
</details>

### `buildViewArray(cm: any, from: any, to: any): LineView[]`

**Parameters:**

- **`cm`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `LineView[]`

**Calls:**

- `getLine`
- `array.push`

<details><summary>Code</summary>

```typescript
function buildViewArray(cm, from, to) {
    var array = [], nextPos;
    for (var pos = from; pos < to; pos = nextPos) {
      var view = new LineView(cm.doc, getLine(cm.doc, pos), pos);
      nextPos = pos + view.size;
      array.push(view);
    }
    return array
  }
```
</details>

### `pushOperation(op: any): void`

**Parameters:**

- **`op`** `any`

**Returns:** `void`

**Calls:**

- `operationGroup.ops.push`

<details><summary>Code</summary>

```typescript
function pushOperation(op) {
    if (operationGroup) {
      operationGroup.ops.push(op);
    } else {
      op.ownsGroup = operationGroup = {
        ops: [op],
        delayedCallbacks: []
      };
    }
  }
```
</details>

### `fireCallbacksForOps(group: any): void`

**Parameters:**

- **`group`** `any`

**Returns:** `void`

**Calls:**

- `callbacks[i].call`
- `op.cursorActivityHandlers[op.cursorActivityCalled++].call`

**Internal Comments:**
```
// Calls delayed callbacks and cursorActivity handlers until no (x2)
// new ones appear (x2)
```

<details><summary>Code</summary>

```typescript
function fireCallbacksForOps(group) {
    // Calls delayed callbacks and cursorActivity handlers until no
    // new ones appear
    var callbacks = group.delayedCallbacks, i = 0;
    do {
      for (; i < callbacks.length; i++)
        { callbacks[i].call(null); }
      for (var j = 0; j < group.ops.length; j++) {
        var op = group.ops[j];
        if (op.cursorActivityHandlers)
          { while (op.cursorActivityCalled < op.cursorActivityHandlers.length)
            { op.cursorActivityHandlers[op.cursorActivityCalled++].call(null, op.cm); } }
      }
    } while (i < callbacks.length)
  }
```
</details>

### `finishOperation(op: any, endCb: any): void`

**Parameters:**

- **`op`** `any`
- **`endCb`** `any`

**Returns:** `void`

**Calls:**

- `fireCallbacksForOps`
- `endCb`

<details><summary>Code</summary>

```typescript
function finishOperation(op, endCb) {
    var group = op.ownsGroup;
    if (!group) { return }

    try { fireCallbacksForOps(group); }
    finally {
      operationGroup = null;
      endCb(group);
    }
  }
```
</details>

### `signalLater(emitter: any, type: any): void`

**Parameters:**

- **`emitter`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `getHandlers`
- `Array.prototype.slice.call`
- `setTimeout`
- `list.push`
- `arr[i].apply`
- `loop`

<details><summary>Code</summary>

```typescript
function signalLater(emitter, type /*, values...*/) {
    var arr = getHandlers(emitter, type);
    if (!arr.length) { return }
    var args = Array.prototype.slice.call(arguments, 2), list;
    if (operationGroup) {
      list = operationGroup.delayedCallbacks;
    } else if (orphanDelayedCallbacks) {
      list = orphanDelayedCallbacks;
    } else {
      list = orphanDelayedCallbacks = [];
      setTimeout(fireOrphanDelayed, 0);
    }
    var loop = function ( i ) {
      list.push(function () { return arr[i].apply(null, args); });
    };

    for (var i = 0; i < arr.length; ++i)
      loop( i );
  }
```
</details>

### `loop(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `list.push`
- `arr[i].apply`

<details><summary>Code</summary>

```typescript
function ( i ) {
      list.push(function () { return arr[i].apply(null, args); });
    }
```
</details>

### `fireOrphanDelayed(): void`

**Returns:** `void`

**Calls:**

- `complex_call_83306`

<details><summary>Code</summary>

```typescript
function fireOrphanDelayed() {
    var delayed = orphanDelayedCallbacks;
    orphanDelayedCallbacks = null;
    for (var i = 0; i < delayed.length; ++i) { delayed[i](); }
  }
```
</details>

### `updateLineForChanges(cm: any, lineView: any, lineN: any, dims: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`
- **`lineN`** `any`
- **`dims`** `any`

**Returns:** `void`

**Calls:**

- `updateLineText`
- `updateLineGutter`
- `updateLineClasses`
- `updateLineWidgets`

<details><summary>Code</summary>

```typescript
function updateLineForChanges(cm, lineView, lineN, dims) {
    for (var j = 0; j < lineView.changes.length; j++) {
      var type = lineView.changes[j];
      if (type == "text") { updateLineText(cm, lineView); }
      else if (type == "gutter") { updateLineGutter(cm, lineView, lineN, dims); }
      else if (type == "class") { updateLineClasses(cm, lineView); }
      else if (type == "widget") { updateLineWidgets(cm, lineView, dims); }
    }
    lineView.changes = null;
  }
```
</details>

### `ensureLineWrapped(lineView: any): any`

**Parameters:**

- **`lineView`** `any`

**Returns:** `any`

**Calls:**

- `elt`
- `lineView.text.parentNode.replaceChild`
- `lineView.node.appendChild`

<details><summary>Code</summary>

```typescript
function ensureLineWrapped(lineView) {
    if (lineView.node == lineView.text) {
      lineView.node = elt("div", null, null, "position: relative");
      if (lineView.text.parentNode)
        { lineView.text.parentNode.replaceChild(lineView.node, lineView.text); }
      lineView.node.appendChild(lineView.text);
      if (ie && ie_version < 8) { lineView.node.style.zIndex = 2; }
    }
    return lineView.node
  }
```
</details>

### `updateLineBackground(cm: any, lineView: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`

**Returns:** `void`

**Calls:**

- `lineView.background.parentNode.removeChild`
- `ensureLineWrapped`
- `wrap.insertBefore`
- `elt`
- `cm.display.input.setUneditable`

<details><summary>Code</summary>

```typescript
function updateLineBackground(cm, lineView) {
    var cls = lineView.bgClass ? lineView.bgClass + " " + (lineView.line.bgClass || "") : lineView.line.bgClass;
    if (cls) { cls += " CodeMirror-linebackground"; }
    if (lineView.background) {
      if (cls) { lineView.background.className = cls; }
      else { lineView.background.parentNode.removeChild(lineView.background); lineView.background = null; }
    } else if (cls) {
      var wrap = ensureLineWrapped(lineView);
      lineView.background = wrap.insertBefore(elt("div", null, cls), wrap.firstChild);
      cm.display.input.setUneditable(lineView.background);
    }
  }
```
</details>

### `getLineContent(cm: any, lineView: any): any`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`

**Returns:** `any`

**Calls:**

- `buildLineContent`

<details><summary>Code</summary>

```typescript
function getLineContent(cm, lineView) {
    var ext = cm.display.externalMeasured;
    if (ext && ext.line == lineView.line) {
      cm.display.externalMeasured = null;
      lineView.measure = ext.measure;
      return ext.built
    }
    return buildLineContent(cm, lineView)
  }
```
</details>

### `updateLineText(cm: any, lineView: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`

**Returns:** `void`

**Calls:**

- `getLineContent`
- `lineView.text.parentNode.replaceChild`
- `updateLineClasses`

<details><summary>Code</summary>

```typescript
function updateLineText(cm, lineView) {
    var cls = lineView.text.className;
    var built = getLineContent(cm, lineView);
    if (lineView.text == lineView.node) { lineView.node = built.pre; }
    lineView.text.parentNode.replaceChild(built.pre, lineView.text);
    lineView.text = built.pre;
    if (built.bgClass != lineView.bgClass || built.textClass != lineView.textClass) {
      lineView.bgClass = built.bgClass;
      lineView.textClass = built.textClass;
      updateLineClasses(cm, lineView);
    } else if (cls) {
      lineView.text.className = cls;
    }
  }
```
</details>

### `updateLineClasses(cm: any, lineView: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`

**Returns:** `void`

**Calls:**

- `updateLineBackground`
- `ensureLineWrapped`

<details><summary>Code</summary>

```typescript
function updateLineClasses(cm, lineView) {
    updateLineBackground(cm, lineView);
    if (lineView.line.wrapClass)
      { ensureLineWrapped(lineView).className = lineView.line.wrapClass; }
    else if (lineView.node != lineView.text)
      { lineView.node.className = ""; }
    var textClass = lineView.textClass ? lineView.textClass + " " + (lineView.line.textClass || "") : lineView.line.textClass;
    lineView.text.className = textClass || "";
  }
```
</details>

### `updateLineGutter(cm: any, lineView: any, lineN: any, dims: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`
- **`lineN`** `any`
- **`dims`** `any`

**Returns:** `void`

**Calls:**

- `lineView.node.removeChild`
- `ensureLineWrapped`
- `elt`
- `cm.display.input.setUneditable`
- `wrap.insertBefore`
- `gutterWrap.setAttribute`
- `wrap$1.insertBefore`
- `gutterWrap.appendChild`
- `lineNumberFor`
- `markers.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function updateLineGutter(cm, lineView, lineN, dims) {
    if (lineView.gutter) {
      lineView.node.removeChild(lineView.gutter);
      lineView.gutter = null;
    }
    if (lineView.gutterBackground) {
      lineView.node.removeChild(lineView.gutterBackground);
      lineView.gutterBackground = null;
    }
    if (lineView.line.gutterClass) {
      var wrap = ensureLineWrapped(lineView);
      lineView.gutterBackground = elt("div", null, "CodeMirror-gutter-background " + lineView.line.gutterClass,
                                      ("left: " + (cm.options.fixedGutter ? dims.fixedPos : -dims.gutterTotalWidth) + "px; width: " + (dims.gutterTotalWidth) + "px"));
      cm.display.input.setUneditable(lineView.gutterBackground);
      wrap.insertBefore(lineView.gutterBackground, lineView.text);
    }
    var markers = lineView.line.gutterMarkers;
    if (cm.options.lineNumbers || markers) {
      var wrap$1 = ensureLineWrapped(lineView);
      var gutterWrap = lineView.gutter = elt("div", null, "CodeMirror-gutter-wrapper", ("left: " + (cm.options.fixedGutter ? dims.fixedPos : -dims.gutterTotalWidth) + "px"));
      gutterWrap.setAttribute("aria-hidden", "true");
      cm.display.input.setUneditable(gutterWrap);
      wrap$1.insertBefore(gutterWrap, lineView.text);
      if (lineView.line.gutterClass)
        { gutterWrap.className += " " + lineView.line.gutterClass; }
      if (cm.options.lineNumbers && (!markers || !markers["CodeMirror-linenumbers"]))
        { lineView.lineNumber = gutterWrap.appendChild(
          elt("div", lineNumberFor(cm.options, lineN),
              "CodeMirror-linenumber CodeMirror-gutter-elt",
              ("left: " + (dims.gutterLeft["CodeMirror-linenumbers"]) + "px; width: " + (cm.display.lineNumInnerWidth) + "px"))); }
      if (markers) { for (var k = 0; k < cm.display.gutterSpecs.length; ++k) {
        var id = cm.display.gutterSpecs[k].className, found = markers.hasOwnProperty(id) && markers[id];
        if (found)
          { gutterWrap.appendChild(elt("div", [found], "CodeMirror-gutter-elt",
                                     ("left: " + (dims.gutterLeft[id]) + "px; width: " + (dims.gutterWidth[id]) + "px"))); }
      } }
    }
  }
```
</details>

### `updateLineWidgets(cm: any, lineView: any, dims: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`
- **`dims`** `any`

**Returns:** `void`

**Calls:**

- `classTest`
- `isWidget.test`
- `lineView.node.removeChild`
- `insertLineWidgets`

<details><summary>Code</summary>

```typescript
function updateLineWidgets(cm, lineView, dims) {
    if (lineView.alignable) { lineView.alignable = null; }
    var isWidget = classTest("CodeMirror-linewidget");
    for (var node = lineView.node.firstChild, next = (void 0); node; node = next) {
      next = node.nextSibling;
      if (isWidget.test(node.className)) { lineView.node.removeChild(node); }
    }
    insertLineWidgets(cm, lineView, dims);
  }
```
</details>

### `buildLineElement(cm: any, lineView: any, lineN: any, dims: any): any`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`
- **`lineN`** `any`
- **`dims`** `any`

**Returns:** `any`

**Calls:**

- `getLineContent`
- `updateLineClasses`
- `updateLineGutter`
- `insertLineWidgets`

<details><summary>Code</summary>

```typescript
function buildLineElement(cm, lineView, lineN, dims) {
    var built = getLineContent(cm, lineView);
    lineView.text = lineView.node = built.pre;
    if (built.bgClass) { lineView.bgClass = built.bgClass; }
    if (built.textClass) { lineView.textClass = built.textClass; }

    updateLineClasses(cm, lineView);
    updateLineGutter(cm, lineView, lineN, dims);
    insertLineWidgets(cm, lineView, dims);
    return lineView.node
  }
```
</details>

### `insertLineWidgets(cm: any, lineView: any, dims: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`
- **`dims`** `any`

**Returns:** `void`

**Calls:**

- `insertLineWidgetsFor`

<details><summary>Code</summary>

```typescript
function insertLineWidgets(cm, lineView, dims) {
    insertLineWidgetsFor(cm, lineView.line, lineView, dims, true);
    if (lineView.rest) { for (var i = 0; i < lineView.rest.length; i++)
      { insertLineWidgetsFor(cm, lineView.rest[i], lineView, dims, false); } }
  }
```
</details>

### `insertLineWidgetsFor(cm: any, line: any, lineView: any, dims: any, allowAbove: any): void`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`
- **`lineView`** `any`
- **`dims`** `any`
- **`allowAbove`** `any`

**Returns:** `void`

**Calls:**

- `ensureLineWrapped`
- `elt`
- `node.setAttribute`
- `positionLineWidget`
- `cm.display.input.setUneditable`
- `wrap.insertBefore`
- `wrap.appendChild`
- `signalLater`

<details><summary>Code</summary>

```typescript
function insertLineWidgetsFor(cm, line, lineView, dims, allowAbove) {
    if (!line.widgets) { return }
    var wrap = ensureLineWrapped(lineView);
    for (var i = 0, ws = line.widgets; i < ws.length; ++i) {
      var widget = ws[i], node = elt("div", [widget.node], "CodeMirror-linewidget" + (widget.className ? " " + widget.className : ""));
      if (!widget.handleMouseEvents) { node.setAttribute("cm-ignore-events", "true"); }
      positionLineWidget(widget, node, lineView, dims);
      cm.display.input.setUneditable(node);
      if (allowAbove && widget.above)
        { wrap.insertBefore(node, lineView.gutter || lineView.text); }
      else
        { wrap.appendChild(node); }
      signalLater(widget, "redraw");
    }
  }
```
</details>

### `positionLineWidget(widget: any, node: any, lineView: any, dims: any): void`

**Parameters:**

- **`widget`** `any`
- **`node`** `any`
- **`lineView`** `any`
- **`dims`** `any`

**Returns:** `void`

**Calls:**

- `(lineView.alignable || (lineView.alignable = [])).push`

<details><summary>Code</summary>

```typescript
function positionLineWidget(widget, node, lineView, dims) {
    if (widget.noHScroll) {
  (lineView.alignable || (lineView.alignable = [])).push(node);
      var width = dims.wrapperWidth;
      node.style.left = dims.fixedPos + "px";
      if (!widget.coverGutter) {
        width -= dims.gutterTotalWidth;
        node.style.paddingLeft = dims.gutterTotalWidth + "px";
      }
      node.style.width = width + "px";
    }
    if (widget.coverGutter) {
      node.style.zIndex = 5;
      node.style.position = "relative";
      if (!widget.noHScroll) { node.style.marginLeft = -dims.gutterTotalWidth + "px"; }
    }
  }
```
</details>

### `widgetHeight(widget: any): any`

**Parameters:**

- **`widget`** `any`

**Returns:** `any`

**Calls:**

- `contains`
- `removeChildrenAndAdd`
- `elt`

<details><summary>Code</summary>

```typescript
function widgetHeight(widget) {
    if (widget.height != null) { return widget.height }
    var cm = widget.doc.cm;
    if (!cm) { return 0 }
    if (!contains(document.body, widget.node)) {
      var parentStyle = "position: relative;";
      if (widget.coverGutter)
        { parentStyle += "margin-left: -" + cm.display.gutters.offsetWidth + "px;"; }
      if (widget.noHScroll)
        { parentStyle += "width: " + cm.display.wrapper.clientWidth + "px;"; }
      removeChildrenAndAdd(cm.display.measure, elt("div", [widget.node], null, parentStyle));
    }
    return widget.height = widget.node.parentNode.offsetHeight
  }
```
</details>

### `eventInWidget(display: any, e: any): boolean`

**Parameters:**

- **`display`** `any`
- **`e`** `any`

**Returns:** `boolean`

**Calls:**

- `e_target`
- `n.getAttribute`

<details><summary>Code</summary>

```typescript
function eventInWidget(display, e) {
    for (var n = e_target(e); n != display.wrapper; n = n.parentNode) {
      if (!n || (n.nodeType == 1 && n.getAttribute("cm-ignore-events") == "true") ||
          (n.parentNode == display.sizer && n != display.mover))
        { return true }
    }
  }
```
</details>

### `paddingTop(display: any): any`

**Parameters:**

- **`display`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function paddingTop(display) {return display.lineSpace.offsetTop}
```
</details>

### `paddingVert(display: any): number`

**Parameters:**

- **`display`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function paddingVert(display) {return display.mover.offsetHeight - display.lineSpace.offsetHeight}
```
</details>

### `paddingH(display: any): any`

**Parameters:**

- **`display`** `any`

**Returns:** `any`

**Calls:**

- `removeChildrenAndAdd`
- `elt`
- `window.getComputedStyle`
- `parseInt`
- `isNaN`

<details><summary>Code</summary>

```typescript
function paddingH(display) {
    if (display.cachedPaddingH) { return display.cachedPaddingH }
    var e = removeChildrenAndAdd(display.measure, elt("pre", "x", "CodeMirror-line-like"));
    var style = window.getComputedStyle ? window.getComputedStyle(e) : e.currentStyle;
    var data = {left: parseInt(style.paddingLeft), right: parseInt(style.paddingRight)};
    if (!isNaN(data.left) && !isNaN(data.right)) { display.cachedPaddingH = data; }
    return data
  }
```
</details>

### `scrollGap(cm: any): number`

**Parameters:**

- **`cm`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function scrollGap(cm) { return scrollerGap - cm.display.nativeBarWidth }
```
</details>

### `displayWidth(cm: any): number`

**Parameters:**

- **`cm`** `any`

**Returns:** `number`

**Calls:**

- `scrollGap`

<details><summary>Code</summary>

```typescript
function displayWidth(cm) {
    return cm.display.scroller.clientWidth - scrollGap(cm) - cm.display.barWidth
  }
```
</details>

### `displayHeight(cm: any): number`

**Parameters:**

- **`cm`** `any`

**Returns:** `number`

**Calls:**

- `scrollGap`

<details><summary>Code</summary>

```typescript
function displayHeight(cm) {
    return cm.display.scroller.clientHeight - scrollGap(cm) - cm.display.barHeight
  }
```
</details>

### `ensureLineHeights(cm: any, lineView: any, rect: any): void`

**Parameters:**

- **`cm`** `any`
- **`lineView`** `any`
- **`rect`** `any`

**Returns:** `void`

**Calls:**

- `displayWidth`
- `lineView.text.firstChild.getClientRects`
- `Math.abs`
- `heights.push`

<details><summary>Code</summary>

```typescript
function ensureLineHeights(cm, lineView, rect) {
    var wrapping = cm.options.lineWrapping;
    var curWidth = wrapping && displayWidth(cm);
    if (!lineView.measure.heights || wrapping && lineView.measure.width != curWidth) {
      var heights = lineView.measure.heights = [];
      if (wrapping) {
        lineView.measure.width = curWidth;
        var rects = lineView.text.firstChild.getClientRects();
        for (var i = 0; i < rects.length - 1; i++) {
          var cur = rects[i], next = rects[i + 1];
          if (Math.abs(cur.bottom - next.bottom) > 2)
            { heights.push((cur.bottom + next.top) / 2 - rect.top); }
        }
      }
      heights.push(rect.bottom - rect.top);
    }
  }
```
</details>

### `mapFromLineView(lineView: any, line: any, lineN: any): { map: any; cache: any; before?: undefined; } | { map: any; cache: any; before: boolean; }`

**Parameters:**

- **`lineView`** `any`
- **`line`** `any`
- **`lineN`** `any`

**Returns:** `{ map: any; cache: any; before?: undefined; } | { map: any; cache: any; before: boolean; }`

**Calls:**

- `lineNo`

<details><summary>Code</summary>

```typescript
function mapFromLineView(lineView, line, lineN) {
    if (lineView.line == line)
      { return {map: lineView.measure.map, cache: lineView.measure.cache} }
    if (lineView.rest) {
      for (var i = 0; i < lineView.rest.length; i++)
        { if (lineView.rest[i] == line)
          { return {map: lineView.measure.maps[i], cache: lineView.measure.caches[i]} } }
      for (var i$1 = 0; i$1 < lineView.rest.length; i$1++)
        { if (lineNo(lineView.rest[i$1]) > lineN)
          { return {map: lineView.measure.maps[i$1], cache: lineView.measure.caches[i$1], before: true} } }
    }
  }
```
</details>

### `updateExternalMeasurement(cm: any, line: any): LineView`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`

**Returns:** `LineView`

**Calls:**

- `visualLine`
- `lineNo`
- `buildLineContent`
- `removeChildrenAndAdd`

<details><summary>Code</summary>

```typescript
function updateExternalMeasurement(cm, line) {
    line = visualLine(line);
    var lineN = lineNo(line);
    var view = cm.display.externalMeasured = new LineView(cm.doc, line, lineN);
    view.lineN = lineN;
    var built = view.built = buildLineContent(cm, view);
    view.text = built.pre;
    removeChildrenAndAdd(cm.display.lineMeasure, built.pre);
    return view
  }
```
</details>

### `measureChar(cm: any, line: any, ch: any, bias: any): { left: any; right: any; top: any; bottom: any; }`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`
- **`ch`** `any`
- **`bias`** `any`

**Returns:** `{ left: any; right: any; top: any; bottom: any; }`

**Calls:**

- `measureCharPrepared`
- `prepareMeasureForLine`

<details><summary>Code</summary>

```typescript
function measureChar(cm, line, ch, bias) {
    return measureCharPrepared(cm, prepareMeasureForLine(cm, line), ch, bias)
  }
```
</details>

### `findViewForLine(cm: any, lineN: any): any`

**Parameters:**

- **`cm`** `any`
- **`lineN`** `any`

**Returns:** `any`

**Calls:**

- `findViewIndex`

<details><summary>Code</summary>

```typescript
function findViewForLine(cm, lineN) {
    if (lineN >= cm.display.viewFrom && lineN < cm.display.viewTo)
      { return cm.display.view[findViewIndex(cm, lineN)] }
    var ext = cm.display.externalMeasured;
    if (ext && lineN >= ext.lineN && lineN < ext.lineN + ext.size)
      { return ext }
  }
```
</details>

### `prepareMeasureForLine(cm: any, line: any): { line: any; view: any; rect: any; map: any; cache: any; before: boolean; hasHeights: boolean; }`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`

**Returns:** `{ line: any; view: any; rect: any; map: any; cache: any; before: boolean; hasHeights: boolean; }`

**Calls:**

- `lineNo`
- `findViewForLine`
- `updateLineForChanges`
- `getDimensions`
- `updateExternalMeasurement`
- `mapFromLineView`

<details><summary>Code</summary>

```typescript
function prepareMeasureForLine(cm, line) {
    var lineN = lineNo(line);
    var view = findViewForLine(cm, lineN);
    if (view && !view.text) {
      view = null;
    } else if (view && view.changes) {
      updateLineForChanges(cm, view, lineN, getDimensions(cm));
      cm.curOp.forceUpdate = true;
    }
    if (!view)
      { view = updateExternalMeasurement(cm, line); }

    var info = mapFromLineView(view, line, lineN);
    return {
      line: line, view: view, rect: null,
      map: info.map, cache: info.cache, before: info.before,
      hasHeights: false
    }
  }
```
</details>

### `measureCharPrepared(cm: any, prepared: any, ch: any, bias: any, varHeight: any): { left: any; right: any; top: any; bottom: any; }`

**Parameters:**

- **`cm`** `any`
- **`prepared`** `any`
- **`ch`** `any`
- **`bias`** `any`
- **`varHeight`** `any`

**Returns:** `{ left: any; right: any; top: any; bottom: any; }`

**Calls:**

- `prepared.cache.hasOwnProperty`
- `prepared.view.text.getBoundingClientRect`
- `ensureLineHeights`
- `measureCharInner`

<details><summary>Code</summary>

```typescript
function measureCharPrepared(cm, prepared, ch, bias, varHeight) {
    if (prepared.before) { ch = -1; }
    var key = ch + (bias || ""), found;
    if (prepared.cache.hasOwnProperty(key)) {
      found = prepared.cache[key];
    } else {
      if (!prepared.rect)
        { prepared.rect = prepared.view.text.getBoundingClientRect(); }
      if (!prepared.hasHeights) {
        ensureLineHeights(cm, prepared.view, prepared.rect);
        prepared.hasHeights = true;
      }
      found = measureCharInner(cm, prepared, ch, bias);
      if (!found.bogus) { prepared.cache[key] = found; }
    }
    return {left: found.left, right: found.right,
            top: varHeight ? found.rtop : found.top,
            bottom: varHeight ? found.rbottom : found.bottom}
  }
```
</details>

### `nodeAndOffsetInLineMap(map: any, ch: any, bias: any): { node: any; start: number; end: number; collapse: any; coverStart: any; coverEnd: any; }`

**Parameters:**

- **`map`** `any`
- **`ch`** `any`
- **`bias`** `any`

**Returns:** `{ node: any; start: number; end: number; collapse: any; coverStart: any; coverEnd: any; }`

**Internal Comments:**
```
// First, search the line map for the text node corresponding to,
// or closest to, the target character.
```

<details><summary>Code</summary>

```typescript
function nodeAndOffsetInLineMap(map, ch, bias) {
    var node, start, end, collapse, mStart, mEnd;
    // First, search the line map for the text node corresponding to,
    // or closest to, the target character.
    for (var i = 0; i < map.length; i += 3) {
      mStart = map[i];
      mEnd = map[i + 1];
      if (ch < mStart) {
        start = 0; end = 1;
        collapse = "left";
      } else if (ch < mEnd) {
        start = ch - mStart;
        end = start + 1;
      } else if (i == map.length - 3 || ch == mEnd && map[i + 3] > ch) {
        end = mEnd - mStart;
        start = end - 1;
        if (ch >= mEnd) { collapse = "right"; }
      }
      if (start != null) {
        node = map[i + 2];
        if (mStart == mEnd && bias == (node.insertLeft ? "left" : "right"))
          { collapse = bias; }
        if (bias == "left" && start == 0)
          { while (i && map[i - 2] == map[i - 3] && map[i - 1].insertLeft) {
            node = map[(i -= 3) + 2];
            collapse = "left";
          } }
        if (bias == "right" && start == mEnd - mStart)
          { while (i < map.length - 3 && map[i + 3] == map[i + 4] && !map[i + 5].insertLeft) {
            node = map[(i += 3) + 2];
            collapse = "right";
          } }
        break
      }
    }
    return {node: node, start: start, end: end, collapse: collapse, coverStart: mStart, coverEnd: mEnd}
  }
```
</details>

### `getUsefulRect(rects: any, bias: any): { left: number; right: number; top: number; bottom: number; }`

**Parameters:**

- **`rects`** `any`
- **`bias`** `any`

**Returns:** `{ left: number; right: number; top: number; bottom: number; }`

<details><summary>Code</summary>

```typescript
function getUsefulRect(rects, bias) {
    var rect = nullRect;
    if (bias == "left") { for (var i = 0; i < rects.length; i++) {
      if ((rect = rects[i]).left != rect.right) { break }
    } } else { for (var i$1 = rects.length - 1; i$1 >= 0; i$1--) {
      if ((rect = rects[i$1]).left != rect.right) { break }
    } }
    return rect
  }
```
</details>

### `measureCharInner(cm: any, prepared: any, ch: any, bias: any): { left: number; right: number; top: any; bottom: any; }`

**Parameters:**

- **`cm`** `any`
- **`prepared`** `any`
- **`ch`** `any`
- **`bias`** `any`

**Returns:** `{ left: number; right: number; top: any; bottom: any; }`

**Calls:**

- `nodeAndOffsetInLineMap`
- `isExtendingChar`
- `prepared.line.text.charAt`
- `node.parentNode.getBoundingClientRect`
- `getUsefulRect`
- `range(node, start, end).getClientRects`
- `maybeUpdateRectForZooming`
- `node.getClientRects`
- `node.getBoundingClientRect`
- `node.parentNode.getClientRects`
- `charWidth`

<details><summary>Code</summary>

```typescript
function measureCharInner(cm, prepared, ch, bias) {
    var place = nodeAndOffsetInLineMap(prepared.map, ch, bias);
    var node = place.node, start = place.start, end = place.end, collapse = place.collapse;

    var rect;
    if (node.nodeType == 3) { // If it is a text node, use a range to retrieve the coordinates.
      for (var i$1 = 0; i$1 < 4; i$1++) { // Retry a maximum of 4 times when nonsense rectangles are returned
        while (start && isExtendingChar(prepared.line.text.charAt(place.coverStart + start))) { --start; }
        while (place.coverStart + end < place.coverEnd && isExtendingChar(prepared.line.text.charAt(place.coverStart + end))) { ++end; }
        if (ie && ie_version < 9 && start == 0 && end == place.coverEnd - place.coverStart)
          { rect = node.parentNode.getBoundingClientRect(); }
        else
          { rect = getUsefulRect(range(node, start, end).getClientRects(), bias); }
        if (rect.left || rect.right || start == 0) { break }
        end = start;
        start = start - 1;
        collapse = "right";
      }
      if (ie && ie_version < 11) { rect = maybeUpdateRectForZooming(cm.display.measure, rect); }
    } else { // If it is a widget, simply get the box for the whole widget.
      if (start > 0) { collapse = bias = "right"; }
      var rects;
      if (cm.options.lineWrapping && (rects = node.getClientRects()).length > 1)
        { rect = rects[bias == "right" ? rects.length - 1 : 0]; }
      else
        { rect = node.getBoundingClientRect(); }
    }
    if (ie && ie_version < 9 && !start && (!rect || !rect.left && !rect.right)) {
      var rSpan = node.parentNode.getClientRects()[0];
      if (rSpan)
        { rect = {left: rSpan.left, right: rSpan.left + charWidth(cm.display), top: rSpan.top, bottom: rSpan.bottom}; }
      else
        { rect = nullRect; }
    }

    var rtop = rect.top - prepared.rect.top, rbot = rect.bottom - prepared.rect.top;
    var mid = (rtop + rbot) / 2;
    var heights = prepared.view.measure.heights;
    var i = 0;
    for (; i < heights.length - 1; i++)
      { if (mid < heights[i]) { break } }
    var top = i ? heights[i - 1] : 0, bot = heights[i];
    var result = {left: (collapse == "right" ? rect.right : rect.left) - prepared.rect.left,
                  right: (collapse == "left" ? rect.left : rect.right) - prepared.rect.left,
                  top: top, bottom: bot};
    if (!rect.left && !rect.right) { result.bogus = true; }
    if (!cm.options.singleCursorHeightPerLine) { result.rtop = rtop; result.rbottom = rbot; }

    return result
  }
```
</details>

### `maybeUpdateRectForZooming(measure: any, rect: any): any`

**Parameters:**

- **`measure`** `any`
- **`rect`** `any`

**Returns:** `any`

**Calls:**

- `hasBadZoomedRects`

<details><summary>Code</summary>

```typescript
function maybeUpdateRectForZooming(measure, rect) {
    if (!window.screen || screen.logicalXDPI == null ||
        screen.logicalXDPI == screen.deviceXDPI || !hasBadZoomedRects(measure))
      { return rect }
    var scaleX = screen.logicalXDPI / screen.deviceXDPI;
    var scaleY = screen.logicalYDPI / screen.deviceYDPI;
    return {left: rect.left * scaleX, right: rect.right * scaleX,
            top: rect.top * scaleY, bottom: rect.bottom * scaleY}
  }
```
</details>

### `clearLineMeasurementCacheFor(lineView: any): void`

**Parameters:**

- **`lineView`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function clearLineMeasurementCacheFor(lineView) {
    if (lineView.measure) {
      lineView.measure.cache = {};
      lineView.measure.heights = null;
      if (lineView.rest) { for (var i = 0; i < lineView.rest.length; i++)
        { lineView.measure.caches[i] = {}; } }
    }
  }
```
</details>

### `clearLineMeasurementCache(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `removeChildren`
- `clearLineMeasurementCacheFor`

<details><summary>Code</summary>

```typescript
function clearLineMeasurementCache(cm) {
    cm.display.externalMeasure = null;
    removeChildren(cm.display.lineMeasure);
    for (var i = 0; i < cm.display.view.length; i++)
      { clearLineMeasurementCacheFor(cm.display.view[i]); }
  }
```
</details>

### `clearCaches(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `clearLineMeasurementCache`

<details><summary>Code</summary>

```typescript
function clearCaches(cm) {
    clearLineMeasurementCache(cm);
    cm.display.cachedCharWidth = cm.display.cachedTextHeight = cm.display.cachedPaddingH = null;
    if (!cm.options.lineWrapping) { cm.display.maxLineChanged = true; }
    cm.display.lineNumChars = null;
  }
```
</details>

### `pageScrollX(): number`

**Returns:** `number`

**Calls:**

- `document.body.getBoundingClientRect`
- `parseInt`
- `getComputedStyle`

**Internal Comments:**
```
// Work around https://bugs.chromium.org/p/chromium/issues/detail?id=489206
// which causes page_Offset and bounding client rects to use
// different reference viewports and invalidate our calculations.
```

<details><summary>Code</summary>

```typescript
function pageScrollX() {
    // Work around https://bugs.chromium.org/p/chromium/issues/detail?id=489206
    // which causes page_Offset and bounding client rects to use
    // different reference viewports and invalidate our calculations.
    if (chrome && android) { return -(document.body.getBoundingClientRect().left - parseInt(getComputedStyle(document.body).marginLeft)) }
    return window.pageXOffset || (document.documentElement || document.body).scrollLeft
  }
```
</details>

### `pageScrollY(): number`

**Returns:** `number`

**Calls:**

- `document.body.getBoundingClientRect`
- `parseInt`
- `getComputedStyle`

<details><summary>Code</summary>

```typescript
function pageScrollY() {
    if (chrome && android) { return -(document.body.getBoundingClientRect().top - parseInt(getComputedStyle(document.body).marginTop)) }
    return window.pageYOffset || (document.documentElement || document.body).scrollTop
  }
```
</details>

### `widgetTopHeight(lineObj: any): number`

**Parameters:**

- **`lineObj`** `any`

**Returns:** `number`

**Calls:**

- `visualLine`
- `widgetHeight`

<details><summary>Code</summary>

```typescript
function widgetTopHeight(lineObj) {
    var ref = visualLine(lineObj);
    var widgets = ref.widgets;
    var height = 0;
    if (widgets) { for (var i = 0; i < widgets.length; ++i) { if (widgets[i].above)
      { height += widgetHeight(widgets[i]); } } }
    return height
  }
```
</details>

### `intoCoordSystem(cm: any, lineObj: any, rect: any, context: any, includeWidgets: any): any`

**Parameters:**

- **`cm`** `any`
- **`lineObj`** `any`
- **`rect`** `any`
- **`context`** `any`
- **`includeWidgets`** `any`

**Returns:** `any`

**Calls:**

- `widgetTopHeight`
- `heightAtLine`
- `paddingTop`
- `cm.display.lineSpace.getBoundingClientRect`
- `pageScrollY`
- `pageScrollX`

<details><summary>Code</summary>

```typescript
function intoCoordSystem(cm, lineObj, rect, context, includeWidgets) {
    if (!includeWidgets) {
      var height = widgetTopHeight(lineObj);
      rect.top += height; rect.bottom += height;
    }
    if (context == "line") { return rect }
    if (!context) { context = "local"; }
    var yOff = heightAtLine(lineObj);
    if (context == "local") { yOff += paddingTop(cm.display); }
    else { yOff -= cm.display.viewOffset; }
    if (context == "page" || context == "window") {
      var lOff = cm.display.lineSpace.getBoundingClientRect();
      yOff += lOff.top + (context == "window" ? 0 : pageScrollY());
      var xOff = lOff.left + (context == "window" ? 0 : pageScrollX());
      rect.left += xOff; rect.right += xOff;
    }
    rect.top += yOff; rect.bottom += yOff;
    return rect
  }
```
</details>

### `fromCoordSystem(cm: any, coords: any, context: any): any`

**Parameters:**

- **`cm`** `any`
- **`coords`** `any`
- **`context`** `any`

**Returns:** `any`

**Calls:**

- `pageScrollX`
- `pageScrollY`
- `cm.display.sizer.getBoundingClientRect`
- `cm.display.lineSpace.getBoundingClientRect`

**Internal Comments:**
```
// First move into "page" coordinate system
```

<details><summary>Code</summary>

```typescript
function fromCoordSystem(cm, coords, context) {
    if (context == "div") { return coords }
    var left = coords.left, top = coords.top;
    // First move into "page" coordinate system
    if (context == "page") {
      left -= pageScrollX();
      top -= pageScrollY();
    } else if (context == "local" || !context) {
      var localBox = cm.display.sizer.getBoundingClientRect();
      left += localBox.left;
      top += localBox.top;
    }

    var lineSpaceBox = cm.display.lineSpace.getBoundingClientRect();
    return {left: left - lineSpaceBox.left, top: top - lineSpaceBox.top}
  }
```
</details>

### `charCoords(cm: any, pos: any, context: any, lineObj: any, bias: any): any`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`context`** `any`
- **`lineObj`** `any`
- **`bias`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `intoCoordSystem`
- `measureChar`

<details><summary>Code</summary>

```typescript
function charCoords(cm, pos, context, lineObj, bias) {
    if (!lineObj) { lineObj = getLine(cm.doc, pos.line); }
    return intoCoordSystem(cm, lineObj, measureChar(cm, lineObj, pos.ch, bias), context)
  }
```
</details>

### `cursorCoords(cm: any, pos: any, context: any, lineObj: any, preparedMeasure: any, varHeight: any): any`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`context`** `any`
- **`lineObj`** `any`
- **`preparedMeasure`** `any`
- **`varHeight`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `prepareMeasureForLine`
- `measureCharPrepared`
- `intoCoordSystem`
- `getOrder`
- `get`
- `getBidiPartAt`
- `getBidi`

<details><summary>Code</summary>

```typescript
function cursorCoords(cm, pos, context, lineObj, preparedMeasure, varHeight) {
    lineObj = lineObj || getLine(cm.doc, pos.line);
    if (!preparedMeasure) { preparedMeasure = prepareMeasureForLine(cm, lineObj); }
    function get(ch, right) {
      var m = measureCharPrepared(cm, preparedMeasure, ch, right ? "right" : "left", varHeight);
      if (right) { m.left = m.right; } else { m.right = m.left; }
      return intoCoordSystem(cm, lineObj, m, context)
    }
    var order = getOrder(lineObj, cm.doc.direction), ch = pos.ch, sticky = pos.sticky;
    if (ch >= lineObj.text.length) {
      ch = lineObj.text.length;
      sticky = "before";
    } else if (ch <= 0) {
      ch = 0;
      sticky = "after";
    }
    if (!order) { return get(sticky == "before" ? ch - 1 : ch, sticky == "before") }

    function getBidi(ch, partPos, invert) {
      var part = order[partPos], right = part.level == 1;
      return get(invert ? ch - 1 : ch, right != invert)
    }
    var partPos = getBidiPartAt(order, ch, sticky);
    var other = bidiOther;
    var val = getBidi(ch, partPos, sticky == "before");
    if (other != null) { val.other = getBidi(ch, other, sticky != "before"); }
    return val
  }
```
</details>

### `get(ch: any, right: any): any`

**Parameters:**

- **`ch`** `any`
- **`right`** `any`

**Returns:** `any`

**Calls:**

- `measureCharPrepared`
- `intoCoordSystem`

<details><summary>Code</summary>

```typescript
function get(ch, right) {
      var m = measureCharPrepared(cm, preparedMeasure, ch, right ? "right" : "left", varHeight);
      if (right) { m.left = m.right; } else { m.right = m.left; }
      return intoCoordSystem(cm, lineObj, m, context)
    }
```
</details>

### `getBidi(ch: any, partPos: any, invert: any): any`

**Parameters:**

- **`ch`** `any`
- **`partPos`** `any`
- **`invert`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function getBidi(ch, partPos, invert) {
      var part = order[partPos], right = part.level == 1;
      return get(invert ? ch - 1 : ch, right != invert)
    }
```
</details>

### `estimateCoords(cm: any, pos: any): { left: number; right: number; top: any; bottom: any; }`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`

**Returns:** `{ left: number; right: number; top: any; bottom: any; }`

**Calls:**

- `clipPos`
- `charWidth`
- `getLine`
- `heightAtLine`
- `paddingTop`

<details><summary>Code</summary>

```typescript
function estimateCoords(cm, pos) {
    var left = 0;
    pos = clipPos(cm.doc, pos);
    if (!cm.options.lineWrapping) { left = charWidth(cm.display) * pos.ch; }
    var lineObj = getLine(cm.doc, pos.line);
    var top = heightAtLine(lineObj) + paddingTop(cm.display);
    return {left: left, right: left, top: top, bottom: top + lineObj.height}
  }
```
</details>

### `PosWithInfo(line: any, ch: any, sticky: any, outside: any, xRel: any): Pos`

**Parameters:**

- **`line`** `any`
- **`ch`** `any`
- **`sticky`** `any`
- **`outside`** `any`
- **`xRel`** `any`

**Returns:** `Pos`

**Calls:**

- `Pos`

<details><summary>Code</summary>

```typescript
function PosWithInfo(line, ch, sticky, outside, xRel) {
    var pos = Pos(line, ch, sticky);
    pos.xRel = xRel;
    if (outside) { pos.outside = outside; }
    return pos
  }
```
</details>

### `coordsChar(cm: any, x: any, y: any): any`

**Parameters:**

- **`cm`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `any`

**Calls:**

- `PosWithInfo`
- `lineAtHeight`
- `getLine`
- `coordsCharInner`
- `collapsedSpanAround`
- `collapsed.find`

<details><summary>Code</summary>

```typescript
function coordsChar(cm, x, y) {
    var doc = cm.doc;
    y += cm.display.viewOffset;
    if (y < 0) { return PosWithInfo(doc.first, 0, null, -1, -1) }
    var lineN = lineAtHeight(doc, y), last = doc.first + doc.size - 1;
    if (lineN > last)
      { return PosWithInfo(doc.first + doc.size - 1, getLine(doc, last).text.length, null, 1, 1) }
    if (x < 0) { x = 0; }

    var lineObj = getLine(doc, lineN);
    for (;;) {
      var found = coordsCharInner(cm, lineObj, lineN, x, y);
      var collapsed = collapsedSpanAround(lineObj, found.ch + (found.xRel > 0 || found.outside > 0 ? 1 : 0));
      if (!collapsed) { return found }
      var rangeEnd = collapsed.find(1);
      if (rangeEnd.line == lineN) { return rangeEnd }
      lineObj = getLine(doc, lineN = rangeEnd.line);
    }
  }
```
</details>

### `wrappedLineExtent(cm: any, lineObj: any, preparedMeasure: any, y: any): { begin: any; end: any; }`

**Parameters:**

- **`cm`** `any`
- **`lineObj`** `any`
- **`preparedMeasure`** `any`
- **`y`** `any`

**Returns:** `{ begin: any; end: any; }`

**Calls:**

- `widgetTopHeight`
- `findFirst`
- `measureCharPrepared`

<details><summary>Code</summary>

```typescript
function wrappedLineExtent(cm, lineObj, preparedMeasure, y) {
    y -= widgetTopHeight(lineObj);
    var end = lineObj.text.length;
    var begin = findFirst(function (ch) { return measureCharPrepared(cm, preparedMeasure, ch - 1).bottom <= y; }, end, 0);
    end = findFirst(function (ch) { return measureCharPrepared(cm, preparedMeasure, ch).top > y; }, begin, end);
    return {begin: begin, end: end}
  }
```
</details>

### `wrappedLineExtentChar(cm: any, lineObj: any, preparedMeasure: any, target: any): { begin: any; end: any; }`

**Parameters:**

- **`cm`** `any`
- **`lineObj`** `any`
- **`preparedMeasure`** `any`
- **`target`** `any`

**Returns:** `{ begin: any; end: any; }`

**Calls:**

- `prepareMeasureForLine`
- `intoCoordSystem`
- `measureCharPrepared`
- `wrappedLineExtent`

<details><summary>Code</summary>

```typescript
function wrappedLineExtentChar(cm, lineObj, preparedMeasure, target) {
    if (!preparedMeasure) { preparedMeasure = prepareMeasureForLine(cm, lineObj); }
    var targetTop = intoCoordSystem(cm, lineObj, measureCharPrepared(cm, preparedMeasure, target), "line").top;
    return wrappedLineExtent(cm, lineObj, preparedMeasure, targetTop)
  }
```
</details>

### `boxIsAfter(box: any, x: any, y: any, left: any): boolean`

**Parameters:**

- **`box`** `any`
- **`x`** `any`
- **`y`** `any`
- **`left`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function boxIsAfter(box, x, y, left) {
    return box.bottom <= y ? false : box.top > y ? true : (left ? box.left : box.right) > x
  }
```
</details>

### `coordsCharInner(cm: any, lineObj: any, lineNo: any, x: any, y: any): Pos`

**Parameters:**

- **`cm`** `any`
- **`lineObj`** `any`
- **`lineNo`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `Pos`

**Calls:**

- `heightAtLine`
- `prepareMeasureForLine`
- `widgetTopHeight`
- `getOrder`
- `complex_call_112437`
- `findFirst`
- `measureCharPrepared`
- `boxIsAfter`
- `cursorCoords`
- `Pos`
- `skipExtendingChars`
- `PosWithInfo`

**Internal Comments:**
```
// Move y into line-local coordinate space (x3)
// When directly calling `measureCharPrepared`, we have to adjust (x2)
// for the widgets at this line. (x2)
// If the line isn't plain left-to-right text, first figure out
// which bidi section the coordinates fall into.
// The awkward -1 offsets are needed because findFirst (called (x3)
// on these below) will treat its first bound as inclusive, (x3)
// second as exclusive, but we want to actually address the (x3)
// characters in the part's range (x3)
// A binary search to find the first character whose bounding box (x2)
// starts after the coordinates. If we run across any whose box wrap (x2)
// the coordinates, store that. (x2)
// If a box around the coordinates was found, use that
// Distinguish coordinates nearer to the left or right side of the box (x2)
// (Adjust for extended bound, if necessary.)
// To determine which side to associate with, get the box to the (x3)
// left of the character and compare it's vertical position to the (x3)
// coordinates (x3)
// Now get accurate coordinates for this place, in order to get a (x2)
// base X position (x2)
```

<details><summary>Code</summary>

```typescript
function coordsCharInner(cm, lineObj, lineNo, x, y) {
    // Move y into line-local coordinate space
    y -= heightAtLine(lineObj);
    var preparedMeasure = prepareMeasureForLine(cm, lineObj);
    // When directly calling `measureCharPrepared`, we have to adjust
    // for the widgets at this line.
    var widgetHeight = widgetTopHeight(lineObj);
    var begin = 0, end = lineObj.text.length, ltr = true;

    var order = getOrder(lineObj, cm.doc.direction);
    // If the line isn't plain left-to-right text, first figure out
    // which bidi section the coordinates fall into.
    if (order) {
      var part = (cm.options.lineWrapping ? coordsBidiPartWrapped : coordsBidiPart)
                   (cm, lineObj, lineNo, preparedMeasure, order, x, y);
      ltr = part.level != 1;
      // The awkward -1 offsets are needed because findFirst (called
      // on these below) will treat its first bound as inclusive,
      // second as exclusive, but we want to actually address the
      // characters in the part's range
      begin = ltr ? part.from : part.to - 1;
      end = ltr ? part.to : part.from - 1;
    }

    // A binary search to find the first character whose bounding box
    // starts after the coordinates. If we run across any whose box wrap
    // the coordinates, store that.
    var chAround = null, boxAround = null;
    var ch = findFirst(function (ch) {
      var box = measureCharPrepared(cm, preparedMeasure, ch);
      box.top += widgetHeight; box.bottom += widgetHeight;
      if (!boxIsAfter(box, x, y, false)) { return false }
      if (box.top <= y && box.left <= x) {
        chAround = ch;
        boxAround = box;
      }
      return true
    }, begin, end);

    var baseX, sticky, outside = false;
    // If a box around the coordinates was found, use that
    if (boxAround) {
      // Distinguish coordinates nearer to the left or right side of the box
      var atLeft = x - boxAround.left < boxAround.right - x, atStart = atLeft == ltr;
      ch = chAround + (atStart ? 0 : 1);
      sticky = atStart ? "after" : "before";
      baseX = atLeft ? boxAround.left : boxAround.right;
    } else {
      // (Adjust for extended bound, if necessary.)
      if (!ltr && (ch == end || ch == begin)) { ch++; }
      // To determine which side to associate with, get the box to the
      // left of the character and compare it's vertical position to the
      // coordinates
      sticky = ch == 0 ? "after" : ch == lineObj.text.length ? "before" :
        (measureCharPrepared(cm, preparedMeasure, ch - (ltr ? 1 : 0)).bottom + widgetHeight <= y) == ltr ?
        "after" : "before";
      // Now get accurate coordinates for this place, in order to get a
      // base X position
      var coords = cursorCoords(cm, Pos(lineNo, ch, sticky), "line", lineObj, preparedMeasure);
      baseX = coords.left;
      outside = y < coords.top ? -1 : y >= coords.bottom ? 1 : 0;
    }

    ch = skipExtendingChars(lineObj.text, ch, 1);
    return PosWithInfo(lineNo, ch, sticky, outside, x - baseX)
  }
```
</details>

### `coordsBidiPart(cm: any, lineObj: any, lineNo: any, preparedMeasure: any, order: any, x: any, y: any): any`

**Parameters:**

- **`cm`** `any`
- **`lineObj`** `any`
- **`lineNo`** `any`
- **`preparedMeasure`** `any`
- **`order`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `any`

**Calls:**

- `findFirst`
- `boxIsAfter`
- `cursorCoords`
- `Pos`

**Internal Comments:**
```
// Bidi parts are sorted left-to-right, and in a non-line-wrapping (x2)
// situation, we can take this ordering to correspond to the visual (x2)
// ordering. This finds the first part whose end is after the given (x2)
// coordinates. (x2)
// If this isn't the first part, the part's start is also after
// the coordinates, and the coordinates aren't on the same line as
// that start, move one part back.
```

<details><summary>Code</summary>

```typescript
function coordsBidiPart(cm, lineObj, lineNo, preparedMeasure, order, x, y) {
    // Bidi parts are sorted left-to-right, and in a non-line-wrapping
    // situation, we can take this ordering to correspond to the visual
    // ordering. This finds the first part whose end is after the given
    // coordinates.
    var index = findFirst(function (i) {
      var part = order[i], ltr = part.level != 1;
      return boxIsAfter(cursorCoords(cm, Pos(lineNo, ltr ? part.to : part.from, ltr ? "before" : "after"),
                                     "line", lineObj, preparedMeasure), x, y, true)
    }, 0, order.length - 1);
    var part = order[index];
    // If this isn't the first part, the part's start is also after
    // the coordinates, and the coordinates aren't on the same line as
    // that start, move one part back.
    if (index > 0) {
      var ltr = part.level != 1;
      var start = cursorCoords(cm, Pos(lineNo, ltr ? part.from : part.to, ltr ? "after" : "before"),
                               "line", lineObj, preparedMeasure);
      if (boxIsAfter(start, x, y, true) && start.top > y)
        { part = order[index - 1]; }
    }
    return part
  }
```
</details>

### `coordsBidiPartWrapped(cm: any, lineObj: any, _lineNo: any, preparedMeasure: any, order: any, x: any, y: any): any`

**Parameters:**

- **`cm`** `any`
- **`lineObj`** `any`
- **`_lineNo`** `any`
- **`preparedMeasure`** `any`
- **`order`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `any`

**Calls:**

- `wrappedLineExtent`
- `/\s/.test`
- `lineObj.text.charAt`
- `measureCharPrepared`
- `Math.min`
- `Math.max`

**Internal Comments:**
```
// In a wrapped line, rtl text on wrapping boundaries can do things (x2)
// that don't correspond to the ordering in our `order` array at (x2)
// all, so a binary search doesn't work, and we want to return a (x2)
// part that only spans one line so that the binary search in (x2)
// coordsCharInner is safe. As such, we first find the extent of the (x2)
// wrapped line, and then do a flat search in which we discard any (x2)
// spans that aren't on the line. (x2)
// Weigh against spans ending before this, so that they are only (x2)
// picked if nothing ends after (x2)
// Clip the part to the wrapped line.
```

<details><summary>Code</summary>

```typescript
function coordsBidiPartWrapped(cm, lineObj, _lineNo, preparedMeasure, order, x, y) {
    // In a wrapped line, rtl text on wrapping boundaries can do things
    // that don't correspond to the ordering in our `order` array at
    // all, so a binary search doesn't work, and we want to return a
    // part that only spans one line so that the binary search in
    // coordsCharInner is safe. As such, we first find the extent of the
    // wrapped line, and then do a flat search in which we discard any
    // spans that aren't on the line.
    var ref = wrappedLineExtent(cm, lineObj, preparedMeasure, y);
    var begin = ref.begin;
    var end = ref.end;
    if (/\s/.test(lineObj.text.charAt(end - 1))) { end--; }
    var part = null, closestDist = null;
    for (var i = 0; i < order.length; i++) {
      var p = order[i];
      if (p.from >= end || p.to <= begin) { continue }
      var ltr = p.level != 1;
      var endX = measureCharPrepared(cm, preparedMeasure, ltr ? Math.min(end, p.to) - 1 : Math.max(begin, p.from)).right;
      // Weigh against spans ending before this, so that they are only
      // picked if nothing ends after
      var dist = endX < x ? x - endX + 1e9 : endX - x;
      if (!part || closestDist > dist) {
        part = p;
        closestDist = dist;
      }
    }
    if (!part) { part = order[order.length - 1]; }
    // Clip the part to the wrapped line.
    if (part.from < begin) { part = {from: begin, to: part.to, level: part.level}; }
    if (part.to > end) { part = {from: part.from, to: end, level: part.level}; }
    return part
  }
```
</details>

### `textHeight(display: any): any`

**Parameters:**

- **`display`** `any`

**Returns:** `any`

**Calls:**

- `elt`
- `measureText.appendChild`
- `document.createTextNode`
- `removeChildrenAndAdd`
- `removeChildren`

**Internal Comments:**
```
// Measure a bunch of lines, for browsers that compute
// fractional heights.
```

<details><summary>Code</summary>

```typescript
function textHeight(display) {
    if (display.cachedTextHeight != null) { return display.cachedTextHeight }
    if (measureText == null) {
      measureText = elt("pre", null, "CodeMirror-line-like");
      // Measure a bunch of lines, for browsers that compute
      // fractional heights.
      for (var i = 0; i < 49; ++i) {
        measureText.appendChild(document.createTextNode("x"));
        measureText.appendChild(elt("br"));
      }
      measureText.appendChild(document.createTextNode("x"));
    }
    removeChildrenAndAdd(display.measure, measureText);
    var height = measureText.offsetHeight / 50;
    if (height > 3) { display.cachedTextHeight = height; }
    removeChildren(display.measure);
    return height || 1
  }
```
</details>

### `charWidth(display: any): any`

**Parameters:**

- **`display`** `any`

**Returns:** `any`

**Calls:**

- `elt`
- `removeChildrenAndAdd`
- `anchor.getBoundingClientRect`

<details><summary>Code</summary>

```typescript
function charWidth(display) {
    if (display.cachedCharWidth != null) { return display.cachedCharWidth }
    var anchor = elt("span", "xxxxxxxxxx");
    var pre = elt("pre", [anchor], "CodeMirror-line-like");
    removeChildrenAndAdd(display.measure, pre);
    var rect = anchor.getBoundingClientRect(), width = (rect.right - rect.left) / 10;
    if (width > 2) { display.cachedCharWidth = width; }
    return width || 10
  }
```
</details>

### `getDimensions(cm: any): { fixedPos: number; gutterTotalWidth: any; gutterLeft: {}; gutterWidth: {}; wrapperWidth: any; }`

**Parameters:**

- **`cm`** `any`

**Returns:** `{ fixedPos: number; gutterTotalWidth: any; gutterLeft: {}; gutterWidth: {}; wrapperWidth: any; }`

**Calls:**

- `compensateForHScroll`

<details><summary>Code</summary>

```typescript
function getDimensions(cm) {
    var d = cm.display, left = {}, width = {};
    var gutterLeft = d.gutters.clientLeft;
    for (var n = d.gutters.firstChild, i = 0; n; n = n.nextSibling, ++i) {
      var id = cm.display.gutterSpecs[i].className;
      left[id] = n.offsetLeft + n.clientLeft + gutterLeft;
      width[id] = n.clientWidth;
    }
    return {fixedPos: compensateForHScroll(d),
            gutterTotalWidth: d.gutters.offsetWidth,
            gutterLeft: left,
            gutterWidth: width,
            wrapperWidth: d.wrapper.clientWidth}
  }
```
</details>

### `compensateForHScroll(display: any): number`

**Parameters:**

- **`display`** `any`

**Returns:** `number`

**Calls:**

- `display.scroller.getBoundingClientRect`
- `display.sizer.getBoundingClientRect`

<details><summary>Code</summary>

```typescript
function compensateForHScroll(display) {
    return display.scroller.getBoundingClientRect().left - display.sizer.getBoundingClientRect().left
  }
```
</details>

### `estimateHeight(cm: any): (line: any) => any`

**Parameters:**

- **`cm`** `any`

**Returns:** `(line: any) => any`

**Calls:**

- `textHeight`
- `Math.max`
- `charWidth`
- `lineIsHidden`
- `Math.ceil`

<details><summary>Code</summary>

```typescript
function estimateHeight(cm) {
    var th = textHeight(cm.display), wrapping = cm.options.lineWrapping;
    var perLine = wrapping && Math.max(5, cm.display.scroller.clientWidth / charWidth(cm.display) - 3);
    return function (line) {
      if (lineIsHidden(cm.doc, line)) { return 0 }

      var widgetsHeight = 0;
      if (line.widgets) { for (var i = 0; i < line.widgets.length; i++) {
        if (line.widgets[i].height) { widgetsHeight += line.widgets[i].height; }
      } }

      if (wrapping)
        { return widgetsHeight + (Math.ceil(line.text.length / perLine) || 1) * th }
      else
        { return widgetsHeight + th }
    }
  }
```
</details>

### `estimateLineHeights(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `estimateHeight`
- `doc.iter`
- `est`
- `updateLineHeight`

<details><summary>Code</summary>

```typescript
function estimateLineHeights(cm) {
    var doc = cm.doc, est = estimateHeight(cm);
    doc.iter(function (line) {
      var estHeight = est(line);
      if (estHeight != line.height) { updateLineHeight(line, estHeight); }
    });
  }
```
</details>

### `posFromMouse(cm: any, e: any, liberal: any, forRect: any): any`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`
- **`liberal`** `any`
- **`forRect`** `any`

**Returns:** `any`

**Calls:**

- `e_target(e).getAttribute`
- `display.lineSpace.getBoundingClientRect`
- `coordsChar`
- `getLine`
- `countColumn`
- `Pos`
- `Math.max`
- `Math.round`
- `paddingH`
- `charWidth`

**Internal Comments:**
```
// Fails unpredictably on IE[67] when mouse is dragged around quickly.
```

<details><summary>Code</summary>

```typescript
function posFromMouse(cm, e, liberal, forRect) {
    var display = cm.display;
    if (!liberal && e_target(e).getAttribute("cm-not-content") == "true") { return null }

    var x, y, space = display.lineSpace.getBoundingClientRect();
    // Fails unpredictably on IE[67] when mouse is dragged around quickly.
    try { x = e.clientX - space.left; y = e.clientY - space.top; }
    catch (e$1) { return null }
    var coords = coordsChar(cm, x, y), line;
    if (forRect && coords.xRel > 0 && (line = getLine(cm.doc, coords.line).text).length == coords.ch) {
      var colDiff = countColumn(line, line.length, cm.options.tabSize) - line.length;
      coords = Pos(coords.line, Math.max(0, Math.round((x - paddingH(cm.display).left) / charWidth(cm.display)) - colDiff));
    }
    return coords
  }
```
</details>

### `findViewIndex(cm: any, n: any): number`

**Parameters:**

- **`cm`** `any`
- **`n`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function findViewIndex(cm, n) {
    if (n >= cm.display.viewTo) { return null }
    n -= cm.display.viewFrom;
    if (n < 0) { return null }
    var view = cm.display.view;
    for (var i = 0; i < view.length; i++) {
      n -= view[i].size;
      if (n < 0) { return i }
    }
  }
```
</details>

### `regChange(cm: any, from: any, to: any, lendiff: any): void`

**Parameters:**

- **`cm`** `any`
- **`from`** `any`
- **`to`** `any`
- **`lendiff`** `any`

**Returns:** `void`

**Calls:**

- `visualLineNo`
- `resetView`
- `visualLineEndNo`
- `viewCuttingPoint`
- `display.view.slice`
- `display.view.slice(0, cutTop.index)
          .concat(buildViewArray(cm, cutTop.lineN, cutBot.lineN))
          .concat`

<details><summary>Code</summary>

```typescript
function regChange(cm, from, to, lendiff) {
    if (from == null) { from = cm.doc.first; }
    if (to == null) { to = cm.doc.first + cm.doc.size; }
    if (!lendiff) { lendiff = 0; }

    var display = cm.display;
    if (lendiff && to < display.viewTo &&
        (display.updateLineNumbers == null || display.updateLineNumbers > from))
      { display.updateLineNumbers = from; }

    cm.curOp.viewChanged = true;

    if (from >= display.viewTo) { // Change after
      if (sawCollapsedSpans && visualLineNo(cm.doc, from) < display.viewTo)
        { resetView(cm); }
    } else if (to <= display.viewFrom) { // Change before
      if (sawCollapsedSpans && visualLineEndNo(cm.doc, to + lendiff) > display.viewFrom) {
        resetView(cm);
      } else {
        display.viewFrom += lendiff;
        display.viewTo += lendiff;
      }
    } else if (from <= display.viewFrom && to >= display.viewTo) { // Full overlap
      resetView(cm);
    } else if (from <= display.viewFrom) { // Top overlap
      var cut = viewCuttingPoint(cm, to, to + lendiff, 1);
      if (cut) {
        display.view = display.view.slice(cut.index);
        display.viewFrom = cut.lineN;
        display.viewTo += lendiff;
      } else {
        resetView(cm);
      }
    } else if (to >= display.viewTo) { // Bottom overlap
      var cut$1 = viewCuttingPoint(cm, from, from, -1);
      if (cut$1) {
        display.view = display.view.slice(0, cut$1.index);
        display.viewTo = cut$1.lineN;
      } else {
        resetView(cm);
      }
    } else { // Gap in the middle
      var cutTop = viewCuttingPoint(cm, from, from, -1);
      var cutBot = viewCuttingPoint(cm, to, to + lendiff, 1);
      if (cutTop && cutBot) {
        display.view = display.view.slice(0, cutTop.index)
          .concat(buildViewArray(cm, cutTop.lineN, cutBot.lineN))
          .concat(display.view.slice(cutBot.index));
        display.viewTo += lendiff;
      } else {
        resetView(cm);
      }
    }

    var ext = display.externalMeasured;
    if (ext) {
      if (to < ext.lineN)
        { ext.lineN += lendiff; }
      else if (from < ext.lineN + ext.size)
        { display.externalMeasured = null; }
    }
  }
```
</details>

### `regLineChange(cm: any, line: any, type: any): void`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `findViewIndex`
- `indexOf`
- `arr.push`

<details><summary>Code</summary>

```typescript
function regLineChange(cm, line, type) {
    cm.curOp.viewChanged = true;
    var display = cm.display, ext = cm.display.externalMeasured;
    if (ext && line >= ext.lineN && line < ext.lineN + ext.size)
      { display.externalMeasured = null; }

    if (line < display.viewFrom || line >= display.viewTo) { return }
    var lineView = display.view[findViewIndex(cm, line)];
    if (lineView.node == null) { return }
    var arr = lineView.changes || (lineView.changes = []);
    if (indexOf(arr, type) == -1) { arr.push(type); }
  }
```
</details>

### `resetView(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function resetView(cm) {
    cm.display.viewFrom = cm.display.viewTo = cm.doc.first;
    cm.display.view = [];
    cm.display.viewOffset = 0;
  }
```
</details>

### `viewCuttingPoint(cm: any, oldN: any, newN: any, dir: any): { index: number; lineN: any; }`

**Parameters:**

- **`cm`** `any`
- **`oldN`** `any`
- **`newN`** `any`
- **`dir`** `any`

**Returns:** `{ index: number; lineN: any; }`

**Calls:**

- `findViewIndex`
- `visualLineNo`

<details><summary>Code</summary>

```typescript
function viewCuttingPoint(cm, oldN, newN, dir) {
    var index = findViewIndex(cm, oldN), diff, view = cm.display.view;
    if (!sawCollapsedSpans || newN == cm.doc.first + cm.doc.size)
      { return {index: index, lineN: newN} }
    var n = cm.display.viewFrom;
    for (var i = 0; i < index; i++)
      { n += view[i].size; }
    if (n != oldN) {
      if (dir > 0) {
        if (index == view.length - 1) { return null }
        diff = (n + view[index].size) - oldN;
        index++;
      } else {
        diff = n - oldN;
      }
      oldN += diff; newN += diff;
    }
    while (visualLineNo(cm.doc, newN) != newN) {
      if (index == (dir < 0 ? 0 : view.length - 1)) { return null }
      newN += dir * view[index - (dir < 0 ? 1 : 0)].size;
      index += dir;
    }
    return {index: index, lineN: newN}
  }
```
</details>

### `adjustView(cm: any, from: any, to: any): void`

**Parameters:**

- **`cm`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `void`

**Calls:**

- `buildViewArray`
- `buildViewArray(cm, from, display.viewFrom).concat`
- `display.view.slice`
- `findViewIndex`
- `display.view.concat`

<details><summary>Code</summary>

```typescript
function adjustView(cm, from, to) {
    var display = cm.display, view = display.view;
    if (view.length == 0 || from >= display.viewTo || to <= display.viewFrom) {
      display.view = buildViewArray(cm, from, to);
      display.viewFrom = from;
    } else {
      if (display.viewFrom > from)
        { display.view = buildViewArray(cm, from, display.viewFrom).concat(display.view); }
      else if (display.viewFrom < from)
        { display.view = display.view.slice(findViewIndex(cm, from)); }
      display.viewFrom = from;
      if (display.viewTo < to)
        { display.view = display.view.concat(buildViewArray(cm, display.viewTo, to)); }
      else if (display.viewTo > to)
        { display.view = display.view.slice(0, findViewIndex(cm, to)); }
    }
    display.viewTo = to;
  }
```
</details>

### `countDirtyView(cm: any): number`

**Parameters:**

- **`cm`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function countDirtyView(cm) {
    var view = cm.display.view, dirty = 0;
    for (var i = 0; i < view.length; i++) {
      var lineView = view[i];
      if (!lineView.hidden && (!lineView.node || lineView.changes)) { ++dirty; }
    }
    return dirty
  }
```
</details>

### `updateSelection(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.display.input.showSelection`
- `cm.display.input.prepareSelection`

<details><summary>Code</summary>

```typescript
function updateSelection(cm) {
    cm.display.input.showSelection(cm.display.input.prepareSelection());
  }
```
</details>

### `prepareSelection(cm: any, primary: any): { cursors: DocumentFragment; selection: DocumentFragment; }`

**Parameters:**

- **`cm`** `any`
- **`primary`** `any`

**Returns:** `{ cursors: DocumentFragment; selection: DocumentFragment; }`

**Calls:**

- `document.createDocumentFragment`
- `range.from`
- `range.to`
- `range.empty`
- `customCursor`
- `drawSelectionCursor`
- `drawSelectionRange`

<details><summary>Code</summary>

```typescript
function prepareSelection(cm, primary) {
    if ( primary === void 0 ) primary = true;

    var doc = cm.doc, result = {};
    var curFragment = result.cursors = document.createDocumentFragment();
    var selFragment = result.selection = document.createDocumentFragment();

    var customCursor = cm.options.$customCursor;
    if (customCursor) { primary = true; }
    for (var i = 0; i < doc.sel.ranges.length; i++) {
      if (!primary && i == doc.sel.primIndex) { continue }
      var range = doc.sel.ranges[i];
      if (range.from().line >= cm.display.viewTo || range.to().line < cm.display.viewFrom) { continue }
      var collapsed = range.empty();
      if (customCursor) {
        var head = customCursor(cm, range);
        if (head) { drawSelectionCursor(cm, head, curFragment); }
      } else if (collapsed || cm.options.showCursorWhenSelecting) {
        drawSelectionCursor(cm, range.head, curFragment);
      }
      if (!collapsed)
        { drawSelectionRange(cm, range, selFragment); }
    }
    return result
  }
```
</details>

### `drawSelectionCursor(cm: any, head: any, output: any): void`

**Parameters:**

- **`cm`** `any`
- **`head`** `any`
- **`output`** `any`

**Returns:** `void`

**Calls:**

- `cursorCoords`
- `output.appendChild`
- `elt`
- `Math.max`
- `/\bcm-fat-cursor\b/.test`
- `cm.getWrapperElement`
- `charCoords`
- `cm.defaultCharWidth`

**Internal Comments:**
```
// Secondary cursor, shown when on a 'jump' in bi-directional text (x2)
```

<details><summary>Code</summary>

```typescript
function drawSelectionCursor(cm, head, output) {
    var pos = cursorCoords(cm, head, "div", null, null, !cm.options.singleCursorHeightPerLine);

    var cursor = output.appendChild(elt("div", "\u00a0", "CodeMirror-cursor"));
    cursor.style.left = pos.left + "px";
    cursor.style.top = pos.top + "px";
    cursor.style.height = Math.max(0, pos.bottom - pos.top) * cm.options.cursorHeight + "px";

    if (/\bcm-fat-cursor\b/.test(cm.getWrapperElement().className)) {
      var charPos = charCoords(cm, head, "div", null, null);
      var width = charPos.right - charPos.left;
      cursor.style.width = (width > 0 ? width : cm.defaultCharWidth()) + "px";
    }

    if (pos.other) {
      // Secondary cursor, shown when on a 'jump' in bi-directional text
      var otherCursor = output.appendChild(elt("div", "\u00a0", "CodeMirror-cursor CodeMirror-secondarycursor"));
      otherCursor.style.display = "";
      otherCursor.style.left = pos.other.left + "px";
      otherCursor.style.top = pos.other.top + "px";
      otherCursor.style.height = (pos.other.bottom - pos.other.top) * .85 + "px";
    }
  }
```
</details>

### `cmpCoords(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function cmpCoords(a, b) { return a.top - b.top || a.left - b.left }
```
</details>

### `drawSelectionRange(cm: any, range: any, output: any): void`

**Parameters:**

- **`cm`** `any`
- **`range`** `any`
- **`output`** `any`

**Returns:** `void`

**Calls:**

- `document.createDocumentFragment`
- `paddingH`
- `Math.max`
- `displayWidth`
- `Math.round`
- `fragment.appendChild`
- `elt`
- `getLine`
- `charCoords`
- `Pos`
- `wrappedLineExtentChar`
- `/\s/.test`
- `lineObj.text.charAt`
- `coords`
- `getOrder`
- `iterateBidiSections`
- `add`
- `wrapX`
- `cmpCoords`
- `range.from`
- `range.to`
- `drawForLine`
- `visualLine`
- `output.appendChild`

<details><summary>Code</summary>

```typescript
function drawSelectionRange(cm, range, output) {
    var display = cm.display, doc = cm.doc;
    var fragment = document.createDocumentFragment();
    var padding = paddingH(cm.display), leftSide = padding.left;
    var rightSide = Math.max(display.sizerWidth, displayWidth(cm) - display.sizer.offsetLeft) - padding.right;
    var docLTR = doc.direction == "ltr";

    function add(left, top, width, bottom) {
      if (top < 0) { top = 0; }
      top = Math.round(top);
      bottom = Math.round(bottom);
      fragment.appendChild(elt("div", null, "CodeMirror-selected", ("position: absolute; left: " + left + "px;\n                             top: " + top + "px; width: " + (width == null ? rightSide - left : width) + "px;\n                             height: " + (bottom - top) + "px")));
    }

    function drawForLine(line, fromArg, toArg) {
      var lineObj = getLine(doc, line);
      var lineLen = lineObj.text.length;
      var start, end;
      function coords(ch, bias) {
        return charCoords(cm, Pos(line, ch), "div", lineObj, bias)
      }

      function wrapX(pos, dir, side) {
        var extent = wrappedLineExtentChar(cm, lineObj, null, pos);
        var prop = (dir == "ltr") == (side == "after") ? "left" : "right";
        var ch = side == "after" ? extent.begin : extent.end - (/\s/.test(lineObj.text.charAt(extent.end - 1)) ? 2 : 1);
        return coords(ch, prop)[prop]
      }

      var order = getOrder(lineObj, doc.direction);
      iterateBidiSections(order, fromArg || 0, toArg == null ? lineLen : toArg, function (from, to, dir, i) {
        var ltr = dir == "ltr";
        var fromPos = coords(from, ltr ? "left" : "right");
        var toPos = coords(to - 1, ltr ? "right" : "left");

        var openStart = fromArg == null && from == 0, openEnd = toArg == null && to == lineLen;
        var first = i == 0, last = !order || i == order.length - 1;
        if (toPos.top - fromPos.top <= 3) { // Single line
          var openLeft = (docLTR ? openStart : openEnd) && first;
          var openRight = (docLTR ? openEnd : openStart) && last;
          var left = openLeft ? leftSide : (ltr ? fromPos : toPos).left;
          var right = openRight ? rightSide : (ltr ? toPos : fromPos).right;
          add(left, fromPos.top, right - left, fromPos.bottom);
        } else { // Multiple lines
          var topLeft, topRight, botLeft, botRight;
          if (ltr) {
            topLeft = docLTR && openStart && first ? leftSide : fromPos.left;
            topRight = docLTR ? rightSide : wrapX(from, dir, "before");
            botLeft = docLTR ? leftSide : wrapX(to, dir, "after");
            botRight = docLTR && openEnd && last ? rightSide : toPos.right;
          } else {
            topLeft = !docLTR ? leftSide : wrapX(from, dir, "before");
            topRight = !docLTR && openStart && first ? rightSide : fromPos.right;
            botLeft = !docLTR && openEnd && last ? leftSide : toPos.left;
            botRight = !docLTR ? rightSide : wrapX(to, dir, "after");
          }
          add(topLeft, fromPos.top, topRight - topLeft, fromPos.bottom);
          if (fromPos.bottom < toPos.top) { add(leftSide, fromPos.bottom, null, toPos.top); }
          add(botLeft, toPos.top, botRight - botLeft, toPos.bottom);
        }

        if (!start || cmpCoords(fromPos, start) < 0) { start = fromPos; }
        if (cmpCoords(toPos, start) < 0) { start = toPos; }
        if (!end || cmpCoords(fromPos, end) < 0) { end = fromPos; }
        if (cmpCoords(toPos, end) < 0) { end = toPos; }
      });
      return {start: start, end: end}
    }

    var sFrom = range.from(), sTo = range.to();
    if (sFrom.line == sTo.line) {
      drawForLine(sFrom.line, sFrom.ch, sTo.ch);
    } else {
      var fromLine = getLine(doc, sFrom.line), toLine = getLine(doc, sTo.line);
      var singleVLine = visualLine(fromLine) == visualLine(toLine);
      var leftEnd = drawForLine(sFrom.line, sFrom.ch, singleVLine ? fromLine.text.length + 1 : null).end;
      var rightStart = drawForLine(sTo.line, singleVLine ? 0 : null, sTo.ch).start;
      if (singleVLine) {
        if (leftEnd.top < rightStart.top - 2) {
          add(leftEnd.right, leftEnd.top, null, leftEnd.bottom);
          add(leftSide, rightStart.top, rightStart.left, rightStart.bottom);
        } else {
          add(leftEnd.right, leftEnd.top, rightStart.left - leftEnd.right, leftEnd.bottom);
        }
      }
      if (leftEnd.bottom < rightStart.top)
        { add(leftSide, leftEnd.bottom, null, rightStart.top); }
    }

    output.appendChild(fragment);
  }
```
</details>

### `add(left: any, top: any, width: any, bottom: any): void`

**Parameters:**

- **`left`** `any`
- **`top`** `any`
- **`width`** `any`
- **`bottom`** `any`

**Returns:** `void`

**Calls:**

- `Math.round`
- `fragment.appendChild`
- `elt`

<details><summary>Code</summary>

```typescript
function add(left, top, width, bottom) {
      if (top < 0) { top = 0; }
      top = Math.round(top);
      bottom = Math.round(bottom);
      fragment.appendChild(elt("div", null, "CodeMirror-selected", ("position: absolute; left: " + left + "px;\n                             top: " + top + "px; width: " + (width == null ? rightSide - left : width) + "px;\n                             height: " + (bottom - top) + "px")));
    }
```
</details>

### `drawForLine(line: any, fromArg: any, toArg: any): { start: undefined; end: undefined; }`

**Parameters:**

- **`line`** `any`
- **`fromArg`** `any`
- **`toArg`** `any`

**Returns:** `{ start: undefined; end: undefined; }`

**Calls:**

- `getLine`
- `charCoords`
- `Pos`
- `wrappedLineExtentChar`
- `/\s/.test`
- `lineObj.text.charAt`
- `coords`
- `getOrder`
- `iterateBidiSections`
- `add`
- `wrapX`
- `cmpCoords`

<details><summary>Code</summary>

```typescript
function drawForLine(line, fromArg, toArg) {
      var lineObj = getLine(doc, line);
      var lineLen = lineObj.text.length;
      var start, end;
      function coords(ch, bias) {
        return charCoords(cm, Pos(line, ch), "div", lineObj, bias)
      }

      function wrapX(pos, dir, side) {
        var extent = wrappedLineExtentChar(cm, lineObj, null, pos);
        var prop = (dir == "ltr") == (side == "after") ? "left" : "right";
        var ch = side == "after" ? extent.begin : extent.end - (/\s/.test(lineObj.text.charAt(extent.end - 1)) ? 2 : 1);
        return coords(ch, prop)[prop]
      }

      var order = getOrder(lineObj, doc.direction);
      iterateBidiSections(order, fromArg || 0, toArg == null ? lineLen : toArg, function (from, to, dir, i) {
        var ltr = dir == "ltr";
        var fromPos = coords(from, ltr ? "left" : "right");
        var toPos = coords(to - 1, ltr ? "right" : "left");

        var openStart = fromArg == null && from == 0, openEnd = toArg == null && to == lineLen;
        var first = i == 0, last = !order || i == order.length - 1;
        if (toPos.top - fromPos.top <= 3) { // Single line
          var openLeft = (docLTR ? openStart : openEnd) && first;
          var openRight = (docLTR ? openEnd : openStart) && last;
          var left = openLeft ? leftSide : (ltr ? fromPos : toPos).left;
          var right = openRight ? rightSide : (ltr ? toPos : fromPos).right;
          add(left, fromPos.top, right - left, fromPos.bottom);
        } else { // Multiple lines
          var topLeft, topRight, botLeft, botRight;
          if (ltr) {
            topLeft = docLTR && openStart && first ? leftSide : fromPos.left;
            topRight = docLTR ? rightSide : wrapX(from, dir, "before");
            botLeft = docLTR ? leftSide : wrapX(to, dir, "after");
            botRight = docLTR && openEnd && last ? rightSide : toPos.right;
          } else {
            topLeft = !docLTR ? leftSide : wrapX(from, dir, "before");
            topRight = !docLTR && openStart && first ? rightSide : fromPos.right;
            botLeft = !docLTR && openEnd && last ? leftSide : toPos.left;
            botRight = !docLTR ? rightSide : wrapX(to, dir, "after");
          }
          add(topLeft, fromPos.top, topRight - topLeft, fromPos.bottom);
          if (fromPos.bottom < toPos.top) { add(leftSide, fromPos.bottom, null, toPos.top); }
          add(botLeft, toPos.top, botRight - botLeft, toPos.bottom);
        }

        if (!start || cmpCoords(fromPos, start) < 0) { start = fromPos; }
        if (cmpCoords(toPos, start) < 0) { start = toPos; }
        if (!end || cmpCoords(fromPos, end) < 0) { end = fromPos; }
        if (cmpCoords(toPos, end) < 0) { end = toPos; }
      });
      return {start: start, end: end}
    }
```
</details>

### `coords(ch: any, bias: any): any`

**Parameters:**

- **`ch`** `any`
- **`bias`** `any`

**Returns:** `any`

**Calls:**

- `charCoords`
- `Pos`

<details><summary>Code</summary>

```typescript
function coords(ch, bias) {
        return charCoords(cm, Pos(line, ch), "div", lineObj, bias)
      }
```
</details>

### `wrapX(pos: any, dir: any, side: any): any`

**Parameters:**

- **`pos`** `any`
- **`dir`** `any`
- **`side`** `any`

**Returns:** `any`

**Calls:**

- `wrappedLineExtentChar`
- `/\s/.test`
- `lineObj.text.charAt`
- `coords`

<details><summary>Code</summary>

```typescript
function wrapX(pos, dir, side) {
        var extent = wrappedLineExtentChar(cm, lineObj, null, pos);
        var prop = (dir == "ltr") == (side == "after") ? "left" : "right";
        var ch = side == "after" ? extent.begin : extent.end - (/\s/.test(lineObj.text.charAt(extent.end - 1)) ? 2 : 1);
        return coords(ch, prop)[prop]
      }
```
</details>

### `restartBlink(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `clearInterval`
- `setInterval`
- `cm.hasFocus`
- `onBlur`

<details><summary>Code</summary>

```typescript
function restartBlink(cm) {
    if (!cm.state.focused) { return }
    var display = cm.display;
    clearInterval(display.blinker);
    var on = true;
    display.cursorDiv.style.visibility = "";
    if (cm.options.cursorBlinkRate > 0)
      { display.blinker = setInterval(function () {
        if (!cm.hasFocus()) { onBlur(cm); }
        display.cursorDiv.style.visibility = (on = !on) ? "" : "hidden";
      }, cm.options.cursorBlinkRate); }
    else if (cm.options.cursorBlinkRate < 0)
      { display.cursorDiv.style.visibility = "hidden"; }
  }
```
</details>

### `ensureFocus(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.hasFocus`
- `cm.display.input.focus`
- `onFocus`

<details><summary>Code</summary>

```typescript
function ensureFocus(cm) {
    if (!cm.hasFocus()) {
      cm.display.input.focus();
      if (!cm.state.focused) { onFocus(cm); }
    }
  }
```
</details>

### `delayBlurEvent(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `setTimeout`
- `onBlur`

<details><summary>Code</summary>

```typescript
function delayBlurEvent(cm) {
    cm.state.delayingBlurEvent = true;
    setTimeout(function () { if (cm.state.delayingBlurEvent) {
      cm.state.delayingBlurEvent = false;
      if (cm.state.focused) { onBlur(cm); }
    } }, 100);
  }
```
</details>

### `onFocus(cm: any, e: any): void`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signal`
- `addClass`
- `cm.display.input.reset`
- `setTimeout`
- `cm.display.input.receivedFocus`
- `restartBlink`

**Internal Comments:**
```
// This test prevents this from firing when a context
// menu is closed (since the input reset would kill the
// select-all detection hack)
```

<details><summary>Code</summary>

```typescript
function onFocus(cm, e) {
    if (cm.state.delayingBlurEvent && !cm.state.draggingText) { cm.state.delayingBlurEvent = false; }

    if (cm.options.readOnly == "nocursor") { return }
    if (!cm.state.focused) {
      signal(cm, "focus", cm, e);
      cm.state.focused = true;
      addClass(cm.display.wrapper, "CodeMirror-focused");
      // This test prevents this from firing when a context
      // menu is closed (since the input reset would kill the
      // select-all detection hack)
      if (!cm.curOp && cm.display.selForContextMenu != cm.doc.sel) {
        cm.display.input.reset();
        if (webkit) { setTimeout(function () { return cm.display.input.reset(true); }, 20); } // Issue #1730
      }
      cm.display.input.receivedFocus();
    }
    restartBlink(cm);
  }
```
</details>

### `onBlur(cm: any, e: any): void`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signal`
- `rmClass`
- `clearInterval`
- `setTimeout`

<details><summary>Code</summary>

```typescript
function onBlur(cm, e) {
    if (cm.state.delayingBlurEvent) { return }

    if (cm.state.focused) {
      signal(cm, "blur", cm, e);
      cm.state.focused = false;
      rmClass(cm.display.wrapper, "CodeMirror-focused");
    }
    clearInterval(cm.display.blinker);
    setTimeout(function () { if (!cm.state.focused) { cm.display.shift = false; } }, 150);
  }
```
</details>

### `updateHeightsInViewport(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `Math.max`
- `display.scroller.getBoundingClientRect`
- `display.lineDiv.getBoundingClientRect`
- `cur.node.getBoundingClientRect`
- `cur.text.firstChild.getBoundingClientRect`
- `updateLineHeight`
- `updateWidgetHeight`
- `Math.ceil`
- `charWidth`
- `Math.abs`

**Internal Comments:**
```
// Check that lines don't extend past the right of the current
// editor width
```

<details><summary>Code</summary>

```typescript
function updateHeightsInViewport(cm) {
    var display = cm.display;
    var prevBottom = display.lineDiv.offsetTop;
    var viewTop = Math.max(0, display.scroller.getBoundingClientRect().top);
    var oldHeight = display.lineDiv.getBoundingClientRect().top;
    var mustScroll = 0;
    for (var i = 0; i < display.view.length; i++) {
      var cur = display.view[i], wrapping = cm.options.lineWrapping;
      var height = (void 0), width = 0;
      if (cur.hidden) { continue }
      oldHeight += cur.line.height;
      if (ie && ie_version < 8) {
        var bot = cur.node.offsetTop + cur.node.offsetHeight;
        height = bot - prevBottom;
        prevBottom = bot;
      } else {
        var box = cur.node.getBoundingClientRect();
        height = box.bottom - box.top;
        // Check that lines don't extend past the right of the current
        // editor width
        if (!wrapping && cur.text.firstChild)
          { width = cur.text.firstChild.getBoundingClientRect().right - box.left - 1; }
      }
      var diff = cur.line.height - height;
      if (diff > .005 || diff < -.005) {
        if (oldHeight < viewTop) { mustScroll -= diff; }
        updateLineHeight(cur.line, height);
        updateWidgetHeight(cur.line);
        if (cur.rest) { for (var j = 0; j < cur.rest.length; j++)
          { updateWidgetHeight(cur.rest[j]); } }
      }
      if (width > cm.display.sizerWidth) {
        var chWidth = Math.ceil(width / charWidth(cm.display));
        if (chWidth > cm.display.maxLineLength) {
          cm.display.maxLineLength = chWidth;
          cm.display.maxLine = cur.line;
          cm.display.maxLineChanged = true;
        }
      }
    }
    if (Math.abs(mustScroll) > 2) { display.scroller.scrollTop += mustScroll; }
  }
```
</details>

### `updateWidgetHeight(line: any): void`

**Parameters:**

- **`line`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function updateWidgetHeight(line) {
    if (line.widgets) { for (var i = 0; i < line.widgets.length; ++i) {
      var w = line.widgets[i], parent = w.node.parentNode;
      if (parent) { w.height = parent.offsetHeight; }
    } }
  }
```
</details>

### `visibleLines(display: any, doc: any, viewport: any): { from: any; to: number; }`

**Parameters:**

- **`display`** `any`
- **`doc`** `any`
- **`viewport`** `any`

**Returns:** `{ from: any; to: number; }`

**Calls:**

- `Math.max`
- `Math.floor`
- `paddingTop`
- `lineAtHeight`
- `heightAtLine`
- `getLine`
- `Math.min`
- `doc.lastLine`

**Internal Comments:**
```
// Ensure is a {from: {line, ch}, to: {line, ch}} object, and
// forces those lines into the viewport (if possible).
```

<details><summary>Code</summary>

```typescript
function visibleLines(display, doc, viewport) {
    var top = viewport && viewport.top != null ? Math.max(0, viewport.top) : display.scroller.scrollTop;
    top = Math.floor(top - paddingTop(display));
    var bottom = viewport && viewport.bottom != null ? viewport.bottom : top + display.wrapper.clientHeight;

    var from = lineAtHeight(doc, top), to = lineAtHeight(doc, bottom);
    // Ensure is a {from: {line, ch}, to: {line, ch}} object, and
    // forces those lines into the viewport (if possible).
    if (viewport && viewport.ensure) {
      var ensureFrom = viewport.ensure.from.line, ensureTo = viewport.ensure.to.line;
      if (ensureFrom < from) {
        from = ensureFrom;
        to = lineAtHeight(doc, heightAtLine(getLine(doc, ensureFrom)) + display.wrapper.clientHeight);
      } else if (Math.min(ensureTo, doc.lastLine()) >= to) {
        from = lineAtHeight(doc, heightAtLine(getLine(doc, ensureTo)) - display.wrapper.clientHeight);
        to = ensureTo;
      }
    }
    return {from: from, to: Math.max(to, from + 1)}
  }
```
</details>

### `maybeScrollWindow(cm: any, rect: any): void`

**Parameters:**

- **`cm`** `any`
- **`rect`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `display.sizer.getBoundingClientRect`
- `elt`
- `paddingTop`
- `scrollGap`
- `Math.max`
- `cm.display.lineSpace.appendChild`
- `scrollNode.scrollIntoView`
- `cm.display.lineSpace.removeChild`

<details><summary>Code</summary>

```typescript
function maybeScrollWindow(cm, rect) {
    if (signalDOMEvent(cm, "scrollCursorIntoView")) { return }

    var display = cm.display, box = display.sizer.getBoundingClientRect(), doScroll = null;
    if (rect.top + box.top < 0) { doScroll = true; }
    else if (rect.bottom + box.top > (window.innerHeight || document.documentElement.clientHeight)) { doScroll = false; }
    if (doScroll != null && !phantom) {
      var scrollNode = elt("div", "\u200b", null, ("position: absolute;\n                         top: " + (rect.top - display.viewOffset - paddingTop(cm.display)) + "px;\n                         height: " + (rect.bottom - rect.top + scrollGap(cm) + display.barHeight) + "px;\n                         left: " + (rect.left) + "px; width: " + (Math.max(2, rect.right - rect.left)) + "px;"));
      cm.display.lineSpace.appendChild(scrollNode);
      scrollNode.scrollIntoView(doScroll);
      cm.display.lineSpace.removeChild(scrollNode);
    }
  }
```
</details>

### `scrollPosIntoView(cm: any, pos: any, end: any, margin: any): { left: number; top: number; right: number; bottom: any; }`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`end`** `any`
- **`margin`** `any`

**Returns:** `{ left: number; top: number; right: number; bottom: any; }`

**Calls:**

- `Pos`
- `cursorCoords`
- `Math.min`
- `Math.max`
- `calculateScrollPos`
- `updateScrollTop`
- `Math.abs`
- `setScrollLeft`

**Internal Comments:**
```
// Set pos and end to the cursor positions around the character pos sticks to (x3)
// If pos.sticky == "before", that is around pos.ch - 1, otherwise around pos.ch (x3)
// If pos == Pos(_, 0, "before"), pos and end are unchanged (x3)
```

<details><summary>Code</summary>

```typescript
function scrollPosIntoView(cm, pos, end, margin) {
    if (margin == null) { margin = 0; }
    var rect;
    if (!cm.options.lineWrapping && pos == end) {
      // Set pos and end to the cursor positions around the character pos sticks to
      // If pos.sticky == "before", that is around pos.ch - 1, otherwise around pos.ch
      // If pos == Pos(_, 0, "before"), pos and end are unchanged
      end = pos.sticky == "before" ? Pos(pos.line, pos.ch + 1, "before") : pos;
      pos = pos.ch ? Pos(pos.line, pos.sticky == "before" ? pos.ch - 1 : pos.ch, "after") : pos;
    }
    for (var limit = 0; limit < 5; limit++) {
      var changed = false;
      var coords = cursorCoords(cm, pos);
      var endCoords = !end || end == pos ? coords : cursorCoords(cm, end);
      rect = {left: Math.min(coords.left, endCoords.left),
              top: Math.min(coords.top, endCoords.top) - margin,
              right: Math.max(coords.left, endCoords.left),
              bottom: Math.max(coords.bottom, endCoords.bottom) + margin};
      var scrollPos = calculateScrollPos(cm, rect);
      var startTop = cm.doc.scrollTop, startLeft = cm.doc.scrollLeft;
      if (scrollPos.scrollTop != null) {
        updateScrollTop(cm, scrollPos.scrollTop);
        if (Math.abs(cm.doc.scrollTop - startTop) > 1) { changed = true; }
      }
      if (scrollPos.scrollLeft != null) {
        setScrollLeft(cm, scrollPos.scrollLeft);
        if (Math.abs(cm.doc.scrollLeft - startLeft) > 1) { changed = true; }
      }
      if (!changed) { break }
    }
    return rect
  }
```
</details>

### `scrollIntoView(cm: any, rect: any): void`

**Parameters:**

- **`cm`** `any`
- **`rect`** `any`

**Returns:** `void`

**Calls:**

- `calculateScrollPos`
- `updateScrollTop`
- `setScrollLeft`

<details><summary>Code</summary>

```typescript
function scrollIntoView(cm, rect) {
    var scrollPos = calculateScrollPos(cm, rect);
    if (scrollPos.scrollTop != null) { updateScrollTop(cm, scrollPos.scrollTop); }
    if (scrollPos.scrollLeft != null) { setScrollLeft(cm, scrollPos.scrollLeft); }
  }
```
</details>

### `calculateScrollPos(cm: any, rect: any): { scrollTop: any; scrollLeft: number; }`

**Parameters:**

- **`cm`** `any`
- **`rect`** `any`

**Returns:** `{ scrollTop: any; scrollLeft: number; }`

**Calls:**

- `textHeight`
- `displayHeight`
- `paddingVert`
- `Math.min`
- `displayWidth`
- `Math.max`

<details><summary>Code</summary>

```typescript
function calculateScrollPos(cm, rect) {
    var display = cm.display, snapMargin = textHeight(cm.display);
    if (rect.top < 0) { rect.top = 0; }
    var screentop = cm.curOp && cm.curOp.scrollTop != null ? cm.curOp.scrollTop : display.scroller.scrollTop;
    var screen = displayHeight(cm), result = {};
    if (rect.bottom - rect.top > screen) { rect.bottom = rect.top + screen; }
    var docBottom = cm.doc.height + paddingVert(display);
    var atTop = rect.top < snapMargin, atBottom = rect.bottom > docBottom - snapMargin;
    if (rect.top < screentop) {
      result.scrollTop = atTop ? 0 : rect.top;
    } else if (rect.bottom > screentop + screen) {
      var newTop = Math.min(rect.top, (atBottom ? docBottom : rect.bottom) - screen);
      if (newTop != screentop) { result.scrollTop = newTop; }
    }

    var gutterSpace = cm.options.fixedGutter ? 0 : display.gutters.offsetWidth;
    var screenleft = cm.curOp && cm.curOp.scrollLeft != null ? cm.curOp.scrollLeft : display.scroller.scrollLeft - gutterSpace;
    var screenw = displayWidth(cm) - display.gutters.offsetWidth;
    var tooWide = rect.right - rect.left > screenw;
    if (tooWide) { rect.right = rect.left + screenw; }
    if (rect.left < 10)
      { result.scrollLeft = 0; }
    else if (rect.left < screenleft)
      { result.scrollLeft = Math.max(0, rect.left + gutterSpace - (tooWide ? 0 : 10)); }
    else if (rect.right > screenw + screenleft - 3)
      { result.scrollLeft = rect.right + (tooWide ? 0 : 10) - screenw; }
    return result
  }
```
</details>

### `addToScrollTop(cm: any, top: any): void`

**Parameters:**

- **`cm`** `any`
- **`top`** `any`

**Returns:** `void`

**Calls:**

- `resolveScrollToPos`

<details><summary>Code</summary>

```typescript
function addToScrollTop(cm, top) {
    if (top == null) { return }
    resolveScrollToPos(cm);
    cm.curOp.scrollTop = (cm.curOp.scrollTop == null ? cm.doc.scrollTop : cm.curOp.scrollTop) + top;
  }
```
</details>

### `ensureCursorVisible(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `resolveScrollToPos`
- `cm.getCursor`

<details><summary>Code</summary>

```typescript
function ensureCursorVisible(cm) {
    resolveScrollToPos(cm);
    var cur = cm.getCursor();
    cm.curOp.scrollToPos = {from: cur, to: cur, margin: cm.options.cursorScrollMargin};
  }
```
</details>

### `scrollToCoords(cm: any, x: any, y: any): void`

**Parameters:**

- **`cm`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `void`

**Calls:**

- `resolveScrollToPos`

<details><summary>Code</summary>

```typescript
function scrollToCoords(cm, x, y) {
    if (x != null || y != null) { resolveScrollToPos(cm); }
    if (x != null) { cm.curOp.scrollLeft = x; }
    if (y != null) { cm.curOp.scrollTop = y; }
  }
```
</details>

### `scrollToRange(cm: any, range: any): void`

**Parameters:**

- **`cm`** `any`
- **`range`** `any`

**Returns:** `void`

**Calls:**

- `resolveScrollToPos`

<details><summary>Code</summary>

```typescript
function scrollToRange(cm, range) {
    resolveScrollToPos(cm);
    cm.curOp.scrollToPos = range;
  }
```
</details>

### `resolveScrollToPos(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `estimateCoords`
- `scrollToCoordsRange`

<details><summary>Code</summary>

```typescript
function resolveScrollToPos(cm) {
    var range = cm.curOp.scrollToPos;
    if (range) {
      cm.curOp.scrollToPos = null;
      var from = estimateCoords(cm, range.from), to = estimateCoords(cm, range.to);
      scrollToCoordsRange(cm, from, to, range.margin);
    }
  }
```
</details>

### `scrollToCoordsRange(cm: any, from: any, to: any, margin: any): void`

**Parameters:**

- **`cm`** `any`
- **`from`** `any`
- **`to`** `any`
- **`margin`** `any`

**Returns:** `void`

**Calls:**

- `calculateScrollPos`
- `Math.min`
- `Math.max`
- `scrollToCoords`

<details><summary>Code</summary>

```typescript
function scrollToCoordsRange(cm, from, to, margin) {
    var sPos = calculateScrollPos(cm, {
      left: Math.min(from.left, to.left),
      top: Math.min(from.top, to.top) - margin,
      right: Math.max(from.right, to.right),
      bottom: Math.max(from.bottom, to.bottom) + margin
    });
    scrollToCoords(cm, sPos.scrollLeft, sPos.scrollTop);
  }
```
</details>

### `updateScrollTop(cm: any, val: any): void`

**Parameters:**

- **`cm`** `any`
- **`val`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `updateDisplaySimple`
- `setScrollTop`
- `startWorker`

<details><summary>Code</summary>

```typescript
function updateScrollTop(cm, val) {
    if (Math.abs(cm.doc.scrollTop - val) < 2) { return }
    if (!gecko) { updateDisplaySimple(cm, {top: val}); }
    setScrollTop(cm, val, true);
    if (gecko) { updateDisplaySimple(cm); }
    startWorker(cm, 100);
  }
```
</details>

### `setScrollTop(cm: any, val: any, forceScroll: any): void`

**Parameters:**

- **`cm`** `any`
- **`val`** `any`
- **`forceScroll`** `any`

**Returns:** `void`

**Calls:**

- `Math.max`
- `Math.min`
- `cm.display.scrollbars.setScrollTop`

<details><summary>Code</summary>

```typescript
function setScrollTop(cm, val, forceScroll) {
    val = Math.max(0, Math.min(cm.display.scroller.scrollHeight - cm.display.scroller.clientHeight, val));
    if (cm.display.scroller.scrollTop == val && !forceScroll) { return }
    cm.doc.scrollTop = val;
    cm.display.scrollbars.setScrollTop(val);
    if (cm.display.scroller.scrollTop != val) { cm.display.scroller.scrollTop = val; }
  }
```
</details>

### `setScrollLeft(cm: any, val: any, isScroller: any, forceScroll: any): void`

**Parameters:**

- **`cm`** `any`
- **`val`** `any`
- **`isScroller`** `any`
- **`forceScroll`** `any`

**Returns:** `void`

**Calls:**

- `Math.max`
- `Math.min`
- `Math.abs`
- `alignHorizontally`
- `cm.display.scrollbars.setScrollLeft`

<details><summary>Code</summary>

```typescript
function setScrollLeft(cm, val, isScroller, forceScroll) {
    val = Math.max(0, Math.min(val, cm.display.scroller.scrollWidth - cm.display.scroller.clientWidth));
    if ((isScroller ? val == cm.doc.scrollLeft : Math.abs(cm.doc.scrollLeft - val) < 2) && !forceScroll) { return }
    cm.doc.scrollLeft = val;
    alignHorizontally(cm);
    if (cm.display.scroller.scrollLeft != val) { cm.display.scroller.scrollLeft = val; }
    cm.display.scrollbars.setScrollLeft(val);
  }
```
</details>

### `measureForScrollbars(cm: any): { clientHeight: any; viewHeight: any; scrollWidth: any; clientWidth: any; viewWidth: any; barLeft: any; docHeight: number; scrollHeight: any; nativeBarWidth: any; gutterWidth: any; }`

**Parameters:**

- **`cm`** `any`

**Returns:** `{ clientHeight: any; viewHeight: any; scrollWidth: any; clientWidth: any; viewWidth: any; barLeft: any; docHeight: number; scrollHeight: any; nativeBarWidth: any; gutterWidth: any; }`

**Calls:**

- `Math.round`
- `paddingVert`
- `scrollGap`

<details><summary>Code</summary>

```typescript
function measureForScrollbars(cm) {
    var d = cm.display, gutterW = d.gutters.offsetWidth;
    var docH = Math.round(cm.doc.height + paddingVert(cm.display));
    return {
      clientHeight: d.scroller.clientHeight,
      viewHeight: d.wrapper.clientHeight,
      scrollWidth: d.scroller.scrollWidth, clientWidth: d.scroller.clientWidth,
      viewWidth: d.wrapper.clientWidth,
      barLeft: cm.options.fixedGutter ? gutterW : 0,
      docHeight: docH,
      scrollHeight: docH + scrollGap(cm) + d.barHeight,
      nativeBarWidth: d.nativeBarWidth,
      gutterWidth: gutterW
    }
  }
```
</details>

### `NativeScrollbars(place: any, scroll: any, cm: any): void`

**Parameters:**

- **`place`** `any`
- **`scroll`** `any`
- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `elt`
- `place`
- `on`
- `scroll`

**Internal Comments:**
```
// Need to set a minimum width to see the scrollbar on IE7 (but must not set it on IE8).
```

<details><summary>Code</summary>

```typescript
function(place, scroll, cm) {
    this.cm = cm;
    var vert = this.vert = elt("div", [elt("div", null, null, "min-width: 1px")], "CodeMirror-vscrollbar");
    var horiz = this.horiz = elt("div", [elt("div", null, null, "height: 100%; min-height: 1px")], "CodeMirror-hscrollbar");
    vert.tabIndex = horiz.tabIndex = -1;
    place(vert); place(horiz);

    on(vert, "scroll", function () {
      if (vert.clientHeight) { scroll(vert.scrollTop, "vertical"); }
    });
    on(horiz, "scroll", function () {
      if (horiz.clientWidth) { scroll(horiz.scrollLeft, "horizontal"); }
    });

    this.checkedZeroWidth = false;
    // Need to set a minimum width to see the scrollbar on IE7 (but must not set it on IE8).
    if (ie && ie_version < 8) { this.horiz.style.minHeight = this.vert.style.minWidth = "18px"; }
  }
```
</details>

### `maybeDisable(): void`

**Returns:** `void`

**Calls:**

- `bar.getBoundingClientRect`
- `document.elementFromPoint`
- `delay.set`

**Internal Comments:**
```
// To find out whether the scrollbar is still visible, we (x2)
// check whether the element under the pixel in the bottom (x2)
// right corner of the scrollbar box is the scrollbar box (x2)
// itself (when the bar is still visible) or its filler child (x2)
// (when the bar is hidden). If it is still visible, we keep (x2)
// it enabled, if it's hidden, we disable pointer events. (x2)
```

<details><summary>Code</summary>

```typescript
function maybeDisable() {
      // To find out whether the scrollbar is still visible, we
      // check whether the element under the pixel in the bottom
      // right corner of the scrollbar box is the scrollbar box
      // itself (when the bar is still visible) or its filler child
      // (when the bar is hidden). If it is still visible, we keep
      // it enabled, if it's hidden, we disable pointer events.
      var box = bar.getBoundingClientRect();
      var elt = type == "vert" ? document.elementFromPoint(box.right - 1, (box.top + box.bottom) / 2)
          : document.elementFromPoint((box.right + box.left) / 2, box.bottom - 1);
      if (elt != bar) { bar.style.pointerEvents = "none"; }
      else { delay.set(1000, maybeDisable); }
    }
```
</details>

### `NullScrollbars(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `updateScrollbars(cm: any, measure: any): void`

**Parameters:**

- **`cm`** `any`
- **`measure`** `any`

**Returns:** `void`

**Calls:**

- `measureForScrollbars`
- `updateScrollbarsInner`
- `updateHeightsInViewport`

<details><summary>Code</summary>

```typescript
function updateScrollbars(cm, measure) {
    if (!measure) { measure = measureForScrollbars(cm); }
    var startWidth = cm.display.barWidth, startHeight = cm.display.barHeight;
    updateScrollbarsInner(cm, measure);
    for (var i = 0; i < 4 && startWidth != cm.display.barWidth || startHeight != cm.display.barHeight; i++) {
      if (startWidth != cm.display.barWidth && cm.options.lineWrapping)
        { updateHeightsInViewport(cm); }
      updateScrollbarsInner(cm, measureForScrollbars(cm));
      startWidth = cm.display.barWidth; startHeight = cm.display.barHeight;
    }
  }
```
</details>

### `updateScrollbarsInner(cm: any, measure: any): void`

**Parameters:**

- **`cm`** `any`
- **`measure`** `any`

**Returns:** `void`

**Calls:**

- `d.scrollbars.update`

<details><summary>Code</summary>

```typescript
function updateScrollbarsInner(cm, measure) {
    var d = cm.display;
    var sizes = d.scrollbars.update(measure);

    d.sizer.style.paddingRight = (d.barWidth = sizes.right) + "px";
    d.sizer.style.paddingBottom = (d.barHeight = sizes.bottom) + "px";
    d.heightForcer.style.borderBottom = sizes.bottom + "px solid transparent";

    if (sizes.right && sizes.bottom) {
      d.scrollbarFiller.style.display = "block";
      d.scrollbarFiller.style.height = sizes.bottom + "px";
      d.scrollbarFiller.style.width = sizes.right + "px";
    } else { d.scrollbarFiller.style.display = ""; }
    if (sizes.bottom && cm.options.coverGutterNextToScrollbar && cm.options.fixedGutter) {
      d.gutterFiller.style.display = "block";
      d.gutterFiller.style.height = sizes.bottom + "px";
      d.gutterFiller.style.width = measure.gutterWidth + "px";
    } else { d.gutterFiller.style.display = ""; }
  }
```
</details>

### `initScrollbars(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.display.scrollbars.clear`
- `rmClass`
- `cm.display.wrapper.insertBefore`
- `on`
- `setTimeout`
- `cm.display.input.focus`
- `node.setAttribute`
- `setScrollLeft`
- `updateScrollTop`
- `addClass`

**Internal Comments:**
```
// Prevent clicks in the scrollbars from killing focus (x3)
```

<details><summary>Code</summary>

```typescript
function initScrollbars(cm) {
    if (cm.display.scrollbars) {
      cm.display.scrollbars.clear();
      if (cm.display.scrollbars.addClass)
        { rmClass(cm.display.wrapper, cm.display.scrollbars.addClass); }
    }

    cm.display.scrollbars = new scrollbarModel[cm.options.scrollbarStyle](function (node) {
      cm.display.wrapper.insertBefore(node, cm.display.scrollbarFiller);
      // Prevent clicks in the scrollbars from killing focus
      on(node, "mousedown", function () {
        if (cm.state.focused) { setTimeout(function () { return cm.display.input.focus(); }, 0); }
      });
      node.setAttribute("cm-not-content", "true");
    }, function (pos, axis) {
      if (axis == "horizontal") { setScrollLeft(cm, pos); }
      else { updateScrollTop(cm, pos); }
    }, cm);
    if (cm.display.scrollbars.addClass)
      { addClass(cm.display.wrapper, cm.display.scrollbars.addClass); }
  }
```
</details>

### `startOperation(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `pushOperation`

<details><summary>Code</summary>

```typescript
function startOperation(cm) {
    cm.curOp = {
      cm: cm,
      viewChanged: false,      // Flag that indicates that lines might need to be redrawn
      startHeight: cm.doc.height, // Used to detect need to update scrollbar
      forceUpdate: false,      // Used to force a redraw
      updateInput: 0,       // Whether to reset the input textarea
      typing: false,           // Whether this reset should be careful to leave existing text (for compositing)
      changeObjs: null,        // Accumulated changes, for firing change events
      cursorActivityHandlers: null, // Set of handlers to fire cursorActivity on
      cursorActivityCalled: 0, // Tracks which cursorActivity handlers have been called already
      selectionChanged: false, // Whether the selection needs to be redrawn
      updateMaxLine: false,    // Set when the widest line needs to be determined anew
      scrollLeft: null, scrollTop: null, // Intermediate scroll position, not pushed to DOM yet
      scrollToPos: null,       // Used to scroll to a specific position
      focus: false,
      id: ++nextOpId,          // Unique ID
      markArrays: null         // Used by addMarkedSpan
    };
    pushOperation(cm.curOp);
  }
```
</details>

### `endOperation(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `finishOperation`
- `endOperations`

<details><summary>Code</summary>

```typescript
function endOperation(cm) {
    var op = cm.curOp;
    if (op) { finishOperation(op, function (group) {
      for (var i = 0; i < group.ops.length; i++)
        { group.ops[i].cm.curOp = null; }
      endOperations(group);
    }); }
  }
```
</details>

### `endOperations(group: any): void`

**Parameters:**

- **`group`** `any`

**Returns:** `void`

**Calls:**

- `endOperation_R1`
- `endOperation_W1`
- `endOperation_R2`
- `endOperation_W2`
- `endOperation_finish`

<details><summary>Code</summary>

```typescript
function endOperations(group) {
    var ops = group.ops;
    for (var i = 0; i < ops.length; i++) // Read DOM
      { endOperation_R1(ops[i]); }
    for (var i$1 = 0; i$1 < ops.length; i$1++) // Write DOM (maybe)
      { endOperation_W1(ops[i$1]); }
    for (var i$2 = 0; i$2 < ops.length; i$2++) // Read DOM
      { endOperation_R2(ops[i$2]); }
    for (var i$3 = 0; i$3 < ops.length; i$3++) // Write DOM (maybe)
      { endOperation_W2(ops[i$3]); }
    for (var i$4 = 0; i$4 < ops.length; i$4++) // Read DOM
      { endOperation_finish(ops[i$4]); }
  }
```
</details>

### `endOperation_R1(op: any): void`

**Parameters:**

- **`op`** `any`

**Returns:** `void`

**Calls:**

- `maybeClipScrollbars`
- `findMaxLine`

<details><summary>Code</summary>

```typescript
function endOperation_R1(op) {
    var cm = op.cm, display = cm.display;
    maybeClipScrollbars(cm);
    if (op.updateMaxLine) { findMaxLine(cm); }

    op.mustUpdate = op.viewChanged || op.forceUpdate || op.scrollTop != null ||
      op.scrollToPos && (op.scrollToPos.from.line < display.viewFrom ||
                         op.scrollToPos.to.line >= display.viewTo) ||
      display.maxLineChanged && cm.options.lineWrapping;
    op.update = op.mustUpdate &&
      new DisplayUpdate(cm, op.mustUpdate && {top: op.scrollTop, ensure: op.scrollToPos}, op.forceUpdate);
  }
```
</details>

### `endOperation_W1(op: any): void`

**Parameters:**

- **`op`** `any`

**Returns:** `void`

**Calls:**

- `updateDisplayIfNeeded`

<details><summary>Code</summary>

```typescript
function endOperation_W1(op) {
    op.updatedDisplay = op.mustUpdate && updateDisplayIfNeeded(op.cm, op.update);
  }
```
</details>

### `endOperation_R2(op: any): void`

**Parameters:**

- **`op`** `any`

**Returns:** `void`

**Calls:**

- `updateHeightsInViewport`
- `measureForScrollbars`
- `measureChar`
- `Math.max`
- `scrollGap`
- `displayWidth`
- `display.input.prepareSelection`

**Internal Comments:**
```
// If the max line changed since it was last measured, measure it,
// and ensure the document's width matches it.
// updateDisplay_W2 will use these properties to do the actual resizing
```

<details><summary>Code</summary>

```typescript
function endOperation_R2(op) {
    var cm = op.cm, display = cm.display;
    if (op.updatedDisplay) { updateHeightsInViewport(cm); }

    op.barMeasure = measureForScrollbars(cm);

    // If the max line changed since it was last measured, measure it,
    // and ensure the document's width matches it.
    // updateDisplay_W2 will use these properties to do the actual resizing
    if (display.maxLineChanged && !cm.options.lineWrapping) {
      op.adjustWidthTo = measureChar(cm, display.maxLine, display.maxLine.text.length).left + 3;
      cm.display.sizerWidth = op.adjustWidthTo;
      op.barMeasure.scrollWidth =
        Math.max(display.scroller.clientWidth, display.sizer.offsetLeft + op.adjustWidthTo + scrollGap(cm) + cm.display.barWidth);
      op.maxScrollLeft = Math.max(0, display.sizer.offsetLeft + op.adjustWidthTo - displayWidth(cm));
    }

    if (op.updatedDisplay || op.selectionChanged)
      { op.preparedSelection = display.input.prepareSelection(); }
  }
```
</details>

### `endOperation_W2(op: any): void`

**Parameters:**

- **`op`** `any`

**Returns:** `void`

**Calls:**

- `setScrollLeft`
- `Math.min`
- `activeElt`
- `cm.display.input.showSelection`
- `updateScrollbars`
- `setDocumentHeight`
- `restartBlink`
- `cm.display.input.reset`
- `ensureFocus`

<details><summary>Code</summary>

```typescript
function endOperation_W2(op) {
    var cm = op.cm;

    if (op.adjustWidthTo != null) {
      cm.display.sizer.style.minWidth = op.adjustWidthTo + "px";
      if (op.maxScrollLeft < cm.doc.scrollLeft)
        { setScrollLeft(cm, Math.min(cm.display.scroller.scrollLeft, op.maxScrollLeft), true); }
      cm.display.maxLineChanged = false;
    }

    var takeFocus = op.focus && op.focus == activeElt();
    if (op.preparedSelection)
      { cm.display.input.showSelection(op.preparedSelection, takeFocus); }
    if (op.updatedDisplay || op.startHeight != cm.doc.height)
      { updateScrollbars(cm, op.barMeasure); }
    if (op.updatedDisplay)
      { setDocumentHeight(cm, op.barMeasure); }

    if (op.selectionChanged) { restartBlink(cm); }

    if (cm.state.focused && op.updateInput)
      { cm.display.input.reset(op.typing); }
    if (takeFocus) { ensureFocus(op.cm); }
  }
```
</details>

### `endOperation_finish(op: any): void`

**Parameters:**

- **`op`** `any`

**Returns:** `void`

**Calls:**

- `postUpdateDisplay`
- `setScrollTop`
- `setScrollLeft`
- `scrollPosIntoView`
- `clipPos`
- `maybeScrollWindow`
- `signal`
- `op.update.finish`

**Internal Comments:**
```
// Abort mouse wheel delta measurement, when scrolling explicitly
// Propagate the scroll position to the actual DOM scroller
// If we need to scroll a specific position into view, do so.
// Fire events for markers that are hidden/unidden by editing or (x2)
// undoing (x2)
// Fire change events, and delayed event handlers
```

<details><summary>Code</summary>

```typescript
function endOperation_finish(op) {
    var cm = op.cm, display = cm.display, doc = cm.doc;

    if (op.updatedDisplay) { postUpdateDisplay(cm, op.update); }

    // Abort mouse wheel delta measurement, when scrolling explicitly
    if (display.wheelStartX != null && (op.scrollTop != null || op.scrollLeft != null || op.scrollToPos))
      { display.wheelStartX = display.wheelStartY = null; }

    // Propagate the scroll position to the actual DOM scroller
    if (op.scrollTop != null) { setScrollTop(cm, op.scrollTop, op.forceScroll); }

    if (op.scrollLeft != null) { setScrollLeft(cm, op.scrollLeft, true, true); }
    // If we need to scroll a specific position into view, do so.
    if (op.scrollToPos) {
      var rect = scrollPosIntoView(cm, clipPos(doc, op.scrollToPos.from),
                                   clipPos(doc, op.scrollToPos.to), op.scrollToPos.margin);
      maybeScrollWindow(cm, rect);
    }

    // Fire events for markers that are hidden/unidden by editing or
    // undoing
    var hidden = op.maybeHiddenMarkers, unhidden = op.maybeUnhiddenMarkers;
    if (hidden) { for (var i = 0; i < hidden.length; ++i)
      { if (!hidden[i].lines.length) { signal(hidden[i], "hide"); } } }
    if (unhidden) { for (var i$1 = 0; i$1 < unhidden.length; ++i$1)
      { if (unhidden[i$1].lines.length) { signal(unhidden[i$1], "unhide"); } } }

    if (display.wrapper.offsetHeight)
      { doc.scrollTop = cm.display.scroller.scrollTop; }

    // Fire change events, and delayed event handlers
    if (op.changeObjs)
      { signal(cm, "changes", cm, op.changeObjs); }
    if (op.update)
      { op.update.finish(); }
  }
```
</details>

### `runInOp(cm: any, f: any): any`

**Parameters:**

- **`cm`** `any`
- **`f`** `any`

**Returns:** `any`

**Calls:**

- `f`
- `startOperation`
- `endOperation`

<details><summary>Code</summary>

```typescript
function runInOp(cm, f) {
    if (cm.curOp) { return f() }
    startOperation(cm);
    try { return f() }
    finally { endOperation(cm); }
  }
```
</details>

### `operation(cm: any, f: any): (...args: any[]) => any`

**Parameters:**

- **`cm`** `any`
- **`f`** `any`

**Returns:** `(...args: any[]) => any`

**Calls:**

- `f.apply`
- `startOperation`
- `endOperation`

<details><summary>Code</summary>

```typescript
function operation(cm, f) {
    return function() {
      if (cm.curOp) { return f.apply(cm, arguments) }
      startOperation(cm);
      try { return f.apply(cm, arguments) }
      finally { endOperation(cm); }
    }
  }
```
</details>

### `methodOp(f: any): (...args: any[]) => any`

**Parameters:**

- **`f`** `any`

**Returns:** `(...args: any[]) => any`

**Calls:**

- `f.apply`
- `startOperation`
- `endOperation`

<details><summary>Code</summary>

```typescript
function methodOp(f) {
    return function() {
      if (this.curOp) { return f.apply(this, arguments) }
      startOperation(this);
      try { return f.apply(this, arguments) }
      finally { endOperation(this); }
    }
  }
```
</details>

### `docMethodOp(f: any): (...args: any[]) => any`

**Parameters:**

- **`f`** `any`

**Returns:** `(...args: any[]) => any`

**Calls:**

- `f.apply`
- `startOperation`
- `endOperation`

<details><summary>Code</summary>

```typescript
function docMethodOp(f) {
    return function() {
      var cm = this.cm;
      if (!cm || cm.curOp) { return f.apply(this, arguments) }
      startOperation(cm);
      try { return f.apply(this, arguments) }
      finally { endOperation(cm); }
    }
  }
```
</details>

### `startWorker(cm: any, time: any): void`

**Parameters:**

- **`cm`** `any`
- **`time`** `any`

**Returns:** `void`

**Calls:**

- `cm.state.highlight.set`
- `bind`

<details><summary>Code</summary>

```typescript
function startWorker(cm, time) {
    if (cm.doc.highlightFrontier < cm.display.viewTo)
      { cm.state.highlight.set(time, bind(highlightWorker, cm)); }
  }
```
</details>

### `highlightWorker(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `getContextBefore`
- `doc.iter`
- `Math.min`
- `copyState`
- `highlightLine`
- `changedLines.push`
- `context.save`
- `context.nextLine`
- `processLine`
- `startWorker`
- `Math.max`
- `runInOp`
- `regLineChange`

<details><summary>Code</summary>

```typescript
function highlightWorker(cm) {
    var doc = cm.doc;
    if (doc.highlightFrontier >= cm.display.viewTo) { return }
    var end = +new Date + cm.options.workTime;
    var context = getContextBefore(cm, doc.highlightFrontier);
    var changedLines = [];

    doc.iter(context.line, Math.min(doc.first + doc.size, cm.display.viewTo + 500), function (line) {
      if (context.line >= cm.display.viewFrom) { // Visible
        var oldStyles = line.styles;
        var resetState = line.text.length > cm.options.maxHighlightLength ? copyState(doc.mode, context.state) : null;
        var highlighted = highlightLine(cm, line, context, true);
        if (resetState) { context.state = resetState; }
        line.styles = highlighted.styles;
        var oldCls = line.styleClasses, newCls = highlighted.classes;
        if (newCls) { line.styleClasses = newCls; }
        else if (oldCls) { line.styleClasses = null; }
        var ischange = !oldStyles || oldStyles.length != line.styles.length ||
          oldCls != newCls && (!oldCls || !newCls || oldCls.bgClass != newCls.bgClass || oldCls.textClass != newCls.textClass);
        for (var i = 0; !ischange && i < oldStyles.length; ++i) { ischange = oldStyles[i] != line.styles[i]; }
        if (ischange) { changedLines.push(context.line); }
        line.stateAfter = context.save();
        context.nextLine();
      } else {
        if (line.text.length <= cm.options.maxHighlightLength)
          { processLine(cm, line.text, context); }
        line.stateAfter = context.line % 5 == 0 ? context.save() : null;
        context.nextLine();
      }
      if (+new Date > end) {
        startWorker(cm, cm.options.workDelay);
        return true
      }
    });
    doc.highlightFrontier = context.line;
    doc.modeFrontier = Math.max(doc.modeFrontier, context.line);
    if (changedLines.length) { runInOp(cm, function () {
      for (var i = 0; i < changedLines.length; i++)
        { regLineChange(cm, changedLines[i], "text"); }
    }); }
  }
```
</details>

### `DisplayUpdate(cm: any, viewport: any, force: any): void`

**Parameters:**

- **`cm`** `any`
- **`viewport`** `any`
- **`force`** `any`

**Returns:** `void`

**Calls:**

- `visibleLines`
- `displayWidth`
- `getDimensions`

**Internal Comments:**
```
// Store some values that we'll need later (but don't want to force a relayout for) (x4)
```

<details><summary>Code</summary>

```typescript
function(cm, viewport, force) {
    var display = cm.display;

    this.viewport = viewport;
    // Store some values that we'll need later (but don't want to force a relayout for)
    this.visible = visibleLines(display, cm.doc, viewport);
    this.editorIsHidden = !display.wrapper.offsetWidth;
    this.wrapperHeight = display.wrapper.clientHeight;
    this.wrapperWidth = display.wrapper.clientWidth;
    this.oldDisplayWidth = displayWidth(cm);
    this.force = force;
    this.dims = getDimensions(cm);
    this.events = [];
  }
```
</details>

### `maybeClipScrollbars(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `scrollGap`

<details><summary>Code</summary>

```typescript
function maybeClipScrollbars(cm) {
    var display = cm.display;
    if (!display.scrollbarsClipped && display.scroller.offsetWidth) {
      display.nativeBarWidth = display.scroller.offsetWidth - display.scroller.clientWidth;
      display.heightForcer.style.height = scrollGap(cm) + "px";
      display.sizer.style.marginBottom = -display.nativeBarWidth + "px";
      display.sizer.style.borderRightWidth = scrollGap(cm) + "px";
      display.scrollbarsClipped = true;
    }
  }
```
</details>

### `selectionSnapshot(cm: any): { activeElt: Element; }`

**Parameters:**

- **`cm`** `any`

**Returns:** `{ activeElt: Element; }`

**Calls:**

- `cm.hasFocus`
- `activeElt`
- `contains`
- `window.getSelection`

<details><summary>Code</summary>

```typescript
function selectionSnapshot(cm) {
    if (cm.hasFocus()) { return null }
    var active = activeElt();
    if (!active || !contains(cm.display.lineDiv, active)) { return null }
    var result = {activeElt: active};
    if (window.getSelection) {
      var sel = window.getSelection();
      if (sel.anchorNode && sel.extend && contains(cm.display.lineDiv, sel.anchorNode)) {
        result.anchorNode = sel.anchorNode;
        result.anchorOffset = sel.anchorOffset;
        result.focusNode = sel.focusNode;
        result.focusOffset = sel.focusOffset;
      }
    }
    return result
  }
```
</details>

### `restoreSelection(snapshot: any): void`

**Parameters:**

- **`snapshot`** `any`

**Returns:** `void`

**Calls:**

- `activeElt`
- `snapshot.activeElt.focus`
- `/^(INPUT|TEXTAREA)$/.test`
- `contains`
- `window.getSelection`
- `document.createRange`
- `range.setEnd`
- `range.collapse`
- `sel.removeAllRanges`
- `sel.addRange`
- `sel.extend`

<details><summary>Code</summary>

```typescript
function restoreSelection(snapshot) {
    if (!snapshot || !snapshot.activeElt || snapshot.activeElt == activeElt()) { return }
    snapshot.activeElt.focus();
    if (!/^(INPUT|TEXTAREA)$/.test(snapshot.activeElt.nodeName) &&
        snapshot.anchorNode && contains(document.body, snapshot.anchorNode) && contains(document.body, snapshot.focusNode)) {
      var sel = window.getSelection(), range = document.createRange();
      range.setEnd(snapshot.anchorNode, snapshot.anchorOffset);
      range.collapse(false);
      sel.removeAllRanges();
      sel.addRange(range);
      sel.extend(snapshot.focusNode, snapshot.focusOffset);
    }
  }
```
</details>

### `updateDisplayIfNeeded(cm: any, update: any): boolean`

**Parameters:**

- **`cm`** `any`
- **`update`** `any`

**Returns:** `boolean`

**Calls:**

- `resetView`
- `countDirtyView`
- `maybeUpdateLineNumberWidth`
- `getDimensions`
- `Math.max`
- `Math.min`
- `visualLineNo`
- `visualLineEndNo`
- `adjustView`
- `heightAtLine`
- `getLine`
- `selectionSnapshot`
- `patchDisplay`
- `restoreSelection`
- `removeChildren`
- `startWorker`

**Internal Comments:**
```
// Bail out if the visible area is already rendered and nothing changed.
// Compute a suitable new viewport (from & to) (x2)
// Position the mover div to align with the current scroll position (x7)
// For big changes, we hide the enclosing element during the (x2)
// update, since that speeds up the operations on most browsers. (x2)
// There might have been a widget with a focused element that got (x3)
// hidden or updated, if so re-focus it. (x3)
// Prevent selection and cursors from interfering with the scroll (x3)
// width and height. (x3)
```

<details><summary>Code</summary>

```typescript
function updateDisplayIfNeeded(cm, update) {
    var display = cm.display, doc = cm.doc;

    if (update.editorIsHidden) {
      resetView(cm);
      return false
    }

    // Bail out if the visible area is already rendered and nothing changed.
    if (!update.force &&
        update.visible.from >= display.viewFrom && update.visible.to <= display.viewTo &&
        (display.updateLineNumbers == null || display.updateLineNumbers >= display.viewTo) &&
        display.renderedView == display.view && countDirtyView(cm) == 0)
      { return false }

    if (maybeUpdateLineNumberWidth(cm)) {
      resetView(cm);
      update.dims = getDimensions(cm);
    }

    // Compute a suitable new viewport (from & to)
    var end = doc.first + doc.size;
    var from = Math.max(update.visible.from - cm.options.viewportMargin, doc.first);
    var to = Math.min(end, update.visible.to + cm.options.viewportMargin);
    if (display.viewFrom < from && from - display.viewFrom < 20) { from = Math.max(doc.first, display.viewFrom); }
    if (display.viewTo > to && display.viewTo - to < 20) { to = Math.min(end, display.viewTo); }
    if (sawCollapsedSpans) {
      from = visualLineNo(cm.doc, from);
      to = visualLineEndNo(cm.doc, to);
    }

    var different = from != display.viewFrom || to != display.viewTo ||
      display.lastWrapHeight != update.wrapperHeight || display.lastWrapWidth != update.wrapperWidth;
    adjustView(cm, from, to);

    display.viewOffset = heightAtLine(getLine(cm.doc, display.viewFrom));
    // Position the mover div to align with the current scroll position
    cm.display.mover.style.top = display.viewOffset + "px";

    var toUpdate = countDirtyView(cm);
    if (!different && toUpdate == 0 && !update.force && display.renderedView == display.view &&
        (display.updateLineNumbers == null || display.updateLineNumbers >= display.viewTo))
      { return false }

    // For big changes, we hide the enclosing element during the
    // update, since that speeds up the operations on most browsers.
    var selSnapshot = selectionSnapshot(cm);
    if (toUpdate > 4) { display.lineDiv.style.display = "none"; }
    patchDisplay(cm, display.updateLineNumbers, update.dims);
    if (toUpdate > 4) { display.lineDiv.style.display = ""; }
    display.renderedView = display.view;
    // There might have been a widget with a focused element that got
    // hidden or updated, if so re-focus it.
    restoreSelection(selSnapshot);

    // Prevent selection and cursors from interfering with the scroll
    // width and height.
    removeChildren(display.cursorDiv);
    removeChildren(display.selectionDiv);
    display.gutters.style.height = display.sizer.style.minHeight = 0;

    if (different) {
      display.lastWrapHeight = update.wrapperHeight;
      display.lastWrapWidth = update.wrapperWidth;
      startWorker(cm, 400);
    }

    display.updateLineNumbers = null;

    return true
  }
```
</details>

### `postUpdateDisplay(cm: any, update: any): void`

**Parameters:**

- **`cm`** `any`
- **`update`** `any`

**Returns:** `void`

**Calls:**

- `displayWidth`
- `Math.min`
- `paddingVert`
- `displayHeight`
- `visibleLines`
- `updateDisplayIfNeeded`
- `updateHeightsInViewport`
- `measureForScrollbars`
- `updateSelection`
- `updateScrollbars`
- `setDocumentHeight`
- `update.signal`

**Internal Comments:**
```
// Clip forced viewport to actual scrollable area.
// Updated line heights might result in the drawn area not (x4)
// actually covering the viewport. Keep looping until it does. (x4)
```

<details><summary>Code</summary>

```typescript
function postUpdateDisplay(cm, update) {
    var viewport = update.viewport;

    for (var first = true;; first = false) {
      if (!first || !cm.options.lineWrapping || update.oldDisplayWidth == displayWidth(cm)) {
        // Clip forced viewport to actual scrollable area.
        if (viewport && viewport.top != null)
          { viewport = {top: Math.min(cm.doc.height + paddingVert(cm.display) - displayHeight(cm), viewport.top)}; }
        // Updated line heights might result in the drawn area not
        // actually covering the viewport. Keep looping until it does.
        update.visible = visibleLines(cm.display, cm.doc, viewport);
        if (update.visible.from >= cm.display.viewFrom && update.visible.to <= cm.display.viewTo)
          { break }
      } else if (first) {
        update.visible = visibleLines(cm.display, cm.doc, viewport);
      }
      if (!updateDisplayIfNeeded(cm, update)) { break }
      updateHeightsInViewport(cm);
      var barMeasure = measureForScrollbars(cm);
      updateSelection(cm);
      updateScrollbars(cm, barMeasure);
      setDocumentHeight(cm, barMeasure);
      update.force = false;
    }

    update.signal(cm, "update", cm);
    if (cm.display.viewFrom != cm.display.reportedViewFrom || cm.display.viewTo != cm.display.reportedViewTo) {
      update.signal(cm, "viewportChange", cm, cm.display.viewFrom, cm.display.viewTo);
      cm.display.reportedViewFrom = cm.display.viewFrom; cm.display.reportedViewTo = cm.display.viewTo;
    }
  }
```
</details>

### `updateDisplaySimple(cm: any, viewport: any): void`

**Parameters:**

- **`cm`** `any`
- **`viewport`** `any`

**Returns:** `void`

**Calls:**

- `updateDisplayIfNeeded`
- `updateHeightsInViewport`
- `postUpdateDisplay`
- `measureForScrollbars`
- `updateSelection`
- `updateScrollbars`
- `setDocumentHeight`
- `update.finish`

<details><summary>Code</summary>

```typescript
function updateDisplaySimple(cm, viewport) {
    var update = new DisplayUpdate(cm, viewport);
    if (updateDisplayIfNeeded(cm, update)) {
      updateHeightsInViewport(cm);
      postUpdateDisplay(cm, update);
      var barMeasure = measureForScrollbars(cm);
      updateSelection(cm);
      updateScrollbars(cm, barMeasure);
      setDocumentHeight(cm, barMeasure);
      update.finish();
    }
  }
```
</details>

### `patchDisplay(cm: any, updateNumbersFrom: any, dims: any): void`

**Parameters:**

- **`cm`** `any`
- **`updateNumbersFrom`** `any`
- **`dims`** `any`

**Returns:** `void`

**Calls:**

- `node.parentNode.removeChild`
- `buildLineElement`
- `container.insertBefore`
- `rm`
- `indexOf`
- `updateLineForChanges`
- `removeChildren`
- `lineView.lineNumber.appendChild`
- `document.createTextNode`
- `lineNumberFor`

**Internal Comments:**
```
// Works around a throw-scroll bug in OS X Webkit
// Loop over the elements in the view, syncing cur (the DOM nodes
// in display.lineDiv) with the view as we go.
```

<details><summary>Code</summary>

```typescript
function patchDisplay(cm, updateNumbersFrom, dims) {
    var display = cm.display, lineNumbers = cm.options.lineNumbers;
    var container = display.lineDiv, cur = container.firstChild;

    function rm(node) {
      var next = node.nextSibling;
      // Works around a throw-scroll bug in OS X Webkit
      if (webkit && mac && cm.display.currentWheelTarget == node)
        { node.style.display = "none"; }
      else
        { node.parentNode.removeChild(node); }
      return next
    }

    var view = display.view, lineN = display.viewFrom;
    // Loop over the elements in the view, syncing cur (the DOM nodes
    // in display.lineDiv) with the view as we go.
    for (var i = 0; i < view.length; i++) {
      var lineView = view[i];
      if (lineView.hidden) ; else if (!lineView.node || lineView.node.parentNode != container) { // Not drawn yet
        var node = buildLineElement(cm, lineView, lineN, dims);
        container.insertBefore(node, cur);
      } else { // Already drawn
        while (cur != lineView.node) { cur = rm(cur); }
        var updateNumber = lineNumbers && updateNumbersFrom != null &&
          updateNumbersFrom <= lineN && lineView.lineNumber;
        if (lineView.changes) {
          if (indexOf(lineView.changes, "gutter") > -1) { updateNumber = false; }
          updateLineForChanges(cm, lineView, lineN, dims);
        }
        if (updateNumber) {
          removeChildren(lineView.lineNumber);
          lineView.lineNumber.appendChild(document.createTextNode(lineNumberFor(cm.options, lineN)));
        }
        cur = lineView.node.nextSibling;
      }
      lineN += lineView.size;
    }
    while (cur) { cur = rm(cur); }
  }
```
</details>

### `rm(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `node.parentNode.removeChild`

**Internal Comments:**
```
// Works around a throw-scroll bug in OS X Webkit
```

<details><summary>Code</summary>

```typescript
function rm(node) {
      var next = node.nextSibling;
      // Works around a throw-scroll bug in OS X Webkit
      if (webkit && mac && cm.display.currentWheelTarget == node)
        { node.style.display = "none"; }
      else
        { node.parentNode.removeChild(node); }
      return next
    }
```
</details>

### `updateGutterSpace(display: any): void`

**Parameters:**

- **`display`** `any`

**Returns:** `void`

**Calls:**

- `signalLater`

**Internal Comments:**
```
// Send an event to consumers responding to changes in gutter width. (x3)
```

<details><summary>Code</summary>

```typescript
function updateGutterSpace(display) {
    var width = display.gutters.offsetWidth;
    display.sizer.style.marginLeft = width + "px";
    // Send an event to consumers responding to changes in gutter width.
    signalLater(display, "gutterChanged", display);
  }
```
</details>

### `setDocumentHeight(cm: any, measure: any): void`

**Parameters:**

- **`cm`** `any`
- **`measure`** `any`

**Returns:** `void`

**Calls:**

- `scrollGap`

<details><summary>Code</summary>

```typescript
function setDocumentHeight(cm, measure) {
    cm.display.sizer.style.minHeight = measure.docHeight + "px";
    cm.display.heightForcer.style.top = measure.docHeight + "px";
    cm.display.gutters.style.height = (measure.docHeight + cm.display.barHeight + scrollGap(cm)) + "px";
  }
```
</details>

### `alignHorizontally(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `compensateForHScroll`

<details><summary>Code</summary>

```typescript
function alignHorizontally(cm) {
    var display = cm.display, view = display.view;
    if (!display.alignWidgets && (!display.gutters.firstChild || !cm.options.fixedGutter)) { return }
    var comp = compensateForHScroll(display) - display.scroller.scrollLeft + cm.doc.scrollLeft;
    var gutterW = display.gutters.offsetWidth, left = comp + "px";
    for (var i = 0; i < view.length; i++) { if (!view[i].hidden) {
      if (cm.options.fixedGutter) {
        if (view[i].gutter)
          { view[i].gutter.style.left = left; }
        if (view[i].gutterBackground)
          { view[i].gutterBackground.style.left = left; }
      }
      var align = view[i].alignable;
      if (align) { for (var j = 0; j < align.length; j++)
        { align[j].style.left = left; } }
    } }
    if (cm.options.fixedGutter)
      { display.gutters.style.left = (comp + gutterW) + "px"; }
  }
```
</details>

### `maybeUpdateLineNumberWidth(cm: any): boolean`

**Parameters:**

- **`cm`** `any`

**Returns:** `boolean`

**Calls:**

- `lineNumberFor`
- `display.measure.appendChild`
- `elt`
- `Math.max`
- `updateGutterSpace`

<details><summary>Code</summary>

```typescript
function maybeUpdateLineNumberWidth(cm) {
    if (!cm.options.lineNumbers) { return false }
    var doc = cm.doc, last = lineNumberFor(cm.options, doc.first + doc.size - 1), display = cm.display;
    if (last.length != display.lineNumChars) {
      var test = display.measure.appendChild(elt("div", [elt("div", last)],
                                                 "CodeMirror-linenumber CodeMirror-gutter-elt"));
      var innerW = test.firstChild.offsetWidth, padding = test.offsetWidth - innerW;
      display.lineGutter.style.width = "";
      display.lineNumInnerWidth = Math.max(innerW, display.lineGutter.offsetWidth - padding) + 1;
      display.lineNumWidth = display.lineNumInnerWidth + padding;
      display.lineNumChars = display.lineNumInnerWidth ? last.length : -1;
      display.lineGutter.style.width = display.lineNumWidth + "px";
      updateGutterSpace(cm.display);
      return true
    }
    return false
  }
```
</details>

### `getGutters(gutters: any, lineNumbers: any): { className: any; style: any; }[]`

**Parameters:**

- **`gutters`** `any`
- **`lineNumbers`** `any`

**Returns:** `{ className: any; style: any; }[]`

**Calls:**

- `result.push`

<details><summary>Code</summary>

```typescript
function getGutters(gutters, lineNumbers) {
    var result = [], sawLineNumbers = false;
    for (var i = 0; i < gutters.length; i++) {
      var name = gutters[i], style = null;
      if (typeof name != "string") { style = name.style; name = name.className; }
      if (name == "CodeMirror-linenumbers") {
        if (!lineNumbers) { continue }
        else { sawLineNumbers = true; }
      }
      result.push({className: name, style: style});
    }
    if (lineNumbers && !sawLineNumbers) { result.push({className: "CodeMirror-linenumbers", style: null}); }
    return result
  }
```
</details>

### `renderGutters(display: any): void`

**Parameters:**

- **`display`** `any`

**Returns:** `void`

**Calls:**

- `removeChildren`
- `gutters.appendChild`
- `elt`
- `updateGutterSpace`

<details><summary>Code</summary>

```typescript
function renderGutters(display) {
    var gutters = display.gutters, specs = display.gutterSpecs;
    removeChildren(gutters);
    display.lineGutter = null;
    for (var i = 0; i < specs.length; ++i) {
      var ref = specs[i];
      var className = ref.className;
      var style = ref.style;
      var gElt = gutters.appendChild(elt("div", null, "CodeMirror-gutter " + className));
      if (style) { gElt.style.cssText = style; }
      if (className == "CodeMirror-linenumbers") {
        display.lineGutter = gElt;
        gElt.style.width = (display.lineNumWidth || 1) + "px";
      }
    }
    gutters.style.display = specs.length ? "" : "none";
    updateGutterSpace(display);
  }
```
</details>

### `updateGutters(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `renderGutters`
- `regChange`
- `alignHorizontally`

<details><summary>Code</summary>

```typescript
function updateGutters(cm) {
    renderGutters(cm.display);
    regChange(cm);
    alignHorizontally(cm);
  }
```
</details>

### `Display(place: any, doc: any, input: any, options: any): void`

**Parameters:**

- **`place`** `any`
- **`doc`** `any`
- **`input`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `elt`
- `d.scrollbarFiller.setAttribute`
- `d.gutterFiller.setAttribute`
- `eltP`
- `d.scroller.setAttribute`
- `d.wrapper.setAttribute`
- `place.appendChild`
- `place`
- `getGutters`
- `renderGutters`
- `input.init`

**Internal Comments:**
```
// Covers bottom-right square when both scrollbars are present. (x4)
// Covers bottom of gutter when coverGutterNextToScrollbar is on (x4)
// and h scrollbar is present. (x4)
// Will contain the actual code, positioned to cover the viewport. (x4)
// Elements are added to these to represent selection and cursors. (x4)
// A visibility: hidden element used to find the size of things. (x4)
// When lines outside of the viewport are measured, they are drawn in this. (x4)
// Wraps everything that needs to exist inside the vertically-padded coordinate system (x4)
// Moved around its parent to cover visible view. (x4)
// Set to the height of the document, allowing scrolling. (x4)
// Behavior of elts with overflow: auto and padding is (x4)
// inconsistent across browsers. This is used to ensure the (x4)
// scrollable area is big enough. (x4)
// Will contain the gutters, if any. (x4)
// Actual scrollable element. (x4)
// The element in which the editor lives. (x4)
// This attribute is respected by automatic translation systems such as Google Translate, (x5)
// and may also be respected by tools used by human translators. (x5)
// Work around IE7 z-index bug (not perfect, hence IE7 not really being supported)
// Current rendered range (may be bigger than the view window). (x4)
// Information about the rendered lines. (x4)
// Holds info about a single rendered line when it was rendered (x4)
// for measurement, while not in view. (x4)
// Empty space (in pixels) above the view (x4)
// Used to only resize the line number gutter when necessary (when (x4)
// the amount of lines crosses a boundary that makes its width change) (x4)
// Set to true when a non-horizontal-scrolling line widget is (x4)
// added. As an optimization, line widget aligning is skipped when (x4)
// this is false. (x4)
// Tracks the maximum line length so that the horizontal scrollbar (x4)
// can be kept static when scrolling. (x4)
// Used for measuring wheel scrolling granularity (x4)
// True when shift is held down. (x4)
// Used to track whether anything happened since the context menu (x4)
// was opened. (x4)
```

<details><summary>Code</summary>

```typescript
function Display(place, doc, input, options) {
    var d = this;
    this.input = input;

    // Covers bottom-right square when both scrollbars are present.
    d.scrollbarFiller = elt("div", null, "CodeMirror-scrollbar-filler");
    d.scrollbarFiller.setAttribute("cm-not-content", "true");
    // Covers bottom of gutter when coverGutterNextToScrollbar is on
    // and h scrollbar is present.
    d.gutterFiller = elt("div", null, "CodeMirror-gutter-filler");
    d.gutterFiller.setAttribute("cm-not-content", "true");
    // Will contain the actual code, positioned to cover the viewport.
    d.lineDiv = eltP("div", null, "CodeMirror-code");
    // Elements are added to these to represent selection and cursors.
    d.selectionDiv = elt("div", null, null, "position: relative; z-index: 1");
    d.cursorDiv = elt("div", null, "CodeMirror-cursors");
    // A visibility: hidden element used to find the size of things.
    d.measure = elt("div", null, "CodeMirror-measure");
    // When lines outside of the viewport are measured, they are drawn in this.
    d.lineMeasure = elt("div", null, "CodeMirror-measure");
    // Wraps everything that needs to exist inside the vertically-padded coordinate system
    d.lineSpace = eltP("div", [d.measure, d.lineMeasure, d.selectionDiv, d.cursorDiv, d.lineDiv],
                      null, "position: relative; outline: none");
    var lines = eltP("div", [d.lineSpace], "CodeMirror-lines");
    // Moved around its parent to cover visible view.
    d.mover = elt("div", [lines], null, "position: relative");
    // Set to the height of the document, allowing scrolling.
    d.sizer = elt("div", [d.mover], "CodeMirror-sizer");
    d.sizerWidth = null;
    // Behavior of elts with overflow: auto and padding is
    // inconsistent across browsers. This is used to ensure the
    // scrollable area is big enough.
    d.heightForcer = elt("div", null, null, "position: absolute; height: " + scrollerGap + "px; width: 1px;");
    // Will contain the gutters, if any.
    d.gutters = elt("div", null, "CodeMirror-gutters");
    d.lineGutter = null;
    // Actual scrollable element.
    d.scroller = elt("div", [d.sizer, d.heightForcer, d.gutters], "CodeMirror-scroll");
    d.scroller.setAttribute("tabIndex", "-1");
    // The element in which the editor lives.
    d.wrapper = elt("div", [d.scrollbarFiller, d.gutterFiller, d.scroller], "CodeMirror");

    // This attribute is respected by automatic translation systems such as Google Translate,
    // and may also be respected by tools used by human translators.
    d.wrapper.setAttribute('translate', 'no');

    // Work around IE7 z-index bug (not perfect, hence IE7 not really being supported)
    if (ie && ie_version < 8) { d.gutters.style.zIndex = -1; d.scroller.style.paddingRight = 0; }
    if (!webkit && !(gecko && mobile)) { d.scroller.draggable = true; }

    if (place) {
      if (place.appendChild) { place.appendChild(d.wrapper); }
      else { place(d.wrapper); }
    }

    // Current rendered range (may be bigger than the view window).
    d.viewFrom = d.viewTo = doc.first;
    d.reportedViewFrom = d.reportedViewTo = doc.first;
    // Information about the rendered lines.
    d.view = [];
    d.renderedView = null;
    // Holds info about a single rendered line when it was rendered
    // for measurement, while not in view.
    d.externalMeasured = null;
    // Empty space (in pixels) above the view
    d.viewOffset = 0;
    d.lastWrapHeight = d.lastWrapWidth = 0;
    d.updateLineNumbers = null;

    d.nativeBarWidth = d.barHeight = d.barWidth = 0;
    d.scrollbarsClipped = false;

    // Used to only resize the line number gutter when necessary (when
    // the amount of lines crosses a boundary that makes its width change)
    d.lineNumWidth = d.lineNumInnerWidth = d.lineNumChars = null;
    // Set to true when a non-horizontal-scrolling line widget is
    // added. As an optimization, line widget aligning is skipped when
    // this is false.
    d.alignWidgets = false;

    d.cachedCharWidth = d.cachedTextHeight = d.cachedPaddingH = null;

    // Tracks the maximum line length so that the horizontal scrollbar
    // can be kept static when scrolling.
    d.maxLine = null;
    d.maxLineLength = 0;
    d.maxLineChanged = false;

    // Used for measuring wheel scrolling granularity
    d.wheelDX = d.wheelDY = d.wheelStartX = d.wheelStartY = null;

    // True when shift is held down.
    d.shift = false;

    // Used to track whether anything happened since the context menu
    // was opened.
    d.selForContextMenu = null;

    d.activeTouch = null;

    d.gutterSpecs = getGutters(options.gutters, options.lineNumbers);
    renderGutters(d);

    input.init(d);
  }
```
</details>

### `wheelEventDelta(e: any): { x: any; y: any; }`

**Parameters:**

- **`e`** `any`

**Returns:** `{ x: any; y: any; }`

<details><summary>Code</summary>

```typescript
function wheelEventDelta(e) {
    var dx = e.wheelDeltaX, dy = e.wheelDeltaY;
    if (dx == null && e.detail && e.axis == e.HORIZONTAL_AXIS) { dx = e.detail; }
    if (dy == null && e.detail && e.axis == e.VERTICAL_AXIS) { dy = e.detail; }
    else if (dy == null) { dy = e.wheelDelta; }
    return {x: dx, y: dy}
  }
```
</details>

### `wheelEventPixels(e: any): { x: any; y: any; }`

**Parameters:**

- **`e`** `any`

**Returns:** `{ x: any; y: any; }`

**Calls:**

- `wheelEventDelta`

<details><summary>Code</summary>

```typescript
function wheelEventPixels(e) {
    var delta = wheelEventDelta(e);
    delta.x *= wheelPixelsPerUnit;
    delta.y *= wheelPixelsPerUnit;
    return delta
  }
```
</details>

### `onScrollWheel(cm: any, e: any): void`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `void`

**Calls:**

- `wheelEventDelta`
- `updateScrollTop`
- `Math.max`
- `setScrollLeft`
- `e_preventDefault`
- `Math.min`
- `updateDisplaySimple`
- `setTimeout`

**Internal Comments:**
```
// Quit if there's nothing to scroll here (x2)
// Webkit browsers on OS X abort momentum scrolls when the target
// of the scroll event is removed from the scrollable element.
// This hack (see related code in patchDisplay) makes sure the
// element is kept around.
// On some browsers, horizontal scrolling will cause redraws to
// happen before the gutter has been realigned, causing it to
// wriggle around in a most unseemly way. When we have an
// estimated pixels/delta value, we just handle horizontal
// scrolling entirely here. It'll be slightly off from native, but
// better than glitching out.
// Only prevent default scrolling if vertical scrolling is
// actually possible. Otherwise, it causes vertical scroll
// jitter on OSX trackpads when deltaX is small and deltaY
// is large (issue #3579)
// 'Project' the visible viewport to cover the area that is being
// scrolled into view (if we know enough to estimate it).
```

<details><summary>Code</summary>

```typescript
function onScrollWheel(cm, e) {
    var delta = wheelEventDelta(e), dx = delta.x, dy = delta.y;
    var pixelsPerUnit = wheelPixelsPerUnit;
    if (e.deltaMode === 0) {
      dx = e.deltaX;
      dy = e.deltaY;
      pixelsPerUnit = 1;
    }

    var display = cm.display, scroll = display.scroller;
    // Quit if there's nothing to scroll here
    var canScrollX = scroll.scrollWidth > scroll.clientWidth;
    var canScrollY = scroll.scrollHeight > scroll.clientHeight;
    if (!(dx && canScrollX || dy && canScrollY)) { return }

    // Webkit browsers on OS X abort momentum scrolls when the target
    // of the scroll event is removed from the scrollable element.
    // This hack (see related code in patchDisplay) makes sure the
    // element is kept around.
    if (dy && mac && webkit) {
      outer: for (var cur = e.target, view = display.view; cur != scroll; cur = cur.parentNode) {
        for (var i = 0; i < view.length; i++) {
          if (view[i].node == cur) {
            cm.display.currentWheelTarget = cur;
            break outer
          }
        }
      }
    }

    // On some browsers, horizontal scrolling will cause redraws to
    // happen before the gutter has been realigned, causing it to
    // wriggle around in a most unseemly way. When we have an
    // estimated pixels/delta value, we just handle horizontal
    // scrolling entirely here. It'll be slightly off from native, but
    // better than glitching out.
    if (dx && !gecko && !presto && pixelsPerUnit != null) {
      if (dy && canScrollY)
        { updateScrollTop(cm, Math.max(0, scroll.scrollTop + dy * pixelsPerUnit)); }
      setScrollLeft(cm, Math.max(0, scroll.scrollLeft + dx * pixelsPerUnit));
      // Only prevent default scrolling if vertical scrolling is
      // actually possible. Otherwise, it causes vertical scroll
      // jitter on OSX trackpads when deltaX is small and deltaY
      // is large (issue #3579)
      if (!dy || (dy && canScrollY))
        { e_preventDefault(e); }
      display.wheelStartX = null; // Abort measurement, if in progress
      return
    }

    // 'Project' the visible viewport to cover the area that is being
    // scrolled into view (if we know enough to estimate it).
    if (dy && pixelsPerUnit != null) {
      var pixels = dy * pixelsPerUnit;
      var top = cm.doc.scrollTop, bot = top + display.wrapper.clientHeight;
      if (pixels < 0) { top = Math.max(0, top + pixels - 50); }
      else { bot = Math.min(cm.doc.height, bot + pixels + 50); }
      updateDisplaySimple(cm, {top: top, bottom: bot});
    }

    if (wheelSamples < 20 && e.deltaMode !== 0) {
      if (display.wheelStartX == null) {
        display.wheelStartX = scroll.scrollLeft; display.wheelStartY = scroll.scrollTop;
        display.wheelDX = dx; display.wheelDY = dy;
        setTimeout(function () {
          if (display.wheelStartX == null) { return }
          var movedX = scroll.scrollLeft - display.wheelStartX;
          var movedY = scroll.scrollTop - display.wheelStartY;
          var sample = (movedY && display.wheelDY && movedY / display.wheelDY) ||
            (movedX && display.wheelDX && movedX / display.wheelDX);
          display.wheelStartX = display.wheelStartY = null;
          if (!sample) { return }
          wheelPixelsPerUnit = (wheelPixelsPerUnit * wheelSamples + sample) / (wheelSamples + 1);
          ++wheelSamples;
        }, 200);
      } else {
        display.wheelDX += dx; display.wheelDY += dy;
      }
    }
  }
```
</details>

### `Selection(ranges: any, primIndex: any): void`

**Parameters:**

- **`ranges`** `any`
- **`primIndex`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(ranges, primIndex) {
    this.ranges = ranges;
    this.primIndex = primIndex;
  }
```
</details>

### `Range(anchor: any, head: any): void`

**Parameters:**

- **`anchor`** `any`
- **`head`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(anchor, head) {
    this.anchor = anchor; this.head = head;
  }
```
</details>

### `normalizeSelection(cm: any, ranges: any, primIndex: any): Selection`

**Parameters:**

- **`cm`** `any`
- **`ranges`** `any`
- **`primIndex`** `any`

**Returns:** `Selection`

**Calls:**

- `ranges.sort`
- `cmp`
- `a.from`
- `b.from`
- `indexOf`
- `prev.to`
- `cur.from`
- `cur.empty`
- `minPos`
- `prev.from`
- `maxPos`
- `cur.to`
- `prev.empty`
- `ranges.splice`

<details><summary>Code</summary>

```typescript
function normalizeSelection(cm, ranges, primIndex) {
    var mayTouch = cm && cm.options.selectionsMayTouch;
    var prim = ranges[primIndex];
    ranges.sort(function (a, b) { return cmp(a.from(), b.from()); });
    primIndex = indexOf(ranges, prim);
    for (var i = 1; i < ranges.length; i++) {
      var cur = ranges[i], prev = ranges[i - 1];
      var diff = cmp(prev.to(), cur.from());
      if (mayTouch && !cur.empty() ? diff > 0 : diff >= 0) {
        var from = minPos(prev.from(), cur.from()), to = maxPos(prev.to(), cur.to());
        var inv = prev.empty() ? cur.from() == cur.head : prev.from() == prev.head;
        if (i <= primIndex) { --primIndex; }
        ranges.splice(--i, 2, new Range(inv ? to : from, inv ? from : to));
      }
    }
    return new Selection(ranges, primIndex)
  }
```
</details>

### `simpleSelection(anchor: any, head: any): Selection`

**Parameters:**

- **`anchor`** `any`
- **`head`** `any`

**Returns:** `Selection`

<details><summary>Code</summary>

```typescript
function simpleSelection(anchor, head) {
    return new Selection([new Range(anchor, head || anchor)], 0)
  }
```
</details>

### `changeEnd(change: any): any`

**Parameters:**

- **`change`** `any`

**Returns:** `any`

**Calls:**

- `Pos`
- `lst`

<details><summary>Code</summary>

```typescript
function changeEnd(change) {
    if (!change.text) { return change.to }
    return Pos(change.from.line + change.text.length - 1,
               lst(change.text).length + (change.text.length == 1 ? change.from.ch : 0))
  }
```
</details>

### `adjustForChange(pos: any, change: any): any`

**Parameters:**

- **`pos`** `any`
- **`change`** `any`

**Returns:** `any`

**Calls:**

- `cmp`
- `changeEnd`
- `Pos`

<details><summary>Code</summary>

```typescript
function adjustForChange(pos, change) {
    if (cmp(pos, change.from) < 0) { return pos }
    if (cmp(pos, change.to) <= 0) { return changeEnd(change) }

    var line = pos.line + change.text.length - (change.to.line - change.from.line) - 1, ch = pos.ch;
    if (pos.line == change.to.line) { ch += changeEnd(change).ch - change.to.ch; }
    return Pos(line, ch)
  }
```
</details>

### `computeSelAfterChange(doc: any, change: any): Selection`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`

**Returns:** `Selection`

**Calls:**

- `out.push`
- `adjustForChange`
- `normalizeSelection`

<details><summary>Code</summary>

```typescript
function computeSelAfterChange(doc, change) {
    var out = [];
    for (var i = 0; i < doc.sel.ranges.length; i++) {
      var range = doc.sel.ranges[i];
      out.push(new Range(adjustForChange(range.anchor, change),
                         adjustForChange(range.head, change)));
    }
    return normalizeSelection(doc.cm, out, doc.sel.primIndex)
  }
```
</details>

### `offsetPos(pos: any, old: any, nw: any): Pos`

**Parameters:**

- **`pos`** `any`
- **`old`** `any`
- **`nw`** `any`

**Returns:** `Pos`

**Calls:**

- `Pos`

<details><summary>Code</summary>

```typescript
function offsetPos(pos, old, nw) {
    if (pos.line == old.line)
      { return Pos(nw.line, pos.ch - old.ch + nw.ch) }
    else
      { return Pos(nw.line + (pos.line - old.line), pos.ch) }
  }
```
</details>

### `computeReplacedSel(doc: any, changes: any, hint: any): Selection`

**Parameters:**

- **`doc`** `any`
- **`changes`** `any`
- **`hint`** `any`

**Returns:** `Selection`

**Calls:**

- `Pos`
- `offsetPos`
- `changeEnd`
- `cmp`

<details><summary>Code</summary>

```typescript
function computeReplacedSel(doc, changes, hint) {
    var out = [];
    var oldPrev = Pos(doc.first, 0), newPrev = oldPrev;
    for (var i = 0; i < changes.length; i++) {
      var change = changes[i];
      var from = offsetPos(change.from, oldPrev, newPrev);
      var to = offsetPos(changeEnd(change), oldPrev, newPrev);
      oldPrev = change.to;
      newPrev = to;
      if (hint == "around") {
        var range = doc.sel.ranges[i], inv = cmp(range.head, range.anchor) < 0;
        out[i] = new Range(inv ? to : from, inv ? from : to);
      } else {
        out[i] = new Range(from, from);
      }
    }
    return new Selection(out, doc.sel.primIndex)
  }
```
</details>

### `loadMode(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `getMode`
- `resetModeState`

<details><summary>Code</summary>

```typescript
function loadMode(cm) {
    cm.doc.mode = getMode(cm.options, cm.doc.modeOption);
    resetModeState(cm);
  }
```
</details>

### `resetModeState(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.doc.iter`
- `startWorker`
- `regChange`

<details><summary>Code</summary>

```typescript
function resetModeState(cm) {
    cm.doc.iter(function (line) {
      if (line.stateAfter) { line.stateAfter = null; }
      if (line.styles) { line.styles = null; }
    });
    cm.doc.modeFrontier = cm.doc.highlightFrontier = cm.doc.first;
    startWorker(cm, 100);
    cm.state.modeGen++;
    if (cm.curOp) { regChange(cm); }
  }
```
</details>

### `isWholeLineUpdate(doc: any, change: any): any`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`

**Returns:** `any`

**Calls:**

- `lst`

<details><summary>Code</summary>

```typescript
function isWholeLineUpdate(doc, change) {
    return change.from.ch == 0 && change.to.ch == 0 && lst(change.text) == "" &&
      (!doc.cm || doc.cm.options.wholeLineUpdateBefore)
  }
```
</details>

### `updateDoc(doc: any, change: any, markedSpans: any, estimateHeight: any): void`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`
- **`markedSpans`** `any`
- **`estimateHeight`** `any`

**Returns:** `void`

**Calls:**

- `updateLine`
- `signalLater`
- `result.push`
- `spansFor`
- `getLine`
- `lst`
- `doc.insert`
- `linesFor`
- `doc.remove`
- `isWholeLineUpdate`
- `update`
- `firstLine.text.slice`
- `added$1.push`
- `lastLine.text.slice`

**Internal Comments:**
```
// Adjust the line structure
// This is a whole-line replace. Treated specially to make (x2)
// sure line objects move the way they are supposed to. (x2)
```

<details><summary>Code</summary>

```typescript
function updateDoc(doc, change, markedSpans, estimateHeight) {
    function spansFor(n) {return markedSpans ? markedSpans[n] : null}
    function update(line, text, spans) {
      updateLine(line, text, spans, estimateHeight);
      signalLater(line, "change", line, change);
    }
    function linesFor(start, end) {
      var result = [];
      for (var i = start; i < end; ++i)
        { result.push(new Line(text[i], spansFor(i), estimateHeight)); }
      return result
    }

    var from = change.from, to = change.to, text = change.text;
    var firstLine = getLine(doc, from.line), lastLine = getLine(doc, to.line);
    var lastText = lst(text), lastSpans = spansFor(text.length - 1), nlines = to.line - from.line;

    // Adjust the line structure
    if (change.full) {
      doc.insert(0, linesFor(0, text.length));
      doc.remove(text.length, doc.size - text.length);
    } else if (isWholeLineUpdate(doc, change)) {
      // This is a whole-line replace. Treated specially to make
      // sure line objects move the way they are supposed to.
      var added = linesFor(0, text.length - 1);
      update(lastLine, lastLine.text, lastSpans);
      if (nlines) { doc.remove(from.line, nlines); }
      if (added.length) { doc.insert(from.line, added); }
    } else if (firstLine == lastLine) {
      if (text.length == 1) {
        update(firstLine, firstLine.text.slice(0, from.ch) + lastText + firstLine.text.slice(to.ch), lastSpans);
      } else {
        var added$1 = linesFor(1, text.length - 1);
        added$1.push(new Line(lastText + firstLine.text.slice(to.ch), lastSpans, estimateHeight));
        update(firstLine, firstLine.text.slice(0, from.ch) + text[0], spansFor(0));
        doc.insert(from.line + 1, added$1);
      }
    } else if (text.length == 1) {
      update(firstLine, firstLine.text.slice(0, from.ch) + text[0] + lastLine.text.slice(to.ch), spansFor(0));
      doc.remove(from.line + 1, nlines);
    } else {
      update(firstLine, firstLine.text.slice(0, from.ch) + text[0], spansFor(0));
      update(lastLine, lastText + lastLine.text.slice(to.ch), lastSpans);
      var added$2 = linesFor(1, text.length - 1);
      if (nlines > 1) { doc.remove(from.line + 1, nlines - 1); }
      doc.insert(from.line + 1, added$2);
    }

    signalLater(doc, "change", doc, change);
  }
```
</details>

### `spansFor(n: any): any`

**Parameters:**

- **`n`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function spansFor(n) {return markedSpans ? markedSpans[n] : null}
```
</details>

### `update(line: any, text: any, spans: any): void`

**Parameters:**

- **`line`** `any`
- **`text`** `any`
- **`spans`** `any`

**Returns:** `void`

**Calls:**

- `updateLine`
- `signalLater`

<details><summary>Code</summary>

```typescript
function update(line, text, spans) {
      updateLine(line, text, spans, estimateHeight);
      signalLater(line, "change", line, change);
    }
```
</details>

### `linesFor(start: any, end: any): Line[]`

**Parameters:**

- **`start`** `any`
- **`end`** `any`

**Returns:** `Line[]`

**Calls:**

- `result.push`
- `spansFor`

<details><summary>Code</summary>

```typescript
function linesFor(start, end) {
      var result = [];
      for (var i = start; i < end; ++i)
        { result.push(new Line(text[i], spansFor(i), estimateHeight)); }
      return result
    }
```
</details>

### `linkedDocs(doc: any, f: any, sharedHistOnly: any): void`

**Parameters:**

- **`doc`** `any`
- **`f`** `any`
- **`sharedHistOnly`** `any`

**Returns:** `void`

**Calls:**

- `f`
- `propagate`

<details><summary>Code</summary>

```typescript
function linkedDocs(doc, f, sharedHistOnly) {
    function propagate(doc, skip, sharedHist) {
      if (doc.linked) { for (var i = 0; i < doc.linked.length; ++i) {
        var rel = doc.linked[i];
        if (rel.doc == skip) { continue }
        var shared = sharedHist && rel.sharedHist;
        if (sharedHistOnly && !shared) { continue }
        f(rel.doc, shared);
        propagate(rel.doc, doc, shared);
      } }
    }
    propagate(doc, null, true);
  }
```
</details>

### `propagate(doc: any, skip: any, sharedHist: any): void`

**Parameters:**

- **`doc`** `any`
- **`skip`** `any`
- **`sharedHist`** `any`

**Returns:** `void`

**Calls:**

- `f`
- `propagate`

<details><summary>Code</summary>

```typescript
function propagate(doc, skip, sharedHist) {
      if (doc.linked) { for (var i = 0; i < doc.linked.length; ++i) {
        var rel = doc.linked[i];
        if (rel.doc == skip) { continue }
        var shared = sharedHist && rel.sharedHist;
        if (sharedHistOnly && !shared) { continue }
        f(rel.doc, shared);
        propagate(rel.doc, doc, shared);
      } }
    }
```
</details>

### `attachDoc(cm: any, doc: any): void`

**Parameters:**

- **`cm`** `any`
- **`doc`** `any`

**Returns:** `void`

**Calls:**

- `estimateLineHeights`
- `loadMode`
- `setDirectionClass`
- `findMaxLine`
- `regChange`

<details><summary>Code</summary>

```typescript
function attachDoc(cm, doc) {
    if (doc.cm) { throw new Error("This document is already in use.") }
    cm.doc = doc;
    doc.cm = cm;
    estimateLineHeights(cm);
    loadMode(cm);
    setDirectionClass(cm);
    cm.options.direction = doc.direction;
    if (!cm.options.lineWrapping) { findMaxLine(cm); }
    cm.options.mode = doc.modeOption;
    regChange(cm);
  }
```
</details>

### `setDirectionClass(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_199433`

<details><summary>Code</summary>

```typescript
function setDirectionClass(cm) {
  (cm.doc.direction == "rtl" ? addClass : rmClass)(cm.display.lineDiv, "CodeMirror-rtl");
  }
```
</details>

### `directionChanged(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `runInOp`
- `setDirectionClass`
- `regChange`

<details><summary>Code</summary>

```typescript
function directionChanged(cm) {
    runInOp(cm, function () {
      setDirectionClass(cm);
      regChange(cm);
    });
  }
```
</details>

### `History(prev: any): void`

**Parameters:**

- **`prev`** `any`

**Returns:** `void`

**Internal Comments:**
```
// Arrays of change events and selections. Doing something adds an (x4)
// event to done and clears undo. Undoing moves events from done (x4)
// to undone, redoing moves them in the other direction. (x4)
// Used to track when changes can be merged into a single undo (x4)
// event (x4)
// Used by the isClean() method (x4)
```

<details><summary>Code</summary>

```typescript
function History(prev) {
    // Arrays of change events and selections. Doing something adds an
    // event to done and clears undo. Undoing moves events from done
    // to undone, redoing moves them in the other direction.
    this.done = []; this.undone = [];
    this.undoDepth = prev ? prev.undoDepth : Infinity;
    // Used to track when changes can be merged into a single undo
    // event
    this.lastModTime = this.lastSelTime = 0;
    this.lastOp = this.lastSelOp = null;
    this.lastOrigin = this.lastSelOrigin = null;
    // Used by the isClean() method
    this.generation = this.maxGeneration = prev ? prev.maxGeneration : 1;
  }
```
</details>

### `historyChangeFromChange(doc: any, change: any): { from: Pos; to: any; text: any[]; }`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`

**Returns:** `{ from: Pos; to: any; text: any[]; }`

**Calls:**

- `copyPos`
- `changeEnd`
- `getBetween`
- `attachLocalSpans`
- `linkedDocs`

<details><summary>Code</summary>

```typescript
function historyChangeFromChange(doc, change) {
    var histChange = {from: copyPos(change.from), to: changeEnd(change), text: getBetween(doc, change.from, change.to)};
    attachLocalSpans(doc, histChange, change.from.line, change.to.line + 1);
    linkedDocs(doc, function (doc) { return attachLocalSpans(doc, histChange, change.from.line, change.to.line + 1); }, true);
    return histChange
  }
```
</details>

### `clearSelectionEvents(array: any): void`

**Parameters:**

- **`array`** `any`

**Returns:** `void`

**Calls:**

- `lst`
- `array.pop`

<details><summary>Code</summary>

```typescript
function clearSelectionEvents(array) {
    while (array.length) {
      var last = lst(array);
      if (last.ranges) { array.pop(); }
      else { break }
    }
  }
```
</details>

### `lastChangeEvent(hist: any, force: any): any`

**Parameters:**

- **`hist`** `any`
- **`force`** `any`

**Returns:** `any`

**Calls:**

- `clearSelectionEvents`
- `lst`
- `hist.done.pop`

<details><summary>Code</summary>

```typescript
function lastChangeEvent(hist, force) {
    if (force) {
      clearSelectionEvents(hist.done);
      return lst(hist.done)
    } else if (hist.done.length && !lst(hist.done).ranges) {
      return lst(hist.done)
    } else if (hist.done.length > 1 && !hist.done[hist.done.length - 2].ranges) {
      hist.done.pop();
      return lst(hist.done)
    }
  }
```
</details>

### `addChangeToHistory(doc: any, change: any, selAfter: any, opId: any): void`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`
- **`selAfter`** `any`
- **`opId`** `any`

**Returns:** `void`

**Calls:**

- `change.origin.charAt`
- `lastChangeEvent`
- `lst`
- `cmp`
- `changeEnd`
- `cur.changes.push`
- `historyChangeFromChange`
- `pushSelectionToHistory`
- `hist.done.push`
- `hist.done.shift`
- `signal`

**Internal Comments:**
```
// Merge this change into the last event (x3)
// Optimized case for simple insertion -- don't want to add (x4)
// new changesets for every character typed (x4)
// Add new sub-event (x5)
// Can not be merged, start a new event. (x2)
```

<details><summary>Code</summary>

```typescript
function addChangeToHistory(doc, change, selAfter, opId) {
    var hist = doc.history;
    hist.undone.length = 0;
    var time = +new Date, cur;
    var last;

    if ((hist.lastOp == opId ||
         hist.lastOrigin == change.origin && change.origin &&
         ((change.origin.charAt(0) == "+" && hist.lastModTime > time - (doc.cm ? doc.cm.options.historyEventDelay : 500)) ||
          change.origin.charAt(0) == "*")) &&
        (cur = lastChangeEvent(hist, hist.lastOp == opId))) {
      // Merge this change into the last event
      last = lst(cur.changes);
      if (cmp(change.from, change.to) == 0 && cmp(change.from, last.to) == 0) {
        // Optimized case for simple insertion -- don't want to add
        // new changesets for every character typed
        last.to = changeEnd(change);
      } else {
        // Add new sub-event
        cur.changes.push(historyChangeFromChange(doc, change));
      }
    } else {
      // Can not be merged, start a new event.
      var before = lst(hist.done);
      if (!before || !before.ranges)
        { pushSelectionToHistory(doc.sel, hist.done); }
      cur = {changes: [historyChangeFromChange(doc, change)],
             generation: hist.generation};
      hist.done.push(cur);
      while (hist.done.length > hist.undoDepth) {
        hist.done.shift();
        if (!hist.done[0].ranges) { hist.done.shift(); }
      }
    }
    hist.done.push(selAfter);
    hist.generation = ++hist.maxGeneration;
    hist.lastModTime = hist.lastSelTime = time;
    hist.lastOp = hist.lastSelOp = opId;
    hist.lastOrigin = hist.lastSelOrigin = change.origin;

    if (!last) { signal(doc, "historyAdded"); }
  }
```
</details>

### `selectionEventCanBeMerged(doc: any, origin: any, prev: any, sel: any): boolean`

**Parameters:**

- **`doc`** `any`
- **`origin`** `any`
- **`prev`** `any`
- **`sel`** `any`

**Returns:** `boolean`

**Calls:**

- `origin.charAt`
- `prev.somethingSelected`
- `sel.somethingSelected`

<details><summary>Code</summary>

```typescript
function selectionEventCanBeMerged(doc, origin, prev, sel) {
    var ch = origin.charAt(0);
    return ch == "*" ||
      ch == "+" &&
      prev.ranges.length == sel.ranges.length &&
      prev.somethingSelected() == sel.somethingSelected() &&
      new Date - doc.history.lastSelTime <= (doc.cm ? doc.cm.options.historyEventDelay : 500)
  }
```
</details>

### `addSelectionToHistory(doc: any, sel: any, opId: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`sel`** `any`
- **`opId`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `selectionEventCanBeMerged`
- `lst`
- `pushSelectionToHistory`
- `clearSelectionEvents`

**Internal Comments:**
```
// A new event is started when the previous origin does not match
// the current, or the origins don't allow matching. Origins
// starting with * are always merged, those starting with + are
// merged when similar and close together in time.
```

<details><summary>Code</summary>

```typescript
function addSelectionToHistory(doc, sel, opId, options) {
    var hist = doc.history, origin = options && options.origin;

    // A new event is started when the previous origin does not match
    // the current, or the origins don't allow matching. Origins
    // starting with * are always merged, those starting with + are
    // merged when similar and close together in time.
    if (opId == hist.lastSelOp ||
        (origin && hist.lastSelOrigin == origin &&
         (hist.lastModTime == hist.lastSelTime && hist.lastOrigin == origin ||
          selectionEventCanBeMerged(doc, origin, lst(hist.done), sel))))
      { hist.done[hist.done.length - 1] = sel; }
    else
      { pushSelectionToHistory(sel, hist.done); }

    hist.lastSelTime = +new Date;
    hist.lastSelOrigin = origin;
    hist.lastSelOp = opId;
    if (options && options.clearRedo !== false)
      { clearSelectionEvents(hist.undone); }
  }
```
</details>

### `pushSelectionToHistory(sel: any, dest: any): void`

**Parameters:**

- **`sel`** `any`
- **`dest`** `any`

**Returns:** `void`

**Calls:**

- `lst`
- `top.equals`
- `dest.push`

<details><summary>Code</summary>

```typescript
function pushSelectionToHistory(sel, dest) {
    var top = lst(dest);
    if (!(top && top.ranges && top.equals(sel)))
      { dest.push(sel); }
  }
```
</details>

### `attachLocalSpans(doc: any, change: any, from: any, to: any): void`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `void`

**Calls:**

- `doc.iter`
- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function attachLocalSpans(doc, change, from, to) {
    var existing = change["spans_" + doc.id], n = 0;
    doc.iter(Math.max(doc.first, from), Math.min(doc.first + doc.size, to), function (line) {
      if (line.markedSpans)
        { (existing || (existing = change["spans_" + doc.id] = {}))[n] = line.markedSpans; }
      ++n;
    });
  }
```
</details>

### `removeClearedSpans(spans: any): any`

**Parameters:**

- **`spans`** `any`

**Returns:** `any`

**Calls:**

- `spans.slice`
- `out.push`

<details><summary>Code</summary>

```typescript
function removeClearedSpans(spans) {
    if (!spans) { return null }
    var out;
    for (var i = 0; i < spans.length; ++i) {
      if (spans[i].marker.explicitlyCleared) { if (!out) { out = spans.slice(0, i); } }
      else if (out) { out.push(spans[i]); }
    }
    return !out ? spans : out.length ? out : null
  }
```
</details>

### `getOldSpans(doc: any, change: any): any[]`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`

**Returns:** `any[]`

**Calls:**

- `nw.push`
- `removeClearedSpans`

<details><summary>Code</summary>

```typescript
function getOldSpans(doc, change) {
    var found = change["spans_" + doc.id];
    if (!found) { return null }
    var nw = [];
    for (var i = 0; i < change.text.length; ++i)
      { nw.push(removeClearedSpans(found[i])); }
    return nw
  }
```
</details>

### `mergeOldSpans(doc: any, change: any): any[]`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`

**Returns:** `any[]`

**Calls:**

- `getOldSpans`
- `stretchSpansOverChange`
- `oldCur.push`

<details><summary>Code</summary>

```typescript
function mergeOldSpans(doc, change) {
    var old = getOldSpans(doc, change);
    var stretched = stretchSpansOverChange(doc, change);
    if (!old) { return stretched }
    if (!stretched) { return old }

    for (var i = 0; i < old.length; ++i) {
      var oldCur = old[i], stretchCur = stretched[i];
      if (oldCur && stretchCur) {
        spans: for (var j = 0; j < stretchCur.length; ++j) {
          var span = stretchCur[j];
          for (var k = 0; k < oldCur.length; ++k)
            { if (oldCur[k].marker == span.marker) { continue spans } }
          oldCur.push(span);
        }
      } else if (stretchCur) {
        old[i] = stretchCur;
      }
    }
    return old
  }
```
</details>

### `copyHistoryArray(events: any, newGroup: any, instantiateSel: any): any[]`

**Parameters:**

- **`events`** `any`
- **`newGroup`** `any`
- **`instantiateSel`** `any`

**Returns:** `any[]`

**Calls:**

- `copy.push`
- `Selection.prototype.deepCopy.call`
- `newChanges.push`
- `prop.match`
- `indexOf`
- `Number`
- `lst`

<details><summary>Code</summary>

```typescript
function copyHistoryArray(events, newGroup, instantiateSel) {
    var copy = [];
    for (var i = 0; i < events.length; ++i) {
      var event = events[i];
      if (event.ranges) {
        copy.push(instantiateSel ? Selection.prototype.deepCopy.call(event) : event);
        continue
      }
      var changes = event.changes, newChanges = [];
      copy.push({changes: newChanges});
      for (var j = 0; j < changes.length; ++j) {
        var change = changes[j], m = (void 0);
        newChanges.push({from: change.from, to: change.to, text: change.text});
        if (newGroup) { for (var prop in change) { if (m = prop.match(/^spans_(\d+)$/)) {
          if (indexOf(newGroup, Number(m[1])) > -1) {
            lst(newChanges)[prop] = change[prop];
            delete change[prop];
          }
        } } }
      }
    }
    return copy
  }
```
</details>

### `extendRange(range: any, head: any, other: any, extend: any): Range`

**Parameters:**

- **`range`** `any`
- **`head`** `any`
- **`other`** `any`
- **`extend`** `any`

**Returns:** `Range`

**Calls:**

- `cmp`

<details><summary>Code</summary>

```typescript
function extendRange(range, head, other, extend) {
    if (extend) {
      var anchor = range.anchor;
      if (other) {
        var posBefore = cmp(head, anchor) < 0;
        if (posBefore != (cmp(other, anchor) < 0)) {
          anchor = head;
          head = other;
        } else if (posBefore != (cmp(head, other) < 0)) {
          head = other;
        }
      }
      return new Range(anchor, head)
    } else {
      return new Range(other || head, head)
    }
  }
```
</details>

### `extendSelection(doc: any, head: any, other: any, options: any, extend: any): void`

**Parameters:**

- **`doc`** `any`
- **`head`** `any`
- **`other`** `any`
- **`options`** `any`
- **`extend`** `any`

**Returns:** `void`

**Calls:**

- `setSelection`
- `extendRange`
- `doc.sel.primary`

<details><summary>Code</summary>

```typescript
function extendSelection(doc, head, other, options, extend) {
    if (extend == null) { extend = doc.cm && (doc.cm.display.shift || doc.extend); }
    setSelection(doc, new Selection([extendRange(doc.sel.primary(), head, other, extend)], 0), options);
  }
```
</details>

### `extendSelections(doc: any, heads: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`heads`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `extendRange`
- `normalizeSelection`
- `setSelection`

<details><summary>Code</summary>

```typescript
function extendSelections(doc, heads, options) {
    var out = [];
    var extend = doc.cm && (doc.cm.display.shift || doc.extend);
    for (var i = 0; i < doc.sel.ranges.length; i++)
      { out[i] = extendRange(doc.sel.ranges[i], heads[i], null, extend); }
    var newSel = normalizeSelection(doc.cm, out, doc.sel.primIndex);
    setSelection(doc, newSel, options);
  }
```
</details>

### `replaceOneSelection(doc: any, i: any, range: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`i`** `any`
- **`range`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `doc.sel.ranges.slice`
- `setSelection`
- `normalizeSelection`

<details><summary>Code</summary>

```typescript
function replaceOneSelection(doc, i, range, options) {
    var ranges = doc.sel.ranges.slice(0);
    ranges[i] = range;
    setSelection(doc, normalizeSelection(doc.cm, ranges, doc.sel.primIndex), options);
  }
```
</details>

### `setSimpleSelection(doc: any, anchor: any, head: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`anchor`** `any`
- **`head`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `setSelection`
- `simpleSelection`

<details><summary>Code</summary>

```typescript
function setSimpleSelection(doc, anchor, head, options) {
    setSelection(doc, simpleSelection(anchor, head), options);
  }
```
</details>

### `filterSelectionChange(doc: any, sel: any, options: any): any`

**Parameters:**

- **`doc`** `any`
- **`sel`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `signal`
- `normalizeSelection`

<details><summary>Code</summary>

```typescript
function filterSelectionChange(doc, sel, options) {
    var obj = {
      ranges: sel.ranges,
      update: function(ranges) {
        this.ranges = [];
        for (var i = 0; i < ranges.length; i++)
          { this.ranges[i] = new Range(clipPos(doc, ranges[i].anchor),
                                     clipPos(doc, ranges[i].head)); }
      },
      origin: options && options.origin
    };
    signal(doc, "beforeSelectionChange", doc, obj);
    if (doc.cm) { signal(doc.cm, "beforeSelectionChange", doc.cm, obj); }
    if (obj.ranges != sel.ranges) { return normalizeSelection(doc.cm, obj.ranges, obj.ranges.length - 1) }
    else { return sel }
  }
```
</details>

### `update(ranges: any): void`

**Parameters:**

- **`ranges`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(ranges) {
        this.ranges = [];
        for (var i = 0; i < ranges.length; i++)
          { this.ranges[i] = new Range(clipPos(doc, ranges[i].anchor),
                                     clipPos(doc, ranges[i].head)); }
      }
```
</details>

### `update(ranges: any): void`

**Parameters:**

- **`ranges`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(ranges) {
        this.ranges = [];
        for (var i = 0; i < ranges.length; i++)
          { this.ranges[i] = new Range(clipPos(doc, ranges[i].anchor),
                                     clipPos(doc, ranges[i].head)); }
      }
```
</details>

### `update(ranges: any): void`

**Parameters:**

- **`ranges`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(ranges) {
        this.ranges = [];
        for (var i = 0; i < ranges.length; i++)
          { this.ranges[i] = new Range(clipPos(doc, ranges[i].anchor),
                                     clipPos(doc, ranges[i].head)); }
      }
```
</details>

### `update(ranges: any): void`

**Parameters:**

- **`ranges`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(ranges) {
        this.ranges = [];
        for (var i = 0; i < ranges.length; i++)
          { this.ranges[i] = new Range(clipPos(doc, ranges[i].anchor),
                                     clipPos(doc, ranges[i].head)); }
      }
```
</details>

### `update(ranges: any): void`

**Parameters:**

- **`ranges`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(ranges) {
        this.ranges = [];
        for (var i = 0; i < ranges.length; i++)
          { this.ranges[i] = new Range(clipPos(doc, ranges[i].anchor),
                                     clipPos(doc, ranges[i].head)); }
      }
```
</details>

### `update(ranges: any): void`

**Parameters:**

- **`ranges`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(ranges) {
        this.ranges = [];
        for (var i = 0; i < ranges.length; i++)
          { this.ranges[i] = new Range(clipPos(doc, ranges[i].anchor),
                                     clipPos(doc, ranges[i].head)); }
      }
```
</details>

### `setSelectionReplaceHistory(doc: any, sel: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`sel`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `lst`
- `setSelectionNoUndo`
- `setSelection`

<details><summary>Code</summary>

```typescript
function setSelectionReplaceHistory(doc, sel, options) {
    var done = doc.history.done, last = lst(done);
    if (last && last.ranges) {
      done[done.length - 1] = sel;
      setSelectionNoUndo(doc, sel, options);
    } else {
      setSelection(doc, sel, options);
    }
  }
```
</details>

### `setSelection(doc: any, sel: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`sel`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `setSelectionNoUndo`
- `addSelectionToHistory`

<details><summary>Code</summary>

```typescript
function setSelection(doc, sel, options) {
    setSelectionNoUndo(doc, sel, options);
    addSelectionToHistory(doc, doc.sel, doc.cm ? doc.cm.curOp.id : NaN, options);
  }
```
</details>

### `setSelectionNoUndo(doc: any, sel: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`sel`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `hasHandler`
- `filterSelectionChange`
- `cmp`
- `sel.primary`
- `doc.sel.primary`
- `setSelectionInner`
- `skipAtomicInSelection`
- `doc.cm.getOption`
- `ensureCursorVisible`

<details><summary>Code</summary>

```typescript
function setSelectionNoUndo(doc, sel, options) {
    if (hasHandler(doc, "beforeSelectionChange") || doc.cm && hasHandler(doc.cm, "beforeSelectionChange"))
      { sel = filterSelectionChange(doc, sel, options); }

    var bias = options && options.bias ||
      (cmp(sel.primary().head, doc.sel.primary().head) < 0 ? -1 : 1);
    setSelectionInner(doc, skipAtomicInSelection(doc, sel, bias, true));

    if (!(options && options.scroll === false) && doc.cm && doc.cm.getOption("readOnly") != "nocursor")
      { ensureCursorVisible(doc.cm); }
  }
```
</details>

### `setSelectionInner(doc: any, sel: any): void`

**Parameters:**

- **`doc`** `any`
- **`sel`** `any`

**Returns:** `void`

**Calls:**

- `sel.equals`
- `signalCursorActivity`
- `signalLater`

<details><summary>Code</summary>

```typescript
function setSelectionInner(doc, sel) {
    if (sel.equals(doc.sel)) { return }

    doc.sel = sel;

    if (doc.cm) {
      doc.cm.curOp.updateInput = 1;
      doc.cm.curOp.selectionChanged = true;
      signalCursorActivity(doc.cm);
    }
    signalLater(doc, "cursorActivity", doc);
  }
```
</details>

### `reCheckSelection(doc: any): void`

**Parameters:**

- **`doc`** `any`

**Returns:** `void`

**Calls:**

- `setSelectionInner`
- `skipAtomicInSelection`

<details><summary>Code</summary>

```typescript
function reCheckSelection(doc) {
    setSelectionInner(doc, skipAtomicInSelection(doc, doc.sel, null, false));
  }
```
</details>

### `skipAtomicInSelection(doc: any, sel: any, bias: any, mayClear: any): any`

**Parameters:**

- **`doc`** `any`
- **`sel`** `any`
- **`bias`** `any`
- **`mayClear`** `any`

**Returns:** `any`

**Calls:**

- `skipAtomic`
- `sel.ranges.slice`
- `normalizeSelection`

<details><summary>Code</summary>

```typescript
function skipAtomicInSelection(doc, sel, bias, mayClear) {
    var out;
    for (var i = 0; i < sel.ranges.length; i++) {
      var range = sel.ranges[i];
      var old = sel.ranges.length == doc.sel.ranges.length && doc.sel.ranges[i];
      var newAnchor = skipAtomic(doc, range.anchor, old && old.anchor, bias, mayClear);
      var newHead = skipAtomic(doc, range.head, old && old.head, bias, mayClear);
      if (out || newAnchor != range.anchor || newHead != range.head) {
        if (!out) { out = sel.ranges.slice(0, i); }
        out[i] = new Range(newAnchor, newHead);
      }
    }
    return out ? normalizeSelection(doc.cm, out, sel.primIndex) : sel
  }
```
</details>

### `skipAtomicInner(doc: any, pos: any, oldPos: any, dir: any, mayClear: any): any`

**Parameters:**

- **`doc`** `any`
- **`pos`** `any`
- **`oldPos`** `any`
- **`dir`** `any`
- **`mayClear`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `signal`
- `m.find`
- `movePos`
- `cmp`
- `skipAtomicInner`

**Internal Comments:**
```
// Determine if we should prevent the cursor being placed to the left/right of an atomic marker (x2)
// Historically this was determined using the inclusiveLeft/Right option, but the new way to control it (x2)
// is with selectLeft/Right (x2)
```

<details><summary>Code</summary>

```typescript
function skipAtomicInner(doc, pos, oldPos, dir, mayClear) {
    var line = getLine(doc, pos.line);
    if (line.markedSpans) { for (var i = 0; i < line.markedSpans.length; ++i) {
      var sp = line.markedSpans[i], m = sp.marker;

      // Determine if we should prevent the cursor being placed to the left/right of an atomic marker
      // Historically this was determined using the inclusiveLeft/Right option, but the new way to control it
      // is with selectLeft/Right
      var preventCursorLeft = ("selectLeft" in m) ? !m.selectLeft : m.inclusiveLeft;
      var preventCursorRight = ("selectRight" in m) ? !m.selectRight : m.inclusiveRight;

      if ((sp.from == null || (preventCursorLeft ? sp.from <= pos.ch : sp.from < pos.ch)) &&
          (sp.to == null || (preventCursorRight ? sp.to >= pos.ch : sp.to > pos.ch))) {
        if (mayClear) {
          signal(m, "beforeCursorEnter");
          if (m.explicitlyCleared) {
            if (!line.markedSpans) { break }
            else {--i; continue}
          }
        }
        if (!m.atomic) { continue }

        if (oldPos) {
          var near = m.find(dir < 0 ? 1 : -1), diff = (void 0);
          if (dir < 0 ? preventCursorRight : preventCursorLeft)
            { near = movePos(doc, near, -dir, near && near.line == pos.line ? line : null); }
          if (near && near.line == pos.line && (diff = cmp(near, oldPos)) && (dir < 0 ? diff < 0 : diff > 0))
            { return skipAtomicInner(doc, near, pos, dir, mayClear) }
        }

        var far = m.find(dir < 0 ? -1 : 1);
        if (dir < 0 ? preventCursorLeft : preventCursorRight)
          { far = movePos(doc, far, dir, far.line == pos.line ? line : null); }
        return far ? skipAtomicInner(doc, far, pos, dir, mayClear) : null
      }
    } }
    return pos
  }
```
</details>

### `skipAtomic(doc: any, pos: any, oldPos: any, bias: any, mayClear: any): any`

**Parameters:**

- **`doc`** `any`
- **`pos`** `any`
- **`oldPos`** `any`
- **`bias`** `any`
- **`mayClear`** `any`

**Returns:** `any`

**Calls:**

- `skipAtomicInner`
- `Pos`

<details><summary>Code</summary>

```typescript
function skipAtomic(doc, pos, oldPos, bias, mayClear) {
    var dir = bias || 1;
    var found = skipAtomicInner(doc, pos, oldPos, dir, mayClear) ||
        (!mayClear && skipAtomicInner(doc, pos, oldPos, dir, true)) ||
        skipAtomicInner(doc, pos, oldPos, -dir, mayClear) ||
        (!mayClear && skipAtomicInner(doc, pos, oldPos, -dir, true));
    if (!found) {
      doc.cantEdit = true;
      return Pos(doc.first, 0)
    }
    return found
  }
```
</details>

### `movePos(doc: any, pos: any, dir: any, line: any): any`

**Parameters:**

- **`doc`** `any`
- **`pos`** `any`
- **`dir`** `any`
- **`line`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `Pos`
- `getLine`

<details><summary>Code</summary>

```typescript
function movePos(doc, pos, dir, line) {
    if (dir < 0 && pos.ch == 0) {
      if (pos.line > doc.first) { return clipPos(doc, Pos(pos.line - 1)) }
      else { return null }
    } else if (dir > 0 && pos.ch == (line || getLine(doc, pos.line)).text.length) {
      if (pos.line < doc.first + doc.size - 1) { return Pos(pos.line + 1, 0) }
      else { return null }
    } else {
      return new Pos(pos.line, pos.ch + dir)
    }
  }
```
</details>

### `selectAll(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.setSelection`
- `Pos`
- `cm.firstLine`
- `cm.lastLine`

<details><summary>Code</summary>

```typescript
function selectAll(cm) {
    cm.setSelection(Pos(cm.firstLine(), 0), Pos(cm.lastLine()), sel_dontScroll);
  }
```
</details>

### `filterChange(doc: any, change: any, update: any): { from: any; to: any; text: any; origin: any; }`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`
- **`update`** `any`

**Returns:** `{ from: any; to: any; text: any; origin: any; }`

**Calls:**

- `clipPos`
- `signal`

<details><summary>Code</summary>

```typescript
function filterChange(doc, change, update) {
    var obj = {
      canceled: false,
      from: change.from,
      to: change.to,
      text: change.text,
      origin: change.origin,
      cancel: function () { return obj.canceled = true; }
    };
    if (update) { obj.update = function (from, to, text, origin) {
      if (from) { obj.from = clipPos(doc, from); }
      if (to) { obj.to = clipPos(doc, to); }
      if (text) { obj.text = text; }
      if (origin !== undefined) { obj.origin = origin; }
    }; }
    signal(doc, "beforeChange", doc, obj);
    if (doc.cm) { signal(doc.cm, "beforeChange", doc.cm, obj); }

    if (obj.canceled) {
      if (doc.cm) { doc.cm.curOp.updateInput = 2; }
      return null
    }
    return {from: obj.from, to: obj.to, text: obj.text, origin: obj.origin}
  }
```
</details>

### `cancel(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () { return obj.canceled = true; }
```
</details>

### `cancel(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () { return obj.canceled = true; }
```
</details>

### `cancel(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () { return obj.canceled = true; }
```
</details>

### `cancel(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () { return obj.canceled = true; }
```
</details>

### `cancel(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () { return obj.canceled = true; }
```
</details>

### `cancel(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () { return obj.canceled = true; }
```
</details>

### `makeChange(doc: any, change: any, ignoreReadOnly: any): any`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`
- **`ignoreReadOnly`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_217268`
- `hasHandler`
- `filterChange`
- `removeReadOnlyRanges`
- `makeChangeInner`

**Internal Comments:**
```
// Possibly split or suppress the update based on the presence (x2)
// of read-only spans in its range. (x2)
```

<details><summary>Code</summary>

```typescript
function makeChange(doc, change, ignoreReadOnly) {
    if (doc.cm) {
      if (!doc.cm.curOp) { return operation(doc.cm, makeChange)(doc, change, ignoreReadOnly) }
      if (doc.cm.state.suppressEdits) { return }
    }

    if (hasHandler(doc, "beforeChange") || doc.cm && hasHandler(doc.cm, "beforeChange")) {
      change = filterChange(doc, change, true);
      if (!change) { return }
    }

    // Possibly split or suppress the update based on the presence
    // of read-only spans in its range.
    var split = sawReadOnlySpans && !ignoreReadOnly && removeReadOnlyRanges(doc, change.from, change.to);
    if (split) {
      for (var i = split.length - 1; i >= 0; --i)
        { makeChangeInner(doc, {from: split[i].from, to: split[i].to, text: i ? [""] : change.text, origin: change.origin}); }
    } else {
      makeChangeInner(doc, change);
    }
  }
```
</details>

### `makeChangeInner(doc: any, change: any): void`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`

**Returns:** `void`

**Calls:**

- `cmp`
- `computeSelAfterChange`
- `addChangeToHistory`
- `makeChangeSingleDoc`
- `stretchSpansOverChange`
- `linkedDocs`
- `indexOf`
- `rebaseHist`
- `rebased.push`

<details><summary>Code</summary>

```typescript
function makeChangeInner(doc, change) {
    if (change.text.length == 1 && change.text[0] == "" && cmp(change.from, change.to) == 0) { return }
    var selAfter = computeSelAfterChange(doc, change);
    addChangeToHistory(doc, change, selAfter, doc.cm ? doc.cm.curOp.id : NaN);

    makeChangeSingleDoc(doc, change, selAfter, stretchSpansOverChange(doc, change));
    var rebased = [];

    linkedDocs(doc, function (doc, sharedHist) {
      if (!sharedHist && indexOf(rebased, doc.history) == -1) {
        rebaseHist(doc.history, change);
        rebased.push(doc.history);
      }
      makeChangeSingleDoc(doc, change, null, stretchSpansOverChange(doc, change));
    });
  }
```
</details>

### `makeChangeFromHistory(doc: any, type: any, allowSelectionOnly: any): any`

**Parameters:**

- **`doc`** `any`
- **`type`** `any`
- **`allowSelectionOnly`** `any`

**Returns:** `any`

**Calls:**

- `event.equals`
- `source.pop`
- `pushSelectionToHistory`
- `setSelection`
- `source.push`
- `dest.push`
- `hasHandler`
- `filterChange`
- `antiChanges.push`
- `historyChangeFromChange`
- `computeSelAfterChange`
- `lst`
- `makeChangeSingleDoc`
- `mergeOldSpans`
- `doc.cm.scrollIntoView`
- `changeEnd`
- `linkedDocs`
- `indexOf`
- `rebaseHist`
- `rebased.push`
- `loop`

**Internal Comments:**
```
// Verify that there is a useable event (so that ctrl-z won't (x2)
// needlessly clear selection events) (x2)
// Build up a reverse change object to add to the opposite history (x2)
// stack (redo when undoing, and vice versa). (x2)
// Propagate to the linked documents (x3)
```

<details><summary>Code</summary>

```typescript
function makeChangeFromHistory(doc, type, allowSelectionOnly) {
    var suppress = doc.cm && doc.cm.state.suppressEdits;
    if (suppress && !allowSelectionOnly) { return }

    var hist = doc.history, event, selAfter = doc.sel;
    var source = type == "undo" ? hist.done : hist.undone, dest = type == "undo" ? hist.undone : hist.done;

    // Verify that there is a useable event (so that ctrl-z won't
    // needlessly clear selection events)
    var i = 0;
    for (; i < source.length; i++) {
      event = source[i];
      if (allowSelectionOnly ? event.ranges && !event.equals(doc.sel) : !event.ranges)
        { break }
    }
    if (i == source.length) { return }
    hist.lastOrigin = hist.lastSelOrigin = null;

    for (;;) {
      event = source.pop();
      if (event.ranges) {
        pushSelectionToHistory(event, dest);
        if (allowSelectionOnly && !event.equals(doc.sel)) {
          setSelection(doc, event, {clearRedo: false});
          return
        }
        selAfter = event;
      } else if (suppress) {
        source.push(event);
        return
      } else { break }
    }

    // Build up a reverse change object to add to the opposite history
    // stack (redo when undoing, and vice versa).
    var antiChanges = [];
    pushSelectionToHistory(selAfter, dest);
    dest.push({changes: antiChanges, generation: hist.generation});
    hist.generation = event.generation || ++hist.maxGeneration;

    var filter = hasHandler(doc, "beforeChange") || doc.cm && hasHandler(doc.cm, "beforeChange");

    var loop = function ( i ) {
      var change = event.changes[i];
      change.origin = type;
      if (filter && !filterChange(doc, change, false)) {
        source.length = 0;
        return {}
      }

      antiChanges.push(historyChangeFromChange(doc, change));

      var after = i ? computeSelAfterChange(doc, change) : lst(source);
      makeChangeSingleDoc(doc, change, after, mergeOldSpans(doc, change));
      if (!i && doc.cm) { doc.cm.scrollIntoView({from: change.from, to: changeEnd(change)}); }
      var rebased = [];

      // Propagate to the linked documents
      linkedDocs(doc, function (doc, sharedHist) {
        if (!sharedHist && indexOf(rebased, doc.history) == -1) {
          rebaseHist(doc.history, change);
          rebased.push(doc.history);
        }
        makeChangeSingleDoc(doc, change, null, mergeOldSpans(doc, change));
      });
    };

    for (var i$1 = event.changes.length - 1; i$1 >= 0; --i$1) {
      var returned = loop( i$1 );

      if ( returned ) return returned.v;
    }
  }
```
</details>

### `loop(i: any): {}`

**Parameters:**

- **`i`** `any`

**Returns:** `{}`

**Calls:**

- `filterChange`
- `antiChanges.push`
- `historyChangeFromChange`
- `computeSelAfterChange`
- `lst`
- `makeChangeSingleDoc`
- `mergeOldSpans`
- `doc.cm.scrollIntoView`
- `changeEnd`
- `linkedDocs`
- `indexOf`
- `rebaseHist`
- `rebased.push`

**Internal Comments:**
```
// Propagate to the linked documents (x3)
```

<details><summary>Code</summary>

```typescript
function ( i ) {
      var change = event.changes[i];
      change.origin = type;
      if (filter && !filterChange(doc, change, false)) {
        source.length = 0;
        return {}
      }

      antiChanges.push(historyChangeFromChange(doc, change));

      var after = i ? computeSelAfterChange(doc, change) : lst(source);
      makeChangeSingleDoc(doc, change, after, mergeOldSpans(doc, change));
      if (!i && doc.cm) { doc.cm.scrollIntoView({from: change.from, to: changeEnd(change)}); }
      var rebased = [];

      // Propagate to the linked documents
      linkedDocs(doc, function (doc, sharedHist) {
        if (!sharedHist && indexOf(rebased, doc.history) == -1) {
          rebaseHist(doc.history, change);
          rebased.push(doc.history);
        }
        makeChangeSingleDoc(doc, change, null, mergeOldSpans(doc, change));
      });
    }
```
</details>

### `shiftDoc(doc: any, distance: any): void`

**Parameters:**

- **`doc`** `any`
- **`distance`** `any`

**Returns:** `void`

**Calls:**

- `map`
- `Pos`
- `regChange`
- `regLineChange`

<details><summary>Code</summary>

```typescript
function shiftDoc(doc, distance) {
    if (distance == 0) { return }
    doc.first += distance;
    doc.sel = new Selection(map(doc.sel.ranges, function (range) { return new Range(
      Pos(range.anchor.line + distance, range.anchor.ch),
      Pos(range.head.line + distance, range.head.ch)
    ); }), doc.sel.primIndex);
    if (doc.cm) {
      regChange(doc.cm, doc.first, doc.first - distance, distance);
      for (var d = doc.cm.display, l = d.viewFrom; l < d.viewTo; l++)
        { regLineChange(doc.cm, l, "gutter"); }
    }
  }
```
</details>

### `makeChangeSingleDoc(doc: any, change: any, selAfter: any, spans: any): any`

**Parameters:**

- **`doc`** `any`
- **`change`** `any`
- **`selAfter`** `any`
- **`spans`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_222190`
- `shiftDoc`
- `doc.lastLine`
- `Pos`
- `lst`
- `getLine`
- `getBetween`
- `computeSelAfterChange`
- `makeChangeSingleDocInEditor`
- `updateDoc`
- `setSelectionNoUndo`
- `skipAtomic`
- `doc.firstLine`

**Internal Comments:**
```
// Clip the change to the size of this doc
```

<details><summary>Code</summary>

```typescript
function makeChangeSingleDoc(doc, change, selAfter, spans) {
    if (doc.cm && !doc.cm.curOp)
      { return operation(doc.cm, makeChangeSingleDoc)(doc, change, selAfter, spans) }

    if (change.to.line < doc.first) {
      shiftDoc(doc, change.text.length - 1 - (change.to.line - change.from.line));
      return
    }
    if (change.from.line > doc.lastLine()) { return }

    // Clip the change to the size of this doc
    if (change.from.line < doc.first) {
      var shift = change.text.length - 1 - (doc.first - change.from.line);
      shiftDoc(doc, shift);
      change = {from: Pos(doc.first, 0), to: Pos(change.to.line + shift, change.to.ch),
                text: [lst(change.text)], origin: change.origin};
    }
    var last = doc.lastLine();
    if (change.to.line > last) {
      change = {from: change.from, to: Pos(last, getLine(doc, last).text.length),
                text: [change.text[0]], origin: change.origin};
    }

    change.removed = getBetween(doc, change.from, change.to);

    if (!selAfter) { selAfter = computeSelAfterChange(doc, change); }
    if (doc.cm) { makeChangeSingleDocInEditor(doc.cm, change, spans); }
    else { updateDoc(doc, change, spans); }
    setSelectionNoUndo(doc, selAfter, sel_dontScroll);

    if (doc.cantEdit && skipAtomic(doc, Pos(doc.firstLine(), 0)))
      { doc.cantEdit = false; }
  }
```
</details>

### `makeChangeSingleDocInEditor(cm: any, change: any, spans: any): void`

**Parameters:**

- **`cm`** `any`
- **`change`** `any`
- **`spans`** `any`

**Returns:** `void`

**Calls:**

- `lineNo`
- `visualLine`
- `getLine`
- `doc.iter`
- `doc.sel.contains`
- `signalCursorActivity`
- `updateDoc`
- `estimateHeight`
- `lineLength`
- `retreatFrontier`
- `startWorker`
- `regChange`
- `isWholeLineUpdate`
- `regLineChange`
- `hasHandler`
- `signalLater`
- `(cm.curOp.changeObjs || (cm.curOp.changeObjs = [])).push`

**Internal Comments:**
```
// Remember that these lines changed, for updating the display
```

<details><summary>Code</summary>

```typescript
function makeChangeSingleDocInEditor(cm, change, spans) {
    var doc = cm.doc, display = cm.display, from = change.from, to = change.to;

    var recomputeMaxLength = false, checkWidthStart = from.line;
    if (!cm.options.lineWrapping) {
      checkWidthStart = lineNo(visualLine(getLine(doc, from.line)));
      doc.iter(checkWidthStart, to.line + 1, function (line) {
        if (line == display.maxLine) {
          recomputeMaxLength = true;
          return true
        }
      });
    }

    if (doc.sel.contains(change.from, change.to) > -1)
      { signalCursorActivity(cm); }

    updateDoc(doc, change, spans, estimateHeight(cm));

    if (!cm.options.lineWrapping) {
      doc.iter(checkWidthStart, from.line + change.text.length, function (line) {
        var len = lineLength(line);
        if (len > display.maxLineLength) {
          display.maxLine = line;
          display.maxLineLength = len;
          display.maxLineChanged = true;
          recomputeMaxLength = false;
        }
      });
      if (recomputeMaxLength) { cm.curOp.updateMaxLine = true; }
    }

    retreatFrontier(doc, from.line);
    startWorker(cm, 400);

    var lendiff = change.text.length - (to.line - from.line) - 1;
    // Remember that these lines changed, for updating the display
    if (change.full)
      { regChange(cm); }
    else if (from.line == to.line && change.text.length == 1 && !isWholeLineUpdate(cm.doc, change))
      { regLineChange(cm, from.line, "text"); }
    else
      { regChange(cm, from.line, to.line + 1, lendiff); }

    var changesHandler = hasHandler(cm, "changes"), changeHandler = hasHandler(cm, "change");
    if (changeHandler || changesHandler) {
      var obj = {
        from: from, to: to,
        text: change.text,
        removed: change.removed,
        origin: change.origin
      };
      if (changeHandler) { signalLater(cm, "change", cm, obj); }
      if (changesHandler) { (cm.curOp.changeObjs || (cm.curOp.changeObjs = [])).push(obj); }
    }
    cm.display.selForContextMenu = null;
  }
```
</details>

### `replaceRange(doc: any, code: any, from: any, to: any, origin: any): void`

**Parameters:**

- **`doc`** `any`
- **`code`** `any`
- **`from`** `any`
- **`to`** `any`
- **`origin`** `any`

**Returns:** `void`

**Calls:**

- `cmp`
- `doc.splitLines`
- `makeChange`

<details><summary>Code</summary>

```typescript
function replaceRange(doc, code, from, to, origin) {
    var assign;

    if (!to) { to = from; }
    if (cmp(to, from) < 0) { (assign = [to, from], from = assign[0], to = assign[1]); }
    if (typeof code == "string") { code = doc.splitLines(code); }
    makeChange(doc, {from: from, to: to, text: code, origin: origin});
  }
```
</details>

### `rebaseHistSelSingle(pos: any, from: any, to: any, diff: any): void`

**Parameters:**

- **`pos`** `any`
- **`from`** `any`
- **`to`** `any`
- **`diff`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function rebaseHistSelSingle(pos, from, to, diff) {
    if (to < pos.line) {
      pos.line += diff;
    } else if (from < pos.line) {
      pos.line = from;
      pos.ch = 0;
    }
  }
```
</details>

### `rebaseHistArray(array: any, from: any, to: any, diff: any): void`

**Parameters:**

- **`array`** `any`
- **`from`** `any`
- **`to`** `any`
- **`diff`** `any`

**Returns:** `void`

**Calls:**

- `sub.deepCopy`
- `rebaseHistSelSingle`
- `Pos`
- `array.splice`

<details><summary>Code</summary>

```typescript
function rebaseHistArray(array, from, to, diff) {
    for (var i = 0; i < array.length; ++i) {
      var sub = array[i], ok = true;
      if (sub.ranges) {
        if (!sub.copied) { sub = array[i] = sub.deepCopy(); sub.copied = true; }
        for (var j = 0; j < sub.ranges.length; j++) {
          rebaseHistSelSingle(sub.ranges[j].anchor, from, to, diff);
          rebaseHistSelSingle(sub.ranges[j].head, from, to, diff);
        }
        continue
      }
      for (var j$1 = 0; j$1 < sub.changes.length; ++j$1) {
        var cur = sub.changes[j$1];
        if (to < cur.from.line) {
          cur.from = Pos(cur.from.line + diff, cur.from.ch);
          cur.to = Pos(cur.to.line + diff, cur.to.ch);
        } else if (from <= cur.to.line) {
          ok = false;
          break
        }
      }
      if (!ok) {
        array.splice(0, i + 1);
        i = 0;
      }
    }
  }
```
</details>

### `rebaseHist(hist: any, change: any): void`

**Parameters:**

- **`hist`** `any`
- **`change`** `any`

**Returns:** `void`

**Calls:**

- `rebaseHistArray`

<details><summary>Code</summary>

```typescript
function rebaseHist(hist, change) {
    var from = change.from.line, to = change.to.line, diff = change.text.length - (to - from) - 1;
    rebaseHistArray(hist.done, from, to, diff);
    rebaseHistArray(hist.undone, from, to, diff);
  }
```
</details>

### `changeLine(doc: any, handle: any, changeType: any, op: any): any`

**Parameters:**

- **`doc`** `any`
- **`handle`** `any`
- **`changeType`** `any`
- **`op`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `clipLine`
- `lineNo`
- `op`
- `regLineChange`

<details><summary>Code</summary>

```typescript
function changeLine(doc, handle, changeType, op) {
    var no = handle, line = handle;
    if (typeof handle == "number") { line = getLine(doc, clipLine(doc, handle)); }
    else { no = lineNo(handle); }
    if (no == null) { return null }
    if (op(line, no) && doc.cm) { regLineChange(doc.cm, no, changeType); }
    return line
  }
```
</details>

### `LeafChunk(lines: any): void`

**Parameters:**

- **`lines`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function LeafChunk(lines) {
    this.lines = lines;
    this.parent = null;
    var height = 0;
    for (var i = 0; i < lines.length; ++i) {
      lines[i].parent = this;
      height += lines[i].height;
    }
    this.height = height;
  }
```
</details>

### `chunkSize(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.lines.length }
```
</details>

### `removeInner(at: any, n: any): void`

**Parameters:**

- **`at`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `cleanUpLine`
- `signalLater`
- `this.lines.splice`

<details><summary>Code</summary>

```typescript
function(at, n) {
      for (var i = at, e = at + n; i < e; ++i) {
        var line = this.lines[i];
        this.height -= line.height;
        cleanUpLine(line);
        signalLater(line, "delete");
      }
      this.lines.splice(at, n);
    }
```
</details>

### `collapse(lines: any): void`

**Parameters:**

- **`lines`** `any`

**Returns:** `void`

**Calls:**

- `lines.push.apply`

<details><summary>Code</summary>

```typescript
function(lines) {
      lines.push.apply(lines, this.lines);
    }
```
</details>

### `insertInner(at: any, lines: any, height: any): void`

**Parameters:**

- **`at`** `any`
- **`lines`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `this.lines.slice(0, at).concat(lines).concat`
- `this.lines.slice`

<details><summary>Code</summary>

```typescript
function(at, lines, height) {
      this.height += height;
      this.lines = this.lines.slice(0, at).concat(lines).concat(this.lines.slice(at));
      for (var i = 0; i < lines.length; ++i) { lines[i].parent = this; }
    }
```
</details>

### `iterN(at: any, n: any, op: any): boolean`

**Parameters:**

- **`at`** `any`
- **`n`** `any`
- **`op`** `any`

**Returns:** `boolean`

**Calls:**

- `op`

<details><summary>Code</summary>

```typescript
function(at, n, op) {
      for (var e = at + n; at < e; ++at)
        { if (op(this.lines[at])) { return true } }
    }
```
</details>

### `chunkSize(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.lines.length }
```
</details>

### `removeInner(at: any, n: any): void`

**Parameters:**

- **`at`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `cleanUpLine`
- `signalLater`
- `this.lines.splice`

<details><summary>Code</summary>

```typescript
function(at, n) {
      for (var i = at, e = at + n; i < e; ++i) {
        var line = this.lines[i];
        this.height -= line.height;
        cleanUpLine(line);
        signalLater(line, "delete");
      }
      this.lines.splice(at, n);
    }
```
</details>

### `collapse(lines: any): void`

**Parameters:**

- **`lines`** `any`

**Returns:** `void`

**Calls:**

- `lines.push.apply`

<details><summary>Code</summary>

```typescript
function(lines) {
      lines.push.apply(lines, this.lines);
    }
```
</details>

### `insertInner(at: any, lines: any, height: any): void`

**Parameters:**

- **`at`** `any`
- **`lines`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `this.lines.slice(0, at).concat(lines).concat`
- `this.lines.slice`

<details><summary>Code</summary>

```typescript
function(at, lines, height) {
      this.height += height;
      this.lines = this.lines.slice(0, at).concat(lines).concat(this.lines.slice(at));
      for (var i = 0; i < lines.length; ++i) { lines[i].parent = this; }
    }
```
</details>

### `iterN(at: any, n: any, op: any): boolean`

**Parameters:**

- **`at`** `any`
- **`n`** `any`
- **`op`** `any`

**Returns:** `boolean`

**Calls:**

- `op`

<details><summary>Code</summary>

```typescript
function(at, n, op) {
      for (var e = at + n; at < e; ++at)
        { if (op(this.lines[at])) { return true } }
    }
```
</details>

### `BranchChunk(children: any): void`

**Parameters:**

- **`children`** `any`

**Returns:** `void`

**Calls:**

- `ch.chunkSize`

<details><summary>Code</summary>

```typescript
function BranchChunk(children) {
    this.children = children;
    var size = 0, height = 0;
    for (var i = 0; i < children.length; ++i) {
      var ch = children[i];
      size += ch.chunkSize(); height += ch.height;
      ch.parent = this;
    }
    this.size = size;
    this.height = height;
    this.parent = null;
  }
```
</details>

### `chunkSize(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function() { return this.size }
```
</details>

### `removeInner(at: any, n: any): void`

**Parameters:**

- **`at`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `child.chunkSize`
- `Math.min`
- `child.removeInner`
- `this.children.splice`
- `this.collapse`

**Internal Comments:**
```
// If the result is smaller than 25 lines, ensure that it is a
// single leaf node.
```

<details><summary>Code</summary>

```typescript
function(at, n) {
      this.size -= n;
      for (var i = 0; i < this.children.length; ++i) {
        var child = this.children[i], sz = child.chunkSize();
        if (at < sz) {
          var rm = Math.min(n, sz - at), oldHeight = child.height;
          child.removeInner(at, rm);
          this.height -= oldHeight - child.height;
          if (sz == rm) { this.children.splice(i--, 1); child.parent = null; }
          if ((n -= rm) == 0) { break }
          at = 0;
        } else { at -= sz; }
      }
      // If the result is smaller than 25 lines, ensure that it is a
      // single leaf node.
      if (this.size - n < 25 &&
          (this.children.length > 1 || !(this.children[0] instanceof LeafChunk))) {
        var lines = [];
        this.collapse(lines);
        this.children = [new LeafChunk(lines)];
        this.children[0].parent = this;
      }
    }
```
</details>

### `collapse(lines: any): void`

**Parameters:**

- **`lines`** `any`

**Returns:** `void`

**Calls:**

- `this.children[i].collapse`

<details><summary>Code</summary>

```typescript
function(lines) {
      for (var i = 0; i < this.children.length; ++i) { this.children[i].collapse(lines); }
    }
```
</details>

### `insertInner(at: any, lines: any, height: any): void`

**Parameters:**

- **`at`** `any`
- **`lines`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `child.chunkSize`
- `child.insertInner`
- `child.lines.slice`
- `this.children.splice`
- `this.maybeSpill`

**Internal Comments:**
```
// To avoid memory thrashing when child.lines is huge (e.g. first view of a large file), it's never spliced. (x2)
// Instead, small slices are taken. They're taken in order because sequential memory accesses are fastest. (x2)
```

<details><summary>Code</summary>

```typescript
function(at, lines, height) {
      this.size += lines.length;
      this.height += height;
      for (var i = 0; i < this.children.length; ++i) {
        var child = this.children[i], sz = child.chunkSize();
        if (at <= sz) {
          child.insertInner(at, lines, height);
          if (child.lines && child.lines.length > 50) {
            // To avoid memory thrashing when child.lines is huge (e.g. first view of a large file), it's never spliced.
            // Instead, small slices are taken. They're taken in order because sequential memory accesses are fastest.
            var remaining = child.lines.length % 25 + 25;
            for (var pos = remaining; pos < child.lines.length;) {
              var leaf = new LeafChunk(child.lines.slice(pos, pos += 25));
              child.height -= leaf.height;
              this.children.splice(++i, 0, leaf);
              leaf.parent = this;
            }
            child.lines = child.lines.slice(0, remaining);
            this.maybeSpill();
          }
          break
        }
        at -= sz;
      }
    }
```
</details>

### `maybeSpill(): void`

**Returns:** `void`

**Calls:**

- `me.children.splice`
- `indexOf`
- `me.parent.children.splice`
- `me.parent.maybeSpill`

<details><summary>Code</summary>

```typescript
function() {
      if (this.children.length <= 10) { return }
      var me = this;
      do {
        var spilled = me.children.splice(me.children.length - 5, 5);
        var sibling = new BranchChunk(spilled);
        if (!me.parent) { // Become the parent node
          var copy = new BranchChunk(me.children);
          copy.parent = me;
          me.children = [copy, sibling];
          me = copy;
       } else {
          me.size -= sibling.size;
          me.height -= sibling.height;
          var myIndex = indexOf(me.parent.children, me);
          me.parent.children.splice(myIndex + 1, 0, sibling);
        }
        sibling.parent = me.parent;
      } while (me.children.length > 10)
      me.parent.maybeSpill();
    }
```
</details>

### `iterN(at: any, n: any, op: any): boolean`

**Parameters:**

- **`at`** `any`
- **`n`** `any`
- **`op`** `any`

**Returns:** `boolean`

**Calls:**

- `child.chunkSize`
- `Math.min`
- `child.iterN`

<details><summary>Code</summary>

```typescript
function(at, n, op) {
      for (var i = 0; i < this.children.length; ++i) {
        var child = this.children[i], sz = child.chunkSize();
        if (at < sz) {
          var used = Math.min(n, sz - at);
          if (child.iterN(at, used, op)) { return true }
          if ((n -= used) == 0) { break }
          at = 0;
        } else { at -= sz; }
      }
    }
```
</details>

### `chunkSize(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function() { return this.size }
```
</details>

### `removeInner(at: any, n: any): void`

**Parameters:**

- **`at`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `child.chunkSize`
- `Math.min`
- `child.removeInner`
- `this.children.splice`
- `this.collapse`

**Internal Comments:**
```
// If the result is smaller than 25 lines, ensure that it is a
// single leaf node.
```

<details><summary>Code</summary>

```typescript
function(at, n) {
      this.size -= n;
      for (var i = 0; i < this.children.length; ++i) {
        var child = this.children[i], sz = child.chunkSize();
        if (at < sz) {
          var rm = Math.min(n, sz - at), oldHeight = child.height;
          child.removeInner(at, rm);
          this.height -= oldHeight - child.height;
          if (sz == rm) { this.children.splice(i--, 1); child.parent = null; }
          if ((n -= rm) == 0) { break }
          at = 0;
        } else { at -= sz; }
      }
      // If the result is smaller than 25 lines, ensure that it is a
      // single leaf node.
      if (this.size - n < 25 &&
          (this.children.length > 1 || !(this.children[0] instanceof LeafChunk))) {
        var lines = [];
        this.collapse(lines);
        this.children = [new LeafChunk(lines)];
        this.children[0].parent = this;
      }
    }
```
</details>

### `collapse(lines: any): void`

**Parameters:**

- **`lines`** `any`

**Returns:** `void`

**Calls:**

- `this.children[i].collapse`

<details><summary>Code</summary>

```typescript
function(lines) {
      for (var i = 0; i < this.children.length; ++i) { this.children[i].collapse(lines); }
    }
```
</details>

### `insertInner(at: any, lines: any, height: any): void`

**Parameters:**

- **`at`** `any`
- **`lines`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `child.chunkSize`
- `child.insertInner`
- `child.lines.slice`
- `this.children.splice`
- `this.maybeSpill`

**Internal Comments:**
```
// To avoid memory thrashing when child.lines is huge (e.g. first view of a large file), it's never spliced. (x2)
// Instead, small slices are taken. They're taken in order because sequential memory accesses are fastest. (x2)
```

<details><summary>Code</summary>

```typescript
function(at, lines, height) {
      this.size += lines.length;
      this.height += height;
      for (var i = 0; i < this.children.length; ++i) {
        var child = this.children[i], sz = child.chunkSize();
        if (at <= sz) {
          child.insertInner(at, lines, height);
          if (child.lines && child.lines.length > 50) {
            // To avoid memory thrashing when child.lines is huge (e.g. first view of a large file), it's never spliced.
            // Instead, small slices are taken. They're taken in order because sequential memory accesses are fastest.
            var remaining = child.lines.length % 25 + 25;
            for (var pos = remaining; pos < child.lines.length;) {
              var leaf = new LeafChunk(child.lines.slice(pos, pos += 25));
              child.height -= leaf.height;
              this.children.splice(++i, 0, leaf);
              leaf.parent = this;
            }
            child.lines = child.lines.slice(0, remaining);
            this.maybeSpill();
          }
          break
        }
        at -= sz;
      }
    }
```
</details>

### `maybeSpill(): void`

**Returns:** `void`

**Calls:**

- `me.children.splice`
- `indexOf`
- `me.parent.children.splice`
- `me.parent.maybeSpill`

<details><summary>Code</summary>

```typescript
function() {
      if (this.children.length <= 10) { return }
      var me = this;
      do {
        var spilled = me.children.splice(me.children.length - 5, 5);
        var sibling = new BranchChunk(spilled);
        if (!me.parent) { // Become the parent node
          var copy = new BranchChunk(me.children);
          copy.parent = me;
          me.children = [copy, sibling];
          me = copy;
       } else {
          me.size -= sibling.size;
          me.height -= sibling.height;
          var myIndex = indexOf(me.parent.children, me);
          me.parent.children.splice(myIndex + 1, 0, sibling);
        }
        sibling.parent = me.parent;
      } while (me.children.length > 10)
      me.parent.maybeSpill();
    }
```
</details>

### `iterN(at: any, n: any, op: any): boolean`

**Parameters:**

- **`at`** `any`
- **`n`** `any`
- **`op`** `any`

**Returns:** `boolean`

**Calls:**

- `child.chunkSize`
- `Math.min`
- `child.iterN`

<details><summary>Code</summary>

```typescript
function(at, n, op) {
      for (var i = 0; i < this.children.length; ++i) {
        var child = this.children[i], sz = child.chunkSize();
        if (at < sz) {
          var used = Math.min(n, sz - at);
          if (child.iterN(at, used, op)) { return true }
          if ((n -= used) == 0) { break }
          at = 0;
        } else { at -= sz; }
      }
    }
```
</details>

### `LineWidget(doc: any, node: any, options: any): void`

**Parameters:**

- **`doc`** `any`
- **`node`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `options.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function(doc, node, options) {
    if (options) { for (var opt in options) { if (options.hasOwnProperty(opt))
      { this[opt] = options[opt]; } } }
    this.doc = doc;
    this.node = node;
  }
```
</details>

### `adjustScrollWhenAboveVisible(cm: any, line: any, diff: any): void`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`
- **`diff`** `any`

**Returns:** `void`

**Calls:**

- `heightAtLine`
- `addToScrollTop`

<details><summary>Code</summary>

```typescript
function adjustScrollWhenAboveVisible(cm, line, diff) {
    if (heightAtLine(line) < ((cm.curOp && cm.curOp.scrollTop) || cm.doc.scrollTop))
      { addToScrollTop(cm, diff); }
  }
```
</details>

### `addLineWidget(doc: any, handle: any, node: any, options: any): LineWidget`

**Parameters:**

- **`doc`** `any`
- **`handle`** `any`
- **`node`** `any`
- **`options`** `any`

**Returns:** `LineWidget`

**Calls:**

- `changeLine`
- `widgets.push`
- `widgets.splice`
- `Math.min`
- `Math.max`
- `lineIsHidden`
- `heightAtLine`
- `updateLineHeight`
- `widgetHeight`
- `addToScrollTop`
- `signalLater`
- `lineNo`

<details><summary>Code</summary>

```typescript
function addLineWidget(doc, handle, node, options) {
    var widget = new LineWidget(doc, node, options);
    var cm = doc.cm;
    if (cm && widget.noHScroll) { cm.display.alignWidgets = true; }
    changeLine(doc, handle, "widget", function (line) {
      var widgets = line.widgets || (line.widgets = []);
      if (widget.insertAt == null) { widgets.push(widget); }
      else { widgets.splice(Math.min(widgets.length, Math.max(0, widget.insertAt)), 0, widget); }
      widget.line = line;
      if (cm && !lineIsHidden(doc, line)) {
        var aboveVisible = heightAtLine(line) < doc.scrollTop;
        updateLineHeight(line, line.height + widgetHeight(widget));
        if (aboveVisible) { addToScrollTop(cm, widget.height); }
        cm.curOp.forceUpdate = true;
      }
      return true
    });
    if (cm) { signalLater(cm, "lineWidgetAdded", cm, widget, typeof handle == "number" ? handle : lineNo(handle)); }
    return widget
  }
```
</details>

### `TextMarker(doc: any, type: any): void`

**Parameters:**

- **`doc`** `any`
- **`type`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(doc, type) {
    this.lines = [];
    this.type = type;
    this.doc = doc;
    this.id = ++nextMarkerId;
  }
```
</details>

### `markText(doc: any, from: any, to: any, options: any, type: any): any`

**Parameters:**

- **`doc`** `any`
- **`from`** `any`
- **`to`** `any`
- **`options`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `markTextShared`
- `complex_call_242235`
- `cmp`
- `copyObj`
- `eltP`
- `marker.widgetNode.setAttribute`
- `conflictingCollapsedRange`
- `seeCollapsedSpans`
- `addChangeToHistory`
- `doc.iter`
- `visualLine`
- `updateLineHeight`
- `addMarkedSpan`
- `lineIsHidden`
- `on`
- `marker.clear`
- `seeReadOnlySpans`
- `doc.clearHistory`
- `regChange`
- `regLineChange`
- `reCheckSelection`
- `signalLater`

**Internal Comments:**
```
// Shared markers (across linked documents) are handled separately
// (markTextShared will call out to this again, once per
// document).
// Ensure we are in an operation.
// Don't connect empty markers unless clearWhenEmpty is false
// Showing up as a widget implies collapsed (widget replaces text) (x4)
// lineIsHidden depends on the presence of the spans, so needs a second pass
// Sync editor state
```

<details><summary>Code</summary>

```typescript
function markText(doc, from, to, options, type) {
    // Shared markers (across linked documents) are handled separately
    // (markTextShared will call out to this again, once per
    // document).
    if (options && options.shared) { return markTextShared(doc, from, to, options, type) }
    // Ensure we are in an operation.
    if (doc.cm && !doc.cm.curOp) { return operation(doc.cm, markText)(doc, from, to, options, type) }

    var marker = new TextMarker(doc, type), diff = cmp(from, to);
    if (options) { copyObj(options, marker, false); }
    // Don't connect empty markers unless clearWhenEmpty is false
    if (diff > 0 || diff == 0 && marker.clearWhenEmpty !== false)
      { return marker }
    if (marker.replacedWith) {
      // Showing up as a widget implies collapsed (widget replaces text)
      marker.collapsed = true;
      marker.widgetNode = eltP("span", [marker.replacedWith], "CodeMirror-widget");
      if (!options.handleMouseEvents) { marker.widgetNode.setAttribute("cm-ignore-events", "true"); }
      if (options.insertLeft) { marker.widgetNode.insertLeft = true; }
    }
    if (marker.collapsed) {
      if (conflictingCollapsedRange(doc, from.line, from, to, marker) ||
          from.line != to.line && conflictingCollapsedRange(doc, to.line, from, to, marker))
        { throw new Error("Inserting collapsed marker partially overlapping an existing one") }
      seeCollapsedSpans();
    }

    if (marker.addToHistory)
      { addChangeToHistory(doc, {from: from, to: to, origin: "markText"}, doc.sel, NaN); }

    var curLine = from.line, cm = doc.cm, updateMaxLine;
    doc.iter(curLine, to.line + 1, function (line) {
      if (cm && marker.collapsed && !cm.options.lineWrapping && visualLine(line) == cm.display.maxLine)
        { updateMaxLine = true; }
      if (marker.collapsed && curLine != from.line) { updateLineHeight(line, 0); }
      addMarkedSpan(line, new MarkedSpan(marker,
                                         curLine == from.line ? from.ch : null,
                                         curLine == to.line ? to.ch : null), doc.cm && doc.cm.curOp);
      ++curLine;
    });
    // lineIsHidden depends on the presence of the spans, so needs a second pass
    if (marker.collapsed) { doc.iter(from.line, to.line + 1, function (line) {
      if (lineIsHidden(doc, line)) { updateLineHeight(line, 0); }
    }); }

    if (marker.clearOnEnter) { on(marker, "beforeCursorEnter", function () { return marker.clear(); }); }

    if (marker.readOnly) {
      seeReadOnlySpans();
      if (doc.history.done.length || doc.history.undone.length)
        { doc.clearHistory(); }
    }
    if (marker.collapsed) {
      marker.id = ++nextMarkerId;
      marker.atomic = true;
    }
    if (cm) {
      // Sync editor state
      if (updateMaxLine) { cm.curOp.updateMaxLine = true; }
      if (marker.collapsed)
        { regChange(cm, from.line, to.line + 1); }
      else if (marker.className || marker.startStyle || marker.endStyle || marker.css ||
               marker.attributes || marker.title)
        { for (var i = from.line; i <= to.line; i++) { regLineChange(cm, i, "text"); } }
      if (marker.atomic) { reCheckSelection(cm.doc); }
      signalLater(cm, "markerAdded", cm, marker);
    }
    return marker
  }
```
</details>

### `SharedTextMarker(markers: any, primary: any): void`

**Parameters:**

- **`markers`** `any`
- **`primary`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(markers, primary) {
    this.markers = markers;
    this.primary = primary;
    for (var i = 0; i < markers.length; ++i)
      { markers[i].parent = this; }
  }
```
</details>

### `markTextShared(doc: any, from: any, to: any, options: any, type: any): any`

**Parameters:**

- **`doc`** `any`
- **`from`** `any`
- **`to`** `any`
- **`options`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `copyObj`
- `markText`
- `linkedDocs`
- `widget.cloneNode`
- `markers.push`
- `clipPos`
- `lst`

<details><summary>Code</summary>

```typescript
function markTextShared(doc, from, to, options, type) {
    options = copyObj(options);
    options.shared = false;
    var markers = [markText(doc, from, to, options, type)], primary = markers[0];
    var widget = options.widgetNode;
    linkedDocs(doc, function (doc) {
      if (widget) { options.widgetNode = widget.cloneNode(true); }
      markers.push(markText(doc, clipPos(doc, from), clipPos(doc, to), options, type));
      for (var i = 0; i < doc.linked.length; ++i)
        { if (doc.linked[i].isParent) { return } }
      primary = lst(markers);
    });
    return new SharedTextMarker(markers, primary)
  }
```
</details>

### `findSharedMarkers(doc: any): any`

**Parameters:**

- **`doc`** `any`

**Returns:** `any`

**Calls:**

- `doc.findMarks`
- `Pos`
- `doc.clipPos`
- `doc.lastLine`

<details><summary>Code</summary>

```typescript
function findSharedMarkers(doc) {
    return doc.findMarks(Pos(doc.first, 0), doc.clipPos(Pos(doc.lastLine())), function (m) { return m.parent; })
  }
```
</details>

### `copySharedMarkers(doc: any, markers: any): void`

**Parameters:**

- **`doc`** `any`
- **`markers`** `any`

**Returns:** `void`

**Calls:**

- `marker.find`
- `doc.clipPos`
- `cmp`
- `markText`
- `marker.markers.push`

<details><summary>Code</summary>

```typescript
function copySharedMarkers(doc, markers) {
    for (var i = 0; i < markers.length; i++) {
      var marker = markers[i], pos = marker.find();
      var mFrom = doc.clipPos(pos.from), mTo = doc.clipPos(pos.to);
      if (cmp(mFrom, mTo)) {
        var subMark = markText(doc, mFrom, mTo, marker.primary, marker.primary.type);
        marker.markers.push(subMark);
        subMark.parent = marker;
      }
    }
  }
```
</details>

### `detachSharedMarkers(markers: any): void`

**Parameters:**

- **`markers`** `any`

**Returns:** `void`

**Calls:**

- `linkedDocs`
- `linked.push`
- `indexOf`
- `marker.markers.splice`
- `loop`

<details><summary>Code</summary>

```typescript
function detachSharedMarkers(markers) {
    var loop = function ( i ) {
      var marker = markers[i], linked = [marker.primary.doc];
      linkedDocs(marker.primary.doc, function (d) { return linked.push(d); });
      for (var j = 0; j < marker.markers.length; j++) {
        var subMarker = marker.markers[j];
        if (indexOf(linked, subMarker.doc) == -1) {
          subMarker.parent = null;
          marker.markers.splice(j--, 1);
        }
      }
    };

    for (var i = 0; i < markers.length; i++) loop( i );
  }
```
</details>

### `loop(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `linkedDocs`
- `linked.push`
- `indexOf`
- `marker.markers.splice`

<details><summary>Code</summary>

```typescript
function ( i ) {
      var marker = markers[i], linked = [marker.primary.doc];
      linkedDocs(marker.primary.doc, function (d) { return linked.push(d); });
      for (var j = 0; j < marker.markers.length; j++) {
        var subMarker = marker.markers[j];
        if (indexOf(linked, subMarker.doc) == -1) {
          subMarker.parent = null;
          marker.markers.splice(j--, 1);
        }
      }
    }
```
</details>

### `Doc(text: any, mode: any, firstLine: any, lineSep: any, direction: any): Doc`

**Parameters:**

- **`text`** `any`
- **`mode`** `any`
- **`firstLine`** `any`
- **`lineSep`** `any`
- **`direction`** `any`

**Returns:** `Doc`

**Calls:**

- `BranchChunk.call`
- `Pos`
- `simpleSelection`
- `this.splitLines`
- `updateDoc`
- `setSelection`

<details><summary>Code</summary>

```typescript
function(text, mode, firstLine, lineSep, direction) {
    if (!(this instanceof Doc)) { return new Doc(text, mode, firstLine, lineSep, direction) }
    if (firstLine == null) { firstLine = 0; }

    BranchChunk.call(this, [new LeafChunk([new Line("", null)])]);
    this.first = firstLine;
    this.scrollTop = this.scrollLeft = 0;
    this.cantEdit = false;
    this.cleanGeneration = 1;
    this.modeFrontier = this.highlightFrontier = firstLine;
    var start = Pos(firstLine, 0);
    this.sel = simpleSelection(start);
    this.history = new History(null);
    this.id = ++nextDocId;
    this.modeOption = mode;
    this.lineSep = lineSep;
    this.direction = (direction == "rtl") ? "rtl" : "ltr";
    this.extend = false;

    if (typeof text == "string") { text = this.splitLines(text); }
    updateDoc(this, {from: start, to: start, text: text});
    setSelection(this, simpleSelection(start), sel_dontScroll);
  }
```
</details>

### `iter(from: any, to: any, op: any): void`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`op`** `any`

**Returns:** `void`

**Calls:**

- `this.iterN`

<details><summary>Code</summary>

```typescript
function(from, to, op) {
      if (op) { this.iterN(from - this.first, to - from, op); }
      else { this.iterN(this.first, this.first + this.size, from); }
    }
```
</details>

### `insert(at: any, lines: any): void`

**Parameters:**

- **`at`** `any`
- **`lines`** `any`

**Returns:** `void`

**Calls:**

- `this.insertInner`

<details><summary>Code</summary>

```typescript
function(at, lines) {
      var height = 0;
      for (var i = 0; i < lines.length; ++i) { height += lines[i].height; }
      this.insertInner(at - this.first, lines, height);
    }
```
</details>

### `remove(at: any, n: any): void`

**Parameters:**

- **`at`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.removeInner`

<details><summary>Code</summary>

```typescript
function(at, n) { this.removeInner(at - this.first, n); }
```
</details>

### `getValue(lineSep: any): string | any[]`

**Parameters:**

- **`lineSep`** `any`

**Returns:** `string | any[]`

**Calls:**

- `getLines`
- `lines.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(lineSep) {
      var lines = getLines(this, this.first, this.first + this.size);
      if (lineSep === false) { return lines }
      return lines.join(lineSep || this.lineSeparator())
    }
```
</details>

### `replaceRange(code: any, from: any, to: any, origin: any): void`

**Parameters:**

- **`code`** `any`
- **`from`** `any`
- **`to`** `any`
- **`origin`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`
- `replaceRange`

<details><summary>Code</summary>

```typescript
function(code, from, to, origin) {
      from = clipPos(this, from);
      to = to ? clipPos(this, to) : from;
      replaceRange(this, code, from, to, origin);
    }
```
</details>

### `getRange(from: any, to: any, lineSep: any): string | any[]`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`lineSep`** `any`

**Returns:** `string | any[]`

**Calls:**

- `getBetween`
- `clipPos`
- `lines.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(from, to, lineSep) {
      var lines = getBetween(this, clipPos(this, from), clipPos(this, to));
      if (lineSep === false) { return lines }
      if (lineSep === '') { return lines.join('') }
      return lines.join(lineSep || this.lineSeparator())
    }
```
</details>

### `getLine(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `this.getLineHandle`

<details><summary>Code</summary>

```typescript
function(line) {var l = this.getLineHandle(line); return l && l.text}
```
</details>

### `getLineHandle(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `isLine`
- `getLine`

<details><summary>Code</summary>

```typescript
function(line) {if (isLine(this, line)) { return getLine(this, line) }}
```
</details>

### `getLineNumber(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `lineNo`

<details><summary>Code</summary>

```typescript
function(line) {return lineNo(line)}
```
</details>

### `getLineHandleVisualStart(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `visualLine`

<details><summary>Code</summary>

```typescript
function(line) {
      if (typeof line == "number") { line = getLine(this, line); }
      return visualLine(line)
    }
```
</details>

### `lineCount(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.size}
```
</details>

### `firstLine(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.first}
```
</details>

### `lastLine(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function() {return this.first + this.size - 1}
```
</details>

### `clipPos(pos: any): any`

**Parameters:**

- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(pos) {return clipPos(this, pos)}
```
</details>

### `getCursor(start: any): any`

**Parameters:**

- **`start`** `any`

**Returns:** `any`

**Calls:**

- `this.sel.primary`
- `range.to`
- `range.from`

<details><summary>Code</summary>

```typescript
function(start) {
      var range = this.sel.primary(), pos;
      if (start == null || start == "head") { pos = range.head; }
      else if (start == "anchor") { pos = range.anchor; }
      else if (start == "end" || start == "to" || start === false) { pos = range.to(); }
      else { pos = range.from(); }
      return pos
    }
```
</details>

### `listSelections(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.sel.ranges }
```
</details>

### `somethingSelected(): any`

**Returns:** `any`

**Calls:**

- `this.sel.somethingSelected`

<details><summary>Code</summary>

```typescript
function() {return this.sel.somethingSelected()}
```
</details>

### `getSelection(lineSep: any): string | any[]`

**Parameters:**

- **`lineSep`** `any`

**Returns:** `string | any[]`

**Calls:**

- `getBetween`
- `ranges[i].from`
- `ranges[i].to`
- `lines.concat`
- `lines.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(lineSep) {
      var ranges = this.sel.ranges, lines;
      for (var i = 0; i < ranges.length; i++) {
        var sel = getBetween(this, ranges[i].from(), ranges[i].to());
        lines = lines ? lines.concat(sel) : sel;
      }
      if (lineSep === false) { return lines }
      else { return lines.join(lineSep || this.lineSeparator()) }
    }
```
</details>

### `getSelections(lineSep: any): any[][]`

**Parameters:**

- **`lineSep`** `any`

**Returns:** `any[][]`

**Calls:**

- `getBetween`
- `ranges[i].from`
- `ranges[i].to`
- `sel.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(lineSep) {
      var parts = [], ranges = this.sel.ranges;
      for (var i = 0; i < ranges.length; i++) {
        var sel = getBetween(this, ranges[i].from(), ranges[i].to());
        if (lineSep !== false) { sel = sel.join(lineSep || this.lineSeparator()); }
        parts[i] = sel;
      }
      return parts
    }
```
</details>

### `replaceSelection(code: any, collapse: any, origin: any): void`

**Parameters:**

- **`code`** `any`
- **`collapse`** `any`
- **`origin`** `any`

**Returns:** `void`

**Calls:**

- `this.replaceSelections`

<details><summary>Code</summary>

```typescript
function(code, collapse, origin) {
      var dup = [];
      for (var i = 0; i < this.sel.ranges.length; i++)
        { dup[i] = code; }
      this.replaceSelections(dup, collapse, origin || "+input");
    }
```
</details>

### `setExtending(val: any): void`

**Parameters:**

- **`val`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(val) {this.extend = val;}
```
</details>

### `getExtending(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.extend}
```
</details>

### `historySize(): { undo: number; redo: number; }`

**Returns:** `{ undo: number; redo: number; }`

<details><summary>Code</summary>

```typescript
function() {
      var hist = this.history, done = 0, undone = 0;
      for (var i = 0; i < hist.done.length; i++) { if (!hist.done[i].ranges) { ++done; } }
      for (var i$1 = 0; i$1 < hist.undone.length; i$1++) { if (!hist.undone[i$1].ranges) { ++undone; } }
      return {undo: done, redo: undone}
    }
```
</details>

### `clearHistory(): void`

**Returns:** `void`

**Calls:**

- `linkedDocs`

<details><summary>Code</summary>

```typescript
function() {
      var this$1 = this;

      this.history = new History(this.history);
      linkedDocs(this, function (doc) { return doc.history = this$1.history; }, true);
    }
```
</details>

### `markClean(): void`

**Returns:** `void`

**Calls:**

- `this.changeGeneration`

<details><summary>Code</summary>

```typescript
function() {
      this.cleanGeneration = this.changeGeneration(true);
    }
```
</details>

### `changeGeneration(forceSplit: any): any`

**Parameters:**

- **`forceSplit`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(forceSplit) {
      if (forceSplit)
        { this.history.lastOp = this.history.lastSelOp = this.history.lastOrigin = null; }
      return this.history.generation
    }
```
</details>

### `isClean(gen: any): boolean`

**Parameters:**

- **`gen`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (gen) {
      return this.history.generation == (gen || this.cleanGeneration)
    }
```
</details>

### `getHistory(): { done: any[]; undone: any[]; }`

**Returns:** `{ done: any[]; undone: any[]; }`

**Calls:**

- `copyHistoryArray`

<details><summary>Code</summary>

```typescript
function() {
      return {done: copyHistoryArray(this.history.done),
              undone: copyHistoryArray(this.history.undone)}
    }
```
</details>

### `setHistory(histData: any): void`

**Parameters:**

- **`histData`** `any`

**Returns:** `void`

**Calls:**

- `copyHistoryArray`
- `histData.done.slice`
- `histData.undone.slice`

<details><summary>Code</summary>

```typescript
function(histData) {
      var hist = this.history = new History(this.history);
      hist.done = copyHistoryArray(histData.done.slice(0), null, true);
      hist.undone = copyHistoryArray(histData.undone.slice(0), null, true);
    }
```
</details>

### `lineInfo(line: any): { line: any; handle: any; text: any; gutterMarkers: any; textClass: any; bgClass: any; wrapClass: any; widgets: any; }`

**Parameters:**

- **`line`** `any`

**Returns:** `{ line: any; handle: any; text: any; gutterMarkers: any; textClass: any; bgClass: any; wrapClass: any; widgets: any; }`

**Calls:**

- `isLine`
- `getLine`
- `lineNo`

<details><summary>Code</summary>

```typescript
function(line) {
      var n;
      if (typeof line == "number") {
        if (!isLine(this, line)) { return null }
        n = line;
        line = getLine(this, line);
        if (!line) { return null }
      } else {
        n = lineNo(line);
        if (n == null) { return null }
      }
      return {line: n, handle: line, text: line.text, gutterMarkers: line.gutterMarkers,
              textClass: line.textClass, bgClass: line.bgClass, wrapClass: line.wrapClass,
              widgets: line.widgets}
    }
```
</details>

### `removeLineWidget(widget: any): void`

**Parameters:**

- **`widget`** `any`

**Returns:** `void`

**Calls:**

- `widget.clear`

<details><summary>Code</summary>

```typescript
function(widget) { widget.clear(); }
```
</details>

### `markText(from: any, to: any, options: any): any`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `markText`
- `clipPos`

<details><summary>Code</summary>

```typescript
function(from, to, options) {
      return markText(this, clipPos(this, from), clipPos(this, to), options, options && options.type || "range")
    }
```
</details>

### `setBookmark(pos: any, options: any): any`

**Parameters:**

- **`pos`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `markText`

<details><summary>Code</summary>

```typescript
function(pos, options) {
      var realOpts = {replacedWith: options && (options.nodeType == null ? options.widget : options),
                      insertLeft: options && options.insertLeft,
                      clearWhenEmpty: false, shared: options && options.shared,
                      handleMouseEvents: options && options.handleMouseEvents};
      pos = clipPos(this, pos);
      return markText(this, pos, pos, realOpts, "bookmark")
    }
```
</details>

### `findMarksAt(pos: any): any[]`

**Parameters:**

- **`pos`** `any`

**Returns:** `any[]`

**Calls:**

- `clipPos`
- `getLine`
- `markers.push`

<details><summary>Code</summary>

```typescript
function(pos) {
      pos = clipPos(this, pos);
      var markers = [], spans = getLine(this, pos.line).markedSpans;
      if (spans) { for (var i = 0; i < spans.length; ++i) {
        var span = spans[i];
        if ((span.from == null || span.from <= pos.ch) &&
            (span.to == null || span.to >= pos.ch))
          { markers.push(span.marker.parent || span.marker); }
      } }
      return markers
    }
```
</details>

### `findMarks(from: any, to: any, filter: any): any[]`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`filter`** `any`

**Returns:** `any[]`

**Calls:**

- `clipPos`
- `this.iter`
- `filter`
- `found.push`

<details><summary>Code</summary>

```typescript
function(from, to, filter) {
      from = clipPos(this, from); to = clipPos(this, to);
      var found = [], lineNo = from.line;
      this.iter(from.line, to.line + 1, function (line) {
        var spans = line.markedSpans;
        if (spans) { for (var i = 0; i < spans.length; i++) {
          var span = spans[i];
          if (!(span.to != null && lineNo == from.line && from.ch >= span.to ||
                span.from == null && lineNo != from.line ||
                span.from != null && lineNo == to.line && span.from >= to.ch) &&
              (!filter || filter(span.marker)))
            { found.push(span.marker.parent || span.marker); }
        } }
        ++lineNo;
      });
      return found
    }
```
</details>

### `getAllMarks(): any[]`

**Returns:** `any[]`

**Calls:**

- `this.iter`
- `markers.push`

<details><summary>Code</summary>

```typescript
function() {
      var markers = [];
      this.iter(function (line) {
        var sps = line.markedSpans;
        if (sps) { for (var i = 0; i < sps.length; ++i)
          { if (sps[i].from != null) { markers.push(sps[i].marker); } } }
      });
      return markers
    }
```
</details>

### `posFromIndex(off: any): any`

**Parameters:**

- **`off`** `any`

**Returns:** `any`

**Calls:**

- `this.lineSeparator`
- `this.iter`
- `clipPos`
- `Pos`

<details><summary>Code</summary>

```typescript
function(off) {
      var ch, lineNo = this.first, sepSize = this.lineSeparator().length;
      this.iter(function (line) {
        var sz = line.text.length + sepSize;
        if (sz > off) { ch = off; return true }
        off -= sz;
        ++lineNo;
      });
      return clipPos(this, Pos(lineNo, ch))
    }
```
</details>

### `indexFromPos(coords: any): any`

**Parameters:**

- **`coords`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `this.lineSeparator`
- `this.iter`

<details><summary>Code</summary>

```typescript
function (coords) {
      coords = clipPos(this, coords);
      var index = coords.ch;
      if (coords.line < this.first || coords.ch < 0) { return 0 }
      var sepSize = this.lineSeparator().length;
      this.iter(this.first, coords.line, function (line) { // iter aborts when callback returns a truthy value
        index += line.text.length + sepSize;
      });
      return index
    }
```
</details>

### `copy(copyHistory: any): Doc`

**Parameters:**

- **`copyHistory`** `any`

**Returns:** `Doc`

**Calls:**

- `getLines`
- `doc.setHistory`
- `this.getHistory`

<details><summary>Code</summary>

```typescript
function(copyHistory) {
      var doc = new Doc(getLines(this, this.first, this.first + this.size),
                        this.modeOption, this.first, this.lineSep, this.direction);
      doc.scrollTop = this.scrollTop; doc.scrollLeft = this.scrollLeft;
      doc.sel = this.sel;
      doc.extend = false;
      if (copyHistory) {
        doc.history.undoDepth = this.history.undoDepth;
        doc.setHistory(this.getHistory());
      }
      return doc
    }
```
</details>

### `linkedDoc(options: any): Doc`

**Parameters:**

- **`options`** `any`

**Returns:** `Doc`

**Calls:**

- `getLines`
- `(this.linked || (this.linked = [])).push`
- `copySharedMarkers`
- `findSharedMarkers`

<details><summary>Code</summary>

```typescript
function(options) {
      if (!options) { options = {}; }
      var from = this.first, to = this.first + this.size;
      if (options.from != null && options.from > from) { from = options.from; }
      if (options.to != null && options.to < to) { to = options.to; }
      var copy = new Doc(getLines(this, from, to), options.mode || this.modeOption, from, this.lineSep, this.direction);
      if (options.sharedHist) { copy.history = this.history
      ; }(this.linked || (this.linked = [])).push({doc: copy, sharedHist: options.sharedHist});
      copy.linked = [{doc: this, isParent: true, sharedHist: options.sharedHist}];
      copySharedMarkers(copy, findSharedMarkers(this));
      return copy
    }
```
</details>

### `unlinkDoc(other: any): void`

**Parameters:**

- **`other`** `any`

**Returns:** `void`

**Calls:**

- `this.linked.splice`
- `other.unlinkDoc`
- `detachSharedMarkers`
- `findSharedMarkers`
- `linkedDocs`
- `splitIds.push`
- `copyHistoryArray`

**Internal Comments:**
```
// If the histories were shared, split them again
```

<details><summary>Code</summary>

```typescript
function(other) {
      if (other instanceof CodeMirror) { other = other.doc; }
      if (this.linked) { for (var i = 0; i < this.linked.length; ++i) {
        var link = this.linked[i];
        if (link.doc != other) { continue }
        this.linked.splice(i, 1);
        other.unlinkDoc(this);
        detachSharedMarkers(findSharedMarkers(this));
        break
      } }
      // If the histories were shared, split them again
      if (other.history == this.history) {
        var splitIds = [other.id];
        linkedDocs(other, function (doc) { return splitIds.push(doc.id); }, true);
        other.history = new History(null);
        other.history.done = copyHistoryArray(this.history.done, splitIds);
        other.history.undone = copyHistoryArray(this.history.undone, splitIds);
      }
    }
```
</details>

### `iterLinkedDocs(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `linkedDocs`

<details><summary>Code</summary>

```typescript
function(f) {linkedDocs(this, f);}
```
</details>

### `getMode(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.mode}
```
</details>

### `getEditor(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.cm}
```
</details>

### `splitLines(str: any): any`

**Parameters:**

- **`str`** `any`

**Returns:** `any`

**Calls:**

- `str.split`
- `splitLinesAuto`

<details><summary>Code</summary>

```typescript
function(str) {
      if (this.lineSep) { return str.split(this.lineSep) }
      return splitLinesAuto(str)
    }
```
</details>

### `lineSeparator(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.lineSep || "\n" }
```
</details>

### `iter(from: any, to: any, op: any): void`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`op`** `any`

**Returns:** `void`

**Calls:**

- `this.iterN`

<details><summary>Code</summary>

```typescript
function(from, to, op) {
      if (op) { this.iterN(from - this.first, to - from, op); }
      else { this.iterN(this.first, this.first + this.size, from); }
    }
```
</details>

### `insert(at: any, lines: any): void`

**Parameters:**

- **`at`** `any`
- **`lines`** `any`

**Returns:** `void`

**Calls:**

- `this.insertInner`

<details><summary>Code</summary>

```typescript
function(at, lines) {
      var height = 0;
      for (var i = 0; i < lines.length; ++i) { height += lines[i].height; }
      this.insertInner(at - this.first, lines, height);
    }
```
</details>

### `remove(at: any, n: any): void`

**Parameters:**

- **`at`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.removeInner`

<details><summary>Code</summary>

```typescript
function(at, n) { this.removeInner(at - this.first, n); }
```
</details>

### `getValue(lineSep: any): string | any[]`

**Parameters:**

- **`lineSep`** `any`

**Returns:** `string | any[]`

**Calls:**

- `getLines`
- `lines.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(lineSep) {
      var lines = getLines(this, this.first, this.first + this.size);
      if (lineSep === false) { return lines }
      return lines.join(lineSep || this.lineSeparator())
    }
```
</details>

### `replaceRange(code: any, from: any, to: any, origin: any): void`

**Parameters:**

- **`code`** `any`
- **`from`** `any`
- **`to`** `any`
- **`origin`** `any`

**Returns:** `void`

**Calls:**

- `clipPos`
- `replaceRange`

<details><summary>Code</summary>

```typescript
function(code, from, to, origin) {
      from = clipPos(this, from);
      to = to ? clipPos(this, to) : from;
      replaceRange(this, code, from, to, origin);
    }
```
</details>

### `getRange(from: any, to: any, lineSep: any): string | any[]`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`lineSep`** `any`

**Returns:** `string | any[]`

**Calls:**

- `getBetween`
- `clipPos`
- `lines.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(from, to, lineSep) {
      var lines = getBetween(this, clipPos(this, from), clipPos(this, to));
      if (lineSep === false) { return lines }
      if (lineSep === '') { return lines.join('') }
      return lines.join(lineSep || this.lineSeparator())
    }
```
</details>

### `getLine(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `this.getLineHandle`

<details><summary>Code</summary>

```typescript
function(line) {var l = this.getLineHandle(line); return l && l.text}
```
</details>

### `getLineHandle(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `isLine`
- `getLine`

<details><summary>Code</summary>

```typescript
function(line) {if (isLine(this, line)) { return getLine(this, line) }}
```
</details>

### `getLineNumber(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `lineNo`

<details><summary>Code</summary>

```typescript
function(line) {return lineNo(line)}
```
</details>

### `getLineHandleVisualStart(line: any): any`

**Parameters:**

- **`line`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `visualLine`

<details><summary>Code</summary>

```typescript
function(line) {
      if (typeof line == "number") { line = getLine(this, line); }
      return visualLine(line)
    }
```
</details>

### `lineCount(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.size}
```
</details>

### `firstLine(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.first}
```
</details>

### `lastLine(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function() {return this.first + this.size - 1}
```
</details>

### `clipPos(pos: any): any`

**Parameters:**

- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`

<details><summary>Code</summary>

```typescript
function(pos) {return clipPos(this, pos)}
```
</details>

### `getCursor(start: any): any`

**Parameters:**

- **`start`** `any`

**Returns:** `any`

**Calls:**

- `this.sel.primary`
- `range.to`
- `range.from`

<details><summary>Code</summary>

```typescript
function(start) {
      var range = this.sel.primary(), pos;
      if (start == null || start == "head") { pos = range.head; }
      else if (start == "anchor") { pos = range.anchor; }
      else if (start == "end" || start == "to" || start === false) { pos = range.to(); }
      else { pos = range.from(); }
      return pos
    }
```
</details>

### `listSelections(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.sel.ranges }
```
</details>

### `somethingSelected(): any`

**Returns:** `any`

**Calls:**

- `this.sel.somethingSelected`

<details><summary>Code</summary>

```typescript
function() {return this.sel.somethingSelected()}
```
</details>

### `getSelection(lineSep: any): string | any[]`

**Parameters:**

- **`lineSep`** `any`

**Returns:** `string | any[]`

**Calls:**

- `getBetween`
- `ranges[i].from`
- `ranges[i].to`
- `lines.concat`
- `lines.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(lineSep) {
      var ranges = this.sel.ranges, lines;
      for (var i = 0; i < ranges.length; i++) {
        var sel = getBetween(this, ranges[i].from(), ranges[i].to());
        lines = lines ? lines.concat(sel) : sel;
      }
      if (lineSep === false) { return lines }
      else { return lines.join(lineSep || this.lineSeparator()) }
    }
```
</details>

### `getSelections(lineSep: any): any[][]`

**Parameters:**

- **`lineSep`** `any`

**Returns:** `any[][]`

**Calls:**

- `getBetween`
- `ranges[i].from`
- `ranges[i].to`
- `sel.join`
- `this.lineSeparator`

<details><summary>Code</summary>

```typescript
function(lineSep) {
      var parts = [], ranges = this.sel.ranges;
      for (var i = 0; i < ranges.length; i++) {
        var sel = getBetween(this, ranges[i].from(), ranges[i].to());
        if (lineSep !== false) { sel = sel.join(lineSep || this.lineSeparator()); }
        parts[i] = sel;
      }
      return parts
    }
```
</details>

### `replaceSelection(code: any, collapse: any, origin: any): void`

**Parameters:**

- **`code`** `any`
- **`collapse`** `any`
- **`origin`** `any`

**Returns:** `void`

**Calls:**

- `this.replaceSelections`

<details><summary>Code</summary>

```typescript
function(code, collapse, origin) {
      var dup = [];
      for (var i = 0; i < this.sel.ranges.length; i++)
        { dup[i] = code; }
      this.replaceSelections(dup, collapse, origin || "+input");
    }
```
</details>

### `setExtending(val: any): void`

**Parameters:**

- **`val`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(val) {this.extend = val;}
```
</details>

### `getExtending(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.extend}
```
</details>

### `historySize(): { undo: number; redo: number; }`

**Returns:** `{ undo: number; redo: number; }`

<details><summary>Code</summary>

```typescript
function() {
      var hist = this.history, done = 0, undone = 0;
      for (var i = 0; i < hist.done.length; i++) { if (!hist.done[i].ranges) { ++done; } }
      for (var i$1 = 0; i$1 < hist.undone.length; i$1++) { if (!hist.undone[i$1].ranges) { ++undone; } }
      return {undo: done, redo: undone}
    }
```
</details>

### `clearHistory(): void`

**Returns:** `void`

**Calls:**

- `linkedDocs`

<details><summary>Code</summary>

```typescript
function() {
      var this$1 = this;

      this.history = new History(this.history);
      linkedDocs(this, function (doc) { return doc.history = this$1.history; }, true);
    }
```
</details>

### `markClean(): void`

**Returns:** `void`

**Calls:**

- `this.changeGeneration`

<details><summary>Code</summary>

```typescript
function() {
      this.cleanGeneration = this.changeGeneration(true);
    }
```
</details>

### `changeGeneration(forceSplit: any): any`

**Parameters:**

- **`forceSplit`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(forceSplit) {
      if (forceSplit)
        { this.history.lastOp = this.history.lastSelOp = this.history.lastOrigin = null; }
      return this.history.generation
    }
```
</details>

### `isClean(gen: any): boolean`

**Parameters:**

- **`gen`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (gen) {
      return this.history.generation == (gen || this.cleanGeneration)
    }
```
</details>

### `getHistory(): { done: any[]; undone: any[]; }`

**Returns:** `{ done: any[]; undone: any[]; }`

**Calls:**

- `copyHistoryArray`

<details><summary>Code</summary>

```typescript
function() {
      return {done: copyHistoryArray(this.history.done),
              undone: copyHistoryArray(this.history.undone)}
    }
```
</details>

### `setHistory(histData: any): void`

**Parameters:**

- **`histData`** `any`

**Returns:** `void`

**Calls:**

- `copyHistoryArray`
- `histData.done.slice`
- `histData.undone.slice`

<details><summary>Code</summary>

```typescript
function(histData) {
      var hist = this.history = new History(this.history);
      hist.done = copyHistoryArray(histData.done.slice(0), null, true);
      hist.undone = copyHistoryArray(histData.undone.slice(0), null, true);
    }
```
</details>

### `lineInfo(line: any): { line: any; handle: any; text: any; gutterMarkers: any; textClass: any; bgClass: any; wrapClass: any; widgets: any; }`

**Parameters:**

- **`line`** `any`

**Returns:** `{ line: any; handle: any; text: any; gutterMarkers: any; textClass: any; bgClass: any; wrapClass: any; widgets: any; }`

**Calls:**

- `isLine`
- `getLine`
- `lineNo`

<details><summary>Code</summary>

```typescript
function(line) {
      var n;
      if (typeof line == "number") {
        if (!isLine(this, line)) { return null }
        n = line;
        line = getLine(this, line);
        if (!line) { return null }
      } else {
        n = lineNo(line);
        if (n == null) { return null }
      }
      return {line: n, handle: line, text: line.text, gutterMarkers: line.gutterMarkers,
              textClass: line.textClass, bgClass: line.bgClass, wrapClass: line.wrapClass,
              widgets: line.widgets}
    }
```
</details>

### `removeLineWidget(widget: any): void`

**Parameters:**

- **`widget`** `any`

**Returns:** `void`

**Calls:**

- `widget.clear`

<details><summary>Code</summary>

```typescript
function(widget) { widget.clear(); }
```
</details>

### `markText(from: any, to: any, options: any): any`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `markText`
- `clipPos`

<details><summary>Code</summary>

```typescript
function(from, to, options) {
      return markText(this, clipPos(this, from), clipPos(this, to), options, options && options.type || "range")
    }
```
</details>

### `setBookmark(pos: any, options: any): any`

**Parameters:**

- **`pos`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `markText`

<details><summary>Code</summary>

```typescript
function(pos, options) {
      var realOpts = {replacedWith: options && (options.nodeType == null ? options.widget : options),
                      insertLeft: options && options.insertLeft,
                      clearWhenEmpty: false, shared: options && options.shared,
                      handleMouseEvents: options && options.handleMouseEvents};
      pos = clipPos(this, pos);
      return markText(this, pos, pos, realOpts, "bookmark")
    }
```
</details>

### `findMarksAt(pos: any): any[]`

**Parameters:**

- **`pos`** `any`

**Returns:** `any[]`

**Calls:**

- `clipPos`
- `getLine`
- `markers.push`

<details><summary>Code</summary>

```typescript
function(pos) {
      pos = clipPos(this, pos);
      var markers = [], spans = getLine(this, pos.line).markedSpans;
      if (spans) { for (var i = 0; i < spans.length; ++i) {
        var span = spans[i];
        if ((span.from == null || span.from <= pos.ch) &&
            (span.to == null || span.to >= pos.ch))
          { markers.push(span.marker.parent || span.marker); }
      } }
      return markers
    }
```
</details>

### `findMarks(from: any, to: any, filter: any): any[]`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`filter`** `any`

**Returns:** `any[]`

**Calls:**

- `clipPos`
- `this.iter`
- `filter`
- `found.push`

<details><summary>Code</summary>

```typescript
function(from, to, filter) {
      from = clipPos(this, from); to = clipPos(this, to);
      var found = [], lineNo = from.line;
      this.iter(from.line, to.line + 1, function (line) {
        var spans = line.markedSpans;
        if (spans) { for (var i = 0; i < spans.length; i++) {
          var span = spans[i];
          if (!(span.to != null && lineNo == from.line && from.ch >= span.to ||
                span.from == null && lineNo != from.line ||
                span.from != null && lineNo == to.line && span.from >= to.ch) &&
              (!filter || filter(span.marker)))
            { found.push(span.marker.parent || span.marker); }
        } }
        ++lineNo;
      });
      return found
    }
```
</details>

### `getAllMarks(): any[]`

**Returns:** `any[]`

**Calls:**

- `this.iter`
- `markers.push`

<details><summary>Code</summary>

```typescript
function() {
      var markers = [];
      this.iter(function (line) {
        var sps = line.markedSpans;
        if (sps) { for (var i = 0; i < sps.length; ++i)
          { if (sps[i].from != null) { markers.push(sps[i].marker); } } }
      });
      return markers
    }
```
</details>

### `posFromIndex(off: any): any`

**Parameters:**

- **`off`** `any`

**Returns:** `any`

**Calls:**

- `this.lineSeparator`
- `this.iter`
- `clipPos`
- `Pos`

<details><summary>Code</summary>

```typescript
function(off) {
      var ch, lineNo = this.first, sepSize = this.lineSeparator().length;
      this.iter(function (line) {
        var sz = line.text.length + sepSize;
        if (sz > off) { ch = off; return true }
        off -= sz;
        ++lineNo;
      });
      return clipPos(this, Pos(lineNo, ch))
    }
```
</details>

### `indexFromPos(coords: any): any`

**Parameters:**

- **`coords`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `this.lineSeparator`
- `this.iter`

<details><summary>Code</summary>

```typescript
function (coords) {
      coords = clipPos(this, coords);
      var index = coords.ch;
      if (coords.line < this.first || coords.ch < 0) { return 0 }
      var sepSize = this.lineSeparator().length;
      this.iter(this.first, coords.line, function (line) { // iter aborts when callback returns a truthy value
        index += line.text.length + sepSize;
      });
      return index
    }
```
</details>

### `copy(copyHistory: any): Doc`

**Parameters:**

- **`copyHistory`** `any`

**Returns:** `Doc`

**Calls:**

- `getLines`
- `doc.setHistory`
- `this.getHistory`

<details><summary>Code</summary>

```typescript
function(copyHistory) {
      var doc = new Doc(getLines(this, this.first, this.first + this.size),
                        this.modeOption, this.first, this.lineSep, this.direction);
      doc.scrollTop = this.scrollTop; doc.scrollLeft = this.scrollLeft;
      doc.sel = this.sel;
      doc.extend = false;
      if (copyHistory) {
        doc.history.undoDepth = this.history.undoDepth;
        doc.setHistory(this.getHistory());
      }
      return doc
    }
```
</details>

### `linkedDoc(options: any): Doc`

**Parameters:**

- **`options`** `any`

**Returns:** `Doc`

**Calls:**

- `getLines`
- `(this.linked || (this.linked = [])).push`
- `copySharedMarkers`
- `findSharedMarkers`

<details><summary>Code</summary>

```typescript
function(options) {
      if (!options) { options = {}; }
      var from = this.first, to = this.first + this.size;
      if (options.from != null && options.from > from) { from = options.from; }
      if (options.to != null && options.to < to) { to = options.to; }
      var copy = new Doc(getLines(this, from, to), options.mode || this.modeOption, from, this.lineSep, this.direction);
      if (options.sharedHist) { copy.history = this.history
      ; }(this.linked || (this.linked = [])).push({doc: copy, sharedHist: options.sharedHist});
      copy.linked = [{doc: this, isParent: true, sharedHist: options.sharedHist}];
      copySharedMarkers(copy, findSharedMarkers(this));
      return copy
    }
```
</details>

### `unlinkDoc(other: any): void`

**Parameters:**

- **`other`** `any`

**Returns:** `void`

**Calls:**

- `this.linked.splice`
- `other.unlinkDoc`
- `detachSharedMarkers`
- `findSharedMarkers`
- `linkedDocs`
- `splitIds.push`
- `copyHistoryArray`

**Internal Comments:**
```
// If the histories were shared, split them again
```

<details><summary>Code</summary>

```typescript
function(other) {
      if (other instanceof CodeMirror) { other = other.doc; }
      if (this.linked) { for (var i = 0; i < this.linked.length; ++i) {
        var link = this.linked[i];
        if (link.doc != other) { continue }
        this.linked.splice(i, 1);
        other.unlinkDoc(this);
        detachSharedMarkers(findSharedMarkers(this));
        break
      } }
      // If the histories were shared, split them again
      if (other.history == this.history) {
        var splitIds = [other.id];
        linkedDocs(other, function (doc) { return splitIds.push(doc.id); }, true);
        other.history = new History(null);
        other.history.done = copyHistoryArray(this.history.done, splitIds);
        other.history.undone = copyHistoryArray(this.history.undone, splitIds);
      }
    }
```
</details>

### `iterLinkedDocs(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `linkedDocs`

<details><summary>Code</summary>

```typescript
function(f) {linkedDocs(this, f);}
```
</details>

### `getMode(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.mode}
```
</details>

### `getEditor(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.cm}
```
</details>

### `splitLines(str: any): any`

**Parameters:**

- **`str`** `any`

**Returns:** `any`

**Calls:**

- `str.split`
- `splitLinesAuto`

<details><summary>Code</summary>

```typescript
function(str) {
      if (this.lineSep) { return str.split(this.lineSep) }
      return splitLinesAuto(str)
    }
```
</details>

### `lineSeparator(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.lineSep || "\n" }
```
</details>

### `onDrop(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `clearDragCursor`
- `signalDOMEvent`
- `eventInWidget`
- `e_preventDefault`
- `posFromMouse`
- `cm.isReadOnly`
- `Array`
- `complex_call_265827`
- `indexOf`
- `markAsReadAndPasteIfAllFilesAreRead`
- `/[\x00-\x08\x0e-\x1f]{2}/.test`
- `reader.readAsText`
- `readTextFromFile`
- `cm.doc.sel.contains`
- `cm.state.draggingText`
- `setTimeout`
- `cm.display.input.focus`
- `e.dataTransfer.getData`
- `cm.listSelections`
- `setSelectionNoUndo`
- `simpleSelection`
- `replaceRange`
- `cm.replaceSelection`

**Internal Comments:**
```
// Might be a file drop, in which case we simply extract the text
// and insert it.
// Don't do a replace if the drop happened inside of the selected text.
// Ensure the editor is re-focused (x3)
```

<details><summary>Code</summary>

```typescript
function onDrop(e) {
    var cm = this;
    clearDragCursor(cm);
    if (signalDOMEvent(cm, e) || eventInWidget(cm.display, e))
      { return }
    e_preventDefault(e);
    if (ie) { lastDrop = +new Date; }
    var pos = posFromMouse(cm, e, true), files = e.dataTransfer.files;
    if (!pos || cm.isReadOnly()) { return }
    // Might be a file drop, in which case we simply extract the text
    // and insert it.
    if (files && files.length && window.FileReader && window.File) {
      var n = files.length, text = Array(n), read = 0;
      var markAsReadAndPasteIfAllFilesAreRead = function () {
        if (++read == n) {
          operation(cm, function () {
            pos = clipPos(cm.doc, pos);
            var change = {from: pos, to: pos,
                          text: cm.doc.splitLines(
                              text.filter(function (t) { return t != null; }).join(cm.doc.lineSeparator())),
                          origin: "paste"};
            makeChange(cm.doc, change);
            setSelectionReplaceHistory(cm.doc, simpleSelection(clipPos(cm.doc, pos), clipPos(cm.doc, changeEnd(change))));
          })();
        }
      };
      var readTextFromFile = function (file, i) {
        if (cm.options.allowDropFileTypes &&
            indexOf(cm.options.allowDropFileTypes, file.type) == -1) {
          markAsReadAndPasteIfAllFilesAreRead();
          return
        }
        var reader = new FileReader;
        reader.onerror = function () { return markAsReadAndPasteIfAllFilesAreRead(); };
        reader.onload = function () {
          var content = reader.result;
          if (/[\x00-\x08\x0e-\x1f]{2}/.test(content)) {
            markAsReadAndPasteIfAllFilesAreRead();
            return
          }
          text[i] = content;
          markAsReadAndPasteIfAllFilesAreRead();
        };
        reader.readAsText(file);
      };
      for (var i = 0; i < files.length; i++) { readTextFromFile(files[i], i); }
    } else { // Normal drop
      // Don't do a replace if the drop happened inside of the selected text.
      if (cm.state.draggingText && cm.doc.sel.contains(pos) > -1) {
        cm.state.draggingText(e);
        // Ensure the editor is re-focused
        setTimeout(function () { return cm.display.input.focus(); }, 20);
        return
      }
      try {
        var text$1 = e.dataTransfer.getData("Text");
        if (text$1) {
          var selected;
          if (cm.state.draggingText && !cm.state.draggingText.copy)
            { selected = cm.listSelections(); }
          setSelectionNoUndo(cm.doc, simpleSelection(pos, pos));
          if (selected) { for (var i$1 = 0; i$1 < selected.length; ++i$1)
            { replaceRange(cm.doc, "", selected[i$1].anchor, selected[i$1].head, "drag"); } }
          cm.replaceSelection(text$1, "around", "paste");
          cm.display.input.focus();
        }
      }
      catch(e$1){}
    }
  }
```
</details>

### `markAsReadAndPasteIfAllFilesAreRead(): void`

**Returns:** `void`

**Calls:**

- `complex_call_265827`

<details><summary>Code</summary>

```typescript
function () {
        if (++read == n) {
          operation(cm, function () {
            pos = clipPos(cm.doc, pos);
            var change = {from: pos, to: pos,
                          text: cm.doc.splitLines(
                              text.filter(function (t) { return t != null; }).join(cm.doc.lineSeparator())),
                          origin: "paste"};
            makeChange(cm.doc, change);
            setSelectionReplaceHistory(cm.doc, simpleSelection(clipPos(cm.doc, pos), clipPos(cm.doc, changeEnd(change))));
          })();
        }
      }
```
</details>

### `readTextFromFile(file: any, i: any): void`

**Parameters:**

- **`file`** `any`
- **`i`** `any`

**Returns:** `void`

**Calls:**

- `indexOf`
- `markAsReadAndPasteIfAllFilesAreRead`
- `/[\x00-\x08\x0e-\x1f]{2}/.test`
- `reader.readAsText`

<details><summary>Code</summary>

```typescript
function (file, i) {
        if (cm.options.allowDropFileTypes &&
            indexOf(cm.options.allowDropFileTypes, file.type) == -1) {
          markAsReadAndPasteIfAllFilesAreRead();
          return
        }
        var reader = new FileReader;
        reader.onerror = function () { return markAsReadAndPasteIfAllFilesAreRead(); };
        reader.onload = function () {
          var content = reader.result;
          if (/[\x00-\x08\x0e-\x1f]{2}/.test(content)) {
            markAsReadAndPasteIfAllFilesAreRead();
            return
          }
          text[i] = content;
          markAsReadAndPasteIfAllFilesAreRead();
        };
        reader.readAsText(file);
      }
```
</details>

### `onDragStart(cm: any, e: any): void`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e_stop`
- `signalDOMEvent`
- `eventInWidget`
- `e.dataTransfer.setData`
- `cm.getSelection`
- `elt`
- `cm.display.wrapper.appendChild`
- `e.dataTransfer.setDragImage`
- `img.parentNode.removeChild`

**Internal Comments:**
```
// Use dummy image instead of default browsers image.
// Recent Safari (~6.0.2) have a tendency to segfault when this happens, so we don't do it there.
// Force a relayout, or Opera won't use our image for some obscure reason (x4)
```

<details><summary>Code</summary>

```typescript
function onDragStart(cm, e) {
    if (ie && (!cm.state.draggingText || +new Date - lastDrop < 100)) { e_stop(e); return }
    if (signalDOMEvent(cm, e) || eventInWidget(cm.display, e)) { return }

    e.dataTransfer.setData("Text", cm.getSelection());
    e.dataTransfer.effectAllowed = "copyMove";

    // Use dummy image instead of default browsers image.
    // Recent Safari (~6.0.2) have a tendency to segfault when this happens, so we don't do it there.
    if (e.dataTransfer.setDragImage && !safari) {
      var img = elt("img", null, null, "position: fixed; left: 0; top: 0;");
      img.src = "data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==";
      if (presto) {
        img.width = img.height = 1;
        cm.display.wrapper.appendChild(img);
        // Force a relayout, or Opera won't use our image for some obscure reason
        img._top = img.offsetTop;
      }
      e.dataTransfer.setDragImage(img, 0, 0);
      if (presto) { img.parentNode.removeChild(img); }
    }
  }
```
</details>

### `onDragOver(cm: any, e: any): void`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `void`

**Calls:**

- `posFromMouse`
- `document.createDocumentFragment`
- `drawSelectionCursor`
- `elt`
- `cm.display.lineSpace.insertBefore`
- `removeChildrenAndAdd`

<details><summary>Code</summary>

```typescript
function onDragOver(cm, e) {
    var pos = posFromMouse(cm, e);
    if (!pos) { return }
    var frag = document.createDocumentFragment();
    drawSelectionCursor(cm, pos, frag);
    if (!cm.display.dragCursor) {
      cm.display.dragCursor = elt("div", null, "CodeMirror-cursors CodeMirror-dragcursors");
      cm.display.lineSpace.insertBefore(cm.display.dragCursor, cm.display.cursorDiv);
    }
    removeChildrenAndAdd(cm.display.dragCursor, frag);
  }
```
</details>

### `clearDragCursor(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.display.lineSpace.removeChild`

<details><summary>Code</summary>

```typescript
function clearDragCursor(cm) {
    if (cm.display.dragCursor) {
      cm.display.lineSpace.removeChild(cm.display.dragCursor);
      cm.display.dragCursor = null;
    }
  }
```
</details>

### `forEachCodeMirror(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `document.getElementsByClassName`
- `editors.push`
- `editors[0].operation`
- `f`

<details><summary>Code</summary>

```typescript
function forEachCodeMirror(f) {
    if (!document.getElementsByClassName) { return }
    var byClass = document.getElementsByClassName("CodeMirror"), editors = [];
    for (var i = 0; i < byClass.length; i++) {
      var cm = byClass[i].CodeMirror;
      if (cm) { editors.push(cm); }
    }
    if (editors.length) { editors[0].operation(function () {
      for (var i = 0; i < editors.length; i++) { f(editors[i]); }
    }); }
  }
```
</details>

### `ensureGlobalHandlers(): void`

**Returns:** `void`

**Calls:**

- `registerGlobalHandlers`

<details><summary>Code</summary>

```typescript
function ensureGlobalHandlers() {
    if (globalsRegistered) { return }
    registerGlobalHandlers();
    globalsRegistered = true;
  }
```
</details>

### `registerGlobalHandlers(): void`

**Returns:** `void`

**Calls:**

- `on`
- `setTimeout`
- `forEachCodeMirror`

**Internal Comments:**
```
// When the window resizes, we need to refresh active editors. (x2)
// When the window loses focus, we want to show the editor as blurred (x3)
```

<details><summary>Code</summary>

```typescript
function registerGlobalHandlers() {
    // When the window resizes, we need to refresh active editors.
    var resizeTimer;
    on(window, "resize", function () {
      if (resizeTimer == null) { resizeTimer = setTimeout(function () {
        resizeTimer = null;
        forEachCodeMirror(onResize);
      }, 100); }
    });
    // When the window loses focus, we want to show the editor as blurred
    on(window, "blur", function () { return forEachCodeMirror(onBlur); });
  }
```
</details>

### `onResize(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.setSize`

**Internal Comments:**
```
// Might be a text scaling operation, clear size caches. (x4)
```

<details><summary>Code</summary>

```typescript
function onResize(cm) {
    var d = cm.display;
    // Might be a text scaling operation, clear size caches.
    d.cachedCharWidth = d.cachedTextHeight = d.cachedPaddingH = null;
    d.scrollbarsClipped = false;
    cm.setSize();
  }
```
</details>

### `normalizeKeyName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `name.split`
- `/^(cmd|meta|m)$/i.test`
- `/^a(lt)?$/i.test`
- `/^(c|ctrl|control)$/i.test`
- `/^s(hift)?$/i.test`

<details><summary>Code</summary>

```typescript
function normalizeKeyName(name) {
    var parts = name.split(/-(?!$)/);
    name = parts[parts.length - 1];
    var alt, ctrl, shift, cmd;
    for (var i = 0; i < parts.length - 1; i++) {
      var mod = parts[i];
      if (/^(cmd|meta|m)$/i.test(mod)) { cmd = true; }
      else if (/^a(lt)?$/i.test(mod)) { alt = true; }
      else if (/^(c|ctrl|control)$/i.test(mod)) { ctrl = true; }
      else if (/^s(hift)?$/i.test(mod)) { shift = true; }
      else { throw new Error("Unrecognized modifier name: " + mod) }
    }
    if (alt) { name = "Alt-" + name; }
    if (ctrl) { name = "Ctrl-" + name; }
    if (cmd) { name = "Cmd-" + name; }
    if (shift) { name = "Shift-" + name; }
    return name
  }
```
</details>

### `normalizeKeyMap(keymap: any): any`

**Parameters:**

- **`keymap`** `any`

**Returns:** `any`

**Calls:**

- `keymap.hasOwnProperty`
- `/^(name|fallthrough|(de|at)tach)$/.test`
- `map`
- `keyname.split`
- `keys.join`
- `keys.slice(0, i + 1).join`

<details><summary>Code</summary>

```typescript
function normalizeKeyMap(keymap) {
    var copy = {};
    for (var keyname in keymap) { if (keymap.hasOwnProperty(keyname)) {
      var value = keymap[keyname];
      if (/^(name|fallthrough|(de|at)tach)$/.test(keyname)) { continue }
      if (value == "...") { delete keymap[keyname]; continue }

      var keys = map(keyname.split(" "), normalizeKeyName);
      for (var i = 0; i < keys.length; i++) {
        var val = (void 0), name = (void 0);
        if (i == keys.length - 1) {
          name = keys.join(" ");
          val = value;
        } else {
          name = keys.slice(0, i + 1).join(" ");
          val = "...";
        }
        var prev = copy[name];
        if (!prev) { copy[name] = val; }
        else if (prev != val) { throw new Error("Inconsistent bindings for " + name) }
      }
      delete keymap[keyname];
    } }
    for (var prop in copy) { keymap[prop] = copy[prop]; }
    return keymap
  }
```
</details>

### `lookupKey(key: any, map: any, handle: any, context: any): any`

**Parameters:**

- **`key`** `any`
- **`map`** `any`
- **`handle`** `any`
- **`context`** `any`

**Returns:** `any`

**Calls:**

- `getKeyMap`
- `map.call`
- `handle`
- `Object.prototype.toString.call`
- `lookupKey`

<details><summary>Code</summary>

```typescript
function lookupKey(key, map, handle, context) {
    map = getKeyMap(map);
    var found = map.call ? map.call(key, context) : map[key];
    if (found === false) { return "nothing" }
    if (found === "...") { return "multi" }
    if (found != null && handle(found)) { return "handled" }

    if (map.fallthrough) {
      if (Object.prototype.toString.call(map.fallthrough) != "[object Array]")
        { return lookupKey(key, map.fallthrough, handle, context) }
      for (var i = 0; i < map.fallthrough.length; i++) {
        var result = lookupKey(key, map.fallthrough[i], handle, context);
        if (result) { return result }
      }
    }
  }
```
</details>

### `isModifierKey(value: any): boolean`

**Parameters:**

- **`value`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isModifierKey(value) {
    var name = typeof value == "string" ? value : keyNames[value.keyCode];
    return name == "Ctrl" || name == "Alt" || name == "Shift" || name == "Mod"
  }
```
</details>

### `addModifierNames(name: any, event: any, noShift: any): any`

**Parameters:**

- **`name`** `any`
- **`event`** `any`
- **`noShift`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function addModifierNames(name, event, noShift) {
    var base = name;
    if (event.altKey && base != "Alt") { name = "Alt-" + name; }
    if ((flipCtrlCmd ? event.metaKey : event.ctrlKey) && base != "Ctrl") { name = "Ctrl-" + name; }
    if ((flipCtrlCmd ? event.ctrlKey : event.metaKey) && base != "Mod") { name = "Cmd-" + name; }
    if (!noShift && event.shiftKey && base != "Shift") { name = "Shift-" + name; }
    return name
  }
```
</details>

### `keyName(event: any, noShift: any): any`

**Parameters:**

- **`event`** `any`
- **`noShift`** `any`

**Returns:** `any`

**Calls:**

- `addModifierNames`

**Internal Comments:**
```
// Ctrl-ScrollLock has keyCode 3, same as Ctrl-Pause,
// so we'll use event.code when available (Chrome 48+, FF 38+, Safari 10.1+)
```

<details><summary>Code</summary>

```typescript
function keyName(event, noShift) {
    if (presto && event.keyCode == 34 && event["char"]) { return false }
    var name = keyNames[event.keyCode];
    if (name == null || event.altGraphKey) { return false }
    // Ctrl-ScrollLock has keyCode 3, same as Ctrl-Pause,
    // so we'll use event.code when available (Chrome 48+, FF 38+, Safari 10.1+)
    if (event.keyCode == 3 && event.code) { name = event.code; }
    return addModifierNames(name, event, noShift)
  }
```
</details>

### `getKeyMap(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getKeyMap(val) {
    return typeof val == "string" ? keyMap[val] : val
  }
```
</details>

### `deleteNearSelection(cm: any, compute: any): void`

**Parameters:**

- **`cm`** `any`
- **`compute`** `any`

**Returns:** `void`

**Calls:**

- `compute`
- `cmp`
- `lst`
- `kill.pop`
- `kill.push`
- `runInOp`
- `replaceRange`
- `ensureCursorVisible`

**Internal Comments:**
```
// Build up a set of ranges to kill first, merging overlapping
// ranges.
// Next, remove those actual ranges. (x3)
```

<details><summary>Code</summary>

```typescript
function deleteNearSelection(cm, compute) {
    var ranges = cm.doc.sel.ranges, kill = [];
    // Build up a set of ranges to kill first, merging overlapping
    // ranges.
    for (var i = 0; i < ranges.length; i++) {
      var toKill = compute(ranges[i]);
      while (kill.length && cmp(toKill.from, lst(kill).to) <= 0) {
        var replaced = kill.pop();
        if (cmp(replaced.from, toKill.from) < 0) {
          toKill.from = replaced.from;
          break
        }
      }
      kill.push(toKill);
    }
    // Next, remove those actual ranges.
    runInOp(cm, function () {
      for (var i = kill.length - 1; i >= 0; i--)
        { replaceRange(cm.doc, "", kill[i].from, kill[i].to, "+delete"); }
      ensureCursorVisible(cm);
    });
  }
```
</details>

### `moveCharLogically(line: any, ch: any, dir: any): any`

**Parameters:**

- **`line`** `any`
- **`ch`** `any`
- **`dir`** `any`

**Returns:** `any`

**Calls:**

- `skipExtendingChars`

<details><summary>Code</summary>

```typescript
function moveCharLogically(line, ch, dir) {
    var target = skipExtendingChars(line.text, ch + dir, dir);
    return target < 0 || target > line.text.length ? null : target
  }
```
</details>

### `moveLogically(line: any, start: any, dir: any): Pos`

**Parameters:**

- **`line`** `any`
- **`start`** `any`
- **`dir`** `any`

**Returns:** `Pos`

**Calls:**

- `moveCharLogically`

<details><summary>Code</summary>

```typescript
function moveLogically(line, start, dir) {
    var ch = moveCharLogically(line, start.ch, dir);
    return ch == null ? null : new Pos(start.line, ch, dir < 0 ? "after" : "before")
  }
```
</details>

### `endOfLine(visually: any, cm: any, lineObj: any, lineNo: any, dir: any): Pos`

**Parameters:**

- **`visually`** `any`
- **`cm`** `any`
- **`lineObj`** `any`
- **`lineNo`** `any`
- **`dir`** `any`

**Returns:** `Pos`

**Calls:**

- `getOrder`
- `lst`
- `prepareMeasureForLine`
- `measureCharPrepared`
- `findFirst`
- `moveCharLogically`

**Internal Comments:**
```
// With a wrapped rtl chunk (possibly spanning multiple bidi parts),
// it could be that the last bidi part is not on the last visual line,
// since visual lines contain content order-consecutive chunks.
// Thus, in rtl, we are looking for the first (content-order) character
// in the rtl chunk that is on the last line (that is, the same line
// as the last (content-order) character).
```

<details><summary>Code</summary>

```typescript
function endOfLine(visually, cm, lineObj, lineNo, dir) {
    if (visually) {
      if (cm.doc.direction == "rtl") { dir = -dir; }
      var order = getOrder(lineObj, cm.doc.direction);
      if (order) {
        var part = dir < 0 ? lst(order) : order[0];
        var moveInStorageOrder = (dir < 0) == (part.level == 1);
        var sticky = moveInStorageOrder ? "after" : "before";
        var ch;
        // With a wrapped rtl chunk (possibly spanning multiple bidi parts),
        // it could be that the last bidi part is not on the last visual line,
        // since visual lines contain content order-consecutive chunks.
        // Thus, in rtl, we are looking for the first (content-order) character
        // in the rtl chunk that is on the last line (that is, the same line
        // as the last (content-order) character).
        if (part.level > 0 || cm.doc.direction == "rtl") {
          var prep = prepareMeasureForLine(cm, lineObj);
          ch = dir < 0 ? lineObj.text.length - 1 : 0;
          var targetTop = measureCharPrepared(cm, prep, ch).top;
          ch = findFirst(function (ch) { return measureCharPrepared(cm, prep, ch).top == targetTop; }, (dir < 0) == (part.level == 1) ? part.from : part.to - 1, ch);
          if (sticky == "before") { ch = moveCharLogically(lineObj, ch, 1); }
        } else { ch = dir < 0 ? part.to : part.from; }
        return new Pos(lineNo, ch, sticky)
      }
    }
    return new Pos(lineNo, dir < 0 ? lineObj.text.length : 0, dir < 0 ? "before" : "after")
  }
```
</details>

### `moveVisually(cm: any, line: any, start: any, dir: any): Pos`

**Parameters:**

- **`cm`** `any`
- **`line`** `any`
- **`start`** `any`
- **`dir`** `any`

**Returns:** `Pos`

**Calls:**

- `getOrder`
- `moveLogically`
- `getBidiPartAt`
- `moveCharLogically`
- `prepareMeasureForLine`
- `wrappedLineExtentChar`
- `getWrappedLineExtent`
- `mv`
- `getRes`
- `searchInVisualLine`

**Internal Comments:**
```
// Case 1: We move within an ltr part in an ltr editor. Even with wrapped lines,
// nothing interesting happens.
// Case 2: We move within an rtl part or in an rtl editor on the same visual line (x2)
// Case 3: Could not move within this bidi part in this visual line, so leave (x2)
// the current bidi part (x2)
// Case 3a: Look for other bidi parts on the same visual line (x2)
// Case 3b: Look for other bidi parts on the next visual line (x2)
// Case 4: Nowhere to move
```

<details><summary>Code</summary>

```typescript
function moveVisually(cm, line, start, dir) {
    var bidi = getOrder(line, cm.doc.direction);
    if (!bidi) { return moveLogically(line, start, dir) }
    if (start.ch >= line.text.length) {
      start.ch = line.text.length;
      start.sticky = "before";
    } else if (start.ch <= 0) {
      start.ch = 0;
      start.sticky = "after";
    }
    var partPos = getBidiPartAt(bidi, start.ch, start.sticky), part = bidi[partPos];
    if (cm.doc.direction == "ltr" && part.level % 2 == 0 && (dir > 0 ? part.to > start.ch : part.from < start.ch)) {
      // Case 1: We move within an ltr part in an ltr editor. Even with wrapped lines,
      // nothing interesting happens.
      return moveLogically(line, start, dir)
    }

    var mv = function (pos, dir) { return moveCharLogically(line, pos instanceof Pos ? pos.ch : pos, dir); };
    var prep;
    var getWrappedLineExtent = function (ch) {
      if (!cm.options.lineWrapping) { return {begin: 0, end: line.text.length} }
      prep = prep || prepareMeasureForLine(cm, line);
      return wrappedLineExtentChar(cm, line, prep, ch)
    };
    var wrappedLineExtent = getWrappedLineExtent(start.sticky == "before" ? mv(start, -1) : start.ch);

    if (cm.doc.direction == "rtl" || part.level == 1) {
      var moveInStorageOrder = (part.level == 1) == (dir < 0);
      var ch = mv(start, moveInStorageOrder ? 1 : -1);
      if (ch != null && (!moveInStorageOrder ? ch >= part.from && ch >= wrappedLineExtent.begin : ch <= part.to && ch <= wrappedLineExtent.end)) {
        // Case 2: We move within an rtl part or in an rtl editor on the same visual line
        var sticky = moveInStorageOrder ? "before" : "after";
        return new Pos(start.line, ch, sticky)
      }
    }

    // Case 3: Could not move within this bidi part in this visual line, so leave
    // the current bidi part

    var searchInVisualLine = function (partPos, dir, wrappedLineExtent) {
      var getRes = function (ch, moveInStorageOrder) { return moveInStorageOrder
        ? new Pos(start.line, mv(ch, 1), "before")
        : new Pos(start.line, ch, "after"); };

      for (; partPos >= 0 && partPos < bidi.length; partPos += dir) {
        var part = bidi[partPos];
        var moveInStorageOrder = (dir > 0) == (part.level != 1);
        var ch = moveInStorageOrder ? wrappedLineExtent.begin : mv(wrappedLineExtent.end, -1);
        if (part.from <= ch && ch < part.to) { return getRes(ch, moveInStorageOrder) }
        ch = moveInStorageOrder ? part.from : mv(part.to, -1);
        if (wrappedLineExtent.begin <= ch && ch < wrappedLineExtent.end) { return getRes(ch, moveInStorageOrder) }
      }
    };

    // Case 3a: Look for other bidi parts on the same visual line
    var res = searchInVisualLine(partPos + dir, dir, wrappedLineExtent);
    if (res) { return res }

    // Case 3b: Look for other bidi parts on the next visual line
    var nextCh = dir > 0 ? wrappedLineExtent.end : mv(wrappedLineExtent.begin, -1);
    if (nextCh != null && !(dir > 0 && nextCh == line.text.length)) {
      res = searchInVisualLine(dir > 0 ? 0 : bidi.length - 1, dir, getWrappedLineExtent(nextCh));
      if (res) { return res }
    }

    // Case 4: Nowhere to move
    return null
  }
```
</details>

### `mv(pos: any, dir: any): any`

**Parameters:**

- **`pos`** `any`
- **`dir`** `any`

**Returns:** `any`

**Calls:**

- `moveCharLogically`

<details><summary>Code</summary>

```typescript
function (pos, dir) { return moveCharLogically(line, pos instanceof Pos ? pos.ch : pos, dir); }
```
</details>

### `getWrappedLineExtent(ch: any): { begin: any; end: any; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ begin: any; end: any; }`

**Calls:**

- `prepareMeasureForLine`
- `wrappedLineExtentChar`

<details><summary>Code</summary>

```typescript
function (ch) {
      if (!cm.options.lineWrapping) { return {begin: 0, end: line.text.length} }
      prep = prep || prepareMeasureForLine(cm, line);
      return wrappedLineExtentChar(cm, line, prep, ch)
    }
```
</details>

### `searchInVisualLine(partPos: any, dir: any, wrappedLineExtent: any): Pos`

**Parameters:**

- **`partPos`** `any`
- **`dir`** `any`
- **`wrappedLineExtent`** `any`

**Returns:** `Pos`

**Calls:**

- `mv`
- `getRes`

<details><summary>Code</summary>

```typescript
function (partPos, dir, wrappedLineExtent) {
      var getRes = function (ch, moveInStorageOrder) { return moveInStorageOrder
        ? new Pos(start.line, mv(ch, 1), "before")
        : new Pos(start.line, ch, "after"); };

      for (; partPos >= 0 && partPos < bidi.length; partPos += dir) {
        var part = bidi[partPos];
        var moveInStorageOrder = (dir > 0) == (part.level != 1);
        var ch = moveInStorageOrder ? wrappedLineExtent.begin : mv(wrappedLineExtent.end, -1);
        if (part.from <= ch && ch < part.to) { return getRes(ch, moveInStorageOrder) }
        ch = moveInStorageOrder ? part.from : mv(part.to, -1);
        if (wrappedLineExtent.begin <= ch && ch < wrappedLineExtent.end) { return getRes(ch, moveInStorageOrder) }
      }
    }
```
</details>

### `getRes(ch: any, moveInStorageOrder: any): Pos`

**Parameters:**

- **`ch`** `any`
- **`moveInStorageOrder`** `any`

**Returns:** `Pos`

**Calls:**

- `mv`

<details><summary>Code</summary>

```typescript
function (ch, moveInStorageOrder) { return moveInStorageOrder
        ? new Pos(start.line, mv(ch, 1), "before")
        : new Pos(start.line, ch, "after"); }
```
</details>

### `singleSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.setSelection`
- `cm.getCursor`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.setSelection(cm.getCursor("anchor"), cm.getCursor("head"), sel_dontScroll); }
```
</details>

### `killLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `range.empty`
- `getLine`
- `cm.lastLine`
- `Pos`
- `range.from`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      if (range.empty()) {
        var len = getLine(cm.doc, range.head.line).text.length;
        if (range.head.ch == len && range.head.line < cm.lastLine())
          { return {from: range.head, to: Pos(range.head.line + 1, 0)} }
        else
          { return {from: range.head, to: Pos(range.head.line, len)} }
      } else {
        return {from: range.from(), to: range.to()}
      }
    }); }
```
</details>

### `deleteLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`
- `clipPos`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0),
      to: clipPos(cm.doc, Pos(range.to().line + 1, 0))
    }); }); }
```
</details>

### `delLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0), to: range.from()
    }); }); }
```
</details>

### `delWrappedLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var leftPos = cm.coordsChar({left: 0, top: top}, "div");
      return {from: leftPos, to: range.from()}
    }); }
```
</details>

### `delWrappedLineRight(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var rightPos = cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div");
      return {from: range.from(), to: rightPos }
    }); }
```
</details>

### `undo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undo(); }
```
</details>

### `redo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redo(); }
```
</details>

### `undoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undoSelection(); }
```
</details>

### `redoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redoSelection(); }
```
</details>

### `goDocStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.firstLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.firstLine(), 0)); }
```
</details>

### `goDocEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.lastLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.lastLine())); }
```
</details>

### `goLineStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStart(cm, range.head.line); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineStartSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStartSmart(cm, range.head); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineEnd`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineEnd(cm, range.head.line); },
      {origin: "+move", bias: -1}
    ); }
```
</details>

### `goLineRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: 0, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeftSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`
- `cm.getLine(pos.line).search`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      var pos = cm.coordsChar({left: 0, top: top}, "div");
      if (pos.ch < cm.getLine(pos.line).search(/\S/)) { return lineStartSmart(cm, range.head) }
      return pos
    }, sel_move); }
```
</details>

### `goLineUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "line"); }
```
</details>

### `goLineDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "line"); }
```
</details>

### `goPageUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "page"); }
```
</details>

### `goPageDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "page"); }
```
</details>

### `goCharLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "char"); }
```
</details>

### `goCharRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "char"); }
```
</details>

### `goColumnLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "column"); }
```
</details>

### `goColumnRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "column"); }
```
</details>

### `goWordLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "word"); }
```
</details>

### `goGroupRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "group"); }
```
</details>

### `goGroupLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "group"); }
```
</details>

### `goWordRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "word"); }
```
</details>

### `delCharBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "codepoint"); }
```
</details>

### `delCharAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "char"); }
```
</details>

### `delWordBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "word"); }
```
</details>

### `delWordAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "word"); }
```
</details>

### `delGroupBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "group"); }
```
</details>

### `delGroupAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "group"); }
```
</details>

### `indentAuto(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("smart"); }
```
</details>

### `indentMore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("add"); }
```
</details>

### `indentLess(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("subtract"); }
```
</details>

### `insertTab(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\t"); }
```
</details>

### `insertSoftTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.listSelections`
- `ranges[i].from`
- `countColumn`
- `cm.getLine`
- `spaces.push`
- `spaceStr`
- `cm.replaceSelections`

<details><summary>Code</summary>

```typescript
function (cm) {
      var spaces = [], ranges = cm.listSelections(), tabSize = cm.options.tabSize;
      for (var i = 0; i < ranges.length; i++) {
        var pos = ranges[i].from();
        var col = countColumn(cm.getLine(pos.line), pos.ch, tabSize);
        spaces.push(spaceStr(tabSize - col % tabSize));
      }
      cm.replaceSelections(spaces);
    }
```
</details>

### `defaultTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.somethingSelected`
- `cm.indentSelection`
- `cm.execCommand`

<details><summary>Code</summary>

```typescript
function (cm) {
      if (cm.somethingSelected()) { cm.indentSelection("add"); }
      else { cm.execCommand("insertTab"); }
    }
```
</details>

### `transposeChars(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `ranges[i].empty`
- `getLine`
- `cm.replaceRange`
- `line.charAt`
- `Pos`
- `cm.doc.lineSeparator`
- `prev.charAt`
- `newSel.push`
- `cm.setSelections`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var ranges = cm.listSelections(), newSel = [];
      for (var i = 0; i < ranges.length; i++) {
        if (!ranges[i].empty()) { continue }
        var cur = ranges[i].head, line = getLine(cm.doc, cur.line).text;
        if (line) {
          if (cur.ch == line.length) { cur = new Pos(cur.line, cur.ch - 1); }
          if (cur.ch > 0) {
            cur = new Pos(cur.line, cur.ch + 1);
            cm.replaceRange(line.charAt(cur.ch - 1) + line.charAt(cur.ch - 2),
                            Pos(cur.line, cur.ch - 2), cur, "+transpose");
          } else if (cur.line > cm.doc.first) {
            var prev = getLine(cm.doc, cur.line - 1).text;
            if (prev) {
              cur = new Pos(cur.line, 1);
              cm.replaceRange(line.charAt(0) + cm.doc.lineSeparator() +
                              prev.charAt(prev.length - 1),
                              Pos(cur.line - 1, prev.length - 1), cur, "+transpose");
            }
          }
        }
        newSel.push(new Range(cur, cur));
      }
      cm.setSelections(newSel);
    }); }
```
</details>

### `newlineAndIndent(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `cm.replaceRange`
- `cm.doc.lineSeparator`
- `cm.indentLine`
- `sels[i$1].from`
- `ensureCursorVisible`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var sels = cm.listSelections();
      for (var i = sels.length - 1; i >= 0; i--)
        { cm.replaceRange(cm.doc.lineSeparator(), sels[i].anchor, sels[i].head, "+input"); }
      sels = cm.listSelections();
      for (var i$1 = 0; i$1 < sels.length; i$1++)
        { cm.indentLine(sels[i$1].from().line, null, true); }
      ensureCursorVisible(cm);
    }); }
```
</details>

### `openLine(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\n", "start"); }
```
</details>

### `toggleOverwrite(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.toggleOverwrite`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.toggleOverwrite(); }
```
</details>

### `singleSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.setSelection`
- `cm.getCursor`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.setSelection(cm.getCursor("anchor"), cm.getCursor("head"), sel_dontScroll); }
```
</details>

### `killLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `range.empty`
- `getLine`
- `cm.lastLine`
- `Pos`
- `range.from`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      if (range.empty()) {
        var len = getLine(cm.doc, range.head.line).text.length;
        if (range.head.ch == len && range.head.line < cm.lastLine())
          { return {from: range.head, to: Pos(range.head.line + 1, 0)} }
        else
          { return {from: range.head, to: Pos(range.head.line, len)} }
      } else {
        return {from: range.from(), to: range.to()}
      }
    }); }
```
</details>

### `deleteLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`
- `clipPos`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0),
      to: clipPos(cm.doc, Pos(range.to().line + 1, 0))
    }); }); }
```
</details>

### `delLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0), to: range.from()
    }); }); }
```
</details>

### `delWrappedLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var leftPos = cm.coordsChar({left: 0, top: top}, "div");
      return {from: leftPos, to: range.from()}
    }); }
```
</details>

### `delWrappedLineRight(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var rightPos = cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div");
      return {from: range.from(), to: rightPos }
    }); }
```
</details>

### `undo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undo(); }
```
</details>

### `redo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redo(); }
```
</details>

### `undoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undoSelection(); }
```
</details>

### `redoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redoSelection(); }
```
</details>

### `goDocStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.firstLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.firstLine(), 0)); }
```
</details>

### `goDocEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.lastLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.lastLine())); }
```
</details>

### `goLineStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStart(cm, range.head.line); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineStartSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStartSmart(cm, range.head); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineEnd`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineEnd(cm, range.head.line); },
      {origin: "+move", bias: -1}
    ); }
```
</details>

### `goLineRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: 0, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeftSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`
- `cm.getLine(pos.line).search`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      var pos = cm.coordsChar({left: 0, top: top}, "div");
      if (pos.ch < cm.getLine(pos.line).search(/\S/)) { return lineStartSmart(cm, range.head) }
      return pos
    }, sel_move); }
```
</details>

### `goLineUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "line"); }
```
</details>

### `goLineDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "line"); }
```
</details>

### `goPageUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "page"); }
```
</details>

### `goPageDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "page"); }
```
</details>

### `goCharLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "char"); }
```
</details>

### `goCharRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "char"); }
```
</details>

### `goColumnLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "column"); }
```
</details>

### `goColumnRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "column"); }
```
</details>

### `goWordLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "word"); }
```
</details>

### `goGroupRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "group"); }
```
</details>

### `goGroupLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "group"); }
```
</details>

### `goWordRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "word"); }
```
</details>

### `delCharBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "codepoint"); }
```
</details>

### `delCharAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "char"); }
```
</details>

### `delWordBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "word"); }
```
</details>

### `delWordAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "word"); }
```
</details>

### `delGroupBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "group"); }
```
</details>

### `delGroupAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "group"); }
```
</details>

### `indentAuto(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("smart"); }
```
</details>

### `indentMore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("add"); }
```
</details>

### `indentLess(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("subtract"); }
```
</details>

### `insertTab(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\t"); }
```
</details>

### `insertSoftTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.listSelections`
- `ranges[i].from`
- `countColumn`
- `cm.getLine`
- `spaces.push`
- `spaceStr`
- `cm.replaceSelections`

<details><summary>Code</summary>

```typescript
function (cm) {
      var spaces = [], ranges = cm.listSelections(), tabSize = cm.options.tabSize;
      for (var i = 0; i < ranges.length; i++) {
        var pos = ranges[i].from();
        var col = countColumn(cm.getLine(pos.line), pos.ch, tabSize);
        spaces.push(spaceStr(tabSize - col % tabSize));
      }
      cm.replaceSelections(spaces);
    }
```
</details>

### `defaultTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.somethingSelected`
- `cm.indentSelection`
- `cm.execCommand`

<details><summary>Code</summary>

```typescript
function (cm) {
      if (cm.somethingSelected()) { cm.indentSelection("add"); }
      else { cm.execCommand("insertTab"); }
    }
```
</details>

### `transposeChars(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `ranges[i].empty`
- `getLine`
- `cm.replaceRange`
- `line.charAt`
- `Pos`
- `cm.doc.lineSeparator`
- `prev.charAt`
- `newSel.push`
- `cm.setSelections`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var ranges = cm.listSelections(), newSel = [];
      for (var i = 0; i < ranges.length; i++) {
        if (!ranges[i].empty()) { continue }
        var cur = ranges[i].head, line = getLine(cm.doc, cur.line).text;
        if (line) {
          if (cur.ch == line.length) { cur = new Pos(cur.line, cur.ch - 1); }
          if (cur.ch > 0) {
            cur = new Pos(cur.line, cur.ch + 1);
            cm.replaceRange(line.charAt(cur.ch - 1) + line.charAt(cur.ch - 2),
                            Pos(cur.line, cur.ch - 2), cur, "+transpose");
          } else if (cur.line > cm.doc.first) {
            var prev = getLine(cm.doc, cur.line - 1).text;
            if (prev) {
              cur = new Pos(cur.line, 1);
              cm.replaceRange(line.charAt(0) + cm.doc.lineSeparator() +
                              prev.charAt(prev.length - 1),
                              Pos(cur.line - 1, prev.length - 1), cur, "+transpose");
            }
          }
        }
        newSel.push(new Range(cur, cur));
      }
      cm.setSelections(newSel);
    }); }
```
</details>

### `newlineAndIndent(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `cm.replaceRange`
- `cm.doc.lineSeparator`
- `cm.indentLine`
- `sels[i$1].from`
- `ensureCursorVisible`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var sels = cm.listSelections();
      for (var i = sels.length - 1; i >= 0; i--)
        { cm.replaceRange(cm.doc.lineSeparator(), sels[i].anchor, sels[i].head, "+input"); }
      sels = cm.listSelections();
      for (var i$1 = 0; i$1 < sels.length; i$1++)
        { cm.indentLine(sels[i$1].from().line, null, true); }
      ensureCursorVisible(cm);
    }); }
```
</details>

### `openLine(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\n", "start"); }
```
</details>

### `toggleOverwrite(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.toggleOverwrite`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.toggleOverwrite(); }
```
</details>

### `singleSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.setSelection`
- `cm.getCursor`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.setSelection(cm.getCursor("anchor"), cm.getCursor("head"), sel_dontScroll); }
```
</details>

### `killLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `range.empty`
- `getLine`
- `cm.lastLine`
- `Pos`
- `range.from`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      if (range.empty()) {
        var len = getLine(cm.doc, range.head.line).text.length;
        if (range.head.ch == len && range.head.line < cm.lastLine())
          { return {from: range.head, to: Pos(range.head.line + 1, 0)} }
        else
          { return {from: range.head, to: Pos(range.head.line, len)} }
      } else {
        return {from: range.from(), to: range.to()}
      }
    }); }
```
</details>

### `deleteLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`
- `clipPos`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0),
      to: clipPos(cm.doc, Pos(range.to().line + 1, 0))
    }); }); }
```
</details>

### `delLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0), to: range.from()
    }); }); }
```
</details>

### `delWrappedLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var leftPos = cm.coordsChar({left: 0, top: top}, "div");
      return {from: leftPos, to: range.from()}
    }); }
```
</details>

### `delWrappedLineRight(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var rightPos = cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div");
      return {from: range.from(), to: rightPos }
    }); }
```
</details>

### `undo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undo(); }
```
</details>

### `redo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redo(); }
```
</details>

### `undoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undoSelection(); }
```
</details>

### `redoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redoSelection(); }
```
</details>

### `goDocStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.firstLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.firstLine(), 0)); }
```
</details>

### `goDocEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.lastLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.lastLine())); }
```
</details>

### `goLineStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStart(cm, range.head.line); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineStartSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStartSmart(cm, range.head); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineEnd`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineEnd(cm, range.head.line); },
      {origin: "+move", bias: -1}
    ); }
```
</details>

### `goLineRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: 0, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeftSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`
- `cm.getLine(pos.line).search`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      var pos = cm.coordsChar({left: 0, top: top}, "div");
      if (pos.ch < cm.getLine(pos.line).search(/\S/)) { return lineStartSmart(cm, range.head) }
      return pos
    }, sel_move); }
```
</details>

### `goLineUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "line"); }
```
</details>

### `goLineDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "line"); }
```
</details>

### `goPageUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "page"); }
```
</details>

### `goPageDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "page"); }
```
</details>

### `goCharLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "char"); }
```
</details>

### `goCharRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "char"); }
```
</details>

### `goColumnLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "column"); }
```
</details>

### `goColumnRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "column"); }
```
</details>

### `goWordLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "word"); }
```
</details>

### `goGroupRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "group"); }
```
</details>

### `goGroupLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "group"); }
```
</details>

### `goWordRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "word"); }
```
</details>

### `delCharBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "codepoint"); }
```
</details>

### `delCharAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "char"); }
```
</details>

### `delWordBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "word"); }
```
</details>

### `delWordAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "word"); }
```
</details>

### `delGroupBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "group"); }
```
</details>

### `delGroupAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "group"); }
```
</details>

### `indentAuto(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("smart"); }
```
</details>

### `indentMore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("add"); }
```
</details>

### `indentLess(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("subtract"); }
```
</details>

### `insertTab(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\t"); }
```
</details>

### `insertSoftTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.listSelections`
- `ranges[i].from`
- `countColumn`
- `cm.getLine`
- `spaces.push`
- `spaceStr`
- `cm.replaceSelections`

<details><summary>Code</summary>

```typescript
function (cm) {
      var spaces = [], ranges = cm.listSelections(), tabSize = cm.options.tabSize;
      for (var i = 0; i < ranges.length; i++) {
        var pos = ranges[i].from();
        var col = countColumn(cm.getLine(pos.line), pos.ch, tabSize);
        spaces.push(spaceStr(tabSize - col % tabSize));
      }
      cm.replaceSelections(spaces);
    }
```
</details>

### `defaultTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.somethingSelected`
- `cm.indentSelection`
- `cm.execCommand`

<details><summary>Code</summary>

```typescript
function (cm) {
      if (cm.somethingSelected()) { cm.indentSelection("add"); }
      else { cm.execCommand("insertTab"); }
    }
```
</details>

### `transposeChars(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `ranges[i].empty`
- `getLine`
- `cm.replaceRange`
- `line.charAt`
- `Pos`
- `cm.doc.lineSeparator`
- `prev.charAt`
- `newSel.push`
- `cm.setSelections`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var ranges = cm.listSelections(), newSel = [];
      for (var i = 0; i < ranges.length; i++) {
        if (!ranges[i].empty()) { continue }
        var cur = ranges[i].head, line = getLine(cm.doc, cur.line).text;
        if (line) {
          if (cur.ch == line.length) { cur = new Pos(cur.line, cur.ch - 1); }
          if (cur.ch > 0) {
            cur = new Pos(cur.line, cur.ch + 1);
            cm.replaceRange(line.charAt(cur.ch - 1) + line.charAt(cur.ch - 2),
                            Pos(cur.line, cur.ch - 2), cur, "+transpose");
          } else if (cur.line > cm.doc.first) {
            var prev = getLine(cm.doc, cur.line - 1).text;
            if (prev) {
              cur = new Pos(cur.line, 1);
              cm.replaceRange(line.charAt(0) + cm.doc.lineSeparator() +
                              prev.charAt(prev.length - 1),
                              Pos(cur.line - 1, prev.length - 1), cur, "+transpose");
            }
          }
        }
        newSel.push(new Range(cur, cur));
      }
      cm.setSelections(newSel);
    }); }
```
</details>

### `newlineAndIndent(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `cm.replaceRange`
- `cm.doc.lineSeparator`
- `cm.indentLine`
- `sels[i$1].from`
- `ensureCursorVisible`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var sels = cm.listSelections();
      for (var i = sels.length - 1; i >= 0; i--)
        { cm.replaceRange(cm.doc.lineSeparator(), sels[i].anchor, sels[i].head, "+input"); }
      sels = cm.listSelections();
      for (var i$1 = 0; i$1 < sels.length; i$1++)
        { cm.indentLine(sels[i$1].from().line, null, true); }
      ensureCursorVisible(cm);
    }); }
```
</details>

### `openLine(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\n", "start"); }
```
</details>

### `toggleOverwrite(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.toggleOverwrite`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.toggleOverwrite(); }
```
</details>

### `singleSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.setSelection`
- `cm.getCursor`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.setSelection(cm.getCursor("anchor"), cm.getCursor("head"), sel_dontScroll); }
```
</details>

### `killLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `range.empty`
- `getLine`
- `cm.lastLine`
- `Pos`
- `range.from`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      if (range.empty()) {
        var len = getLine(cm.doc, range.head.line).text.length;
        if (range.head.ch == len && range.head.line < cm.lastLine())
          { return {from: range.head, to: Pos(range.head.line + 1, 0)} }
        else
          { return {from: range.head, to: Pos(range.head.line, len)} }
      } else {
        return {from: range.from(), to: range.to()}
      }
    }); }
```
</details>

### `deleteLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`
- `clipPos`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0),
      to: clipPos(cm.doc, Pos(range.to().line + 1, 0))
    }); }); }
```
</details>

### `delLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0), to: range.from()
    }); }); }
```
</details>

### `delWrappedLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var leftPos = cm.coordsChar({left: 0, top: top}, "div");
      return {from: leftPos, to: range.from()}
    }); }
```
</details>

### `delWrappedLineRight(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var rightPos = cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div");
      return {from: range.from(), to: rightPos }
    }); }
```
</details>

### `undo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undo(); }
```
</details>

### `redo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redo(); }
```
</details>

### `undoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undoSelection(); }
```
</details>

### `redoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redoSelection(); }
```
</details>

### `goDocStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.firstLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.firstLine(), 0)); }
```
</details>

### `goDocEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.lastLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.lastLine())); }
```
</details>

### `goLineStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStart(cm, range.head.line); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineStartSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStartSmart(cm, range.head); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineEnd`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineEnd(cm, range.head.line); },
      {origin: "+move", bias: -1}
    ); }
```
</details>

### `goLineRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: 0, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeftSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`
- `cm.getLine(pos.line).search`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      var pos = cm.coordsChar({left: 0, top: top}, "div");
      if (pos.ch < cm.getLine(pos.line).search(/\S/)) { return lineStartSmart(cm, range.head) }
      return pos
    }, sel_move); }
```
</details>

### `goLineUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "line"); }
```
</details>

### `goLineDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "line"); }
```
</details>

### `goPageUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "page"); }
```
</details>

### `goPageDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "page"); }
```
</details>

### `goCharLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "char"); }
```
</details>

### `goCharRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "char"); }
```
</details>

### `goColumnLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "column"); }
```
</details>

### `goColumnRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "column"); }
```
</details>

### `goWordLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "word"); }
```
</details>

### `goGroupRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "group"); }
```
</details>

### `goGroupLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "group"); }
```
</details>

### `goWordRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "word"); }
```
</details>

### `delCharBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "codepoint"); }
```
</details>

### `delCharAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "char"); }
```
</details>

### `delWordBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "word"); }
```
</details>

### `delWordAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "word"); }
```
</details>

### `delGroupBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "group"); }
```
</details>

### `delGroupAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "group"); }
```
</details>

### `indentAuto(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("smart"); }
```
</details>

### `indentMore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("add"); }
```
</details>

### `indentLess(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("subtract"); }
```
</details>

### `insertTab(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\t"); }
```
</details>

### `insertSoftTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.listSelections`
- `ranges[i].from`
- `countColumn`
- `cm.getLine`
- `spaces.push`
- `spaceStr`
- `cm.replaceSelections`

<details><summary>Code</summary>

```typescript
function (cm) {
      var spaces = [], ranges = cm.listSelections(), tabSize = cm.options.tabSize;
      for (var i = 0; i < ranges.length; i++) {
        var pos = ranges[i].from();
        var col = countColumn(cm.getLine(pos.line), pos.ch, tabSize);
        spaces.push(spaceStr(tabSize - col % tabSize));
      }
      cm.replaceSelections(spaces);
    }
```
</details>

### `defaultTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.somethingSelected`
- `cm.indentSelection`
- `cm.execCommand`

<details><summary>Code</summary>

```typescript
function (cm) {
      if (cm.somethingSelected()) { cm.indentSelection("add"); }
      else { cm.execCommand("insertTab"); }
    }
```
</details>

### `transposeChars(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `ranges[i].empty`
- `getLine`
- `cm.replaceRange`
- `line.charAt`
- `Pos`
- `cm.doc.lineSeparator`
- `prev.charAt`
- `newSel.push`
- `cm.setSelections`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var ranges = cm.listSelections(), newSel = [];
      for (var i = 0; i < ranges.length; i++) {
        if (!ranges[i].empty()) { continue }
        var cur = ranges[i].head, line = getLine(cm.doc, cur.line).text;
        if (line) {
          if (cur.ch == line.length) { cur = new Pos(cur.line, cur.ch - 1); }
          if (cur.ch > 0) {
            cur = new Pos(cur.line, cur.ch + 1);
            cm.replaceRange(line.charAt(cur.ch - 1) + line.charAt(cur.ch - 2),
                            Pos(cur.line, cur.ch - 2), cur, "+transpose");
          } else if (cur.line > cm.doc.first) {
            var prev = getLine(cm.doc, cur.line - 1).text;
            if (prev) {
              cur = new Pos(cur.line, 1);
              cm.replaceRange(line.charAt(0) + cm.doc.lineSeparator() +
                              prev.charAt(prev.length - 1),
                              Pos(cur.line - 1, prev.length - 1), cur, "+transpose");
            }
          }
        }
        newSel.push(new Range(cur, cur));
      }
      cm.setSelections(newSel);
    }); }
```
</details>

### `newlineAndIndent(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `cm.replaceRange`
- `cm.doc.lineSeparator`
- `cm.indentLine`
- `sels[i$1].from`
- `ensureCursorVisible`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var sels = cm.listSelections();
      for (var i = sels.length - 1; i >= 0; i--)
        { cm.replaceRange(cm.doc.lineSeparator(), sels[i].anchor, sels[i].head, "+input"); }
      sels = cm.listSelections();
      for (var i$1 = 0; i$1 < sels.length; i$1++)
        { cm.indentLine(sels[i$1].from().line, null, true); }
      ensureCursorVisible(cm);
    }); }
```
</details>

### `openLine(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\n", "start"); }
```
</details>

### `toggleOverwrite(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.toggleOverwrite`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.toggleOverwrite(); }
```
</details>

### `singleSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.setSelection`
- `cm.getCursor`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.setSelection(cm.getCursor("anchor"), cm.getCursor("head"), sel_dontScroll); }
```
</details>

### `killLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `range.empty`
- `getLine`
- `cm.lastLine`
- `Pos`
- `range.from`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      if (range.empty()) {
        var len = getLine(cm.doc, range.head.line).text.length;
        if (range.head.ch == len && range.head.line < cm.lastLine())
          { return {from: range.head, to: Pos(range.head.line + 1, 0)} }
        else
          { return {from: range.head, to: Pos(range.head.line, len)} }
      } else {
        return {from: range.from(), to: range.to()}
      }
    }); }
```
</details>

### `deleteLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`
- `clipPos`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0),
      to: clipPos(cm.doc, Pos(range.to().line + 1, 0))
    }); }); }
```
</details>

### `delLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0), to: range.from()
    }); }); }
```
</details>

### `delWrappedLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var leftPos = cm.coordsChar({left: 0, top: top}, "div");
      return {from: leftPos, to: range.from()}
    }); }
```
</details>

### `delWrappedLineRight(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var rightPos = cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div");
      return {from: range.from(), to: rightPos }
    }); }
```
</details>

### `undo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undo(); }
```
</details>

### `redo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redo(); }
```
</details>

### `undoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undoSelection(); }
```
</details>

### `redoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redoSelection(); }
```
</details>

### `goDocStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.firstLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.firstLine(), 0)); }
```
</details>

### `goDocEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.lastLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.lastLine())); }
```
</details>

### `goLineStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStart(cm, range.head.line); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineStartSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStartSmart(cm, range.head); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineEnd`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineEnd(cm, range.head.line); },
      {origin: "+move", bias: -1}
    ); }
```
</details>

### `goLineRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: 0, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeftSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`
- `cm.getLine(pos.line).search`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      var pos = cm.coordsChar({left: 0, top: top}, "div");
      if (pos.ch < cm.getLine(pos.line).search(/\S/)) { return lineStartSmart(cm, range.head) }
      return pos
    }, sel_move); }
```
</details>

### `goLineUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "line"); }
```
</details>

### `goLineDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "line"); }
```
</details>

### `goPageUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "page"); }
```
</details>

### `goPageDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "page"); }
```
</details>

### `goCharLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "char"); }
```
</details>

### `goCharRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "char"); }
```
</details>

### `goColumnLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "column"); }
```
</details>

### `goColumnRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "column"); }
```
</details>

### `goWordLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "word"); }
```
</details>

### `goGroupRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "group"); }
```
</details>

### `goGroupLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "group"); }
```
</details>

### `goWordRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "word"); }
```
</details>

### `delCharBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "codepoint"); }
```
</details>

### `delCharAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "char"); }
```
</details>

### `delWordBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "word"); }
```
</details>

### `delWordAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "word"); }
```
</details>

### `delGroupBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "group"); }
```
</details>

### `delGroupAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "group"); }
```
</details>

### `indentAuto(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("smart"); }
```
</details>

### `indentMore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("add"); }
```
</details>

### `indentLess(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("subtract"); }
```
</details>

### `insertTab(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\t"); }
```
</details>

### `insertSoftTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.listSelections`
- `ranges[i].from`
- `countColumn`
- `cm.getLine`
- `spaces.push`
- `spaceStr`
- `cm.replaceSelections`

<details><summary>Code</summary>

```typescript
function (cm) {
      var spaces = [], ranges = cm.listSelections(), tabSize = cm.options.tabSize;
      for (var i = 0; i < ranges.length; i++) {
        var pos = ranges[i].from();
        var col = countColumn(cm.getLine(pos.line), pos.ch, tabSize);
        spaces.push(spaceStr(tabSize - col % tabSize));
      }
      cm.replaceSelections(spaces);
    }
```
</details>

### `defaultTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.somethingSelected`
- `cm.indentSelection`
- `cm.execCommand`

<details><summary>Code</summary>

```typescript
function (cm) {
      if (cm.somethingSelected()) { cm.indentSelection("add"); }
      else { cm.execCommand("insertTab"); }
    }
```
</details>

### `transposeChars(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `ranges[i].empty`
- `getLine`
- `cm.replaceRange`
- `line.charAt`
- `Pos`
- `cm.doc.lineSeparator`
- `prev.charAt`
- `newSel.push`
- `cm.setSelections`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var ranges = cm.listSelections(), newSel = [];
      for (var i = 0; i < ranges.length; i++) {
        if (!ranges[i].empty()) { continue }
        var cur = ranges[i].head, line = getLine(cm.doc, cur.line).text;
        if (line) {
          if (cur.ch == line.length) { cur = new Pos(cur.line, cur.ch - 1); }
          if (cur.ch > 0) {
            cur = new Pos(cur.line, cur.ch + 1);
            cm.replaceRange(line.charAt(cur.ch - 1) + line.charAt(cur.ch - 2),
                            Pos(cur.line, cur.ch - 2), cur, "+transpose");
          } else if (cur.line > cm.doc.first) {
            var prev = getLine(cm.doc, cur.line - 1).text;
            if (prev) {
              cur = new Pos(cur.line, 1);
              cm.replaceRange(line.charAt(0) + cm.doc.lineSeparator() +
                              prev.charAt(prev.length - 1),
                              Pos(cur.line - 1, prev.length - 1), cur, "+transpose");
            }
          }
        }
        newSel.push(new Range(cur, cur));
      }
      cm.setSelections(newSel);
    }); }
```
</details>

### `newlineAndIndent(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `cm.replaceRange`
- `cm.doc.lineSeparator`
- `cm.indentLine`
- `sels[i$1].from`
- `ensureCursorVisible`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var sels = cm.listSelections();
      for (var i = sels.length - 1; i >= 0; i--)
        { cm.replaceRange(cm.doc.lineSeparator(), sels[i].anchor, sels[i].head, "+input"); }
      sels = cm.listSelections();
      for (var i$1 = 0; i$1 < sels.length; i$1++)
        { cm.indentLine(sels[i$1].from().line, null, true); }
      ensureCursorVisible(cm);
    }); }
```
</details>

### `openLine(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\n", "start"); }
```
</details>

### `toggleOverwrite(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.toggleOverwrite`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.toggleOverwrite(); }
```
</details>

### `singleSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.setSelection`
- `cm.getCursor`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.setSelection(cm.getCursor("anchor"), cm.getCursor("head"), sel_dontScroll); }
```
</details>

### `killLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `range.empty`
- `getLine`
- `cm.lastLine`
- `Pos`
- `range.from`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      if (range.empty()) {
        var len = getLine(cm.doc, range.head.line).text.length;
        if (range.head.ch == len && range.head.line < cm.lastLine())
          { return {from: range.head, to: Pos(range.head.line + 1, 0)} }
        else
          { return {from: range.head, to: Pos(range.head.line, len)} }
      } else {
        return {from: range.from(), to: range.to()}
      }
    }); }
```
</details>

### `deleteLine(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`
- `clipPos`
- `range.to`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0),
      to: clipPos(cm.doc, Pos(range.to().line + 1, 0))
    }); }); }
```
</details>

### `delLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `Pos`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) { return ({
      from: Pos(range.from().line, 0), to: range.from()
    }); }); }
```
</details>

### `delWrappedLineLeft(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var leftPos = cm.coordsChar({left: 0, top: top}, "div");
      return {from: leftPos, to: range.from()}
    }); }
```
</details>

### `delWrappedLineRight(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `deleteNearSelection`
- `cm.charCoords`
- `cm.coordsChar`
- `range.from`

<details><summary>Code</summary>

```typescript
function (cm) { return deleteNearSelection(cm, function (range) {
      var top = cm.charCoords(range.head, "div").top + 5;
      var rightPos = cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div");
      return {from: range.from(), to: rightPos }
    }); }
```
</details>

### `undo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undo(); }
```
</details>

### `redo(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redo`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redo(); }
```
</details>

### `undoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.undoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.undoSelection(); }
```
</details>

### `redoSelection(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.redoSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.redoSelection(); }
```
</details>

### `goDocStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.firstLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.firstLine(), 0)); }
```
</details>

### `goDocEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelection`
- `Pos`
- `cm.lastLine`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelection(Pos(cm.lastLine())); }
```
</details>

### `goLineStart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStart(cm, range.head.line); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineStartSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineStartSmart(cm, range.head); },
      {origin: "+move", bias: 1}
    ); }
```
</details>

### `goLineEnd(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `lineEnd`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) { return lineEnd(cm, range.head.line); },
      {origin: "+move", bias: -1}
    ); }
```
</details>

### `goLineRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: cm.display.lineDiv.offsetWidth + 100, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      return cm.coordsChar({left: 0, top: top}, "div")
    }, sel_move); }
```
</details>

### `goLineLeftSmart(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.extendSelectionsBy`
- `cm.cursorCoords`
- `cm.coordsChar`
- `cm.getLine(pos.line).search`
- `lineStartSmart`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.extendSelectionsBy(function (range) {
      var top = cm.cursorCoords(range.head, "div").top + 5;
      var pos = cm.coordsChar({left: 0, top: top}, "div");
      if (pos.ch < cm.getLine(pos.line).search(/\S/)) { return lineStartSmart(cm, range.head) }
      return pos
    }, sel_move); }
```
</details>

### `goLineUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "line"); }
```
</details>

### `goLineDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "line"); }
```
</details>

### `goPageUp(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(-1, "page"); }
```
</details>

### `goPageDown(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveV`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveV(1, "page"); }
```
</details>

### `goCharLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "char"); }
```
</details>

### `goCharRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "char"); }
```
</details>

### `goColumnLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "column"); }
```
</details>

### `goColumnRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "column"); }
```
</details>

### `goWordLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "word"); }
```
</details>

### `goGroupRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "group"); }
```
</details>

### `goGroupLeft(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(-1, "group"); }
```
</details>

### `goWordRight(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.moveH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.moveH(1, "word"); }
```
</details>

### `delCharBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "codepoint"); }
```
</details>

### `delCharAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "char"); }
```
</details>

### `delWordBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "word"); }
```
</details>

### `delWordAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "word"); }
```
</details>

### `delGroupBefore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(-1, "group"); }
```
</details>

### `delGroupAfter(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.deleteH`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.deleteH(1, "group"); }
```
</details>

### `indentAuto(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("smart"); }
```
</details>

### `indentMore(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("add"); }
```
</details>

### `indentLess(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.indentSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.indentSelection("subtract"); }
```
</details>

### `insertTab(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\t"); }
```
</details>

### `insertSoftTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.listSelections`
- `ranges[i].from`
- `countColumn`
- `cm.getLine`
- `spaces.push`
- `spaceStr`
- `cm.replaceSelections`

<details><summary>Code</summary>

```typescript
function (cm) {
      var spaces = [], ranges = cm.listSelections(), tabSize = cm.options.tabSize;
      for (var i = 0; i < ranges.length; i++) {
        var pos = ranges[i].from();
        var col = countColumn(cm.getLine(pos.line), pos.ch, tabSize);
        spaces.push(spaceStr(tabSize - col % tabSize));
      }
      cm.replaceSelections(spaces);
    }
```
</details>

### `defaultTab(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.somethingSelected`
- `cm.indentSelection`
- `cm.execCommand`

<details><summary>Code</summary>

```typescript
function (cm) {
      if (cm.somethingSelected()) { cm.indentSelection("add"); }
      else { cm.execCommand("insertTab"); }
    }
```
</details>

### `transposeChars(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `ranges[i].empty`
- `getLine`
- `cm.replaceRange`
- `line.charAt`
- `Pos`
- `cm.doc.lineSeparator`
- `prev.charAt`
- `newSel.push`
- `cm.setSelections`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var ranges = cm.listSelections(), newSel = [];
      for (var i = 0; i < ranges.length; i++) {
        if (!ranges[i].empty()) { continue }
        var cur = ranges[i].head, line = getLine(cm.doc, cur.line).text;
        if (line) {
          if (cur.ch == line.length) { cur = new Pos(cur.line, cur.ch - 1); }
          if (cur.ch > 0) {
            cur = new Pos(cur.line, cur.ch + 1);
            cm.replaceRange(line.charAt(cur.ch - 1) + line.charAt(cur.ch - 2),
                            Pos(cur.line, cur.ch - 2), cur, "+transpose");
          } else if (cur.line > cm.doc.first) {
            var prev = getLine(cm.doc, cur.line - 1).text;
            if (prev) {
              cur = new Pos(cur.line, 1);
              cm.replaceRange(line.charAt(0) + cm.doc.lineSeparator() +
                              prev.charAt(prev.length - 1),
                              Pos(cur.line - 1, prev.length - 1), cur, "+transpose");
            }
          }
        }
        newSel.push(new Range(cur, cur));
      }
      cm.setSelections(newSel);
    }); }
```
</details>

### `newlineAndIndent(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`
- `cm.listSelections`
- `cm.replaceRange`
- `cm.doc.lineSeparator`
- `cm.indentLine`
- `sels[i$1].from`
- `ensureCursorVisible`

<details><summary>Code</summary>

```typescript
function (cm) { return runInOp(cm, function () {
      var sels = cm.listSelections();
      for (var i = sels.length - 1; i >= 0; i--)
        { cm.replaceRange(cm.doc.lineSeparator(), sels[i].anchor, sels[i].head, "+input"); }
      sels = cm.listSelections();
      for (var i$1 = 0; i$1 < sels.length; i$1++)
        { cm.indentLine(sels[i$1].from().line, null, true); }
      ensureCursorVisible(cm);
    }); }
```
</details>

### `openLine(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.replaceSelection`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.replaceSelection("\n", "start"); }
```
</details>

### `toggleOverwrite(cm: any): any`

**Parameters:**

- **`cm`** `any`

**Returns:** `any`

**Calls:**

- `cm.toggleOverwrite`

<details><summary>Code</summary>

```typescript
function (cm) { return cm.toggleOverwrite(); }
```
</details>

### `lineStart(cm: any, lineN: any): Pos`

**Parameters:**

- **`cm`** `any`
- **`lineN`** `any`

**Returns:** `Pos`

**Calls:**

- `getLine`
- `visualLine`
- `lineNo`
- `endOfLine`

<details><summary>Code</summary>

```typescript
function lineStart(cm, lineN) {
    var line = getLine(cm.doc, lineN);
    var visual = visualLine(line);
    if (visual != line) { lineN = lineNo(visual); }
    return endOfLine(true, cm, visual, lineN, 1)
  }
```
</details>

### `lineEnd(cm: any, lineN: any): Pos`

**Parameters:**

- **`cm`** `any`
- **`lineN`** `any`

**Returns:** `Pos`

**Calls:**

- `getLine`
- `visualLineEnd`
- `lineNo`
- `endOfLine`

<details><summary>Code</summary>

```typescript
function lineEnd(cm, lineN) {
    var line = getLine(cm.doc, lineN);
    var visual = visualLineEnd(line);
    if (visual != line) { lineN = lineNo(visual); }
    return endOfLine(true, cm, line, lineN, -1)
  }
```
</details>

### `lineStartSmart(cm: any, pos: any): Pos`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`

**Returns:** `Pos`

**Calls:**

- `lineStart`
- `getLine`
- `getOrder`
- `Math.max`
- `line.text.search`
- `Pos`

<details><summary>Code</summary>

```typescript
function lineStartSmart(cm, pos) {
    var start = lineStart(cm, pos.line);
    var line = getLine(cm.doc, start.line);
    var order = getOrder(line, cm.doc.direction);
    if (!order || order[0].level == 0) {
      var firstNonWS = Math.max(start.ch, line.text.search(/\S/));
      var inWS = pos.line == start.line && pos.ch <= firstNonWS && pos.ch;
      return Pos(start.line, inWS ? 0 : firstNonWS, start.sticky)
    }
    return start
  }
```
</details>

### `doHandleBinding(cm: any, bound: any, dropShift: any): boolean`

**Parameters:**

- **`cm`** `any`
- **`bound`** `any`
- **`dropShift`** `any`

**Returns:** `boolean`

**Calls:**

- `cm.display.input.ensurePolled`
- `cm.isReadOnly`
- `bound`

**Internal Comments:**
```
// Ensure previous input has been read, so that the handler sees a (x6)
// consistent view of the document (x6)
```

<details><summary>Code</summary>

```typescript
function doHandleBinding(cm, bound, dropShift) {
    if (typeof bound == "string") {
      bound = commands[bound];
      if (!bound) { return false }
    }
    // Ensure previous input has been read, so that the handler sees a
    // consistent view of the document
    cm.display.input.ensurePolled();
    var prevShift = cm.display.shift, done = false;
    try {
      if (cm.isReadOnly()) { cm.state.suppressEdits = true; }
      if (dropShift) { cm.display.shift = false; }
      done = bound(cm) != Pass;
    } finally {
      cm.display.shift = prevShift;
      cm.state.suppressEdits = false;
    }
    return done
  }
```
</details>

### `lookupKeyForEditor(cm: any, name: any, handle: any): any`

**Parameters:**

- **`cm`** `any`
- **`name`** `any`
- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `lookupKey`

<details><summary>Code</summary>

```typescript
function lookupKeyForEditor(cm, name, handle) {
    for (var i = 0; i < cm.state.keyMaps.length; i++) {
      var result = lookupKey(name, cm.state.keyMaps[i], handle, cm);
      if (result) { return result }
    }
    return (cm.options.extraKeys && lookupKey(name, cm.options.extraKeys, handle, cm))
      || lookupKey(name, cm.options.keyMap, handle, cm)
  }
```
</details>

### `dispatchKey(cm: any, name: any, e: any, handle: any): boolean | "handled"`

**Parameters:**

- **`cm`** `any`
- **`name`** `any`
- **`e`** `any`
- **`handle`** `any`

**Returns:** `boolean | "handled"`

**Calls:**

- `isModifierKey`
- `/\'$/.test`
- `stopSeq.set`
- `cm.display.input.reset`
- `dispatchKeyInner`

<details><summary>Code</summary>

```typescript
function dispatchKey(cm, name, e, handle) {
    var seq = cm.state.keySeq;
    if (seq) {
      if (isModifierKey(name)) { return "handled" }
      if (/\'$/.test(name))
        { cm.state.keySeq = null; }
      else
        { stopSeq.set(50, function () {
          if (cm.state.keySeq == seq) {
            cm.state.keySeq = null;
            cm.display.input.reset();
          }
        }); }
      if (dispatchKeyInner(cm, seq + " " + name, e, handle)) { return true }
    }
    return dispatchKeyInner(cm, name, e, handle)
  }
```
</details>

### `dispatchKeyInner(cm: any, name: any, e: any, handle: any): boolean`

**Parameters:**

- **`cm`** `any`
- **`name`** `any`
- **`e`** `any`
- **`handle`** `any`

**Returns:** `boolean`

**Calls:**

- `lookupKeyForEditor`
- `signalLater`
- `e_preventDefault`
- `restartBlink`

<details><summary>Code</summary>

```typescript
function dispatchKeyInner(cm, name, e, handle) {
    var result = lookupKeyForEditor(cm, name, handle);

    if (result == "multi")
      { cm.state.keySeq = name; }
    if (result == "handled")
      { signalLater(cm, "keyHandled", cm, name, e); }

    if (result == "handled" || result == "multi") {
      e_preventDefault(e);
      restartBlink(cm);
    }

    return !!result
  }
```
</details>

### `handleKeyBinding(cm: any, e: any): boolean | "handled"`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `boolean | "handled"`

**Calls:**

- `keyName`
- `dispatchKey`
- `doHandleBinding`
- `/^go[A-Z]/.test`

**Internal Comments:**
```
// First try to resolve full name (including 'Shift-'). Failing
// that, see if there is a cursor-motion command (starting with
// 'go') bound to the keyname without 'Shift-'.
```

<details><summary>Code</summary>

```typescript
function handleKeyBinding(cm, e) {
    var name = keyName(e, true);
    if (!name) { return false }

    if (e.shiftKey && !cm.state.keySeq) {
      // First try to resolve full name (including 'Shift-'). Failing
      // that, see if there is a cursor-motion command (starting with
      // 'go') bound to the keyname without 'Shift-'.
      return dispatchKey(cm, "Shift-" + name, e, function (b) { return doHandleBinding(cm, b, true); })
          || dispatchKey(cm, name, e, function (b) {
               if (typeof b == "string" ? /^go[A-Z]/.test(b) : b.motion)
                 { return doHandleBinding(cm, b) }
             })
    } else {
      return dispatchKey(cm, name, e, function (b) { return doHandleBinding(cm, b); })
    }
  }
```
</details>

### `handleCharBinding(cm: any, e: any, ch: any): boolean | "handled"`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`
- **`ch`** `any`

**Returns:** `boolean | "handled"`

**Calls:**

- `dispatchKey`
- `doHandleBinding`

<details><summary>Code</summary>

```typescript
function handleCharBinding(cm, e, ch) {
    return dispatchKey(cm, "'" + ch + "'", e, function (b) { return doHandleBinding(cm, b, true); })
  }
```
</details>

### `onKeyDown(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `cm.display.input.getField`
- `activeElt`
- `signalDOMEvent`
- `handleKeyBinding`
- `cm.replaceSelection`
- `document.execCommand`
- `/\bCodeMirror-crosshair\b/.test`
- `showCrossHair`

**Internal Comments:**
```
// IE does strange things with escape.
// Opera has no cut event... we try to at least catch the key combo
// Turn mouse into crosshair when Alt is held on Mac.
```

<details><summary>Code</summary>

```typescript
function onKeyDown(e) {
    var cm = this;
    if (e.target && e.target != cm.display.input.getField()) { return }
    cm.curOp.focus = activeElt();
    if (signalDOMEvent(cm, e)) { return }
    // IE does strange things with escape.
    if (ie && ie_version < 11 && e.keyCode == 27) { e.returnValue = false; }
    var code = e.keyCode;
    cm.display.shift = code == 16 || e.shiftKey;
    var handled = handleKeyBinding(cm, e);
    if (presto) {
      lastStoppedKey = handled ? code : null;
      // Opera has no cut event... we try to at least catch the key combo
      if (!handled && code == 88 && !hasCopyEvent && (mac ? e.metaKey : e.ctrlKey))
        { cm.replaceSelection("", null, "cut"); }
    }
    if (gecko && !mac && !handled && code == 46 && e.shiftKey && !e.ctrlKey && document.execCommand)
      { document.execCommand("cut"); }

    // Turn mouse into crosshair when Alt is held on Mac.
    if (code == 18 && !/\bCodeMirror-crosshair\b/.test(cm.display.lineDiv.className))
      { showCrossHair(cm); }
  }
```
</details>

### `showCrossHair(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `addClass`
- `rmClass`
- `off`
- `on`

<details><summary>Code</summary>

```typescript
function showCrossHair(cm) {
    var lineDiv = cm.display.lineDiv;
    addClass(lineDiv, "CodeMirror-crosshair");

    function up(e) {
      if (e.keyCode == 18 || !e.altKey) {
        rmClass(lineDiv, "CodeMirror-crosshair");
        off(document, "keyup", up);
        off(document, "mouseover", up);
      }
    }
    on(document, "keyup", up);
    on(document, "mouseover", up);
  }
```
</details>

### `up(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `rmClass`
- `off`

<details><summary>Code</summary>

```typescript
function up(e) {
      if (e.keyCode == 18 || !e.altKey) {
        rmClass(lineDiv, "CodeMirror-crosshair");
        off(document, "keyup", up);
        off(document, "mouseover", up);
      }
    }
```
</details>

### `onKeyUp(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`

<details><summary>Code</summary>

```typescript
function onKeyUp(e) {
    if (e.keyCode == 16) { this.doc.sel.shift = false; }
    signalDOMEvent(this, e);
  }
```
</details>

### `onKeyPress(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `cm.display.input.getField`
- `eventInWidget`
- `signalDOMEvent`
- `e_preventDefault`
- `handleKeyBinding`
- `String.fromCharCode`
- `handleCharBinding`
- `cm.display.input.onKeyPress`

**Internal Comments:**
```
// Some browsers fire keypress events for backspace
```

<details><summary>Code</summary>

```typescript
function onKeyPress(e) {
    var cm = this;
    if (e.target && e.target != cm.display.input.getField()) { return }
    if (eventInWidget(cm.display, e) || signalDOMEvent(cm, e) || e.ctrlKey && !e.altKey || mac && e.metaKey) { return }
    var keyCode = e.keyCode, charCode = e.charCode;
    if (presto && keyCode == lastStoppedKey) {lastStoppedKey = null; e_preventDefault(e); return}
    if ((presto && (!e.which || e.which < 10)) && handleKeyBinding(cm, e)) { return }
    var ch = String.fromCharCode(charCode == null ? keyCode : charCode);
    // Some browsers fire keypress events for backspace
    if (ch == "\x08") { return }
    if (handleCharBinding(cm, e, ch)) { return }
    cm.display.input.onKeyPress(e);
  }
```
</details>

### `PastClick(time: any, pos: any, button: any): void`

**Parameters:**

- **`time`** `any`
- **`pos`** `any`
- **`button`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(time, pos, button) {
    this.time = time;
    this.pos = pos;
    this.button = button;
  }
```
</details>

### `clickRepeat(pos: any, button: any): "triple" | "double" | "single"`

**Parameters:**

- **`pos`** `any`
- **`button`** `any`

**Returns:** `"triple" | "double" | "single"`

**Calls:**

- `lastDoubleClick.compare`
- `lastClick.compare`

<details><summary>Code</summary>

```typescript
function clickRepeat(pos, button) {
    var now = +new Date;
    if (lastDoubleClick && lastDoubleClick.compare(now, pos, button)) {
      lastClick = lastDoubleClick = null;
      return "triple"
    } else if (lastClick && lastClick.compare(now, pos, button)) {
      lastDoubleClick = new PastClick(now, pos, button);
      lastClick = null;
      return "double"
    } else {
      lastClick = new PastClick(now, pos, button);
      lastDoubleClick = null;
      return "single"
    }
  }
```
</details>

### `onMouseDown(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `display.input.supportsTouch`
- `display.input.ensurePolled`
- `eventInWidget`
- `setTimeout`
- `clickInGutter`
- `posFromMouse`
- `e_button`
- `clickRepeat`
- `window.focus`
- `cm.state.selectingText`
- `handleMappedButton`
- `leftButtonDown`
- `e_target`
- `e_preventDefault`
- `extendSelection`
- `display.input.focus`
- `cm.display.input.onContextMenu`
- `delayBlurEvent`

**Internal Comments:**
```
// Briefly turn off draggability, to allow widgets to do (x5)
// normal dragging things. (x5)
// #3261: make sure, that we're not starting a second selection
```

<details><summary>Code</summary>

```typescript
function onMouseDown(e) {
    var cm = this, display = cm.display;
    if (signalDOMEvent(cm, e) || display.activeTouch && display.input.supportsTouch()) { return }
    display.input.ensurePolled();
    display.shift = e.shiftKey;

    if (eventInWidget(display, e)) {
      if (!webkit) {
        // Briefly turn off draggability, to allow widgets to do
        // normal dragging things.
        display.scroller.draggable = false;
        setTimeout(function () { return display.scroller.draggable = true; }, 100);
      }
      return
    }
    if (clickInGutter(cm, e)) { return }
    var pos = posFromMouse(cm, e), button = e_button(e), repeat = pos ? clickRepeat(pos, button) : "single";
    window.focus();

    // #3261: make sure, that we're not starting a second selection
    if (button == 1 && cm.state.selectingText)
      { cm.state.selectingText(e); }

    if (pos && handleMappedButton(cm, button, pos, repeat, e)) { return }

    if (button == 1) {
      if (pos) { leftButtonDown(cm, pos, repeat, e); }
      else if (e_target(e) == display.scroller) { e_preventDefault(e); }
    } else if (button == 2) {
      if (pos) { extendSelection(cm.doc, pos); }
      setTimeout(function () { return display.input.focus(); }, 20);
    } else if (button == 3) {
      if (captureRightClick) { cm.display.input.onContextMenu(e); }
      else { delayBlurEvent(cm); }
    }
  }
```
</details>

### `handleMappedButton(cm: any, button: any, pos: any, repeat: any, event: any): boolean | "handled"`

**Parameters:**

- **`cm`** `any`
- **`button`** `any`
- **`pos`** `any`
- **`repeat`** `any`
- **`event`** `any`

**Returns:** `boolean | "handled"`

**Calls:**

- `dispatchKey`
- `addModifierNames`
- `cm.isReadOnly`
- `bound`

<details><summary>Code</summary>

```typescript
function handleMappedButton(cm, button, pos, repeat, event) {
    var name = "Click";
    if (repeat == "double") { name = "Double" + name; }
    else if (repeat == "triple") { name = "Triple" + name; }
    name = (button == 1 ? "Left" : button == 2 ? "Middle" : "Right") + name;

    return dispatchKey(cm,  addModifierNames(name, event), event, function (bound) {
      if (typeof bound == "string") { bound = commands[bound]; }
      if (!bound) { return false }
      var done = false;
      try {
        if (cm.isReadOnly()) { cm.state.suppressEdits = true; }
        done = bound(cm, pos) != Pass;
      } finally {
        cm.state.suppressEdits = false;
      }
      return done
    })
  }
```
</details>

### `configureMouse(cm: any, repeat: any, event: any): any`

**Parameters:**

- **`cm`** `any`
- **`repeat`** `any`
- **`event`** `any`

**Returns:** `any`

**Calls:**

- `cm.getOption`
- `option`

<details><summary>Code</summary>

```typescript
function configureMouse(cm, repeat, event) {
    var option = cm.getOption("configureMouse");
    var value = option ? option(cm, repeat, event) : {};
    if (value.unit == null) {
      var rect = chromeOS ? event.shiftKey && event.metaKey : event.altKey;
      value.unit = rect ? "rectangle" : repeat == "single" ? "char" : repeat == "double" ? "word" : "line";
    }
    if (value.extend == null || cm.doc.extend) { value.extend = cm.doc.extend || event.shiftKey; }
    if (value.addNew == null) { value.addNew = mac ? event.metaKey : event.ctrlKey; }
    if (value.moveOnDrag == null) { value.moveOnDrag = !(mac ? event.altKey : event.ctrlKey); }
    return value
  }
```
</details>

### `leftButtonDown(cm: any, pos: any, repeat: any, event: any): void`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`repeat`** `any`
- **`event`** `any`

**Returns:** `void`

**Calls:**

- `setTimeout`
- `bind`
- `activeElt`
- `configureMouse`
- `cm.isReadOnly`
- `sel.contains`
- `cmp`
- `(contained = sel.ranges[contained]).from`
- `contained.to`
- `leftButtonStartDrag`
- `leftButtonSelect`

<details><summary>Code</summary>

```typescript
function leftButtonDown(cm, pos, repeat, event) {
    if (ie) { setTimeout(bind(ensureFocus, cm), 0); }
    else { cm.curOp.focus = activeElt(); }

    var behavior = configureMouse(cm, repeat, event);

    var sel = cm.doc.sel, contained;
    if (cm.options.dragDrop && dragAndDrop && !cm.isReadOnly() &&
        repeat == "single" && (contained = sel.contains(pos)) > -1 &&
        (cmp((contained = sel.ranges[contained]).from(), pos) < 0 || pos.xRel > 0) &&
        (cmp(contained.to(), pos) > 0 || pos.xRel < 0))
      { leftButtonStartDrag(cm, event, pos, behavior); }
    else
      { leftButtonSelect(cm, event, pos, behavior); }
  }
```
</details>

### `leftButtonStartDrag(cm: any, event: any, pos: any, behavior: any): void`

**Parameters:**

- **`cm`** `any`
- **`event`** `any`
- **`pos`** `any`
- **`behavior`** `any`

**Returns:** `void`

**Calls:**

- `operation`
- `cm.hasFocus`
- `delayBlurEvent`
- `off`
- `e_preventDefault`
- `extendSelection`
- `setTimeout`
- `display.wrapper.ownerDocument.body.focus`
- `display.input.focus`
- `Math.abs`
- `on`
- `display.scroller.dragDrop`

**Internal Comments:**
```
// Work around unexplainable focus problem in IE9 (#2127) and Chrome (#3081)
// Let the drag handler handle this.
// IE's approach to draggable
```

<details><summary>Code</summary>

```typescript
function leftButtonStartDrag(cm, event, pos, behavior) {
    var display = cm.display, moved = false;
    var dragEnd = operation(cm, function (e) {
      if (webkit) { display.scroller.draggable = false; }
      cm.state.draggingText = false;
      if (cm.state.delayingBlurEvent) {
        if (cm.hasFocus()) { cm.state.delayingBlurEvent = false; }
        else { delayBlurEvent(cm); }
      }
      off(display.wrapper.ownerDocument, "mouseup", dragEnd);
      off(display.wrapper.ownerDocument, "mousemove", mouseMove);
      off(display.scroller, "dragstart", dragStart);
      off(display.scroller, "drop", dragEnd);
      if (!moved) {
        e_preventDefault(e);
        if (!behavior.addNew)
          { extendSelection(cm.doc, pos, null, null, behavior.extend); }
        // Work around unexplainable focus problem in IE9 (#2127) and Chrome (#3081)
        if ((webkit && !safari) || ie && ie_version == 9)
          { setTimeout(function () {display.wrapper.ownerDocument.body.focus({preventScroll: true}); display.input.focus();}, 20); }
        else
          { display.input.focus(); }
      }
    });
    var mouseMove = function(e2) {
      moved = moved || Math.abs(event.clientX - e2.clientX) + Math.abs(event.clientY - e2.clientY) >= 10;
    };
    var dragStart = function () { return moved = true; };
    // Let the drag handler handle this.
    if (webkit) { display.scroller.draggable = true; }
    cm.state.draggingText = dragEnd;
    dragEnd.copy = !behavior.moveOnDrag;
    on(display.wrapper.ownerDocument, "mouseup", dragEnd);
    on(display.wrapper.ownerDocument, "mousemove", mouseMove);
    on(display.scroller, "dragstart", dragStart);
    on(display.scroller, "drop", dragEnd);

    cm.state.delayingBlurEvent = true;
    setTimeout(function () { return display.input.focus(); }, 20);
    // IE's approach to draggable
    if (display.scroller.dragDrop) { display.scroller.dragDrop(); }
  }
```
</details>

### `mouseMove(e2: any): void`

**Parameters:**

- **`e2`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function(e2) {
      moved = moved || Math.abs(event.clientX - e2.clientX) + Math.abs(event.clientY - e2.clientY) >= 10;
    }
```
</details>

### `dragStart(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () { return moved = true; }
```
</details>

### `rangeForUnit(cm: any, pos: any, unit: any): any`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`unit`** `any`

**Returns:** `any`

**Calls:**

- `cm.findWordAt`
- `Pos`
- `clipPos`
- `unit`

<details><summary>Code</summary>

```typescript
function rangeForUnit(cm, pos, unit) {
    if (unit == "char") { return new Range(pos, pos) }
    if (unit == "word") { return cm.findWordAt(pos) }
    if (unit == "line") { return new Range(Pos(pos.line, 0), clipPos(cm.doc, Pos(pos.line + 1, 0))) }
    var result = unit(cm, pos);
    return new Range(result.from, result.to)
  }
```
</details>

### `leftButtonSelect(cm: any, event: any, start: any, behavior: any): void`

**Parameters:**

- **`cm`** `any`
- **`event`** `any`
- **`start`** `any`
- **`behavior`** `any`

**Returns:** `void`

**Calls:**

- `delayBlurEvent`
- `e_preventDefault`
- `doc.sel.contains`
- `doc.sel.primary`
- `posFromMouse`
- `rangeForUnit`
- `extendRange`
- `setSelection`
- `normalizeSelection`
- `ranges.concat`
- `ranges[ourIndex].empty`
- `ranges.slice(0, ourIndex).concat`
- `ranges.slice`
- `replaceOneSelection`
- `cmp`
- `countColumn`
- `getLine`
- `Math.min`
- `Math.max`
- `cm.lastLine`
- `findColumn`
- `ranges.push`
- `Pos`
- `startSel.ranges.slice(0, ourIndex).concat`
- `cm.scrollIntoView`
- `minPos`
- `oldRange.from`
- `maxPos`
- `oldRange.to`
- `startSel.ranges.slice`
- `bidiSimplify`
- `clipPos`
- `display.wrapper.getBoundingClientRect`
- `activeElt`
- `extendTo`
- `visibleLines`
- `setTimeout`
- `operation`
- `extend`
- `display.input.focus`
- `off`
- `e_button`
- `done`
- `on`

**Internal Comments:**
```
// Used to ensure timeout re-tries don't fire when another extend (x2)
// happened in the meantime (clearTimeout isn't reliable -- at (x2)
// least on Chrome, the timeouts still happen even when cleared, (x2)
// if the clear happens after their scheduled firing time). (x2)
// If e is null or undefined we interpret this as someone trying
// to explicitly cancel the selection rather than the user
// letting go of the mouse button.
```

<details><summary>Code</summary>

```typescript
function leftButtonSelect(cm, event, start, behavior) {
    if (ie) { delayBlurEvent(cm); }
    var display = cm.display, doc = cm.doc;
    e_preventDefault(event);

    var ourRange, ourIndex, startSel = doc.sel, ranges = startSel.ranges;
    if (behavior.addNew && !behavior.extend) {
      ourIndex = doc.sel.contains(start);
      if (ourIndex > -1)
        { ourRange = ranges[ourIndex]; }
      else
        { ourRange = new Range(start, start); }
    } else {
      ourRange = doc.sel.primary();
      ourIndex = doc.sel.primIndex;
    }

    if (behavior.unit == "rectangle") {
      if (!behavior.addNew) { ourRange = new Range(start, start); }
      start = posFromMouse(cm, event, true, true);
      ourIndex = -1;
    } else {
      var range = rangeForUnit(cm, start, behavior.unit);
      if (behavior.extend)
        { ourRange = extendRange(ourRange, range.anchor, range.head, behavior.extend); }
      else
        { ourRange = range; }
    }

    if (!behavior.addNew) {
      ourIndex = 0;
      setSelection(doc, new Selection([ourRange], 0), sel_mouse);
      startSel = doc.sel;
    } else if (ourIndex == -1) {
      ourIndex = ranges.length;
      setSelection(doc, normalizeSelection(cm, ranges.concat([ourRange]), ourIndex),
                   {scroll: false, origin: "*mouse"});
    } else if (ranges.length > 1 && ranges[ourIndex].empty() && behavior.unit == "char" && !behavior.extend) {
      setSelection(doc, normalizeSelection(cm, ranges.slice(0, ourIndex).concat(ranges.slice(ourIndex + 1)), 0),
                   {scroll: false, origin: "*mouse"});
      startSel = doc.sel;
    } else {
      replaceOneSelection(doc, ourIndex, ourRange, sel_mouse);
    }

    var lastPos = start;
    function extendTo(pos) {
      if (cmp(lastPos, pos) == 0) { return }
      lastPos = pos;

      if (behavior.unit == "rectangle") {
        var ranges = [], tabSize = cm.options.tabSize;
        var startCol = countColumn(getLine(doc, start.line).text, start.ch, tabSize);
        var posCol = countColumn(getLine(doc, pos.line).text, pos.ch, tabSize);
        var left = Math.min(startCol, posCol), right = Math.max(startCol, posCol);
        for (var line = Math.min(start.line, pos.line), end = Math.min(cm.lastLine(), Math.max(start.line, pos.line));
             line <= end; line++) {
          var text = getLine(doc, line).text, leftPos = findColumn(text, left, tabSize);
          if (left == right)
            { ranges.push(new Range(Pos(line, leftPos), Pos(line, leftPos))); }
          else if (text.length > leftPos)
            { ranges.push(new Range(Pos(line, leftPos), Pos(line, findColumn(text, right, tabSize)))); }
        }
        if (!ranges.length) { ranges.push(new Range(start, start)); }
        setSelection(doc, normalizeSelection(cm, startSel.ranges.slice(0, ourIndex).concat(ranges), ourIndex),
                     {origin: "*mouse", scroll: false});
        cm.scrollIntoView(pos);
      } else {
        var oldRange = ourRange;
        var range = rangeForUnit(cm, pos, behavior.unit);
        var anchor = oldRange.anchor, head;
        if (cmp(range.anchor, anchor) > 0) {
          head = range.head;
          anchor = minPos(oldRange.from(), range.anchor);
        } else {
          head = range.anchor;
          anchor = maxPos(oldRange.to(), range.head);
        }
        var ranges$1 = startSel.ranges.slice(0);
        ranges$1[ourIndex] = bidiSimplify(cm, new Range(clipPos(doc, anchor), head));
        setSelection(doc, normalizeSelection(cm, ranges$1, ourIndex), sel_mouse);
      }
    }

    var editorSize = display.wrapper.getBoundingClientRect();
    // Used to ensure timeout re-tries don't fire when another extend
    // happened in the meantime (clearTimeout isn't reliable -- at
    // least on Chrome, the timeouts still happen even when cleared,
    // if the clear happens after their scheduled firing time).
    var counter = 0;

    function extend(e) {
      var curCount = ++counter;
      var cur = posFromMouse(cm, e, true, behavior.unit == "rectangle");
      if (!cur) { return }
      if (cmp(cur, lastPos) != 0) {
        cm.curOp.focus = activeElt();
        extendTo(cur);
        var visible = visibleLines(display, doc);
        if (cur.line >= visible.to || cur.line < visible.from)
          { setTimeout(operation(cm, function () {if (counter == curCount) { extend(e); }}), 150); }
      } else {
        var outside = e.clientY < editorSize.top ? -20 : e.clientY > editorSize.bottom ? 20 : 0;
        if (outside) { setTimeout(operation(cm, function () {
          if (counter != curCount) { return }
          display.scroller.scrollTop += outside;
          extend(e);
        }), 50); }
      }
    }

    function done(e) {
      cm.state.selectingText = false;
      counter = Infinity;
      // If e is null or undefined we interpret this as someone trying
      // to explicitly cancel the selection rather than the user
      // letting go of the mouse button.
      if (e) {
        e_preventDefault(e);
        display.input.focus();
      }
      off(display.wrapper.ownerDocument, "mousemove", move);
      off(display.wrapper.ownerDocument, "mouseup", up);
      doc.history.lastSelOrigin = null;
    }

    var move = operation(cm, function (e) {
      if (e.buttons === 0 || !e_button(e)) { done(e); }
      else { extend(e); }
    });
    var up = operation(cm, done);
    cm.state.selectingText = up;
    on(display.wrapper.ownerDocument, "mousemove", move);
    on(display.wrapper.ownerDocument, "mouseup", up);
  }
```
</details>

### `extendTo(pos: any): void`

**Parameters:**

- **`pos`** `any`

**Returns:** `void`

**Calls:**

- `cmp`
- `countColumn`
- `getLine`
- `Math.min`
- `Math.max`
- `cm.lastLine`
- `findColumn`
- `ranges.push`
- `Pos`
- `setSelection`
- `normalizeSelection`
- `startSel.ranges.slice(0, ourIndex).concat`
- `cm.scrollIntoView`
- `rangeForUnit`
- `minPos`
- `oldRange.from`
- `maxPos`
- `oldRange.to`
- `startSel.ranges.slice`
- `bidiSimplify`
- `clipPos`

<details><summary>Code</summary>

```typescript
function extendTo(pos) {
      if (cmp(lastPos, pos) == 0) { return }
      lastPos = pos;

      if (behavior.unit == "rectangle") {
        var ranges = [], tabSize = cm.options.tabSize;
        var startCol = countColumn(getLine(doc, start.line).text, start.ch, tabSize);
        var posCol = countColumn(getLine(doc, pos.line).text, pos.ch, tabSize);
        var left = Math.min(startCol, posCol), right = Math.max(startCol, posCol);
        for (var line = Math.min(start.line, pos.line), end = Math.min(cm.lastLine(), Math.max(start.line, pos.line));
             line <= end; line++) {
          var text = getLine(doc, line).text, leftPos = findColumn(text, left, tabSize);
          if (left == right)
            { ranges.push(new Range(Pos(line, leftPos), Pos(line, leftPos))); }
          else if (text.length > leftPos)
            { ranges.push(new Range(Pos(line, leftPos), Pos(line, findColumn(text, right, tabSize)))); }
        }
        if (!ranges.length) { ranges.push(new Range(start, start)); }
        setSelection(doc, normalizeSelection(cm, startSel.ranges.slice(0, ourIndex).concat(ranges), ourIndex),
                     {origin: "*mouse", scroll: false});
        cm.scrollIntoView(pos);
      } else {
        var oldRange = ourRange;
        var range = rangeForUnit(cm, pos, behavior.unit);
        var anchor = oldRange.anchor, head;
        if (cmp(range.anchor, anchor) > 0) {
          head = range.head;
          anchor = minPos(oldRange.from(), range.anchor);
        } else {
          head = range.anchor;
          anchor = maxPos(oldRange.to(), range.head);
        }
        var ranges$1 = startSel.ranges.slice(0);
        ranges$1[ourIndex] = bidiSimplify(cm, new Range(clipPos(doc, anchor), head));
        setSelection(doc, normalizeSelection(cm, ranges$1, ourIndex), sel_mouse);
      }
    }
```
</details>

### `extend(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `posFromMouse`
- `cmp`
- `activeElt`
- `extendTo`
- `visibleLines`
- `setTimeout`
- `operation`
- `extend`

<details><summary>Code</summary>

```typescript
function extend(e) {
      var curCount = ++counter;
      var cur = posFromMouse(cm, e, true, behavior.unit == "rectangle");
      if (!cur) { return }
      if (cmp(cur, lastPos) != 0) {
        cm.curOp.focus = activeElt();
        extendTo(cur);
        var visible = visibleLines(display, doc);
        if (cur.line >= visible.to || cur.line < visible.from)
          { setTimeout(operation(cm, function () {if (counter == curCount) { extend(e); }}), 150); }
      } else {
        var outside = e.clientY < editorSize.top ? -20 : e.clientY > editorSize.bottom ? 20 : 0;
        if (outside) { setTimeout(operation(cm, function () {
          if (counter != curCount) { return }
          display.scroller.scrollTop += outside;
          extend(e);
        }), 50); }
      }
    }
```
</details>

### `done(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e_preventDefault`
- `display.input.focus`
- `off`

**Internal Comments:**
```
// If e is null or undefined we interpret this as someone trying
// to explicitly cancel the selection rather than the user
// letting go of the mouse button.
```

<details><summary>Code</summary>

```typescript
function done(e) {
      cm.state.selectingText = false;
      counter = Infinity;
      // If e is null or undefined we interpret this as someone trying
      // to explicitly cancel the selection rather than the user
      // letting go of the mouse button.
      if (e) {
        e_preventDefault(e);
        display.input.focus();
      }
      off(display.wrapper.ownerDocument, "mousemove", move);
      off(display.wrapper.ownerDocument, "mouseup", up);
      doc.history.lastSelOrigin = null;
    }
```
</details>

### `bidiSimplify(cm: any, range: any): any`

**Parameters:**

- **`cm`** `any`
- **`range`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `cmp`
- `getOrder`
- `getBidiPartAt`

**Internal Comments:**
```
// Compute the relative visual position of the head compared to the (x2)
// anchor (<0 is to the left, >0 to the right) (x2)
```

<details><summary>Code</summary>

```typescript
function bidiSimplify(cm, range) {
    var anchor = range.anchor;
    var head = range.head;
    var anchorLine = getLine(cm.doc, anchor.line);
    if (cmp(anchor, head) == 0 && anchor.sticky == head.sticky) { return range }
    var order = getOrder(anchorLine);
    if (!order) { return range }
    var index = getBidiPartAt(order, anchor.ch, anchor.sticky), part = order[index];
    if (part.from != anchor.ch && part.to != anchor.ch) { return range }
    var boundary = index + ((part.from == anchor.ch) == (part.level != 1) ? 0 : 1);
    if (boundary == 0 || boundary == order.length) { return range }

    // Compute the relative visual position of the head compared to the
    // anchor (<0 is to the left, >0 to the right)
    var leftSide;
    if (head.line != anchor.line) {
      leftSide = (head.line - anchor.line) * (cm.doc.direction == "ltr" ? 1 : -1) > 0;
    } else {
      var headIndex = getBidiPartAt(order, head.ch, head.sticky);
      var dir = headIndex - index || (head.ch - anchor.ch) * (part.level == 1 ? -1 : 1);
      if (headIndex == boundary - 1 || headIndex == boundary)
        { leftSide = dir < 0; }
      else
        { leftSide = dir > 0; }
    }

    var usePart = order[boundary + (leftSide ? -1 : 0)];
    var from = leftSide == (usePart.level == 1);
    var ch = from ? usePart.from : usePart.to, sticky = from ? "after" : "before";
    return anchor.ch == ch && anchor.sticky == sticky ? range : new Range(new Pos(anchor.line, ch, sticky), head)
  }
```
</details>

### `gutterEvent(cm: any, e: any, type: any, prevent: any): any`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`
- **`type`** `any`
- **`prevent`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `cm.display.gutters.getBoundingClientRect`
- `e_preventDefault`
- `display.lineDiv.getBoundingClientRect`
- `hasHandler`
- `e_defaultPrevented`
- `g.getBoundingClientRect`
- `lineAtHeight`
- `signal`

<details><summary>Code</summary>

```typescript
function gutterEvent(cm, e, type, prevent) {
    var mX, mY;
    if (e.touches) {
      mX = e.touches[0].clientX;
      mY = e.touches[0].clientY;
    } else {
      try { mX = e.clientX; mY = e.clientY; }
      catch(e$1) { return false }
    }
    if (mX >= Math.floor(cm.display.gutters.getBoundingClientRect().right)) { return false }
    if (prevent) { e_preventDefault(e); }

    var display = cm.display;
    var lineBox = display.lineDiv.getBoundingClientRect();

    if (mY > lineBox.bottom || !hasHandler(cm, type)) { return e_defaultPrevented(e) }
    mY -= lineBox.top - display.viewOffset;

    for (var i = 0; i < cm.display.gutterSpecs.length; ++i) {
      var g = display.gutters.childNodes[i];
      if (g && g.getBoundingClientRect().right >= mX) {
        var line = lineAtHeight(cm.doc, mY);
        var gutter = cm.display.gutterSpecs[i];
        signal(cm, type, cm, line, gutter.className, e);
        return e_defaultPrevented(e)
      }
    }
  }
```
</details>

### `clickInGutter(cm: any, e: any): any`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `any`

**Calls:**

- `gutterEvent`

<details><summary>Code</summary>

```typescript
function clickInGutter(cm, e) {
    return gutterEvent(cm, e, "gutterClick", true)
  }
```
</details>

### `onContextMenu(cm: any, e: any): void`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `void`

**Calls:**

- `eventInWidget`
- `contextMenuInGutter`
- `signalDOMEvent`
- `cm.display.input.onContextMenu`

<details><summary>Code</summary>

```typescript
function onContextMenu(cm, e) {
    if (eventInWidget(cm.display, e) || contextMenuInGutter(cm, e)) { return }
    if (signalDOMEvent(cm, e, "contextmenu")) { return }
    if (!captureRightClick) { cm.display.input.onContextMenu(e); }
  }
```
</details>

### `contextMenuInGutter(cm: any, e: any): any`

**Parameters:**

- **`cm`** `any`
- **`e`** `any`

**Returns:** `any`

**Calls:**

- `hasHandler`
- `gutterEvent`

<details><summary>Code</summary>

```typescript
function contextMenuInGutter(cm, e) {
    if (!hasHandler(cm, "gutterContextMenu")) { return false }
    return gutterEvent(cm, e, "gutterContextMenu", false)
  }
```
</details>

### `themeChanged(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.display.wrapper.className.replace`
- `cm.options.theme.replace`
- `clearCaches`

<details><summary>Code</summary>

```typescript
function themeChanged(cm) {
    cm.display.wrapper.className = cm.display.wrapper.className.replace(/\s*cm-s-\S+/g, "") +
      cm.options.theme.replace(/(^|\s)\s*/g, " cm-s-");
    clearCaches(cm);
  }
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Init"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Init"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Init"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Init"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Init"}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function(){return "CodeMirror.Init"}
```
</details>

### `defineOptions(CodeMirror: any): void`

**Parameters:**

- **`CodeMirror`** `any`

**Returns:** `void`

**Calls:**

- `handle`
- `option`
- `cm.setValue`
- `loadMode`
- `resetModeState`
- `clearCaches`
- `regChange`
- `cm.doc.iter`
- `line.text.indexOf`
- `newBreaks.push`
- `Pos`
- `replaceRange`
- `val.test`
- `cm.refresh`
- `cm.getInputField`
- `themeChanged`
- `updateGutters`
- `getKeyMap`
- `prev.detach`
- `next.attach`
- `getGutters`
- `compensateForHScroll`
- `updateScrollbars`
- `initScrollbars`
- `cm.display.scrollbars.setScrollTop`
- `cm.display.scrollbars.setScrollLeft`
- `onBlur`
- `cm.display.input.blur`
- `cm.display.input.readOnlyChanged`
- `cm.display.input.screenReaderLabelChanged`
- `cm.display.input.reset`
- `cm.display.input.resetPosition`
- `cm.display.input.getField`
- `cm.doc.setDirection`

**Internal Comments:**
```
// Passed to option handlers when there is no old value. (x4)
// These two are, on init, called from the constructor because they (x3)
// have to be initialized before the editor can start at all. (x3)
```

<details><summary>Code</summary>

```typescript
function defineOptions(CodeMirror) {
    var optionHandlers = CodeMirror.optionHandlers;

    function option(name, deflt, handle, notOnInit) {
      CodeMirror.defaults[name] = deflt;
      if (handle) { optionHandlers[name] =
        notOnInit ? function (cm, val, old) {if (old != Init) { handle(cm, val, old); }} : handle; }
    }

    CodeMirror.defineOption = option;

    // Passed to option handlers when there is no old value.
    CodeMirror.Init = Init;

    // These two are, on init, called from the constructor because they
    // have to be initialized before the editor can start at all.
    option("value", "", function (cm, val) { return cm.setValue(val); }, true);
    option("mode", null, function (cm, val) {
      cm.doc.modeOption = val;
      loadMode(cm);
    }, true);

    option("indentUnit", 2, loadMode, true);
    option("indentWithTabs", false);
    option("smartIndent", true);
    option("tabSize", 4, function (cm) {
      resetModeState(cm);
      clearCaches(cm);
      regChange(cm);
    }, true);

    option("lineSeparator", null, function (cm, val) {
      cm.doc.lineSep = val;
      if (!val) { return }
      var newBreaks = [], lineNo = cm.doc.first;
      cm.doc.iter(function (line) {
        for (var pos = 0;;) {
          var found = line.text.indexOf(val, pos);
          if (found == -1) { break }
          pos = found + val.length;
          newBreaks.push(Pos(lineNo, found));
        }
        lineNo++;
      });
      for (var i = newBreaks.length - 1; i >= 0; i--)
        { replaceRange(cm.doc, val, newBreaks[i], Pos(newBreaks[i].line, newBreaks[i].ch + val.length)); }
    });
    option("specialChars", /[\u0000-\u001f\u007f-\u009f\u00ad\u061c\u200b\u200e\u200f\u2028\u2029\ufeff\ufff9-\ufffc]/g, function (cm, val, old) {
      cm.state.specialChars = new RegExp(val.source + (val.test("\t") ? "" : "|\t"), "g");
      if (old != Init) { cm.refresh(); }
    });
    option("specialCharPlaceholder", defaultSpecialCharPlaceholder, function (cm) { return cm.refresh(); }, true);
    option("electricChars", true);
    option("inputStyle", mobile ? "contenteditable" : "textarea", function () {
      throw new Error("inputStyle can not (yet) be changed in a running editor") // FIXME
    }, true);
    option("spellcheck", false, function (cm, val) { return cm.getInputField().spellcheck = val; }, true);
    option("autocorrect", false, function (cm, val) { return cm.getInputField().autocorrect = val; }, true);
    option("autocapitalize", false, function (cm, val) { return cm.getInputField().autocapitalize = val; }, true);
    option("rtlMoveVisually", !windows);
    option("wholeLineUpdateBefore", true);

    option("theme", "default", function (cm) {
      themeChanged(cm);
      updateGutters(cm);
    }, true);
    option("keyMap", "default", function (cm, val, old) {
      var next = getKeyMap(val);
      var prev = old != Init && getKeyMap(old);
      if (prev && prev.detach) { prev.detach(cm, next); }
      if (next.attach) { next.attach(cm, prev || null); }
    });
    option("extraKeys", null);
    option("configureMouse", null);

    option("lineWrapping", false, wrappingChanged, true);
    option("gutters", [], function (cm, val) {
      cm.display.gutterSpecs = getGutters(val, cm.options.lineNumbers);
      updateGutters(cm);
    }, true);
    option("fixedGutter", true, function (cm, val) {
      cm.display.gutters.style.left = val ? compensateForHScroll(cm.display) + "px" : "0";
      cm.refresh();
    }, true);
    option("coverGutterNextToScrollbar", false, function (cm) { return updateScrollbars(cm); }, true);
    option("scrollbarStyle", "native", function (cm) {
      initScrollbars(cm);
      updateScrollbars(cm);
      cm.display.scrollbars.setScrollTop(cm.doc.scrollTop);
      cm.display.scrollbars.setScrollLeft(cm.doc.scrollLeft);
    }, true);
    option("lineNumbers", false, function (cm, val) {
      cm.display.gutterSpecs = getGutters(cm.options.gutters, val);
      updateGutters(cm);
    }, true);
    option("firstLineNumber", 1, updateGutters, true);
    option("lineNumberFormatter", function (integer) { return integer; }, updateGutters, true);
    option("showCursorWhenSelecting", false, updateSelection, true);

    option("resetSelectionOnContextMenu", true);
    option("lineWiseCopyCut", true);
    option("pasteLinesPerSelection", true);
    option("selectionsMayTouch", false);

    option("readOnly", false, function (cm, val) {
      if (val == "nocursor") {
        onBlur(cm);
        cm.display.input.blur();
      }
      cm.display.input.readOnlyChanged(val);
    });

    option("screenReaderLabel", null, function (cm, val) {
      val = (val === '') ? null : val;
      cm.display.input.screenReaderLabelChanged(val);
    });

    option("disableInput", false, function (cm, val) {if (!val) { cm.display.input.reset(); }}, true);
    option("dragDrop", true, dragDropChanged);
    option("allowDropFileTypes", null);

    option("cursorBlinkRate", 530);
    option("cursorScrollMargin", 0);
    option("cursorHeight", 1, updateSelection, true);
    option("singleCursorHeightPerLine", true, updateSelection, true);
    option("workTime", 100);
    option("workDelay", 100);
    option("flattenSpans", true, resetModeState, true);
    option("addModeClass", false, resetModeState, true);
    option("pollInterval", 100);
    option("undoDepth", 200, function (cm, val) { return cm.doc.history.undoDepth = val; });
    option("historyEventDelay", 1250);
    option("viewportMargin", 10, function (cm) { return cm.refresh(); }, true);
    option("maxHighlightLength", 10000, resetModeState, true);
    option("moveInputWithCursor", true, function (cm, val) {
      if (!val) { cm.display.input.resetPosition(); }
    });

    option("tabindex", null, function (cm, val) { return cm.display.input.getField().tabIndex = val || ""; });
    option("autofocus", null);
    option("direction", "ltr", function (cm, val) { return cm.doc.setDirection(val); }, true);
    option("phrases", null);
  }
```
</details>

### `option(name: any, deflt: any, handle: any, notOnInit: any): void`

**Parameters:**

- **`name`** `any`
- **`deflt`** `any`
- **`handle`** `any`
- **`notOnInit`** `any`

**Returns:** `void`

**Calls:**

- `handle`

<details><summary>Code</summary>

```typescript
function option(name, deflt, handle, notOnInit) {
      CodeMirror.defaults[name] = deflt;
      if (handle) { optionHandlers[name] =
        notOnInit ? function (cm, val, old) {if (old != Init) { handle(cm, val, old); }} : handle; }
    }
```
</details>

### `dragDropChanged(cm: any, value: any, old: any): void`

**Parameters:**

- **`cm`** `any`
- **`value`** `any`
- **`old`** `any`

**Returns:** `void`

**Calls:**

- `toggle`

<details><summary>Code</summary>

```typescript
function dragDropChanged(cm, value, old) {
    var wasOn = old && old != Init;
    if (!value != !wasOn) {
      var funcs = cm.display.dragFunctions;
      var toggle = value ? on : off;
      toggle(cm.display.scroller, "dragstart", funcs.start);
      toggle(cm.display.scroller, "dragenter", funcs.enter);
      toggle(cm.display.scroller, "dragover", funcs.over);
      toggle(cm.display.scroller, "dragleave", funcs.leave);
      toggle(cm.display.scroller, "drop", funcs.drop);
    }
  }
```
</details>

### `wrappingChanged(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `addClass`
- `rmClass`
- `findMaxLine`
- `estimateLineHeights`
- `regChange`
- `clearCaches`
- `setTimeout`
- `updateScrollbars`

<details><summary>Code</summary>

```typescript
function wrappingChanged(cm) {
    if (cm.options.lineWrapping) {
      addClass(cm.display.wrapper, "CodeMirror-wrap");
      cm.display.sizer.style.minWidth = "";
      cm.display.sizerWidth = null;
    } else {
      rmClass(cm.display.wrapper, "CodeMirror-wrap");
      findMaxLine(cm);
    }
    estimateLineHeights(cm);
    regChange(cm);
    clearCaches(cm);
    setTimeout(function () { return updateScrollbars(cm); }, 100);
  }
```
</details>

### `CodeMirror(place: any, options: any): CodeMirror`

**Parameters:**

- **`place`** `any`
- **`options`** `any`

**Returns:** `CodeMirror`

**Calls:**

- `copyObj`
- `themeChanged`
- `initScrollbars`
- `display.input.focus`
- `setTimeout`
- `this$1.display.input.reset`
- `registerEventHandlers`
- `ensureGlobalHandlers`
- `startOperation`
- `attachDoc`
- `this.hasFocus`
- `this$1.hasFocus`
- `onFocus`
- `onBlur`
- `optionHandlers.hasOwnProperty`
- `complex_call_324495`
- `maybeUpdateLineNumberWidth`
- `options.finishInit`
- `complex_call_324691`
- `endOperation`
- `getComputedStyle`

**Internal Comments:**
```
// Determine effective options based on given values and defaults. (x3)
// Override magic textarea content restore that IE sometimes does
// on our hidden textarea on reload
// Suppress optimizelegibility in Webkit, since it breaks text
// measuring on line wrapping boundaries.
```

<details><summary>Code</summary>

```typescript
function CodeMirror(place, options) {
    var this$1 = this;

    if (!(this instanceof CodeMirror)) { return new CodeMirror(place, options) }

    this.options = options = options ? copyObj(options) : {};
    // Determine effective options based on given values and defaults.
    copyObj(defaults, options, false);

    var doc = options.value;
    if (typeof doc == "string") { doc = new Doc(doc, options.mode, null, options.lineSeparator, options.direction); }
    else if (options.mode) { doc.modeOption = options.mode; }
    this.doc = doc;

    var input = new CodeMirror.inputStyles[options.inputStyle](this);
    var display = this.display = new Display(place, doc, input, options);
    display.wrapper.CodeMirror = this;
    themeChanged(this);
    if (options.lineWrapping)
      { this.display.wrapper.className += " CodeMirror-wrap"; }
    initScrollbars(this);

    this.state = {
      keyMaps: [],  // stores maps added by addKeyMap
      overlays: [], // highlighting overlays, as added by addOverlay
      modeGen: 0,   // bumped when mode/overlay changes, used to invalidate highlighting info
      overwrite: false,
      delayingBlurEvent: false,
      focused: false,
      suppressEdits: false, // used to disable editing during key handlers when in readOnly mode
      pasteIncoming: -1, cutIncoming: -1, // help recognize paste/cut edits in input.poll
      selectingText: false,
      draggingText: false,
      highlight: new Delayed(), // stores highlight worker timeout
      keySeq: null,  // Unfinished key sequence
      specialChars: null
    };

    if (options.autofocus && !mobile) { display.input.focus(); }

    // Override magic textarea content restore that IE sometimes does
    // on our hidden textarea on reload
    if (ie && ie_version < 11) { setTimeout(function () { return this$1.display.input.reset(true); }, 20); }

    registerEventHandlers(this);
    ensureGlobalHandlers();

    startOperation(this);
    this.curOp.forceUpdate = true;
    attachDoc(this, doc);

    if ((options.autofocus && !mobile) || this.hasFocus())
      { setTimeout(function () {
        if (this$1.hasFocus() && !this$1.state.focused) { onFocus(this$1); }
      }, 20); }
    else
      { onBlur(this); }

    for (var opt in optionHandlers) { if (optionHandlers.hasOwnProperty(opt))
      { optionHandlers[opt](this, options[opt], Init); } }
    maybeUpdateLineNumberWidth(this);
    if (options.finishInit) { options.finishInit(this); }
    for (var i = 0; i < initHooks.length; ++i) { initHooks[i](this); }
    endOperation(this);
    // Suppress optimizelegibility in Webkit, since it breaks text
    // measuring on line wrapping boundaries.
    if (webkit && options.lineWrapping &&
        getComputedStyle(display.lineDiv).textRendering == "optimizelegibility")
      { display.lineDiv.style.textRendering = "auto"; }
  }
```
</details>

### `registerEventHandlers(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `on`
- `operation`
- `signalDOMEvent`
- `posFromMouse`
- `clickInGutter`
- `eventInWidget`
- `e_preventDefault`
- `cm.findWordAt`
- `extendSelection`
- `onContextMenu`
- `d.input.getField`
- `d.scroller.contains`
- `setTimeout`
- `isMouseLikeTouchEvent`
- `d.input.ensurePolled`
- `clearTimeout`
- `cm.coordsChar`
- `farAway`
- `Pos`
- `clipPos`
- `cm.setSelection`
- `cm.focus`
- `finishTouch`
- `updateScrollTop`
- `setScrollLeft`
- `signal`
- `onScrollWheel`
- `e_stop`
- `onDragOver`
- `onDragStart`
- `clearDragCursor`
- `onKeyUp.call`
- `onFocus`
- `onBlur`

**Internal Comments:**
```
// Older IE's will not fire a second mousedown for a double click
// Some browsers fire contextmenu *after* opening the menu, at (x3)
// which point we can't mess with it anymore. Context menu is (x3)
// handled in onMouseDown for these browsers. (x3)
// Used to suppress mouse event handling when a touch happens (x2)
// Sync scrolling between fake scrollbars and real scrollable (x3)
// area, ensure viewport is updated when scrolling. (x3)
// Listen to wheel events in order to try and update the viewport on time. (x3)
// Prevent wrapper from ever scrolling (x3)
```

<details><summary>Code</summary>

```typescript
function registerEventHandlers(cm) {
    var d = cm.display;
    on(d.scroller, "mousedown", operation(cm, onMouseDown));
    // Older IE's will not fire a second mousedown for a double click
    if (ie && ie_version < 11)
      { on(d.scroller, "dblclick", operation(cm, function (e) {
        if (signalDOMEvent(cm, e)) { return }
        var pos = posFromMouse(cm, e);
        if (!pos || clickInGutter(cm, e) || eventInWidget(cm.display, e)) { return }
        e_preventDefault(e);
        var word = cm.findWordAt(pos);
        extendSelection(cm.doc, word.anchor, word.head);
      })); }
    else
      { on(d.scroller, "dblclick", function (e) { return signalDOMEvent(cm, e) || e_preventDefault(e); }); }
    // Some browsers fire contextmenu *after* opening the menu, at
    // which point we can't mess with it anymore. Context menu is
    // handled in onMouseDown for these browsers.
    on(d.scroller, "contextmenu", function (e) { return onContextMenu(cm, e); });
    on(d.input.getField(), "contextmenu", function (e) {
      if (!d.scroller.contains(e.target)) { onContextMenu(cm, e); }
    });

    // Used to suppress mouse event handling when a touch happens
    var touchFinished, prevTouch = {end: 0};
    function finishTouch() {
      if (d.activeTouch) {
        touchFinished = setTimeout(function () { return d.activeTouch = null; }, 1000);
        prevTouch = d.activeTouch;
        prevTouch.end = +new Date;
      }
    }
    function isMouseLikeTouchEvent(e) {
      if (e.touches.length != 1) { return false }
      var touch = e.touches[0];
      return touch.radiusX <= 1 && touch.radiusY <= 1
    }
    function farAway(touch, other) {
      if (other.left == null) { return true }
      var dx = other.left - touch.left, dy = other.top - touch.top;
      return dx * dx + dy * dy > 20 * 20
    }
    on(d.scroller, "touchstart", function (e) {
      if (!signalDOMEvent(cm, e) && !isMouseLikeTouchEvent(e) && !clickInGutter(cm, e)) {
        d.input.ensurePolled();
        clearTimeout(touchFinished);
        var now = +new Date;
        d.activeTouch = {start: now, moved: false,
                         prev: now - prevTouch.end <= 300 ? prevTouch : null};
        if (e.touches.length == 1) {
          d.activeTouch.left = e.touches[0].pageX;
          d.activeTouch.top = e.touches[0].pageY;
        }
      }
    });
    on(d.scroller, "touchmove", function () {
      if (d.activeTouch) { d.activeTouch.moved = true; }
    });
    on(d.scroller, "touchend", function (e) {
      var touch = d.activeTouch;
      if (touch && !eventInWidget(d, e) && touch.left != null &&
          !touch.moved && new Date - touch.start < 300) {
        var pos = cm.coordsChar(d.activeTouch, "page"), range;
        if (!touch.prev || farAway(touch, touch.prev)) // Single tap
          { range = new Range(pos, pos); }
        else if (!touch.prev.prev || farAway(touch, touch.prev.prev)) // Double tap
          { range = cm.findWordAt(pos); }
        else // Triple tap
          { range = new Range(Pos(pos.line, 0), clipPos(cm.doc, Pos(pos.line + 1, 0))); }
        cm.setSelection(range.anchor, range.head);
        cm.focus();
        e_preventDefault(e);
      }
      finishTouch();
    });
    on(d.scroller, "touchcancel", finishTouch);

    // Sync scrolling between fake scrollbars and real scrollable
    // area, ensure viewport is updated when scrolling.
    on(d.scroller, "scroll", function () {
      if (d.scroller.clientHeight) {
        updateScrollTop(cm, d.scroller.scrollTop);
        setScrollLeft(cm, d.scroller.scrollLeft, true);
        signal(cm, "scroll", cm);
      }
    });

    // Listen to wheel events in order to try and update the viewport on time.
    on(d.scroller, "mousewheel", function (e) { return onScrollWheel(cm, e); });
    on(d.scroller, "DOMMouseScroll", function (e) { return onScrollWheel(cm, e); });

    // Prevent wrapper from ever scrolling
    on(d.wrapper, "scroll", function () { return d.wrapper.scrollTop = d.wrapper.scrollLeft = 0; });

    d.dragFunctions = {
      enter: function (e) {if (!signalDOMEvent(cm, e)) { e_stop(e); }},
      over: function (e) {if (!signalDOMEvent(cm, e)) { onDragOver(cm, e); e_stop(e); }},
      start: function (e) { return onDragStart(cm, e); },
      drop: operation(cm, onDrop),
      leave: function (e) {if (!signalDOMEvent(cm, e)) { clearDragCursor(cm); }}
    };

    var inp = d.input.getField();
    on(inp, "keyup", function (e) { return onKeyUp.call(cm, e); });
    on(inp, "keydown", operation(cm, onKeyDown));
    on(inp, "keypress", operation(cm, onKeyPress));
    on(inp, "focus", function (e) { return onFocus(cm, e); });
    on(inp, "blur", function (e) { return onBlur(cm, e); });
  }
```
</details>

### `finishTouch(): void`

**Returns:** `void`

**Calls:**

- `setTimeout`

<details><summary>Code</summary>

```typescript
function finishTouch() {
      if (d.activeTouch) {
        touchFinished = setTimeout(function () { return d.activeTouch = null; }, 1000);
        prevTouch = d.activeTouch;
        prevTouch.end = +new Date;
      }
    }
```
</details>

### `isMouseLikeTouchEvent(e: any): boolean`

**Parameters:**

- **`e`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isMouseLikeTouchEvent(e) {
      if (e.touches.length != 1) { return false }
      var touch = e.touches[0];
      return touch.radiusX <= 1 && touch.radiusY <= 1
    }
```
</details>

### `farAway(touch: any, other: any): boolean`

**Parameters:**

- **`touch`** `any`
- **`other`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function farAway(touch, other) {
      if (other.left == null) { return true }
      var dx = other.left - touch.left, dy = other.top - touch.top;
      return dx * dx + dy * dy > 20 * 20
    }
```
</details>

### `enter(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `e_stop`

<details><summary>Code</summary>

```typescript
function (e) {if (!signalDOMEvent(cm, e)) { e_stop(e); }}
```
</details>

### `over(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `onDragOver`
- `e_stop`

<details><summary>Code</summary>

```typescript
function (e) {if (!signalDOMEvent(cm, e)) { onDragOver(cm, e); e_stop(e); }}
```
</details>

### `start(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `onDragStart`

<details><summary>Code</summary>

```typescript
function (e) { return onDragStart(cm, e); }
```
</details>

### `leave(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `clearDragCursor`

<details><summary>Code</summary>

```typescript
function (e) {if (!signalDOMEvent(cm, e)) { clearDragCursor(cm); }}
```
</details>

### `enter(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `e_stop`

<details><summary>Code</summary>

```typescript
function (e) {if (!signalDOMEvent(cm, e)) { e_stop(e); }}
```
</details>

### `over(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `onDragOver`
- `e_stop`

<details><summary>Code</summary>

```typescript
function (e) {if (!signalDOMEvent(cm, e)) { onDragOver(cm, e); e_stop(e); }}
```
</details>

### `start(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `onDragStart`

<details><summary>Code</summary>

```typescript
function (e) { return onDragStart(cm, e); }
```
</details>

### `leave(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `clearDragCursor`

<details><summary>Code</summary>

```typescript
function (e) {if (!signalDOMEvent(cm, e)) { clearDragCursor(cm); }}
```
</details>

### `indentLine(cm: any, n: any, how: any, aggressive: any): boolean`

**Parameters:**

- **`cm`** `any`
- **`n`** `any`
- **`how`** `any`
- **`aggressive`** `any`

**Returns:** `boolean`

**Calls:**

- `getContextBefore`
- `getLine`
- `countColumn`
- `line.text.match`
- `/\S/.test`
- `doc.mode.indent`
- `line.text.slice`
- `Math.max`
- `Math.floor`
- `spaceStr`
- `replaceRange`
- `Pos`
- `replaceOneSelection`

**Internal Comments:**
```
// Fall back to "prev" when the mode doesn't have an indentation
// method.
// Ensure that, if the cursor was in the whitespace at the start
// of the line, it is moved to the end of that space.
```

<details><summary>Code</summary>

```typescript
function indentLine(cm, n, how, aggressive) {
    var doc = cm.doc, state;
    if (how == null) { how = "add"; }
    if (how == "smart") {
      // Fall back to "prev" when the mode doesn't have an indentation
      // method.
      if (!doc.mode.indent) { how = "prev"; }
      else { state = getContextBefore(cm, n).state; }
    }

    var tabSize = cm.options.tabSize;
    var line = getLine(doc, n), curSpace = countColumn(line.text, null, tabSize);
    if (line.stateAfter) { line.stateAfter = null; }
    var curSpaceString = line.text.match(/^\s*/)[0], indentation;
    if (!aggressive && !/\S/.test(line.text)) {
      indentation = 0;
      how = "not";
    } else if (how == "smart") {
      indentation = doc.mode.indent(state, line.text.slice(curSpaceString.length), line.text);
      if (indentation == Pass || indentation > 150) {
        if (!aggressive) { return }
        how = "prev";
      }
    }
    if (how == "prev") {
      if (n > doc.first) { indentation = countColumn(getLine(doc, n-1).text, null, tabSize); }
      else { indentation = 0; }
    } else if (how == "add") {
      indentation = curSpace + cm.options.indentUnit;
    } else if (how == "subtract") {
      indentation = curSpace - cm.options.indentUnit;
    } else if (typeof how == "number") {
      indentation = curSpace + how;
    }
    indentation = Math.max(0, indentation);

    var indentString = "", pos = 0;
    if (cm.options.indentWithTabs)
      { for (var i = Math.floor(indentation / tabSize); i; --i) {pos += tabSize; indentString += "\t";} }
    if (pos < indentation) { indentString += spaceStr(indentation - pos); }

    if (indentString != curSpaceString) {
      replaceRange(doc, indentString, Pos(n, 0), Pos(n, curSpaceString.length), "+input");
      line.stateAfter = null;
      return true
    } else {
      // Ensure that, if the cursor was in the whitespace at the start
      // of the line, it is moved to the end of that space.
      for (var i$1 = 0; i$1 < doc.sel.ranges.length; i$1++) {
        var range = doc.sel.ranges[i$1];
        if (range.head.line == n && range.head.ch < curSpaceString.length) {
          var pos$1 = Pos(n, curSpaceString.length);
          replaceOneSelection(doc, i$1, new Range(pos$1, pos$1));
          break
        }
      }
    }
  }
```
</details>

### `setLastCopied(newLastCopied: any): void`

**Parameters:**

- **`newLastCopied`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setLastCopied(newLastCopied) {
    lastCopied = newLastCopied;
  }
```
</details>

### `applyTextInput(cm: any, inserted: any, deleted: any, sel: any, origin: any): void`

**Parameters:**

- **`cm`** `any`
- **`inserted`** `any`
- **`deleted`** `any`
- **`sel`** `any`
- **`origin`** `any`

**Returns:** `void`

**Calls:**

- `splitLinesAuto`
- `lastCopied.text.join`
- `multiPaste.push`
- `doc.splitLines`
- `map`
- `range.from`
- `range.to`
- `range.empty`
- `Pos`
- `Math.min`
- `getLine`
- `lst`
- `textLines.join`
- `makeChange`
- `signalLater`
- `triggerElectric`
- `ensureCursorVisible`

**Internal Comments:**
```
// When pasting N lines into N selections, insert one line per selection
// Normal behavior is to insert the new text into every selection
```

<details><summary>Code</summary>

```typescript
function applyTextInput(cm, inserted, deleted, sel, origin) {
    var doc = cm.doc;
    cm.display.shift = false;
    if (!sel) { sel = doc.sel; }

    var recent = +new Date - 200;
    var paste = origin == "paste" || cm.state.pasteIncoming > recent;
    var textLines = splitLinesAuto(inserted), multiPaste = null;
    // When pasting N lines into N selections, insert one line per selection
    if (paste && sel.ranges.length > 1) {
      if (lastCopied && lastCopied.text.join("\n") == inserted) {
        if (sel.ranges.length % lastCopied.text.length == 0) {
          multiPaste = [];
          for (var i = 0; i < lastCopied.text.length; i++)
            { multiPaste.push(doc.splitLines(lastCopied.text[i])); }
        }
      } else if (textLines.length == sel.ranges.length && cm.options.pasteLinesPerSelection) {
        multiPaste = map(textLines, function (l) { return [l]; });
      }
    }

    var updateInput = cm.curOp.updateInput;
    // Normal behavior is to insert the new text into every selection
    for (var i$1 = sel.ranges.length - 1; i$1 >= 0; i$1--) {
      var range = sel.ranges[i$1];
      var from = range.from(), to = range.to();
      if (range.empty()) {
        if (deleted && deleted > 0) // Handle deletion
          { from = Pos(from.line, from.ch - deleted); }
        else if (cm.state.overwrite && !paste) // Handle overwrite
          { to = Pos(to.line, Math.min(getLine(doc, to.line).text.length, to.ch + lst(textLines).length)); }
        else if (paste && lastCopied && lastCopied.lineWise && lastCopied.text.join("\n") == textLines.join("\n"))
          { from = to = Pos(from.line, 0); }
      }
      var changeEvent = {from: from, to: to, text: multiPaste ? multiPaste[i$1 % multiPaste.length] : textLines,
                         origin: origin || (paste ? "paste" : cm.state.cutIncoming > recent ? "cut" : "+input")};
      makeChange(cm.doc, changeEvent);
      signalLater(cm, "inputRead", cm, changeEvent);
    }
    if (inserted && !paste)
      { triggerElectric(cm, inserted); }

    ensureCursorVisible(cm);
    if (cm.curOp.updateInput < 2) { cm.curOp.updateInput = updateInput; }
    cm.curOp.typing = true;
    cm.state.pasteIncoming = cm.state.cutIncoming = -1;
  }
```
</details>

### `handlePaste(e: any, cm: any): boolean`

**Parameters:**

- **`e`** `any`
- **`cm`** `any`

**Returns:** `boolean`

**Calls:**

- `e.clipboardData.getData`
- `e.preventDefault`
- `cm.isReadOnly`
- `runInOp`
- `applyTextInput`

<details><summary>Code</summary>

```typescript
function handlePaste(e, cm) {
    var pasted = e.clipboardData && e.clipboardData.getData("Text");
    if (pasted) {
      e.preventDefault();
      if (!cm.isReadOnly() && !cm.options.disableInput)
        { runInOp(cm, function () { return applyTextInput(cm, pasted, 0, null, "paste"); }); }
      return true
    }
  }
```
</details>

### `triggerElectric(cm: any, inserted: any): void`

**Parameters:**

- **`cm`** `any`
- **`inserted`** `any`

**Returns:** `void`

**Calls:**

- `cm.getModeAt`
- `inserted.indexOf`
- `mode.electricChars.charAt`
- `indentLine`
- `mode.electricInput.test`
- `getLine(cm.doc, range.head.line).text.slice`
- `signalLater`

**Internal Comments:**
```
// When an 'electric' character is inserted, immediately trigger a reindent
```

<details><summary>Code</summary>

```typescript
function triggerElectric(cm, inserted) {
    // When an 'electric' character is inserted, immediately trigger a reindent
    if (!cm.options.electricChars || !cm.options.smartIndent) { return }
    var sel = cm.doc.sel;

    for (var i = sel.ranges.length - 1; i >= 0; i--) {
      var range = sel.ranges[i];
      if (range.head.ch > 100 || (i && sel.ranges[i - 1].head.line == range.head.line)) { continue }
      var mode = cm.getModeAt(range.head);
      var indented = false;
      if (mode.electricChars) {
        for (var j = 0; j < mode.electricChars.length; j++)
          { if (inserted.indexOf(mode.electricChars.charAt(j)) > -1) {
            indented = indentLine(cm, range.head.line, "smart");
            break
          } }
      } else if (mode.electricInput) {
        if (mode.electricInput.test(getLine(cm.doc, range.head.line).text.slice(0, range.head.ch)))
          { indented = indentLine(cm, range.head.line, "smart"); }
      }
      if (indented) { signalLater(cm, "electricInput", cm, range.head.line); }
    }
  }
```
</details>

### `copyableRanges(cm: any): { text: any[]; ranges: { anchor: Pos; head: Pos; }[]; }`

**Parameters:**

- **`cm`** `any`

**Returns:** `{ text: any[]; ranges: { anchor: Pos; head: Pos; }[]; }`

**Calls:**

- `Pos`
- `ranges.push`
- `text.push`
- `cm.getRange`

<details><summary>Code</summary>

```typescript
function copyableRanges(cm) {
    var text = [], ranges = [];
    for (var i = 0; i < cm.doc.sel.ranges.length; i++) {
      var line = cm.doc.sel.ranges[i].head.line;
      var lineRange = {anchor: Pos(line, 0), head: Pos(line + 1, 0)};
      ranges.push(lineRange);
      text.push(cm.getRange(lineRange.anchor, lineRange.head));
    }
    return {text: text, ranges: ranges}
  }
```
</details>

### `disableBrowserMagic(field: any, spellcheck: any, autocorrect: any, autocapitalize: any): void`

**Parameters:**

- **`field`** `any`
- **`spellcheck`** `any`
- **`autocorrect`** `any`
- **`autocapitalize`** `any`

**Returns:** `void`

**Calls:**

- `field.setAttribute`

<details><summary>Code</summary>

```typescript
function disableBrowserMagic(field, spellcheck, autocorrect, autocapitalize) {
    field.setAttribute("autocorrect", autocorrect ? "" : "off");
    field.setAttribute("autocapitalize", autocapitalize ? "" : "off");
    field.setAttribute("spellcheck", !!spellcheck);
  }
```
</details>

### `hiddenTextarea(): any`

**Returns:** `any`

**Calls:**

- `elt`
- `te.setAttribute`
- `disableBrowserMagic`

**Internal Comments:**
```
// The textarea is kept positioned near the cursor to prevent the
// fact that it'll be scrolled into view on input from scrolling
// our fake cursor out of view. On webkit, when wrap=off, paste is
// very slow. So make the area wide instead.
// If border: 0; -- iOS fails to open keyboard (issue #1287)
```

<details><summary>Code</summary>

```typescript
function hiddenTextarea() {
    var te = elt("textarea", null, null, "position: absolute; bottom: -1em; padding: 0; width: 1px; height: 1em; min-height: 1em; outline: none");
    var div = elt("div", [te], null, "overflow: hidden; position: relative; width: 3px; height: 0px;");
    // The textarea is kept positioned near the cursor to prevent the
    // fact that it'll be scrolled into view on input from scrolling
    // our fake cursor out of view. On webkit, when wrap=off, paste is
    // very slow. So make the area wide instead.
    if (webkit) { te.style.width = "1000px"; }
    else { te.setAttribute("wrap", "off"); }
    // If border: 0; -- iOS fails to open keyboard (issue #1287)
    if (ios) { te.style.border = "1px solid black"; }
    disableBrowserMagic(te);
    return div
  }
```
</details>

### `addEditorMethods(CodeMirror: any): void`

**Parameters:**

- **`CodeMirror`** `any`

**Returns:** `void`

**Calls:**

- `window.focus`
- `this.display.input.focus`
- `optionHandlers.hasOwnProperty`
- `complex_call_338886`
- `signal`
- `complex_call_339168`
- `getKeyMap`
- `maps.splice`
- `methodOp`
- `CodeMirror.getMode`
- `insertSorted`
- `regChange`
- `overlays.splice`
- `isLine`
- `indentLine`
- `range.empty`
- `range.from`
- `range.to`
- `Math.max`
- `Math.min`
- `this.lastLine`
- `newRanges[i].from`
- `replaceOneSelection`
- `newRanges[i].to`
- `ensureCursorVisible`
- `takeToken`
- `Pos`
- `clipPos`
- `getLineStyles`
- `getLine`
- `type.indexOf`
- `type.slice`
- `CodeMirror.innerMode`
- `this.getTokenAt`
- `this.getHelpers`
- `helpers.hasOwnProperty`
- `this.getModeAt`
- `found.push`
- `cur.pred`
- `indexOf`
- `clipLine`
- `getContextBefore`
- `this.doc.sel.primary`
- `cursorCoords`
- `charCoords`
- `fromCoordSystem`
- `coordsChar`
- `lineAtHeight`
- `intoCoordSystem`
- `heightAtLine`
- `textHeight`
- `charWidth`
- `node.setAttribute`
- `this.display.input.setUneditable`
- `display.sizer.appendChild`
- `scrollIntoView`
- `commands.hasOwnProperty`
- `commands[cmd].call`
- `triggerElectric`
- `findPosH`
- `this.extendSelectionsBy`
- `sel.somethingSelected`
- `doc.replaceSelection`
- `deleteNearSelection`
- `findPosV`
- `doc.sel.somethingSelected`
- `doc.extendSelectionsBy`
- `goals.push`
- `doc.sel.primary`
- `addToScrollTop`
- `this.getHelper`
- `line.charAt`
- `isWordChar`
- `/\s/.test`
- `check`
- `addClass`
- `rmClass`
- `this.display.input.getField`
- `activeElt`
- `scrollToCoords`
- `scrollGap`
- `displayHeight`
- `displayWidth`
- `scrollToRange`
- `scrollToCoordsRange`
- `/^\d+$/.test`
- `String`
- `interpret`
- `clearLineMeasurementCache`
- `this.doc.iter`
- `regLineChange`
- `runInOp`
- `startOperation`
- `endOperation`
- `clearCaches`
- `updateGutterSpace`
- `Math.abs`
- `estimateLineHeights`
- `this.state.selectingText`
- `attachDoc`
- `this.display.input.reset`
- `signalLater`
- `Object.prototype.hasOwnProperty.call`
- `eventMixin`
- `CodeMirror.registerHelper`
- `helpers[type]._global.push`

**Internal Comments:**
```
// Fetch the parser token for a given character. Useful for hacks (x2)
// that want to inspect the mode state (say, for completion). (x2)
// Default to positioning above (if specified and possible); otherwise default to positioning below
// Find the word at the given position (as returned by coordsChar). (x2)
// Cancel the current text selection if any (#5821)
```

<details><summary>Code</summary>

```typescript
function addEditorMethods(CodeMirror) {
    var optionHandlers = CodeMirror.optionHandlers;

    var helpers = CodeMirror.helpers = {};

    CodeMirror.prototype = {
      constructor: CodeMirror,
      focus: function(){window.focus(); this.display.input.focus();},

      setOption: function(option, value) {
        var options = this.options, old = options[option];
        if (options[option] == value && option != "mode") { return }
        options[option] = value;
        if (optionHandlers.hasOwnProperty(option))
          { operation(this, optionHandlers[option])(this, value, old); }
        signal(this, "optionChange", this, option);
      },

      getOption: function(option) {return this.options[option]},
      getDoc: function() {return this.doc},

      addKeyMap: function(map, bottom) {
        this.state.keyMaps[bottom ? "push" : "unshift"](getKeyMap(map));
      },
      removeKeyMap: function(map) {
        var maps = this.state.keyMaps;
        for (var i = 0; i < maps.length; ++i)
          { if (maps[i] == map || maps[i].name == map) {
            maps.splice(i, 1);
            return true
          } }
      },

      addOverlay: methodOp(function(spec, options) {
        var mode = spec.token ? spec : CodeMirror.getMode(this.options, spec);
        if (mode.startState) { throw new Error("Overlays may not be stateful.") }
        insertSorted(this.state.overlays,
                     {mode: mode, modeSpec: spec, opaque: options && options.opaque,
                      priority: (options && options.priority) || 0},
                     function (overlay) { return overlay.priority; });
        this.state.modeGen++;
        regChange(this);
      }),
      removeOverlay: methodOp(function(spec) {
        var overlays = this.state.overlays;
        for (var i = 0; i < overlays.length; ++i) {
          var cur = overlays[i].modeSpec;
          if (cur == spec || typeof spec == "string" && cur.name == spec) {
            overlays.splice(i, 1);
            this.state.modeGen++;
            regChange(this);
            return
          }
        }
      }),

      indentLine: methodOp(function(n, dir, aggressive) {
        if (typeof dir != "string" && typeof dir != "number") {
          if (dir == null) { dir = this.options.smartIndent ? "smart" : "prev"; }
          else { dir = dir ? "add" : "subtract"; }
        }
        if (isLine(this.doc, n)) { indentLine(this, n, dir, aggressive); }
      }),
      indentSelection: methodOp(function(how) {
        var ranges = this.doc.sel.ranges, end = -1;
        for (var i = 0; i < ranges.length; i++) {
          var range = ranges[i];
          if (!range.empty()) {
            var from = range.from(), to = range.to();
            var start = Math.max(end, from.line);
            end = Math.min(this.lastLine(), to.line - (to.ch ? 0 : 1)) + 1;
            for (var j = start; j < end; ++j)
              { indentLine(this, j, how); }
            var newRanges = this.doc.sel.ranges;
            if (from.ch == 0 && ranges.length == newRanges.length && newRanges[i].from().ch > 0)
              { replaceOneSelection(this.doc, i, new Range(from, newRanges[i].to()), sel_dontScroll); }
          } else if (range.head.line > end) {
            indentLine(this, range.head.line, how, true);
            end = range.head.line;
            if (i == this.doc.sel.primIndex) { ensureCursorVisible(this); }
          }
        }
      }),

      // Fetch the parser token for a given character. Useful for hacks
      // that want to inspect the mode state (say, for completion).
      getTokenAt: function(pos, precise) {
        return takeToken(this, pos, precise)
      },

      getLineTokens: function(line, precise) {
        return takeToken(this, Pos(line), precise, true)
      },

      getTokenTypeAt: function(pos) {
        pos = clipPos(this.doc, pos);
        var styles = getLineStyles(this, getLine(this.doc, pos.line));
        var before = 0, after = (styles.length - 1) / 2, ch = pos.ch;
        var type;
        if (ch == 0) { type = styles[2]; }
        else { for (;;) {
          var mid = (before + after) >> 1;
          if ((mid ? styles[mid * 2 - 1] : 0) >= ch) { after = mid; }
          else if (styles[mid * 2 + 1] < ch) { before = mid + 1; }
          else { type = styles[mid * 2 + 2]; break }
        } }
        var cut = type ? type.indexOf("overlay ") : -1;
        return cut < 0 ? type : cut == 0 ? null : type.slice(0, cut - 1)
      },

      getModeAt: function(pos) {
        var mode = this.doc.mode;
        if (!mode.innerMode) { return mode }
        return CodeMirror.innerMode(mode, this.getTokenAt(pos).state).mode
      },

      getHelper: function(pos, type) {
        return this.getHelpers(pos, type)[0]
      },

      getHelpers: function(pos, type) {
        var found = [];
        if (!helpers.hasOwnProperty(type)) { return found }
        var help = helpers[type], mode = this.getModeAt(pos);
        if (typeof mode[type] == "string") {
          if (help[mode[type]]) { found.push(help[mode[type]]); }
        } else if (mode[type]) {
          for (var i = 0; i < mode[type].length; i++) {
            var val = help[mode[type][i]];
            if (val) { found.push(val); }
          }
        } else if (mode.helperType && help[mode.helperType]) {
          found.push(help[mode.helperType]);
        } else if (help[mode.name]) {
          found.push(help[mode.name]);
        }
        for (var i$1 = 0; i$1 < help._global.length; i$1++) {
          var cur = help._global[i$1];
          if (cur.pred(mode, this) && indexOf(found, cur.val) == -1)
            { found.push(cur.val); }
        }
        return found
      },

      getStateAfter: function(line, precise) {
        var doc = this.doc;
        line = clipLine(doc, line == null ? doc.first + doc.size - 1: line);
        return getContextBefore(this, line + 1, precise).state
      },

      cursorCoords: function(start, mode) {
        var pos, range = this.doc.sel.primary();
        if (start == null) { pos = range.head; }
        else if (typeof start == "object") { pos = clipPos(this.doc, start); }
        else { pos = start ? range.from() : range.to(); }
        return cursorCoords(this, pos, mode || "page")
      },

      charCoords: function(pos, mode) {
        return charCoords(this, clipPos(this.doc, pos), mode || "page")
      },

      coordsChar: function(coords, mode) {
        coords = fromCoordSystem(this, coords, mode || "page");
        return coordsChar(this, coords.left, coords.top)
      },

      lineAtHeight: function(height, mode) {
        height = fromCoordSystem(this, {top: height, left: 0}, mode || "page").top;
        return lineAtHeight(this.doc, height + this.display.viewOffset)
      },
      heightAtLine: function(line, mode, includeWidgets) {
        var end = false, lineObj;
        if (typeof line == "number") {
          var last = this.doc.first + this.doc.size - 1;
          if (line < this.doc.first) { line = this.doc.first; }
          else if (line > last) { line = last; end = true; }
          lineObj = getLine(this.doc, line);
        } else {
          lineObj = line;
        }
        return intoCoordSystem(this, lineObj, {top: 0, left: 0}, mode || "page", includeWidgets || end).top +
          (end ? this.doc.height - heightAtLine(lineObj) : 0)
      },

      defaultTextHeight: function() { return textHeight(this.display) },
      defaultCharWidth: function() { return charWidth(this.display) },

      getViewport: function() { return {from: this.display.viewFrom, to: this.display.viewTo}},

      addWidget: function(pos, node, scroll, vert, horiz) {
        var display = this.display;
        pos = cursorCoords(this, clipPos(this.doc, pos));
        var top = pos.bottom, left = pos.left;
        node.style.position = "absolute";
        node.setAttribute("cm-ignore-events", "true");
        this.display.input.setUneditable(node);
        display.sizer.appendChild(node);
        if (vert == "over") {
          top = pos.top;
        } else if (vert == "above" || vert == "near") {
          var vspace = Math.max(display.wrapper.clientHeight, this.doc.height),
          hspace = Math.max(display.sizer.clientWidth, display.lineSpace.clientWidth);
          // Default to positioning above (if specified and possible); otherwise default to positioning below
          if ((vert == 'above' || pos.bottom + node.offsetHeight > vspace) && pos.top > node.offsetHeight)
            { top = pos.top - node.offsetHeight; }
          else if (pos.bottom + node.offsetHeight <= vspace)
            { top = pos.bottom; }
          if (left + node.offsetWidth > hspace)
            { left = hspace - node.offsetWidth; }
        }
        node.style.top = top + "px";
        node.style.left = node.style.right = "";
        if (horiz == "right") {
          left = display.sizer.clientWidth - node.offsetWidth;
          node.style.right = "0px";
        } else {
          if (horiz == "left") { left = 0; }
          else if (horiz == "middle") { left = (display.sizer.clientWidth - node.offsetWidth) / 2; }
          node.style.left = left + "px";
        }
        if (scroll)
          { scrollIntoView(this, {left: left, top: top, right: left + node.offsetWidth, bottom: top + node.offsetHeight}); }
      },

      triggerOnKeyDown: methodOp(onKeyDown),
      triggerOnKeyPress: methodOp(onKeyPress),
      triggerOnKeyUp: onKeyUp,
      triggerOnMouseDown: methodOp(onMouseDown),

      execCommand: function(cmd) {
        if (commands.hasOwnProperty(cmd))
          { return commands[cmd].call(null, this) }
      },

      triggerElectric: methodOp(function(text) { triggerElectric(this, text); }),

      findPosH: function(from, amount, unit, visually) {
        var dir = 1;
        if (amount < 0) { dir = -1; amount = -amount; }
        var cur = clipPos(this.doc, from);
        for (var i = 0; i < amount; ++i) {
          cur = findPosH(this.doc, cur, dir, unit, visually);
          if (cur.hitSide) { break }
        }
        return cur
      },

      moveH: methodOp(function(dir, unit) {
        var this$1 = this;

        this.extendSelectionsBy(function (range) {
          if (this$1.display.shift || this$1.doc.extend || range.empty())
            { return findPosH(this$1.doc, range.head, dir, unit, this$1.options.rtlMoveVisually) }
          else
            { return dir < 0 ? range.from() : range.to() }
        }, sel_move);
      }),

      deleteH: methodOp(function(dir, unit) {
        var sel = this.doc.sel, doc = this.doc;
        if (sel.somethingSelected())
          { doc.replaceSelection("", null, "+delete"); }
        else
          { deleteNearSelection(this, function (range) {
            var other = findPosH(doc, range.head, dir, unit, false);
            return dir < 0 ? {from: other, to: range.head} : {from: range.head, to: other}
          }); }
      }),

      findPosV: function(from, amount, unit, goalColumn) {
        var dir = 1, x = goalColumn;
        if (amount < 0) { dir = -1; amount = -amount; }
        var cur = clipPos(this.doc, from);
        for (var i = 0; i < amount; ++i) {
          var coords = cursorCoords(this, cur, "div");
          if (x == null) { x = coords.left; }
          else { coords.left = x; }
          cur = findPosV(this, coords, dir, unit);
          if (cur.hitSide) { break }
        }
        return cur
      },

      moveV: methodOp(function(dir, unit) {
        var this$1 = this;

        var doc = this.doc, goals = [];
        var collapse = !this.display.shift && !doc.extend && doc.sel.somethingSelected();
        doc.extendSelectionsBy(function (range) {
          if (collapse)
            { return dir < 0 ? range.from() : range.to() }
          var headPos = cursorCoords(this$1, range.head, "div");
          if (range.goalColumn != null) { headPos.left = range.goalColumn; }
          goals.push(headPos.left);
          var pos = findPosV(this$1, headPos, dir, unit);
          if (unit == "page" && range == doc.sel.primary())
            { addToScrollTop(this$1, charCoords(this$1, pos, "div").top - headPos.top); }
          return pos
        }, sel_move);
        if (goals.length) { for (var i = 0; i < doc.sel.ranges.length; i++)
          { doc.sel.ranges[i].goalColumn = goals[i]; } }
      }),

      // Find the word at the given position (as returned by coordsChar).
      findWordAt: function(pos) {
        var doc = this.doc, line = getLine(doc, pos.line).text;
        var start = pos.ch, end = pos.ch;
        if (line) {
          var helper = this.getHelper(pos, "wordChars");
          if ((pos.sticky == "before" || end == line.length) && start) { --start; } else { ++end; }
          var startChar = line.charAt(start);
          var check = isWordChar(startChar, helper)
            ? function (ch) { return isWordChar(ch, helper); }
            : /\s/.test(startChar) ? function (ch) { return /\s/.test(ch); }
            : function (ch) { return (!/\s/.test(ch) && !isWordChar(ch)); };
          while (start > 0 && check(line.charAt(start - 1))) { --start; }
          while (end < line.length && check(line.charAt(end))) { ++end; }
        }
        return new Range(Pos(pos.line, start), Pos(pos.line, end))
      },

      toggleOverwrite: function(value) {
        if (value != null && value == this.state.overwrite) { return }
        if (this.state.overwrite = !this.state.overwrite)
          { addClass(this.display.cursorDiv, "CodeMirror-overwrite"); }
        else
          { rmClass(this.display.cursorDiv, "CodeMirror-overwrite"); }

        signal(this, "overwriteToggle", this, this.state.overwrite);
      },
      hasFocus: function() { return this.display.input.getField() == activeElt() },
      isReadOnly: function() { return !!(this.options.readOnly || this.doc.cantEdit) },

      scrollTo: methodOp(function (x, y) { scrollToCoords(this, x, y); }),
      getScrollInfo: function() {
        var scroller = this.display.scroller;
        return {left: scroller.scrollLeft, top: scroller.scrollTop,
                height: scroller.scrollHeight - scrollGap(this) - this.display.barHeight,
                width: scroller.scrollWidth - scrollGap(this) - this.display.barWidth,
                clientHeight: displayHeight(this), clientWidth: displayWidth(this)}
      },

      scrollIntoView: methodOp(function(range, margin) {
        if (range == null) {
          range = {from: this.doc.sel.primary().head, to: null};
          if (margin == null) { margin = this.options.cursorScrollMargin; }
        } else if (typeof range == "number") {
          range = {from: Pos(range, 0), to: null};
        } else if (range.from == null) {
          range = {from: range, to: null};
        }
        if (!range.to) { range.to = range.from; }
        range.margin = margin || 0;

        if (range.from.line != null) {
          scrollToRange(this, range);
        } else {
          scrollToCoordsRange(this, range.from, range.to, range.margin);
        }
      }),

      setSize: methodOp(function(width, height) {
        var this$1 = this;

        var interpret = function (val) { return typeof val == "number" || /^\d+$/.test(String(val)) ? val + "px" : val; };
        if (width != null) { this.display.wrapper.style.width = interpret(width); }
        if (height != null) { this.display.wrapper.style.height = interpret(height); }
        if (this.options.lineWrapping) { clearLineMeasurementCache(this); }
        var lineNo = this.display.viewFrom;
        this.doc.iter(lineNo, this.display.viewTo, function (line) {
          if (line.widgets) { for (var i = 0; i < line.widgets.length; i++)
            { if (line.widgets[i].noHScroll) { regLineChange(this$1, lineNo, "widget"); break } } }
          ++lineNo;
        });
        this.curOp.forceUpdate = true;
        signal(this, "refresh", this);
      }),

      operation: function(f){return runInOp(this, f)},
      startOperation: function(){return startOperation(this)},
      endOperation: function(){return endOperation(this)},

      refresh: methodOp(function() {
        var oldHeight = this.display.cachedTextHeight;
        regChange(this);
        this.curOp.forceUpdate = true;
        clearCaches(this);
        scrollToCoords(this, this.doc.scrollLeft, this.doc.scrollTop);
        updateGutterSpace(this.display);
        if (oldHeight == null || Math.abs(oldHeight - textHeight(this.display)) > .5 || this.options.lineWrapping)
          { estimateLineHeights(this); }
        signal(this, "refresh", this);
      }),

      swapDoc: methodOp(function(doc) {
        var old = this.doc;
        old.cm = null;
        // Cancel the current text selection if any (#5821)
        if (this.state.selectingText) { this.state.selectingText(); }
        attachDoc(this, doc);
        clearCaches(this);
        this.display.input.reset();
        scrollToCoords(this, doc.scrollLeft, doc.scrollTop);
        this.curOp.forceScroll = true;
        signalLater(this, "swapDoc", this, old);
        return old
      }),

      phrase: function(phraseText) {
        var phrases = this.options.phrases;
        return phrases && Object.prototype.hasOwnProperty.call(phrases, phraseText) ? phrases[phraseText] : phraseText
      },

      getInputField: function(){return this.display.input.getField()},
      getWrapperElement: function(){return this.display.wrapper},
      getScrollerElement: function(){return this.display.scroller},
      getGutterElement: function(){return this.display.gutters}
    };
    eventMixin(CodeMirror);

    CodeMirror.registerHelper = function(type, name, value) {
      if (!helpers.hasOwnProperty(type)) { helpers[type] = CodeMirror[type] = {_global: []}; }
      helpers[type][name] = value;
    };
    CodeMirror.registerGlobalHelper = function(type, name, predicate, value) {
      CodeMirror.registerHelper(type, name, value);
      helpers[type]._global.push({pred: predicate, val: value});
    };
  }
```
</details>

### `focus(): void`

**Returns:** `void`

**Calls:**

- `window.focus`
- `this.display.input.focus`

<details><summary>Code</summary>

```typescript
function(){window.focus(); this.display.input.focus();}
```
</details>

### `setOption(option: any, value: any): void`

**Parameters:**

- **`option`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `optionHandlers.hasOwnProperty`
- `complex_call_338886`
- `signal`

<details><summary>Code</summary>

```typescript
function(option, value) {
        var options = this.options, old = options[option];
        if (options[option] == value && option != "mode") { return }
        options[option] = value;
        if (optionHandlers.hasOwnProperty(option))
          { operation(this, optionHandlers[option])(this, value, old); }
        signal(this, "optionChange", this, option);
      }
```
</details>

### `getOption(option: any): any`

**Parameters:**

- **`option`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(option) {return this.options[option]}
```
</details>

### `getDoc(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.doc}
```
</details>

### `addKeyMap(map: any, bottom: any): void`

**Parameters:**

- **`map`** `any`
- **`bottom`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_339168`
- `getKeyMap`

<details><summary>Code</summary>

```typescript
function(map, bottom) {
        this.state.keyMaps[bottom ? "push" : "unshift"](getKeyMap(map));
      }
```
</details>

### `removeKeyMap(map: any): boolean`

**Parameters:**

- **`map`** `any`

**Returns:** `boolean`

**Calls:**

- `maps.splice`

<details><summary>Code</summary>

```typescript
function(map) {
        var maps = this.state.keyMaps;
        for (var i = 0; i < maps.length; ++i)
          { if (maps[i] == map || maps[i].name == map) {
            maps.splice(i, 1);
            return true
          } }
      }
```
</details>

### `getTokenAt(pos: any, precise: any): any[] | Token`

**Parameters:**

- **`pos`** `any`
- **`precise`** `any`

**Returns:** `any[] | Token`

**Calls:**

- `takeToken`

<details><summary>Code</summary>

```typescript
function(pos, precise) {
        return takeToken(this, pos, precise)
      }
```
</details>

### `getLineTokens(line: any, precise: any): any[] | Token`

**Parameters:**

- **`line`** `any`
- **`precise`** `any`

**Returns:** `any[] | Token`

**Calls:**

- `takeToken`
- `Pos`

<details><summary>Code</summary>

```typescript
function(line, precise) {
        return takeToken(this, Pos(line), precise, true)
      }
```
</details>

### `getTokenTypeAt(pos: any): any`

**Parameters:**

- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `getLineStyles`
- `getLine`
- `type.indexOf`
- `type.slice`

<details><summary>Code</summary>

```typescript
function(pos) {
        pos = clipPos(this.doc, pos);
        var styles = getLineStyles(this, getLine(this.doc, pos.line));
        var before = 0, after = (styles.length - 1) / 2, ch = pos.ch;
        var type;
        if (ch == 0) { type = styles[2]; }
        else { for (;;) {
          var mid = (before + after) >> 1;
          if ((mid ? styles[mid * 2 - 1] : 0) >= ch) { after = mid; }
          else if (styles[mid * 2 + 1] < ch) { before = mid + 1; }
          else { type = styles[mid * 2 + 2]; break }
        } }
        var cut = type ? type.indexOf("overlay ") : -1;
        return cut < 0 ? type : cut == 0 ? null : type.slice(0, cut - 1)
      }
```
</details>

### `getModeAt(pos: any): any`

**Parameters:**

- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `CodeMirror.innerMode`
- `this.getTokenAt`

<details><summary>Code</summary>

```typescript
function(pos) {
        var mode = this.doc.mode;
        if (!mode.innerMode) { return mode }
        return CodeMirror.innerMode(mode, this.getTokenAt(pos).state).mode
      }
```
</details>

### `getHelper(pos: any, type: any): any`

**Parameters:**

- **`pos`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `this.getHelpers`

<details><summary>Code</summary>

```typescript
function(pos, type) {
        return this.getHelpers(pos, type)[0]
      }
```
</details>

### `getHelpers(pos: any, type: any): any[]`

**Parameters:**

- **`pos`** `any`
- **`type`** `any`

**Returns:** `any[]`

**Calls:**

- `helpers.hasOwnProperty`
- `this.getModeAt`
- `found.push`
- `cur.pred`
- `indexOf`

<details><summary>Code</summary>

```typescript
function(pos, type) {
        var found = [];
        if (!helpers.hasOwnProperty(type)) { return found }
        var help = helpers[type], mode = this.getModeAt(pos);
        if (typeof mode[type] == "string") {
          if (help[mode[type]]) { found.push(help[mode[type]]); }
        } else if (mode[type]) {
          for (var i = 0; i < mode[type].length; i++) {
            var val = help[mode[type][i]];
            if (val) { found.push(val); }
          }
        } else if (mode.helperType && help[mode.helperType]) {
          found.push(help[mode.helperType]);
        } else if (help[mode.name]) {
          found.push(help[mode.name]);
        }
        for (var i$1 = 0; i$1 < help._global.length; i$1++) {
          var cur = help._global[i$1];
          if (cur.pred(mode, this) && indexOf(found, cur.val) == -1)
            { found.push(cur.val); }
        }
        return found
      }
```
</details>

### `getStateAfter(line: any, precise: any): any`

**Parameters:**

- **`line`** `any`
- **`precise`** `any`

**Returns:** `any`

**Calls:**

- `clipLine`
- `getContextBefore`

<details><summary>Code</summary>

```typescript
function(line, precise) {
        var doc = this.doc;
        line = clipLine(doc, line == null ? doc.first + doc.size - 1: line);
        return getContextBefore(this, line + 1, precise).state
      }
```
</details>

### `cursorCoords(start: any, mode: any): any`

**Parameters:**

- **`start`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `this.doc.sel.primary`
- `clipPos`
- `range.from`
- `range.to`
- `cursorCoords`

<details><summary>Code</summary>

```typescript
function(start, mode) {
        var pos, range = this.doc.sel.primary();
        if (start == null) { pos = range.head; }
        else if (typeof start == "object") { pos = clipPos(this.doc, start); }
        else { pos = start ? range.from() : range.to(); }
        return cursorCoords(this, pos, mode || "page")
      }
```
</details>

### `charCoords(pos: any, mode: any): any`

**Parameters:**

- **`pos`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `charCoords`
- `clipPos`

<details><summary>Code</summary>

```typescript
function(pos, mode) {
        return charCoords(this, clipPos(this.doc, pos), mode || "page")
      }
```
</details>

### `coordsChar(coords: any, mode: any): any`

**Parameters:**

- **`coords`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `fromCoordSystem`
- `coordsChar`

<details><summary>Code</summary>

```typescript
function(coords, mode) {
        coords = fromCoordSystem(this, coords, mode || "page");
        return coordsChar(this, coords.left, coords.top)
      }
```
</details>

### `lineAtHeight(height: any, mode: any): any`

**Parameters:**

- **`height`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `fromCoordSystem`
- `lineAtHeight`

<details><summary>Code</summary>

```typescript
function(height, mode) {
        height = fromCoordSystem(this, {top: height, left: 0}, mode || "page").top;
        return lineAtHeight(this.doc, height + this.display.viewOffset)
      }
```
</details>

### `heightAtLine(line: any, mode: any, includeWidgets: any): any`

**Parameters:**

- **`line`** `any`
- **`mode`** `any`
- **`includeWidgets`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `intoCoordSystem`
- `heightAtLine`

<details><summary>Code</summary>

```typescript
function(line, mode, includeWidgets) {
        var end = false, lineObj;
        if (typeof line == "number") {
          var last = this.doc.first + this.doc.size - 1;
          if (line < this.doc.first) { line = this.doc.first; }
          else if (line > last) { line = last; end = true; }
          lineObj = getLine(this.doc, line);
        } else {
          lineObj = line;
        }
        return intoCoordSystem(this, lineObj, {top: 0, left: 0}, mode || "page", includeWidgets || end).top +
          (end ? this.doc.height - heightAtLine(lineObj) : 0)
      }
```
</details>

### `defaultTextHeight(): any`

**Returns:** `any`

**Calls:**

- `textHeight`

<details><summary>Code</summary>

```typescript
function() { return textHeight(this.display) }
```
</details>

### `defaultCharWidth(): any`

**Returns:** `any`

**Calls:**

- `charWidth`

<details><summary>Code</summary>

```typescript
function() { return charWidth(this.display) }
```
</details>

### `getViewport(): { from: any; to: any; }`

**Returns:** `{ from: any; to: any; }`

<details><summary>Code</summary>

```typescript
function() { return {from: this.display.viewFrom, to: this.display.viewTo}}
```
</details>

### `addWidget(pos: any, node: any, scroll: any, vert: any, horiz: any): void`

**Parameters:**

- **`pos`** `any`
- **`node`** `any`
- **`scroll`** `any`
- **`vert`** `any`
- **`horiz`** `any`

**Returns:** `void`

**Calls:**

- `cursorCoords`
- `clipPos`
- `node.setAttribute`
- `this.display.input.setUneditable`
- `display.sizer.appendChild`
- `Math.max`
- `scrollIntoView`

**Internal Comments:**
```
// Default to positioning above (if specified and possible); otherwise default to positioning below
```

<details><summary>Code</summary>

```typescript
function(pos, node, scroll, vert, horiz) {
        var display = this.display;
        pos = cursorCoords(this, clipPos(this.doc, pos));
        var top = pos.bottom, left = pos.left;
        node.style.position = "absolute";
        node.setAttribute("cm-ignore-events", "true");
        this.display.input.setUneditable(node);
        display.sizer.appendChild(node);
        if (vert == "over") {
          top = pos.top;
        } else if (vert == "above" || vert == "near") {
          var vspace = Math.max(display.wrapper.clientHeight, this.doc.height),
          hspace = Math.max(display.sizer.clientWidth, display.lineSpace.clientWidth);
          // Default to positioning above (if specified and possible); otherwise default to positioning below
          if ((vert == 'above' || pos.bottom + node.offsetHeight > vspace) && pos.top > node.offsetHeight)
            { top = pos.top - node.offsetHeight; }
          else if (pos.bottom + node.offsetHeight <= vspace)
            { top = pos.bottom; }
          if (left + node.offsetWidth > hspace)
            { left = hspace - node.offsetWidth; }
        }
        node.style.top = top + "px";
        node.style.left = node.style.right = "";
        if (horiz == "right") {
          left = display.sizer.clientWidth - node.offsetWidth;
          node.style.right = "0px";
        } else {
          if (horiz == "left") { left = 0; }
          else if (horiz == "middle") { left = (display.sizer.clientWidth - node.offsetWidth) / 2; }
          node.style.left = left + "px";
        }
        if (scroll)
          { scrollIntoView(this, {left: left, top: top, right: left + node.offsetWidth, bottom: top + node.offsetHeight}); }
      }
```
</details>

### `execCommand(cmd: any): any`

**Parameters:**

- **`cmd`** `any`

**Returns:** `any`

**Calls:**

- `commands.hasOwnProperty`
- `commands[cmd].call`

<details><summary>Code</summary>

```typescript
function(cmd) {
        if (commands.hasOwnProperty(cmd))
          { return commands[cmd].call(null, this) }
      }
```
</details>

### `findPosH(from: any, amount: any, unit: any, visually: any): any`

**Parameters:**

- **`from`** `any`
- **`amount`** `any`
- **`unit`** `any`
- **`visually`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `findPosH`

<details><summary>Code</summary>

```typescript
function(from, amount, unit, visually) {
        var dir = 1;
        if (amount < 0) { dir = -1; amount = -amount; }
        var cur = clipPos(this.doc, from);
        for (var i = 0; i < amount; ++i) {
          cur = findPosH(this.doc, cur, dir, unit, visually);
          if (cur.hitSide) { break }
        }
        return cur
      }
```
</details>

### `findPosV(from: any, amount: any, unit: any, goalColumn: any): any`

**Parameters:**

- **`from`** `any`
- **`amount`** `any`
- **`unit`** `any`
- **`goalColumn`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `cursorCoords`
- `findPosV`

<details><summary>Code</summary>

```typescript
function(from, amount, unit, goalColumn) {
        var dir = 1, x = goalColumn;
        if (amount < 0) { dir = -1; amount = -amount; }
        var cur = clipPos(this.doc, from);
        for (var i = 0; i < amount; ++i) {
          var coords = cursorCoords(this, cur, "div");
          if (x == null) { x = coords.left; }
          else { coords.left = x; }
          cur = findPosV(this, coords, dir, unit);
          if (cur.hitSide) { break }
        }
        return cur
      }
```
</details>

### `findWordAt(pos: any): Range`

**Parameters:**

- **`pos`** `any`

**Returns:** `Range`

**Calls:**

- `getLine`
- `this.getHelper`
- `line.charAt`
- `isWordChar`
- `/\s/.test`
- `check`
- `Pos`

<details><summary>Code</summary>

```typescript
function(pos) {
        var doc = this.doc, line = getLine(doc, pos.line).text;
        var start = pos.ch, end = pos.ch;
        if (line) {
          var helper = this.getHelper(pos, "wordChars");
          if ((pos.sticky == "before" || end == line.length) && start) { --start; } else { ++end; }
          var startChar = line.charAt(start);
          var check = isWordChar(startChar, helper)
            ? function (ch) { return isWordChar(ch, helper); }
            : /\s/.test(startChar) ? function (ch) { return /\s/.test(ch); }
            : function (ch) { return (!/\s/.test(ch) && !isWordChar(ch)); };
          while (start > 0 && check(line.charAt(start - 1))) { --start; }
          while (end < line.length && check(line.charAt(end))) { ++end; }
        }
        return new Range(Pos(pos.line, start), Pos(pos.line, end))
      }
```
</details>

### `toggleOverwrite(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `addClass`
- `rmClass`
- `signal`

<details><summary>Code</summary>

```typescript
function(value) {
        if (value != null && value == this.state.overwrite) { return }
        if (this.state.overwrite = !this.state.overwrite)
          { addClass(this.display.cursorDiv, "CodeMirror-overwrite"); }
        else
          { rmClass(this.display.cursorDiv, "CodeMirror-overwrite"); }

        signal(this, "overwriteToggle", this, this.state.overwrite);
      }
```
</details>

### `hasFocus(): boolean`

**Returns:** `boolean`

**Calls:**

- `this.display.input.getField`
- `activeElt`

<details><summary>Code</summary>

```typescript
function() { return this.display.input.getField() == activeElt() }
```
</details>

### `isReadOnly(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return !!(this.options.readOnly || this.doc.cantEdit) }
```
</details>

### `getScrollInfo(): { left: any; top: any; height: number; width: number; clientHeight: number; clientWidth: number; }`

**Returns:** `{ left: any; top: any; height: number; width: number; clientHeight: number; clientWidth: number; }`

**Calls:**

- `scrollGap`
- `displayHeight`
- `displayWidth`

<details><summary>Code</summary>

```typescript
function() {
        var scroller = this.display.scroller;
        return {left: scroller.scrollLeft, top: scroller.scrollTop,
                height: scroller.scrollHeight - scrollGap(this) - this.display.barHeight,
                width: scroller.scrollWidth - scrollGap(this) - this.display.barWidth,
                clientHeight: displayHeight(this), clientWidth: displayWidth(this)}
      }
```
</details>

### `interpret(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

**Calls:**

- `/^\d+$/.test`
- `String`

<details><summary>Code</summary>

```typescript
function (val) { return typeof val == "number" || /^\d+$/.test(String(val)) ? val + "px" : val; }
```
</details>

### `operation(f: any): any`

**Parameters:**

- **`f`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`

<details><summary>Code</summary>

```typescript
function(f){return runInOp(this, f)}
```
</details>

### `startOperation(): void`

**Returns:** `void`

**Calls:**

- `startOperation`

<details><summary>Code</summary>

```typescript
function(){return startOperation(this)}
```
</details>

### `endOperation(): void`

**Returns:** `void`

**Calls:**

- `endOperation`

<details><summary>Code</summary>

```typescript
function(){return endOperation(this)}
```
</details>

### `phrase(phraseText: any): any`

**Parameters:**

- **`phraseText`** `any`

**Returns:** `any`

**Calls:**

- `Object.prototype.hasOwnProperty.call`

<details><summary>Code</summary>

```typescript
function(phraseText) {
        var phrases = this.options.phrases;
        return phrases && Object.prototype.hasOwnProperty.call(phrases, phraseText) ? phrases[phraseText] : phraseText
      }
```
</details>

### `getInputField(): any`

**Returns:** `any`

**Calls:**

- `this.display.input.getField`

<details><summary>Code</summary>

```typescript
function(){return this.display.input.getField()}
```
</details>

### `getWrapperElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this.display.wrapper}
```
</details>

### `getScrollerElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this.display.scroller}
```
</details>

### `getGutterElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this.display.gutters}
```
</details>

### `focus(): void`

**Returns:** `void`

**Calls:**

- `window.focus`
- `this.display.input.focus`

<details><summary>Code</summary>

```typescript
function(){window.focus(); this.display.input.focus();}
```
</details>

### `setOption(option: any, value: any): void`

**Parameters:**

- **`option`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `optionHandlers.hasOwnProperty`
- `complex_call_338886`
- `signal`

<details><summary>Code</summary>

```typescript
function(option, value) {
        var options = this.options, old = options[option];
        if (options[option] == value && option != "mode") { return }
        options[option] = value;
        if (optionHandlers.hasOwnProperty(option))
          { operation(this, optionHandlers[option])(this, value, old); }
        signal(this, "optionChange", this, option);
      }
```
</details>

### `getOption(option: any): any`

**Parameters:**

- **`option`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(option) {return this.options[option]}
```
</details>

### `getDoc(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {return this.doc}
```
</details>

### `addKeyMap(map: any, bottom: any): void`

**Parameters:**

- **`map`** `any`
- **`bottom`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_339168`
- `getKeyMap`

<details><summary>Code</summary>

```typescript
function(map, bottom) {
        this.state.keyMaps[bottom ? "push" : "unshift"](getKeyMap(map));
      }
```
</details>

### `removeKeyMap(map: any): boolean`

**Parameters:**

- **`map`** `any`

**Returns:** `boolean`

**Calls:**

- `maps.splice`

<details><summary>Code</summary>

```typescript
function(map) {
        var maps = this.state.keyMaps;
        for (var i = 0; i < maps.length; ++i)
          { if (maps[i] == map || maps[i].name == map) {
            maps.splice(i, 1);
            return true
          } }
      }
```
</details>

### `getTokenAt(pos: any, precise: any): any[] | Token`

**Parameters:**

- **`pos`** `any`
- **`precise`** `any`

**Returns:** `any[] | Token`

**Calls:**

- `takeToken`

<details><summary>Code</summary>

```typescript
function(pos, precise) {
        return takeToken(this, pos, precise)
      }
```
</details>

### `getLineTokens(line: any, precise: any): any[] | Token`

**Parameters:**

- **`line`** `any`
- **`precise`** `any`

**Returns:** `any[] | Token`

**Calls:**

- `takeToken`
- `Pos`

<details><summary>Code</summary>

```typescript
function(line, precise) {
        return takeToken(this, Pos(line), precise, true)
      }
```
</details>

### `getTokenTypeAt(pos: any): any`

**Parameters:**

- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `getLineStyles`
- `getLine`
- `type.indexOf`
- `type.slice`

<details><summary>Code</summary>

```typescript
function(pos) {
        pos = clipPos(this.doc, pos);
        var styles = getLineStyles(this, getLine(this.doc, pos.line));
        var before = 0, after = (styles.length - 1) / 2, ch = pos.ch;
        var type;
        if (ch == 0) { type = styles[2]; }
        else { for (;;) {
          var mid = (before + after) >> 1;
          if ((mid ? styles[mid * 2 - 1] : 0) >= ch) { after = mid; }
          else if (styles[mid * 2 + 1] < ch) { before = mid + 1; }
          else { type = styles[mid * 2 + 2]; break }
        } }
        var cut = type ? type.indexOf("overlay ") : -1;
        return cut < 0 ? type : cut == 0 ? null : type.slice(0, cut - 1)
      }
```
</details>

### `getModeAt(pos: any): any`

**Parameters:**

- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `CodeMirror.innerMode`
- `this.getTokenAt`

<details><summary>Code</summary>

```typescript
function(pos) {
        var mode = this.doc.mode;
        if (!mode.innerMode) { return mode }
        return CodeMirror.innerMode(mode, this.getTokenAt(pos).state).mode
      }
```
</details>

### `getHelper(pos: any, type: any): any`

**Parameters:**

- **`pos`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `this.getHelpers`

<details><summary>Code</summary>

```typescript
function(pos, type) {
        return this.getHelpers(pos, type)[0]
      }
```
</details>

### `getHelpers(pos: any, type: any): any[]`

**Parameters:**

- **`pos`** `any`
- **`type`** `any`

**Returns:** `any[]`

**Calls:**

- `helpers.hasOwnProperty`
- `this.getModeAt`
- `found.push`
- `cur.pred`
- `indexOf`

<details><summary>Code</summary>

```typescript
function(pos, type) {
        var found = [];
        if (!helpers.hasOwnProperty(type)) { return found }
        var help = helpers[type], mode = this.getModeAt(pos);
        if (typeof mode[type] == "string") {
          if (help[mode[type]]) { found.push(help[mode[type]]); }
        } else if (mode[type]) {
          for (var i = 0; i < mode[type].length; i++) {
            var val = help[mode[type][i]];
            if (val) { found.push(val); }
          }
        } else if (mode.helperType && help[mode.helperType]) {
          found.push(help[mode.helperType]);
        } else if (help[mode.name]) {
          found.push(help[mode.name]);
        }
        for (var i$1 = 0; i$1 < help._global.length; i$1++) {
          var cur = help._global[i$1];
          if (cur.pred(mode, this) && indexOf(found, cur.val) == -1)
            { found.push(cur.val); }
        }
        return found
      }
```
</details>

### `getStateAfter(line: any, precise: any): any`

**Parameters:**

- **`line`** `any`
- **`precise`** `any`

**Returns:** `any`

**Calls:**

- `clipLine`
- `getContextBefore`

<details><summary>Code</summary>

```typescript
function(line, precise) {
        var doc = this.doc;
        line = clipLine(doc, line == null ? doc.first + doc.size - 1: line);
        return getContextBefore(this, line + 1, precise).state
      }
```
</details>

### `cursorCoords(start: any, mode: any): any`

**Parameters:**

- **`start`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `this.doc.sel.primary`
- `clipPos`
- `range.from`
- `range.to`
- `cursorCoords`

<details><summary>Code</summary>

```typescript
function(start, mode) {
        var pos, range = this.doc.sel.primary();
        if (start == null) { pos = range.head; }
        else if (typeof start == "object") { pos = clipPos(this.doc, start); }
        else { pos = start ? range.from() : range.to(); }
        return cursorCoords(this, pos, mode || "page")
      }
```
</details>

### `charCoords(pos: any, mode: any): any`

**Parameters:**

- **`pos`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `charCoords`
- `clipPos`

<details><summary>Code</summary>

```typescript
function(pos, mode) {
        return charCoords(this, clipPos(this.doc, pos), mode || "page")
      }
```
</details>

### `coordsChar(coords: any, mode: any): any`

**Parameters:**

- **`coords`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `fromCoordSystem`
- `coordsChar`

<details><summary>Code</summary>

```typescript
function(coords, mode) {
        coords = fromCoordSystem(this, coords, mode || "page");
        return coordsChar(this, coords.left, coords.top)
      }
```
</details>

### `lineAtHeight(height: any, mode: any): any`

**Parameters:**

- **`height`** `any`
- **`mode`** `any`

**Returns:** `any`

**Calls:**

- `fromCoordSystem`
- `lineAtHeight`

<details><summary>Code</summary>

```typescript
function(height, mode) {
        height = fromCoordSystem(this, {top: height, left: 0}, mode || "page").top;
        return lineAtHeight(this.doc, height + this.display.viewOffset)
      }
```
</details>

### `heightAtLine(line: any, mode: any, includeWidgets: any): any`

**Parameters:**

- **`line`** `any`
- **`mode`** `any`
- **`includeWidgets`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `intoCoordSystem`
- `heightAtLine`

<details><summary>Code</summary>

```typescript
function(line, mode, includeWidgets) {
        var end = false, lineObj;
        if (typeof line == "number") {
          var last = this.doc.first + this.doc.size - 1;
          if (line < this.doc.first) { line = this.doc.first; }
          else if (line > last) { line = last; end = true; }
          lineObj = getLine(this.doc, line);
        } else {
          lineObj = line;
        }
        return intoCoordSystem(this, lineObj, {top: 0, left: 0}, mode || "page", includeWidgets || end).top +
          (end ? this.doc.height - heightAtLine(lineObj) : 0)
      }
```
</details>

### `defaultTextHeight(): any`

**Returns:** `any`

**Calls:**

- `textHeight`

<details><summary>Code</summary>

```typescript
function() { return textHeight(this.display) }
```
</details>

### `defaultCharWidth(): any`

**Returns:** `any`

**Calls:**

- `charWidth`

<details><summary>Code</summary>

```typescript
function() { return charWidth(this.display) }
```
</details>

### `getViewport(): { from: any; to: any; }`

**Returns:** `{ from: any; to: any; }`

<details><summary>Code</summary>

```typescript
function() { return {from: this.display.viewFrom, to: this.display.viewTo}}
```
</details>

### `addWidget(pos: any, node: any, scroll: any, vert: any, horiz: any): void`

**Parameters:**

- **`pos`** `any`
- **`node`** `any`
- **`scroll`** `any`
- **`vert`** `any`
- **`horiz`** `any`

**Returns:** `void`

**Calls:**

- `cursorCoords`
- `clipPos`
- `node.setAttribute`
- `this.display.input.setUneditable`
- `display.sizer.appendChild`
- `Math.max`
- `scrollIntoView`

**Internal Comments:**
```
// Default to positioning above (if specified and possible); otherwise default to positioning below
```

<details><summary>Code</summary>

```typescript
function(pos, node, scroll, vert, horiz) {
        var display = this.display;
        pos = cursorCoords(this, clipPos(this.doc, pos));
        var top = pos.bottom, left = pos.left;
        node.style.position = "absolute";
        node.setAttribute("cm-ignore-events", "true");
        this.display.input.setUneditable(node);
        display.sizer.appendChild(node);
        if (vert == "over") {
          top = pos.top;
        } else if (vert == "above" || vert == "near") {
          var vspace = Math.max(display.wrapper.clientHeight, this.doc.height),
          hspace = Math.max(display.sizer.clientWidth, display.lineSpace.clientWidth);
          // Default to positioning above (if specified and possible); otherwise default to positioning below
          if ((vert == 'above' || pos.bottom + node.offsetHeight > vspace) && pos.top > node.offsetHeight)
            { top = pos.top - node.offsetHeight; }
          else if (pos.bottom + node.offsetHeight <= vspace)
            { top = pos.bottom; }
          if (left + node.offsetWidth > hspace)
            { left = hspace - node.offsetWidth; }
        }
        node.style.top = top + "px";
        node.style.left = node.style.right = "";
        if (horiz == "right") {
          left = display.sizer.clientWidth - node.offsetWidth;
          node.style.right = "0px";
        } else {
          if (horiz == "left") { left = 0; }
          else if (horiz == "middle") { left = (display.sizer.clientWidth - node.offsetWidth) / 2; }
          node.style.left = left + "px";
        }
        if (scroll)
          { scrollIntoView(this, {left: left, top: top, right: left + node.offsetWidth, bottom: top + node.offsetHeight}); }
      }
```
</details>

### `execCommand(cmd: any): any`

**Parameters:**

- **`cmd`** `any`

**Returns:** `any`

**Calls:**

- `commands.hasOwnProperty`
- `commands[cmd].call`

<details><summary>Code</summary>

```typescript
function(cmd) {
        if (commands.hasOwnProperty(cmd))
          { return commands[cmd].call(null, this) }
      }
```
</details>

### `findPosH(from: any, amount: any, unit: any, visually: any): any`

**Parameters:**

- **`from`** `any`
- **`amount`** `any`
- **`unit`** `any`
- **`visually`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `findPosH`

<details><summary>Code</summary>

```typescript
function(from, amount, unit, visually) {
        var dir = 1;
        if (amount < 0) { dir = -1; amount = -amount; }
        var cur = clipPos(this.doc, from);
        for (var i = 0; i < amount; ++i) {
          cur = findPosH(this.doc, cur, dir, unit, visually);
          if (cur.hitSide) { break }
        }
        return cur
      }
```
</details>

### `findPosV(from: any, amount: any, unit: any, goalColumn: any): any`

**Parameters:**

- **`from`** `any`
- **`amount`** `any`
- **`unit`** `any`
- **`goalColumn`** `any`

**Returns:** `any`

**Calls:**

- `clipPos`
- `cursorCoords`
- `findPosV`

<details><summary>Code</summary>

```typescript
function(from, amount, unit, goalColumn) {
        var dir = 1, x = goalColumn;
        if (amount < 0) { dir = -1; amount = -amount; }
        var cur = clipPos(this.doc, from);
        for (var i = 0; i < amount; ++i) {
          var coords = cursorCoords(this, cur, "div");
          if (x == null) { x = coords.left; }
          else { coords.left = x; }
          cur = findPosV(this, coords, dir, unit);
          if (cur.hitSide) { break }
        }
        return cur
      }
```
</details>

### `findWordAt(pos: any): Range`

**Parameters:**

- **`pos`** `any`

**Returns:** `Range`

**Calls:**

- `getLine`
- `this.getHelper`
- `line.charAt`
- `isWordChar`
- `/\s/.test`
- `check`
- `Pos`

<details><summary>Code</summary>

```typescript
function(pos) {
        var doc = this.doc, line = getLine(doc, pos.line).text;
        var start = pos.ch, end = pos.ch;
        if (line) {
          var helper = this.getHelper(pos, "wordChars");
          if ((pos.sticky == "before" || end == line.length) && start) { --start; } else { ++end; }
          var startChar = line.charAt(start);
          var check = isWordChar(startChar, helper)
            ? function (ch) { return isWordChar(ch, helper); }
            : /\s/.test(startChar) ? function (ch) { return /\s/.test(ch); }
            : function (ch) { return (!/\s/.test(ch) && !isWordChar(ch)); };
          while (start > 0 && check(line.charAt(start - 1))) { --start; }
          while (end < line.length && check(line.charAt(end))) { ++end; }
        }
        return new Range(Pos(pos.line, start), Pos(pos.line, end))
      }
```
</details>

### `toggleOverwrite(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `addClass`
- `rmClass`
- `signal`

<details><summary>Code</summary>

```typescript
function(value) {
        if (value != null && value == this.state.overwrite) { return }
        if (this.state.overwrite = !this.state.overwrite)
          { addClass(this.display.cursorDiv, "CodeMirror-overwrite"); }
        else
          { rmClass(this.display.cursorDiv, "CodeMirror-overwrite"); }

        signal(this, "overwriteToggle", this, this.state.overwrite);
      }
```
</details>

### `hasFocus(): boolean`

**Returns:** `boolean`

**Calls:**

- `this.display.input.getField`
- `activeElt`

<details><summary>Code</summary>

```typescript
function() { return this.display.input.getField() == activeElt() }
```
</details>

### `isReadOnly(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return !!(this.options.readOnly || this.doc.cantEdit) }
```
</details>

### `getScrollInfo(): { left: any; top: any; height: number; width: number; clientHeight: number; clientWidth: number; }`

**Returns:** `{ left: any; top: any; height: number; width: number; clientHeight: number; clientWidth: number; }`

**Calls:**

- `scrollGap`
- `displayHeight`
- `displayWidth`

<details><summary>Code</summary>

```typescript
function() {
        var scroller = this.display.scroller;
        return {left: scroller.scrollLeft, top: scroller.scrollTop,
                height: scroller.scrollHeight - scrollGap(this) - this.display.barHeight,
                width: scroller.scrollWidth - scrollGap(this) - this.display.barWidth,
                clientHeight: displayHeight(this), clientWidth: displayWidth(this)}
      }
```
</details>

### `operation(f: any): any`

**Parameters:**

- **`f`** `any`

**Returns:** `any`

**Calls:**

- `runInOp`

<details><summary>Code</summary>

```typescript
function(f){return runInOp(this, f)}
```
</details>

### `startOperation(): void`

**Returns:** `void`

**Calls:**

- `startOperation`

<details><summary>Code</summary>

```typescript
function(){return startOperation(this)}
```
</details>

### `endOperation(): void`

**Returns:** `void`

**Calls:**

- `endOperation`

<details><summary>Code</summary>

```typescript
function(){return endOperation(this)}
```
</details>

### `phrase(phraseText: any): any`

**Parameters:**

- **`phraseText`** `any`

**Returns:** `any`

**Calls:**

- `Object.prototype.hasOwnProperty.call`

<details><summary>Code</summary>

```typescript
function(phraseText) {
        var phrases = this.options.phrases;
        return phrases && Object.prototype.hasOwnProperty.call(phrases, phraseText) ? phrases[phraseText] : phraseText
      }
```
</details>

### `getInputField(): any`

**Returns:** `any`

**Calls:**

- `this.display.input.getField`

<details><summary>Code</summary>

```typescript
function(){return this.display.input.getField()}
```
</details>

### `getWrapperElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this.display.wrapper}
```
</details>

### `getScrollerElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this.display.scroller}
```
</details>

### `getGutterElement(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this.display.gutters}
```
</details>

### `findPosH(doc: any, pos: any, dir: any, unit: any, visually: any): any`

**Parameters:**

- **`doc`** `any`
- **`pos`** `any`
- **`dir`** `any`
- **`unit`** `any`
- **`visually`** `any`

**Returns:** `any`

**Calls:**

- `getLine`
- `lineObj.text.charCodeAt`
- `isNaN`
- `Math.max`
- `Math.min`
- `moveVisually`
- `moveLogically`
- `findNextLine`
- `endOfLine`
- `moveOnce`
- `doc.cm.getHelper`
- `lineObj.text.charAt`
- `isWordChar`
- `/\s/.test`
- `skipAtomic`
- `equalCursorPos`

<details><summary>Code</summary>

```typescript
function findPosH(doc, pos, dir, unit, visually) {
    var oldPos = pos;
    var origDir = dir;
    var lineObj = getLine(doc, pos.line);
    var lineDir = visually && doc.direction == "rtl" ? -dir : dir;
    function findNextLine() {
      var l = pos.line + lineDir;
      if (l < doc.first || l >= doc.first + doc.size) { return false }
      pos = new Pos(l, pos.ch, pos.sticky);
      return lineObj = getLine(doc, l)
    }
    function moveOnce(boundToLine) {
      var next;
      if (unit == "codepoint") {
        var ch = lineObj.text.charCodeAt(pos.ch + (dir > 0 ? 0 : -1));
        if (isNaN(ch)) {
          next = null;
        } else {
          var astral = dir > 0 ? ch >= 0xD800 && ch < 0xDC00 : ch >= 0xDC00 && ch < 0xDFFF;
          next = new Pos(pos.line, Math.max(0, Math.min(lineObj.text.length, pos.ch + dir * (astral ? 2 : 1))), -dir);
        }
      } else if (visually) {
        next = moveVisually(doc.cm, lineObj, pos, dir);
      } else {
        next = moveLogically(lineObj, pos, dir);
      }
      if (next == null) {
        if (!boundToLine && findNextLine())
          { pos = endOfLine(visually, doc.cm, lineObj, pos.line, lineDir); }
        else
          { return false }
      } else {
        pos = next;
      }
      return true
    }

    if (unit == "char" || unit == "codepoint") {
      moveOnce();
    } else if (unit == "column") {
      moveOnce(true);
    } else if (unit == "word" || unit == "group") {
      var sawType = null, group = unit == "group";
      var helper = doc.cm && doc.cm.getHelper(pos, "wordChars");
      for (var first = true;; first = false) {
        if (dir < 0 && !moveOnce(!first)) { break }
        var cur = lineObj.text.charAt(pos.ch) || "\n";
        var type = isWordChar(cur, helper) ? "w"
          : group && cur == "\n" ? "n"
          : !group || /\s/.test(cur) ? null
          : "p";
        if (group && !first && !type) { type = "s"; }
        if (sawType && sawType != type) {
          if (dir < 0) {dir = 1; moveOnce(); pos.sticky = "after";}
          break
        }

        if (type) { sawType = type; }
        if (dir > 0 && !moveOnce(!first)) { break }
      }
    }
    var result = skipAtomic(doc, pos, oldPos, origDir, true);
    if (equalCursorPos(oldPos, result)) { result.hitSide = true; }
    return result
  }
```
</details>

### `findNextLine(): any`

**Returns:** `any`

**Calls:**

- `getLine`

<details><summary>Code</summary>

```typescript
function findNextLine() {
      var l = pos.line + lineDir;
      if (l < doc.first || l >= doc.first + doc.size) { return false }
      pos = new Pos(l, pos.ch, pos.sticky);
      return lineObj = getLine(doc, l)
    }
```
</details>

### `moveOnce(boundToLine: any): boolean`

**Parameters:**

- **`boundToLine`** `any`

**Returns:** `boolean`

**Calls:**

- `lineObj.text.charCodeAt`
- `isNaN`
- `Math.max`
- `Math.min`
- `moveVisually`
- `moveLogically`
- `findNextLine`
- `endOfLine`

<details><summary>Code</summary>

```typescript
function moveOnce(boundToLine) {
      var next;
      if (unit == "codepoint") {
        var ch = lineObj.text.charCodeAt(pos.ch + (dir > 0 ? 0 : -1));
        if (isNaN(ch)) {
          next = null;
        } else {
          var astral = dir > 0 ? ch >= 0xD800 && ch < 0xDC00 : ch >= 0xDC00 && ch < 0xDFFF;
          next = new Pos(pos.line, Math.max(0, Math.min(lineObj.text.length, pos.ch + dir * (astral ? 2 : 1))), -dir);
        }
      } else if (visually) {
        next = moveVisually(doc.cm, lineObj, pos, dir);
      } else {
        next = moveLogically(lineObj, pos, dir);
      }
      if (next == null) {
        if (!boundToLine && findNextLine())
          { pos = endOfLine(visually, doc.cm, lineObj, pos.line, lineDir); }
        else
          { return false }
      } else {
        pos = next;
      }
      return true
    }
```
</details>

### `findPosV(cm: any, pos: any, dir: any, unit: any): any`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`dir`** `any`
- **`unit`** `any`

**Returns:** `any`

**Calls:**

- `Math.min`
- `Math.max`
- `textHeight`
- `coordsChar`

<details><summary>Code</summary>

```typescript
function findPosV(cm, pos, dir, unit) {
    var doc = cm.doc, x = pos.left, y;
    if (unit == "page") {
      var pageSize = Math.min(cm.display.wrapper.clientHeight, window.innerHeight || document.documentElement.clientHeight);
      var moveAmount = Math.max(pageSize - .5 * textHeight(cm.display), 3);
      y = (dir > 0 ? pos.bottom : pos.top) + dir * moveAmount;

    } else if (unit == "line") {
      y = dir > 0 ? pos.bottom + 3 : pos.top - 3;
    }
    var target;
    for (;;) {
      target = coordsChar(cm, x, y);
      if (!target.outside) { break }
      if (dir < 0 ? y <= 0 : y >= doc.height) { target.hitSide = true; break }
      y += dir * 5;
    }
    return target
  }
```
</details>

### `ContentEditableInput(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(cm) {
    this.cm = cm;
    this.lastAnchorNode = this.lastAnchorOffset = this.lastFocusNode = this.lastFocusOffset = null;
    this.polling = new Delayed();
    this.composing = null;
    this.gracePeriod = false;
    this.readDOMTimeout = null;
  }
```
</details>

### `belongsToInput(e: any): boolean`

**Parameters:**

- **`e`** `any`

**Returns:** `boolean`

**Calls:**

- `/\bCodeMirror-(?:line)?widget\b/.test`

<details><summary>Code</summary>

```typescript
function belongsToInput(e) {
      for (var t = e.target; t; t = t.parentNode) {
        if (t == div) { return true }
        if (/\bCodeMirror-(?:line)?widget\b/.test(t.className)) { break }
      }
      return false
    }
```
</details>

### `onCopyCut(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `belongsToInput`
- `signalDOMEvent`
- `cm.somethingSelected`
- `setLastCopied`
- `cm.getSelections`
- `cm.replaceSelection`
- `copyableRanges`
- `cm.operation`
- `cm.setSelections`
- `e.clipboardData.clearData`
- `lastCopied.text.join`
- `e.clipboardData.setData`
- `e.clipboardData.getData`
- `e.preventDefault`
- `hiddenTextarea`
- `cm.display.lineSpace.insertBefore`
- `activeElt`
- `selectInput`
- `setTimeout`
- `cm.display.lineSpace.removeChild`
- `hadFocus.focus`
- `input.showPrimarySelection`

**Internal Comments:**
```
// iOS exposes the clipboard API, but seems to discard content inserted into it (x5)
// Old-fashioned briefly-focus-a-textarea hack (x2)
```

<details><summary>Code</summary>

```typescript
function onCopyCut(e) {
      if (!belongsToInput(e) || signalDOMEvent(cm, e)) { return }
      if (cm.somethingSelected()) {
        setLastCopied({lineWise: false, text: cm.getSelections()});
        if (e.type == "cut") { cm.replaceSelection("", null, "cut"); }
      } else if (!cm.options.lineWiseCopyCut) {
        return
      } else {
        var ranges = copyableRanges(cm);
        setLastCopied({lineWise: true, text: ranges.text});
        if (e.type == "cut") {
          cm.operation(function () {
            cm.setSelections(ranges.ranges, 0, sel_dontScroll);
            cm.replaceSelection("", null, "cut");
          });
        }
      }
      if (e.clipboardData) {
        e.clipboardData.clearData();
        var content = lastCopied.text.join("\n");
        // iOS exposes the clipboard API, but seems to discard content inserted into it
        e.clipboardData.setData("Text", content);
        if (e.clipboardData.getData("Text") == content) {
          e.preventDefault();
          return
        }
      }
      // Old-fashioned briefly-focus-a-textarea hack
      var kludge = hiddenTextarea(), te = kludge.firstChild;
      cm.display.lineSpace.insertBefore(kludge, cm.display.lineSpace.firstChild);
      te.value = lastCopied.text.join("\n");
      var hadFocus = activeElt();
      selectInput(te);
      setTimeout(function () {
        cm.display.lineSpace.removeChild(kludge);
        hadFocus.focus();
        if (hadFocus == div) { input.showPrimarySelection(); }
      }, 50);
    }
```
</details>

### `poll(): void`

**Returns:** `void`

**Calls:**

- `input.pollSelection`
- `input.polling.set`

<details><summary>Code</summary>

```typescript
function poll() {
      if (input.cm.state.focused) {
        input.pollSelection();
        input.polling.set(input.cm.options.pollInterval, poll);
      }
    }
```
</details>

### `posToDOM(cm: any, pos: any): { node: any; start: number; end: number; collapse: any; coverStart: any; coverEnd: any; }`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`

**Returns:** `{ node: any; start: number; end: number; collapse: any; coverStart: any; coverEnd: any; }`

**Calls:**

- `findViewForLine`
- `getLine`
- `mapFromLineView`
- `getOrder`
- `getBidiPartAt`
- `nodeAndOffsetInLineMap`

<details><summary>Code</summary>

```typescript
function posToDOM(cm, pos) {
    var view = findViewForLine(cm, pos.line);
    if (!view || view.hidden) { return null }
    var line = getLine(cm.doc, pos.line);
    var info = mapFromLineView(view, line, pos.line);

    var order = getOrder(line, cm.doc.direction), side = "left";
    if (order) {
      var partPos = getBidiPartAt(order, pos.ch);
      side = partPos % 2 ? "right" : "left";
    }
    var result = nodeAndOffsetInLineMap(info.map, pos.ch, side);
    result.offset = result.collapse == "right" ? result.end : result.start;
    return result
  }
```
</details>

### `isInGutter(node: any): boolean`

**Parameters:**

- **`node`** `any`

**Returns:** `boolean`

**Calls:**

- `/CodeMirror-gutter-wrapper/.test`

<details><summary>Code</summary>

```typescript
function isInGutter(node) {
    for (var scan = node; scan; scan = scan.parentNode)
      { if (/CodeMirror-gutter-wrapper/.test(scan.className)) { return true } }
    return false
  }
```
</details>

### `badPos(pos: any, bad: any): any`

**Parameters:**

- **`pos`** `any`
- **`bad`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function badPos(pos, bad) { if (bad) { pos.bad = true; } return pos }
```
</details>

### `domTextBetween(cm: any, from: any, to: any, fromLine: any, toLine: any): string`

**Parameters:**

- **`cm`** `any`
- **`from`** `any`
- **`to`** `any`
- **`fromLine`** `any`
- **`toLine`** `any`

**Returns:** `string`

**Calls:**

- `cm.doc.lineSeparator`
- `close`
- `node.getAttribute`
- `addText`
- `cm.findMarks`
- `Pos`
- `recognizeMarker`
- `found[0].find`
- `getBetween(cm.doc, range.from, range.to).join`
- `/^(pre|div|p|li|table|br)$/i.test`
- `/^br$/i.test`
- `walk`
- `/^(pre|p)$/i.test`
- `node.nodeValue.replace(/\u200b/g, "").replace`

<details><summary>Code</summary>

```typescript
function domTextBetween(cm, from, to, fromLine, toLine) {
    var text = "", closing = false, lineSep = cm.doc.lineSeparator(), extraLinebreak = false;
    function recognizeMarker(id) { return function (marker) { return marker.id == id; } }
    function close() {
      if (closing) {
        text += lineSep;
        if (extraLinebreak) { text += lineSep; }
        closing = extraLinebreak = false;
      }
    }
    function addText(str) {
      if (str) {
        close();
        text += str;
      }
    }
    function walk(node) {
      if (node.nodeType == 1) {
        var cmText = node.getAttribute("cm-text");
        if (cmText) {
          addText(cmText);
          return
        }
        var markerID = node.getAttribute("cm-marker"), range;
        if (markerID) {
          var found = cm.findMarks(Pos(fromLine, 0), Pos(toLine + 1, 0), recognizeMarker(+markerID));
          if (found.length && (range = found[0].find(0)))
            { addText(getBetween(cm.doc, range.from, range.to).join(lineSep)); }
          return
        }
        if (node.getAttribute("contenteditable") == "false") { return }
        var isBlock = /^(pre|div|p|li|table|br)$/i.test(node.nodeName);
        if (!/^br$/i.test(node.nodeName) && node.textContent.length == 0) { return }

        if (isBlock) { close(); }
        for (var i = 0; i < node.childNodes.length; i++)
          { walk(node.childNodes[i]); }

        if (/^(pre|p)$/i.test(node.nodeName)) { extraLinebreak = true; }
        if (isBlock) { closing = true; }
      } else if (node.nodeType == 3) {
        addText(node.nodeValue.replace(/\u200b/g, "").replace(/\u00a0/g, " "));
      }
    }
    for (;;) {
      walk(from);
      if (from == to) { break }
      from = from.nextSibling;
      extraLinebreak = false;
    }
    return text
  }
```
</details>

### `recognizeMarker(id: any): (marker: any) => boolean`

**Parameters:**

- **`id`** `any`

**Returns:** `(marker: any) => boolean`

<details><summary>Code</summary>

```typescript
function recognizeMarker(id) { return function (marker) { return marker.id == id; } }
```
</details>

### `close(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function close() {
      if (closing) {
        text += lineSep;
        if (extraLinebreak) { text += lineSep; }
        closing = extraLinebreak = false;
      }
    }
```
</details>

### `addText(str: any): void`

**Parameters:**

- **`str`** `any`

**Returns:** `void`

**Calls:**

- `close`

<details><summary>Code</summary>

```typescript
function addText(str) {
      if (str) {
        close();
        text += str;
      }
    }
```
</details>

### `walk(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `node.getAttribute`
- `addText`
- `cm.findMarks`
- `Pos`
- `recognizeMarker`
- `found[0].find`
- `getBetween(cm.doc, range.from, range.to).join`
- `/^(pre|div|p|li|table|br)$/i.test`
- `/^br$/i.test`
- `close`
- `walk`
- `/^(pre|p)$/i.test`
- `node.nodeValue.replace(/\u200b/g, "").replace`

<details><summary>Code</summary>

```typescript
function walk(node) {
      if (node.nodeType == 1) {
        var cmText = node.getAttribute("cm-text");
        if (cmText) {
          addText(cmText);
          return
        }
        var markerID = node.getAttribute("cm-marker"), range;
        if (markerID) {
          var found = cm.findMarks(Pos(fromLine, 0), Pos(toLine + 1, 0), recognizeMarker(+markerID));
          if (found.length && (range = found[0].find(0)))
            { addText(getBetween(cm.doc, range.from, range.to).join(lineSep)); }
          return
        }
        if (node.getAttribute("contenteditable") == "false") { return }
        var isBlock = /^(pre|div|p|li|table|br)$/i.test(node.nodeName);
        if (!/^br$/i.test(node.nodeName) && node.textContent.length == 0) { return }

        if (isBlock) { close(); }
        for (var i = 0; i < node.childNodes.length; i++)
          { walk(node.childNodes[i]); }

        if (/^(pre|p)$/i.test(node.nodeName)) { extraLinebreak = true; }
        if (isBlock) { closing = true; }
      } else if (node.nodeType == 3) {
        addText(node.nodeValue.replace(/\u200b/g, "").replace(/\u00a0/g, " "));
      }
    }
```
</details>

### `domToPos(cm: any, node: any, offset: any): any`

**Parameters:**

- **`cm`** `any`
- **`node`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `badPos`
- `cm.clipPos`
- `Pos`
- `locateNodeInLineView`

<details><summary>Code</summary>

```typescript
function domToPos(cm, node, offset) {
    var lineNode;
    if (node == cm.display.lineDiv) {
      lineNode = cm.display.lineDiv.childNodes[offset];
      if (!lineNode) { return badPos(cm.clipPos(Pos(cm.display.viewTo - 1)), true) }
      node = null; offset = 0;
    } else {
      for (lineNode = node;; lineNode = lineNode.parentNode) {
        if (!lineNode || lineNode == cm.display.lineDiv) { return null }
        if (lineNode.parentNode && lineNode.parentNode == cm.display.lineDiv) { break }
      }
    }
    for (var i = 0; i < cm.display.view.length; i++) {
      var lineView = cm.display.view[i];
      if (lineView.node == lineNode)
        { return locateNodeInLineView(lineView, node, offset) }
    }
  }
```
</details>

### `locateNodeInLineView(lineView: any, node: any, offset: any): any`

**Parameters:**

- **`lineView`** `any`
- **`node`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `contains`
- `badPos`
- `Pos`
- `lineNo`
- `lst`
- `find`

**Internal Comments:**
```
// FIXME this is all really shaky. might handle the few cases it needs to handle, but likely to cause problems
```

<details><summary>Code</summary>

```typescript
function locateNodeInLineView(lineView, node, offset) {
    var wrapper = lineView.text.firstChild, bad = false;
    if (!node || !contains(wrapper, node)) { return badPos(Pos(lineNo(lineView.line), 0), true) }
    if (node == wrapper) {
      bad = true;
      node = wrapper.childNodes[offset];
      offset = 0;
      if (!node) {
        var line = lineView.rest ? lst(lineView.rest) : lineView.line;
        return badPos(Pos(lineNo(line), line.text.length), bad)
      }
    }

    var textNode = node.nodeType == 3 ? node : null, topNode = node;
    if (!textNode && node.childNodes.length == 1 && node.firstChild.nodeType == 3) {
      textNode = node.firstChild;
      if (offset) { offset = textNode.nodeValue.length; }
    }
    while (topNode.parentNode != wrapper) { topNode = topNode.parentNode; }
    var measure = lineView.measure, maps = measure.maps;

    function find(textNode, topNode, offset) {
      for (var i = -1; i < (maps ? maps.length : 0); i++) {
        var map = i < 0 ? measure.map : maps[i];
        for (var j = 0; j < map.length; j += 3) {
          var curNode = map[j + 2];
          if (curNode == textNode || curNode == topNode) {
            var line = lineNo(i < 0 ? lineView.line : lineView.rest[i]);
            var ch = map[j] + offset;
            if (offset < 0 || curNode != textNode) { ch = map[j + (offset ? 1 : 0)]; }
            return Pos(line, ch)
          }
        }
      }
    }
    var found = find(textNode, topNode, offset);
    if (found) { return badPos(found, bad) }

    // FIXME this is all really shaky. might handle the few cases it needs to handle, but likely to cause problems
    for (var after = topNode.nextSibling, dist = textNode ? textNode.nodeValue.length - offset : 0; after; after = after.nextSibling) {
      found = find(after, after.firstChild, 0);
      if (found)
        { return badPos(Pos(found.line, found.ch - dist), bad) }
      else
        { dist += after.textContent.length; }
    }
    for (var before = topNode.previousSibling, dist$1 = offset; before; before = before.previousSibling) {
      found = find(before, before.firstChild, -1);
      if (found)
        { return badPos(Pos(found.line, found.ch + dist$1), bad) }
      else
        { dist$1 += before.textContent.length; }
    }
  }
```
</details>

### `find(textNode: any, topNode: any, offset: any): Pos`

**Parameters:**

- **`textNode`** `any`
- **`topNode`** `any`
- **`offset`** `any`

**Returns:** `Pos`

**Calls:**

- `lineNo`
- `Pos`

<details><summary>Code</summary>

```typescript
function find(textNode, topNode, offset) {
      for (var i = -1; i < (maps ? maps.length : 0); i++) {
        var map = i < 0 ? measure.map : maps[i];
        for (var j = 0; j < map.length; j += 3) {
          var curNode = map[j + 2];
          if (curNode == textNode || curNode == topNode) {
            var line = lineNo(i < 0 ? lineView.line : lineView.rest[i]);
            var ch = map[j] + offset;
            if (offset < 0 || curNode != textNode) { ch = map[j + (offset ? 1 : 0)]; }
            return Pos(line, ch)
          }
        }
      }
    }
```
</details>

### `TextareaInput(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Internal Comments:**
```
// See input.poll and input.reset (x4)
// Flag that indicates whether we expect input to appear real soon (x4)
// now (after some event like 'keypress' or 'input') and are (x4)
// polling intensively. (x4)
// Self-resetting timeout for the poller (x4)
// Used to work around IE issue with selection being forgotten when focus moves away from textarea (x4)
```

<details><summary>Code</summary>

```typescript
function(cm) {
    this.cm = cm;
    // See input.poll and input.reset
    this.prevInput = "";

    // Flag that indicates whether we expect input to appear real soon
    // now (after some event like 'keypress' or 'input') and are
    // polling intensively.
    this.pollingFast = false;
    // Self-resetting timeout for the poller
    this.polling = new Delayed();
    // Used to work around IE issue with selection being forgotten when focus moves away from textarea
    this.hasSelection = false;
    this.composing = null;
  }
```
</details>

### `prepareCopyCut(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `signalDOMEvent`
- `cm.somethingSelected`
- `setLastCopied`
- `cm.getSelections`
- `copyableRanges`
- `cm.setSelections`
- `ranges.text.join`
- `selectInput`

<details><summary>Code</summary>

```typescript
function prepareCopyCut(e) {
      if (signalDOMEvent(cm, e)) { return }
      if (cm.somethingSelected()) {
        setLastCopied({lineWise: false, text: cm.getSelections()});
      } else if (!cm.options.lineWiseCopyCut) {
        return
      } else {
        var ranges = copyableRanges(cm);
        setLastCopied({lineWise: true, text: ranges.text});
        if (e.type == "cut") {
          cm.setSelections(ranges.ranges, null, sel_dontScroll);
        } else {
          input.prevInput = "";
          te.value = ranges.text.join("\n");
          selectInput(te);
        }
      }
      if (e.type == "cut") { cm.state.cutIncoming = +new Date; }
    }
```
</details>

### `p(): void`

**Returns:** `void`

**Calls:**

- `input.poll`
- `input.polling.set`
- `input.slowPoll`

<details><summary>Code</summary>

```typescript
function p() {
      var changed = input.poll();
      if (!changed && !missed) {missed = true; input.polling.set(60, p);}
      else {input.pollingFast = false; input.slowPoll();}
    }
```
</details>

### `prepareSelectAllHack(): void`

**Returns:** `void`

**Calls:**

- `cm.somethingSelected`

**Internal Comments:**
```
// Re-set this, in case some other handler touched the (x4)
// selection in the meantime. (x4)
```

<details><summary>Code</summary>

```typescript
function prepareSelectAllHack() {
      if (te.selectionStart != null) {
        var selected = cm.somethingSelected();
        var extval = "\u200b" + (selected ? te.value : "");
        te.value = "\u21da"; // Used to catch context-menu undo
        te.value = extval;
        input.prevInput = selected ? "" : "\u200b";
        te.selectionStart = 1; te.selectionEnd = extval.length;
        // Re-set this, in case some other handler touched the
        // selection in the meantime.
        display.selForContextMenu = cm.doc.sel;
      }
    }
```
</details>

### `rehide(): void`

**Returns:** `void`

**Calls:**

- `display.scrollbars.setScrollTop`
- `prepareSelectAllHack`
- `complex_call_394033`
- `setTimeout`
- `display.input.reset`

**Internal Comments:**
```
// Try to detect the user choosing select-all
```

<details><summary>Code</summary>

```typescript
function rehide() {
      if (input.contextMenuPending != rehide) { return }
      input.contextMenuPending = false;
      input.wrapper.style.cssText = oldWrapperCSS;
      te.style.cssText = oldCSS;
      if (ie && ie_version < 9) { display.scrollbars.setScrollTop(display.scroller.scrollTop = scrollPos); }

      // Try to detect the user choosing select-all
      if (te.selectionStart != null) {
        if (!ie || (ie && ie_version < 9)) { prepareSelectAllHack(); }
        var i = 0, poll = function () {
          if (display.selForContextMenu == cm.doc.sel && te.selectionStart == 0 &&
              te.selectionEnd > 0 && input.prevInput == "\u200b") {
            operation(cm, selectAll)(cm);
          } else if (i++ < 10) {
            display.detectingSelectAll = setTimeout(poll, 500);
          } else {
            display.selForContextMenu = null;
            display.input.reset();
          }
        };
        display.detectingSelectAll = setTimeout(poll, 200);
      }
    }
```
</details>

### `poll(): void`

**Returns:** `void`

**Calls:**

- `complex_call_394033`
- `setTimeout`
- `display.input.reset`

<details><summary>Code</summary>

```typescript
function () {
          if (display.selForContextMenu == cm.doc.sel && te.selectionStart == 0 &&
              te.selectionEnd > 0 && input.prevInput == "\u200b") {
            operation(cm, selectAll)(cm);
          } else if (i++ < 10) {
            display.detectingSelectAll = setTimeout(poll, 500);
          } else {
            display.selForContextMenu = null;
            display.input.reset();
          }
        }
```
</details>

### `mouseup(): void`

**Returns:** `void`

**Calls:**

- `off`
- `setTimeout`

<details><summary>Code</summary>

```typescript
function () {
        off(window, "mouseup", mouseup);
        setTimeout(rehide, 20);
      }
```
</details>

### `fromTextArea(textarea: any, options: any): CodeMirror`

**Parameters:**

- **`textarea`** `any`
- **`options`** `any`

**Returns:** `CodeMirror`

**Calls:**

- `copyObj`
- `activeElt`
- `textarea.getAttribute`
- `cm.getValue`
- `on`
- `save`
- `form.submit`
- `textarea.parentNode.removeChild`
- `cm.getWrapperElement`
- `off`
- `CodeMirror`
- `textarea.parentNode.insertBefore`

**Internal Comments:**
```
// Set autofocus to true if this textarea is focused, or if it has
// autofocus and no other element is focused.
// Deplorable hack to make the submit method do the right thing.
```

<details><summary>Code</summary>

```typescript
function fromTextArea(textarea, options) {
    options = options ? copyObj(options) : {};
    options.value = textarea.value;
    if (!options.tabindex && textarea.tabIndex)
      { options.tabindex = textarea.tabIndex; }
    if (!options.placeholder && textarea.placeholder)
      { options.placeholder = textarea.placeholder; }
    // Set autofocus to true if this textarea is focused, or if it has
    // autofocus and no other element is focused.
    if (options.autofocus == null) {
      var hasFocus = activeElt();
      options.autofocus = hasFocus == textarea ||
        textarea.getAttribute("autofocus") != null && hasFocus == document.body;
    }

    function save() {textarea.value = cm.getValue();}

    var realSubmit;
    if (textarea.form) {
      on(textarea.form, "submit", save);
      // Deplorable hack to make the submit method do the right thing.
      if (!options.leaveSubmitMethodAlone) {
        var form = textarea.form;
        realSubmit = form.submit;
        try {
          var wrappedSubmit = form.submit = function () {
            save();
            form.submit = realSubmit;
            form.submit();
            form.submit = wrappedSubmit;
          };
        } catch(e) {}
      }
    }

    options.finishInit = function (cm) {
      cm.save = save;
      cm.getTextArea = function () { return textarea; };
      cm.toTextArea = function () {
        cm.toTextArea = isNaN; // Prevent this from being ran twice
        save();
        textarea.parentNode.removeChild(cm.getWrapperElement());
        textarea.style.display = "";
        if (textarea.form) {
          off(textarea.form, "submit", save);
          if (!options.leaveSubmitMethodAlone && typeof textarea.form.submit == "function")
            { textarea.form.submit = realSubmit; }
        }
      };
    };

    textarea.style.display = "none";
    var cm = CodeMirror(function (node) { return textarea.parentNode.insertBefore(node, textarea.nextSibling); },
      options);
    return cm
  }
```
</details>

### `save(): void`

**Returns:** `void`

**Calls:**

- `cm.getValue`

<details><summary>Code</summary>

```typescript
function save() {textarea.value = cm.getValue();}
```
</details>

### `addLegacyProps(CodeMirror: any): void`

**Parameters:**

- **`CodeMirror`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function addLegacyProps(CodeMirror) {
    CodeMirror.off = off;
    CodeMirror.on = on;
    CodeMirror.wheelEventPixels = wheelEventPixels;
    CodeMirror.Doc = Doc;
    CodeMirror.splitLines = splitLinesAuto;
    CodeMirror.countColumn = countColumn;
    CodeMirror.findColumn = findColumn;
    CodeMirror.isWordChar = isWordCharBasic;
    CodeMirror.Pass = Pass;
    CodeMirror.signal = signal;
    CodeMirror.Line = Line;
    CodeMirror.changeEnd = changeEnd;
    CodeMirror.scrollbarModel = scrollbarModel;
    CodeMirror.Pos = Pos;
    CodeMirror.cmpPos = cmp;
    CodeMirror.modes = modes;
    CodeMirror.mimeModes = mimeModes;
    CodeMirror.resolveMode = resolveMode;
    CodeMirror.getMode = getMode;
    CodeMirror.modeExtensions = modeExtensions;
    CodeMirror.extendMode = extendMode;
    CodeMirror.copyState = copyState;
    CodeMirror.startState = startState;
    CodeMirror.innerMode = innerMode;
    CodeMirror.commands = commands;
    CodeMirror.keyMap = keyMap;
    CodeMirror.keyName = keyName;
    CodeMirror.isModifierKey = isModifierKey;
    CodeMirror.lookupKey = lookupKey;
    CodeMirror.normalizeKeyMap = normalizeKeyMap;
    CodeMirror.StringStream = StringStream;
    CodeMirror.SharedTextMarker = SharedTextMarker;
    CodeMirror.TextMarker = TextMarker;
    CodeMirror.LineWidget = LineWidget;
    CodeMirror.e_preventDefault = e_preventDefault;
    CodeMirror.e_stopPropagation = e_stopPropagation;
    CodeMirror.e_stop = e_stop;
    CodeMirror.addClass = addClass;
    CodeMirror.contains = contains;
    CodeMirror.rmClass = rmClass;
    CodeMirror.keyNames = keyNames;
  }
```
</details>

### `token(stream: any): any`

**Parameters:**

- **`stream`** `any`

**Returns:** `any`

**Calls:**

- `stream.skipToEnd`

<details><summary>Code</summary>

```typescript
function (stream) { return stream.skipToEnd(); }
```
</details>

### `token(stream: any): any`

**Parameters:**

- **`stream`** `any`

**Returns:** `any`

**Calls:**

- `stream.skipToEnd`

<details><summary>Code</summary>

```typescript
function (stream) { return stream.skipToEnd(); }
```
</details>


---