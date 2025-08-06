[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `opentype.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 452 |
| 📊 Variables & Constants | 1129 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/opentype.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `object` | `{}` | let/var | `{}` | ✗ |
| `$defineProperty` | `<T>(o: T, p: PropertyKey, attributes:...` | let/var | `Object.defineProperty` | ✗ |
| `result` | `<T>(o: T, p: PropertyKey, attributes:...` | let/var | `$defineProperty(object, object, object) && $defineProperty` | ✗ |
| `defineProperty` | `<T>(o: T, p: PropertyKey, attributes:...` | let/var | `(function() { // IE 8 only supports `Object.defineProperty` on DOM elements t...` | ✗ |
| `size` | `number` | let/var | `string.length` | ✗ |
| `index` | `number` | let/var | `position ? Number(position) : 0` | ✗ |
| `second` | `any` | let/var | `*not shown*` | ✗ |
| `TINF_OK` | `number` | let/var | `0` | ✗ |
| `TINF_DATA_ERROR` | `number` | let/var | `-3` | ✗ |
| `sltree` | `Tree` | let/var | `new Tree()` | ✗ |
| `sdtree` | `Tree` | let/var | `new Tree()` | ✗ |
| `length_bits` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(30)` | ✗ |
| `length_base` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array(30)` | ✗ |
| `dist_bits` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(30)` | ✗ |
| `dist_base` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array(30)` | ✗ |
| `clcidx` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array([ 16, 17, 18, 0, 8, 7, 9, 6, 10, 5, 11, 4, 12, 3, 13, 2, 14, 1...` | ✗ |
| `code_tree` | `Tree` | let/var | `new Tree()` | ✗ |
| `lengths` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(288 + 32)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `sum` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `offs` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array(16)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `sum` | `any` | let/var | `*not shown*` | ✗ |
| `bit` | `number` | let/var | `d.tag & 1` | ✗ |
| `val` | `number` | let/var | `d.tag & (0xffff >>> (16 - num))` | ✗ |
| `sum` | `number` | let/var | `0` | ✗ |
| `cur` | `number` | let/var | `0` | ✗ |
| `len` | `number` | let/var | `0` | ✗ |
| `tag` | `any` | let/var | `d.tag` | ✗ |
| `hlit` | `any` | let/var | `*not shown*` | ✗ |
| `hdist` | `any` | let/var | `*not shown*` | ✗ |
| `hclen` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `num` | `any` | let/var | `*not shown*` | ✗ |
| `length` | `any` | let/var | `*not shown*` | ✗ |
| `prev` | `number` | let/var | `lengths[num - 1]` | ✗ |
| `length` | `any` | let/var | `*not shown*` | ✗ |
| `dist` | `any` | let/var | `*not shown*` | ✗ |
| `offs` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `length` | `any` | let/var | `*not shown*` | ✗ |
| `invlength` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `Data` | let/var | `new Data(source, dest)` | ✗ |
| `bfinal` | `any` | let/var | `*not shown*` | ✗ |
| `btype` | `any` | let/var | `*not shown*` | ✗ |
| `res` | `any` | let/var | `*not shown*` | ✗ |
| `tinyInflate` | `(source: any, dest: any) => any` | let/var | `tinf_uncompress` | ✗ |
| `p0` | `number[]` | let/var | `[x0, y0]` | ✗ |
| `p1` | `number[]` | let/var | `[x1, y1]` | ✗ |
| `p2` | `number[]` | let/var | `[x2, y2]` | ✗ |
| `p3` | `number[]` | let/var | `[x, y]` | ✗ |
| `b` | `number` | let/var | `6 * p0[i] - 12 * p1[i] + 6 * p2[i]` | ✗ |
| `a` | `number` | let/var | `-3 * p0[i] + 9 * p1[i] - 9 * p2[i] + 3 * p3[i]` | ✗ |
| `c` | `number` | let/var | `3 * p1[i] - 3 * p0[i]` | ✗ |
| `t` | `number` | let/var | `-c / b` | ✗ |
| `b2ac` | `number` | let/var | `Math.pow(b, 2) - 4 * c * a` | ✗ |
| `t1` | `number` | let/var | `(-b + Math.sqrt(b2ac)) / (2 * a)` | ✗ |
| `t2` | `number` | let/var | `(-b - Math.sqrt(b2ac)) / (2 * a)` | ✗ |
| `cp1x` | `number` | let/var | `x0 + 2 / 3 * (x1 - x0)` | ✗ |
| `cp1y` | `number` | let/var | `y0 + 2 / 3 * (y1 - y0)` | ✗ |
| `cp2x` | `number` | let/var | `cp1x + 1 / 3 * (x - x0)` | ✗ |
| `cp2y` | `number` | let/var | `cp1y + 1 / 3 * (y - y0)` | ✗ |
| `box` | `any[] & BoundingBox` | let/var | `pathOrCommands` | ✗ |
| `box` | `BoundingBox` | let/var | `new BoundingBox()` | ✗ |
| `startX` | `number` | let/var | `0` | ✗ |
| `startY` | `number` | let/var | `0` | ✗ |
| `prevX` | `number` | let/var | `0` | ✗ |
| `prevY` | `number` | let/var | `0` | ✗ |
| `cmd` | `any` | let/var | `this.commands[i]` | ✗ |
| `cmd` | `any` | let/var | `this.commands[i]` | ✗ |
| `arguments$1` | `IArguments` | let/var | `arguments` | ✗ |
| `s` | `string` | let/var | `''` | ✗ |
| `v` | `any` | let/var | `arguments$1[i]` | ✗ |
| `d` | `string` | let/var | `''` | ✗ |
| `cmd` | `any` | let/var | `this.commands[i]` | ✗ |
| `svg` | `string` | let/var | `'<path d="'` | ✗ |
| `check` | `{ fail: (message: any) => void; argum...` | let/var | `{ fail: fail, argument: argument, assert: argument }` | ✗ |
| `LIMIT16` | `number` | let/var | `32768` | ✗ |
| `LIMIT32` | `number` | let/var | `2147483648` | ✗ |
| `decode` | `typeof decode` | let/var | `{}` | ✗ |
| `encode` | `typeof encode` | let/var | `{}` | ✗ |
| `sizeOf` | `typeof sizeOf` | let/var | `{}` | ✗ |
| `b` | `any[]` | let/var | `[]` | ✗ |
| `nibbles` | `string` | let/var | `''` | ✗ |
| `c` | `any` | let/var | `value[i]` | ✗ |
| `out` | `number[]` | let/var | `[30]` | ✗ |
| `codePoints` | `any[]` | let/var | `[]` | ✗ |
| `numChars` | `number` | let/var | `numBytes` | ✗ |
| `codePoints` | `any[]` | let/var | `[]` | ✗ |
| `numChars` | `number` | let/var | `numBytes / 2` | ✗ |
| `b` | `any[]` | let/var | `[]` | ✗ |
| `eightBitMacEncodings` | `{ 'x-mac-croatian': string; 'x-mac-cy...` | let/var | `{ 'x-mac-croatian': // Python: 'mac_croatian' 'ÄÅÇÉÑÖÜáàâäãåçéèêëíìîïñóòôöõúù...` | ✗ |
| `table` | `any` | let/var | `eightBitMacEncodings[encoding]` | ✗ |
| `result` | `string` | let/var | `''` | ✗ |
| `macEncodingTableCache` | `WeakMap<WeakKey, any>` | let/var | `typeof WeakMap === 'function' && new WeakMap()` | ✗ |
| `macEncodingCacheKeys` | `any` | let/var | `*not shown*` | ✗ |
| `cacheKey` | `any` | let/var | `macEncodingCacheKeys[encoding]` | ✗ |
| `decodingTable` | `any` | let/var | `eightBitMacEncodings[encoding]` | ✗ |
| `encodingTable` | `{}` | let/var | `{}` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `runLength` | `number` | let/var | `0` | ✗ |
| `numDeltas` | `any` | let/var | `deltas.length` | ✗ |
| `runLength` | `number` | let/var | `0` | ✗ |
| `numDeltas` | `any` | let/var | `deltas.length` | ✗ |
| `pos` | `any` | let/var | `offset` | ✗ |
| `value` | `any` | let/var | `deltas[pos]` | ✗ |
| `runLength` | `number` | let/var | `0` | ✗ |
| `numDeltas` | `any` | let/var | `deltas.length` | ✗ |
| `pos` | `any` | let/var | `offset` | ✗ |
| `value` | `any` | let/var | `deltas[pos]` | ✗ |
| `val` | `any` | let/var | `deltas[i]` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `value` | `any` | let/var | `deltas[pos]` | ✗ |
| `offset` | `number` | let/var | `1` | ✗ |
| `offsets` | `number[]` | let/var | `[offset]` | ✗ |
| `data` | `any[]` | let/var | `[]` | ✗ |
| `encodedOffsets` | `any[]` | let/var | `[]` | ✗ |
| `offSize` | `number` | let/var | `(1 + Math.floor(Math.log(offset) / Math.log(2)) / 8) \| 0` | ✗ |
| `offsetEncoder` | `(v: any) => any[]` | let/var | `[undefined, encode.BYTE, encode.USHORT, encode.UINT24, encode.ULONG][offSize]` | ✗ |
| `d` | `any[]` | let/var | `[]` | ✗ |
| `length` | `number` | let/var | `keys.length` | ✗ |
| `v` | `any` | let/var | `m[k]` | ✗ |
| `d` | `any[]` | let/var | `[]` | ✗ |
| `wmm` | `WeakMap<WeakKey, any>` | let/var | `typeof WeakMap === 'function' && new WeakMap()` | ✗ |
| `d` | `any[]` | let/var | `[]` | ✗ |
| `length` | `any` | let/var | `ops.length` | ✗ |
| `op` | `any` | let/var | `ops[i]` | ✗ |
| `encodingFunction` | `any` | let/var | `encode[v.type]` | ✗ |
| `sizeOfFunction` | `any` | let/var | `sizeOf[v.type]` | ✗ |
| `d` | `any[]` | let/var | `[]` | ✗ |
| `length` | `any` | let/var | `table.fields.length` | ✗ |
| `subtables` | `any[]` | let/var | `[]` | ✗ |
| `subtableOffsets` | `any[]` | let/var | `[]` | ✗ |
| `field` | `any` | let/var | `table.fields[i]` | ✗ |
| `encodingFunction` | `any` | let/var | `encode[field.type]` | ✗ |
| `value` | `any` | let/var | `table[field.name]` | ✗ |
| `o` | `number` | let/var | `subtableOffsets[i$1]` | ✗ |
| `offset` | `number` | let/var | `d.length` | ✗ |
| `numBytes` | `number` | let/var | `0` | ✗ |
| `length` | `any` | let/var | `table.fields.length` | ✗ |
| `field` | `any` | let/var | `table.fields[i]` | ✗ |
| `sizeOfFunction` | `any` | let/var | `sizeOf[field.type]` | ✗ |
| `value` | `any` | let/var | `table[field.name]` | ✗ |
| `field` | `any` | let/var | `fields[i]` | ✗ |
| `k` | `string` | let/var | `optionKeys[i$1]` | ✗ |
| `v` | `any` | let/var | `options[k]` | ✗ |
| `fields` | `any[]` | let/var | `new Array(list.length + 1)` | ✗ |
| `count` | `any` | let/var | `records.length` | ✗ |
| `fields` | `any[]` | let/var | `new Array(count + 1)` | ✗ |
| `count` | `any` | let/var | `records.length` | ✗ |
| `fields` | `any[]` | let/var | `[]` | ✗ |
| `script` | `any` | let/var | `scriptRecord.script` | ✗ |
| `defaultLangSys` | `any` | let/var | `script.defaultLangSys` | ✗ |
| `langSys` | `any` | let/var | `langSysRecord.langSys` | ✗ |
| `feature` | `any` | let/var | `featureRecord.feature` | ✗ |
| `subtableCallback` | `any` | let/var | `subtableMakers[lookupTable.lookupType]` | ✗ |
| `table` | `{ Table: typeof Table; Record: typeof...` | let/var | `{ Table: Table, Record: Table, Coverage: Coverage, ScriptList: ScriptList, Fe...` | ✗ |
| `tag` | `string` | let/var | `''` | ✗ |
| `v` | `number` | let/var | `0` | ✗ |
| `bytes` | `any[]` | let/var | `[]` | ✗ |
| `s` | `string` | let/var | `''` | ✗ |
| `typeOffsets` | `{ byte: number; uShort: number; short...` | let/var | `{ byte: 1, uShort: 2, short: 2, uLong: 4, fixed: 4, longDateTime: 8, tag: 4 }` | ✗ |
| `v` | `number` | let/var | `this.data.getInt16(this.offset + this.relativeOffset) / 16384` | ✗ |
| `dataView` | `any` | let/var | `this.data` | ✗ |
| `offset` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `string` | `string` | let/var | `''` | ✗ |
| `offsets` | `any[]` | let/var | `new Array(count)` | ✗ |
| `dataView` | `any` | let/var | `this.data` | ✗ |
| `offset` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `offsets` | `any[]` | let/var | `new Array(count)` | ✗ |
| `dataView` | `any` | let/var | `this.data` | ✗ |
| `offset` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `list` | `any[]` | let/var | `new Array(count)` | ✗ |
| `dataView` | `any` | let/var | `this.data` | ✗ |
| `offset` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `list` | `any[]` | let/var | `new Array(count)` | ✗ |
| `dataView` | `any` | let/var | `this.data` | ✗ |
| `offset` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `list` | `any[]` | let/var | `new Array(count)` | ✗ |
| `list` | `any[]` | let/var | `new Array(count)` | ✗ |
| `records` | `any[]` | let/var | `new Array(count)` | ✗ |
| `rec` | `{}` | let/var | `{}` | ✗ |
| `fieldName` | `string` | let/var | `fields[j]` | ✗ |
| `fieldType` | `any` | let/var | `recordDescription[fieldName]` | ✗ |
| `records` | `any[]` | let/var | `new Array(count)` | ✗ |
| `rec` | `{}` | let/var | `{}` | ✗ |
| `fieldName` | `string` | let/var | `fields[j]` | ✗ |
| `fieldType` | `any` | let/var | `recordDescription[fieldName]` | ✗ |
| `struct` | `{}` | let/var | `{}` | ✗ |
| `fieldName` | `string` | let/var | `fields[j]` | ✗ |
| `fieldType` | `any` | let/var | `description[fieldName]` | ✗ |
| `valueRecord` | `{ xPlacement: any; yPlacement: any; x...` | let/var | `{}` | ✗ |
| `values` | `any[]` | let/var | `new Array(valueCount)` | ✗ |
| `count` | `number` | let/var | `offsets.length` | ✗ |
| `relativeOffset` | `number` | let/var | `this.relativeOffset` | ✗ |
| `list` | `any[]` | let/var | `new Array(count)` | ✗ |
| `start` | `any` | let/var | `offsets[i]` | ✗ |
| `subList` | `any[]` | let/var | `new Array(subOffsets.length)` | ✗ |
| `startOffset` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `ranges` | `any[]` | let/var | `new Array(count)` | ✗ |
| `startOffset` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `langSysTable` | `{ reserved: any; reqFeatureIndex: any...` | let/var | `{ reserved: Parser.uShort, reqFeatureIndex: Parser.uShort, featureIndexes: Pa...` | ✗ |
| `useMarkFilteringSet` | `number` | let/var | `lookupFlag & 0x10` | ✗ |
| `parse` | `{ getByte: (dataView: any, offset: an...` | let/var | `{ getByte: getByte, getCard8: getByte, getUShort: getUShort, getCard16: getUS...` | ✗ |
| `groupCount` | `any` | let/var | `*not shown*` | ✗ |
| `segCount` | `any` | let/var | `*not shown*` | ✗ |
| `endCountParser` | `Parser` | let/var | `new parse.Parser(data, start + offset + 14)` | ✗ |
| `startCountParser` | `Parser` | let/var | `new parse.Parser(data, start + offset + 16 + segCount * 2)` | ✗ |
| `idDeltaParser` | `Parser` | let/var | `new parse.Parser(data, start + offset + 16 + segCount * 4)` | ✗ |
| `idRangeOffsetParser` | `Parser` | let/var | `new parse.Parser(data, start + offset + 16 + segCount * 6)` | ✗ |
| `glyphIndexOffset` | `any` | let/var | `start + offset + 16 + segCount * 8` | ✗ |
| `glyphIndex` | `any` | let/var | `(void 0)` | ✗ |
| `cmap` | `{ version: any; numTables: any; forma...` | let/var | `{}` | ✗ |
| `offset` | `number` | let/var | `-1` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start + offset)` | ✗ |
| `isPlan0Only` | `boolean` | let/var | `true` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `cmapTable` | `{ name: string; type: string; value: ...` | let/var | `[ {name: 'version', type: 'USHORT', value: 0}, {name: 'numTables', type: 'USH...` | ✗ |
| `t` | `Table` | let/var | `new table.Table('cmap', cmapTable)` | ✗ |
| `segCount` | `any` | let/var | `t.segments.length` | ✗ |
| `segCountToRemove` | `number` | let/var | `0` | ✗ |
| `endCounts` | `any[]` | let/var | `[]` | ✗ |
| `startCounts` | `any[]` | let/var | `[]` | ✗ |
| `idDeltas` | `any[]` | let/var | `[]` | ✗ |
| `idRangeOffsets` | `any[]` | let/var | `[]` | ✗ |
| `glyphIds` | `any[]` | let/var | `[]` | ✗ |
| `cmap12Groups` | `any[]` | let/var | `[]` | ✗ |
| `segment` | `any` | let/var | `t.segments[i]` | ✗ |
| `cmap12Length` | `number` | let/var | `16 + // Subtable header cmap12Groups.length * 4` | ✗ |
| `cmap` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseCmapTable, make: makeCmapTable }` | ✗ |
| `cffStandardStrings` | `string[]` | let/var | `[ '.notdef', 'space', 'exclam', 'quotedbl', 'numbersign', 'dollar', 'percent'...` | ✗ |
| `cffStandardEncoding` | `string[]` | let/var | `[ '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '',...` | ✗ |
| `cffExpertEncoding` | `string[]` | let/var | `[ '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '',...` | ✗ |
| `standardNames` | `string[]` | let/var | `[ '.notdef', '.null', 'nonmarkingreturn', 'space', 'exclam', 'quotedbl', 'num...` | ✗ |
| `glyphs` | `any` | let/var | `this.font.glyphs` | ✗ |
| `charName` | `string` | let/var | `this.encoding[code]` | ✗ |
| `glyph` | `any` | let/var | `*not shown*` | ✗ |
| `glyphIndexMap` | `any` | let/var | `font.tables.cmap.glyphIndexMap` | ✗ |
| `c` | `string` | let/var | `charCodes[i]` | ✗ |
| `glyphIndex` | `any` | let/var | `glyphIndexMap[c]` | ✗ |
| `glyphIndexMap` | `any` | let/var | `font.tables.cmap.glyphIndexMap` | ✗ |
| `c` | `string` | let/var | `charCodes[i]` | ✗ |
| `glyphIndex` | `any` | let/var | `glyphIndexMap[c]` | ✗ |
| `draw` | `{ line: (ctx: any, x1: any, y1: any, ...` | let/var | `{ line: line }` | ✗ |
| `_path` | `any` | let/var | `path \|\| new Path()` | ✗ |
| `commands` | `any` | let/var | `*not shown*` | ✗ |
| `hPoints` | `any` | let/var | `*not shown*` | ✗ |
| `xScale` | `any` | let/var | `options.xScale` | ✗ |
| `yScale` | `any` | let/var | `options.yScale` | ✗ |
| `scale` | `number` | let/var | `1 / (this.path.unitsPerEm \|\| 1000) * fontSize` | ✗ |
| `p` | `Path` | let/var | `new Path()` | ✗ |
| `cmd` | `any` | let/var | `commands[i]` | ✗ |
| `contours` | `any[]` | let/var | `[]` | ✗ |
| `currentContour` | `any[]` | let/var | `[]` | ✗ |
| `pt` | `any` | let/var | `this.points[i]` | ✗ |
| `commands` | `any` | let/var | `this.path.commands` | ✗ |
| `xCoords` | `any[]` | let/var | `[]` | ✗ |
| `yCoords` | `any[]` | let/var | `[]` | ✗ |
| `cmd` | `any` | let/var | `commands[i]` | ✗ |
| `metrics` | `{ xMin: any; yMin: any; xMax: any; yM...` | let/var | `{ xMin: Math.min.apply(null, xCoords), yMin: Math.min.apply(null, yCoords), x...` | ✗ |
| `scale` | `number` | let/var | `1 / this.path.unitsPerEm * fontSize` | ✗ |
| `blueCircles` | `any[]` | let/var | `[]` | ✗ |
| `redCircles` | `any[]` | let/var | `[]` | ✗ |
| `path` | `any` | let/var | `this.path` | ✗ |
| `cmd` | `any` | let/var | `path.commands[i]` | ✗ |
| `scale` | `any` | let/var | `*not shown*` | ✗ |
| `xMin` | `number` | let/var | `this.xMin \|\| 0` | ✗ |
| `yMin` | `number` | let/var | `this.yMin \|\| 0` | ✗ |
| `xMax` | `number` | let/var | `this.xMax \|\| 0` | ✗ |
| `yMax` | `number` | let/var | `this.yMax \|\| 0` | ✗ |
| `advanceWidth` | `number` | let/var | `this.advanceWidth \|\| 0` | ✗ |
| `glyph` | `any` | let/var | `glyphs[i]` | ✗ |
| `glyph` | `any` | let/var | `this.glyphs[index]` | ✗ |
| `unicodeObj` | `any` | let/var | `this.font._IndexToUnicodeMap[index]` | ✗ |
| `glyph` | `Glyph` | let/var | `new Glyph({index: index, font: font})` | ✗ |
| `glyph` | `Glyph` | let/var | `new Glyph({index: index, font: font})` | ✗ |
| `glyphset` | `{ GlyphSet: typeof GlyphSet; glyphLoa...` | let/var | `{ GlyphSet: GlyphSet, glyphLoader: glyphLoader, ttfGlyphLoader: ttfGlyphLoade...` | ✗ |
| `bias` | `any` | let/var | `*not shown*` | ✗ |
| `offsets` | `any[]` | let/var | `[]` | ✗ |
| `objects` | `any[]` | let/var | `[]` | ✗ |
| `objectOffset` | `any` | let/var | `*not shown*` | ✗ |
| `endOffset` | `any` | let/var | `*not shown*` | ✗ |
| `pos` | `any` | let/var | `start + 3` | ✗ |
| `offsets` | `any[]` | let/var | `[]` | ✗ |
| `objectOffset` | `any` | let/var | `*not shown*` | ✗ |
| `endOffset` | `any` | let/var | `*not shown*` | ✗ |
| `pos` | `any` | let/var | `start + 3` | ✗ |
| `objectOffset` | `number` | let/var | `0` | ✗ |
| `s` | `string` | let/var | `''` | ✗ |
| `eof` | `number` | let/var | `15` | ✗ |
| `lookup` | `string[]` | let/var | `['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '.', 'E', 'E-', null, '-']` | ✗ |
| `n1` | `number` | let/var | `b >> 4` | ✗ |
| `n2` | `number` | let/var | `b & 15` | ✗ |
| `b1` | `any` | let/var | `*not shown*` | ✗ |
| `b2` | `any` | let/var | `*not shown*` | ✗ |
| `b3` | `any` | let/var | `*not shown*` | ✗ |
| `b4` | `any` | let/var | `*not shown*` | ✗ |
| `o` | `{}` | let/var | `{}` | ✗ |
| `key` | `any` | let/var | `entries[i][0]` | ✗ |
| `values` | `any` | let/var | `entries[i][1]` | ✗ |
| `value` | `any` | let/var | `(void 0)` | ✗ |
| `parser` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `entries` | `any[]` | let/var | `[]` | ✗ |
| `operands` | `any[]` | let/var | `[]` | ✗ |
| `newDict` | `{}` | let/var | `{}` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `m` | `any` | let/var | `meta[i]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `header` | `{ formatMajor: any; formatMinor: any;...` | let/var | `{}` | ✗ |
| `TOP_DICT_META` | `({ name: string; op: number; type: st...` | let/var | `[ {name: 'version', op: 0, type: 'SID'}, {name: 'notice', op: 1, type: 'SID'}...` | ✗ |
| `PRIVATE_DICT_META` | `{ name: string; op: number; type: str...` | let/var | `[ {name: 'subrs', op: 19, type: 'offset', value: 0}, {name: 'defaultWidthX', ...` | ✗ |
| `topDictArray` | `any[]` | let/var | `[]` | ✗ |
| `topDictData` | `DataView<any>` | let/var | `new DataView(new Uint8Array(cffIndex[iTopDict]).buffer)` | ✗ |
| `privateSize` | `any` | let/var | `topDict.private[0]` | ✗ |
| `privateOffset` | `any` | let/var | `topDict.private[1]` | ✗ |
| `subrOffset` | `any` | let/var | `privateOffset + privateDict.subrs` | ✗ |
| `sid` | `any` | let/var | `*not shown*` | ✗ |
| `count` | `any` | let/var | `*not shown*` | ✗ |
| `parser` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `charset` | `string[]` | let/var | `['.notdef']` | ✗ |
| `code` | `any` | let/var | `*not shown*` | ✗ |
| `enc` | `{}` | let/var | `{}` | ✗ |
| `parser` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `c1x` | `any` | let/var | `*not shown*` | ✗ |
| `c1y` | `any` | let/var | `*not shown*` | ✗ |
| `c2x` | `any` | let/var | `*not shown*` | ✗ |
| `c2y` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `Path` | let/var | `new Path()` | ✗ |
| `stack` | `any[]` | let/var | `[]` | ✗ |
| `nStems` | `number` | let/var | `0` | ✗ |
| `haveWidth` | `boolean` | let/var | `false` | ✗ |
| `open` | `boolean` | let/var | `false` | ✗ |
| `x` | `number` | let/var | `0` | ✗ |
| `y` | `number` | let/var | `0` | ✗ |
| `subrs` | `any` | let/var | `*not shown*` | ✗ |
| `subrsBias` | `any` | let/var | `*not shown*` | ✗ |
| `defaultWidthX` | `any` | let/var | `*not shown*` | ✗ |
| `nominalWidthX` | `any` | let/var | `*not shown*` | ✗ |
| `fdIndex` | `any` | let/var | `font.tables.cff.topDict._fdSelect[glyph.index]` | ✗ |
| `fdDict` | `any` | let/var | `font.tables.cff.topDict._fdArray[fdIndex]` | ✗ |
| `width` | `any` | let/var | `defaultWidthX` | ✗ |
| `hasWidthArg` | `any` | let/var | `*not shown*` | ✗ |
| `b1` | `any` | let/var | `*not shown*` | ✗ |
| `b2` | `any` | let/var | `*not shown*` | ✗ |
| `b3` | `any` | let/var | `*not shown*` | ✗ |
| `b4` | `any` | let/var | `*not shown*` | ✗ |
| `codeIndex` | `any` | let/var | `*not shown*` | ✗ |
| `subrCode` | `any` | let/var | `*not shown*` | ✗ |
| `jpx` | `any` | let/var | `*not shown*` | ✗ |
| `jpy` | `any` | let/var | `*not shown*` | ✗ |
| `c3x` | `any` | let/var | `*not shown*` | ✗ |
| `c3y` | `any` | let/var | `*not shown*` | ✗ |
| `c4x` | `any` | let/var | `*not shown*` | ✗ |
| `c4y` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `v` | `any` | let/var | `code[i]` | ✗ |
| `fdSelect` | `any[]` | let/var | `[]` | ✗ |
| `fdIndex` | `any` | let/var | `*not shown*` | ✗ |
| `parser` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `topDict` | `{}` | let/var | `topDictArray[0]` | ✗ |
| `fdArrayOffset` | `any` | let/var | `topDict.fdArray` | ✗ |
| `fdSelectOffset` | `any` | let/var | `topDict.fdSelect` | ✗ |
| `privateDictOffset` | `any` | let/var | `start + topDict.private[1]` | ✗ |
| `subrOffset` | `any` | let/var | `privateDictOffset + privateDict.subrs` | ✗ |
| `charStringsIndex` | `any` | let/var | `*not shown*` | ✗ |
| `charString` | `any` | let/var | `charStringsIndex.objects[i]` | ✗ |
| `sid` | `any` | let/var | `*not shown*` | ✗ |
| `t` | `Table` | let/var | `new table.Record('Name INDEX', [ {name: 'names', type: 'INDEX', value: []} ])` | ✗ |
| `m` | `{}` | let/var | `{}` | ✗ |
| `entry` | `any` | let/var | `meta[i]` | ✗ |
| `value` | `any` | let/var | `attrs[entry.name]` | ✗ |
| `t` | `Table` | let/var | `new table.Record('Top DICT', [ {name: 'dict', type: 'DICT', value: {}} ])` | ✗ |
| `t` | `Table` | let/var | `new table.Record('Top DICT INDEX', [ {name: 'topDicts', type: 'INDEX', value:...` | ✗ |
| `t` | `Table` | let/var | `new table.Record('String INDEX', [ {name: 'strings', type: 'INDEX', value: []...` | ✗ |
| `t` | `Table` | let/var | `new table.Record('Charsets', [ {name: 'format', type: 'Card8', value: 0} ])` | ✗ |
| `glyphName` | `any` | let/var | `glyphNames[i]` | ✗ |
| `ops` | `any[]` | let/var | `[]` | ✗ |
| `path` | `any` | let/var | `glyph.path` | ✗ |
| `x` | `number` | let/var | `0` | ✗ |
| `y` | `number` | let/var | `0` | ✗ |
| `dx` | `any` | let/var | `(void 0)` | ✗ |
| `dy` | `any` | let/var | `(void 0)` | ✗ |
| `cmd` | `any` | let/var | `path.commands[i]` | ✗ |
| `_13` | `number` | let/var | `1 / 3` | ✗ |
| `_23` | `number` | let/var | `2 / 3` | ✗ |
| `t` | `Table` | let/var | `new table.Record('CharStrings INDEX', [ {name: 'charStrings', type: 'INDEX', ...` | ✗ |
| `t` | `Table` | let/var | `new table.Record('Private DICT', [ {name: 'dict', type: 'DICT', value: {}} ])` | ✗ |
| `t` | `Table` | let/var | `new table.Table('CFF ', [ {name: 'header', type: 'RECORD'}, {name: 'nameIndex...` | ✗ |
| `fontScale` | `number` | let/var | `1 / options.unitsPerEm` | ✗ |
| `attrs` | `{ version: any; fullName: any; family...` | let/var | `{ version: options.version, fullName: options.fullName, familyName: options.f...` | ✗ |
| `privateAttrs` | `{}` | let/var | `{}` | ✗ |
| `glyphNames` | `any[]` | let/var | `[]` | ✗ |
| `glyph` | `any` | let/var | `*not shown*` | ✗ |
| `strings` | `any[]` | let/var | `[]` | ✗ |
| `startOffset` | `any` | let/var | `t.header.sizeOf() + t.nameIndex.sizeOf() + t.topDictIndex.sizeOf() + t.string...` | ✗ |
| `cff` | `{ parse: (data: any, start: any, font...` | let/var | `{ parse: parseCFFTable, make: makeCFFTable }` | ✗ |
| `head` | `{ version: any; fontRevision: number;...` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `timestamp` | `number` | let/var | `Math.round(new Date().getTime() / 1000) + 2082844800` | ✗ |
| `createdTimestamp` | `number` | let/var | `timestamp` | ✗ |
| `head` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseHeadTable, make: makeHeadTable }` | ✗ |
| `hhea` | `{ version: any; ascender: any; descen...` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `hhea` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseHheaTable, make: makeHheaTable }` | ✗ |
| `advanceWidth` | `any` | let/var | `*not shown*` | ✗ |
| `leftSideBearing` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `advanceWidth` | `any` | let/var | `*not shown*` | ✗ |
| `leftSideBearing` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `t` | `Table` | let/var | `new table.Table('hmtx', [])` | ✗ |
| `advanceWidth` | `any` | let/var | `glyph.advanceWidth \|\| 0` | ✗ |
| `leftSideBearing` | `any` | let/var | `glyph.leftSideBearing \|\| 0` | ✗ |
| `hmtx` | `{ parse: (font: any, data: any, start...` | let/var | `{ parse: parseHmtxTable, make: makeHmtxTable }` | ✗ |
| `result` | `Table` | let/var | `new table.Table('ltag', [ {name: 'version', type: 'ULONG', value: 1}, {name: ...` | ✗ |
| `stringPool` | `string` | let/var | `''` | ✗ |
| `stringPoolOffset` | `number` | let/var | `12 + tags.length * 4` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `tags` | `any[]` | let/var | `[]` | ✗ |
| `tag` | `string` | let/var | `''` | ✗ |
| `offset` | `any` | let/var | `start + p.parseUShort()` | ✗ |
| `ltag` | `{ make: (tags: any) => Table; parse: ...` | let/var | `{ make: makeLtagTable, parse: parseLtagTable }` | ✗ |
| `maxp` | `{ version: any; numGlyphs: any; maxPo...` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `maxp` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseMaxpTable, make: makeMaxpTable }` | ✗ |
| `nameTableNames` | `string[]` | let/var | `[ 'copyright', // 0 'fontFamily', // 1 'fontSubfamily', // 2 'uniqueID', // 3...` | ✗ |
| `macLanguages` | `{ 0: string; 1: string; 2: string; 3:...` | let/var | `{ 0: 'en', 1: 'fr', 2: 'de', 3: 'it', 4: 'nl', 5: 'sv', 6: 'es', 7: 'da', 8: ...` | ✗ |
| `macLanguageToScript` | `{ 0: number; 1: number; 2: number; 3:...` | let/var | `{ 0: 0, // langEnglish → smRoman 1: 0, // langFrench → smRoman 2: 0, // langG...` | ✗ |
| `windowsLanguages` | `{ 1078: string; 1052: string; 1156: s...` | let/var | `{ 0x0436: 'af', 0x041C: 'sq', 0x0484: 'gsw', 0x045E: 'am', 0x1401: 'ar-DZ', 0...` | ✗ |
| `utf16` | `string` | let/var | `'utf-16'` | ✗ |
| `macScriptEncodings` | `{ 0: string; 1: string; 2: string; 3:...` | let/var | `{ 0: 'macintosh', // smRoman 1: 'x-mac-japanese', // smJapanese 2: 'x-mac-chi...` | ✗ |
| `macLanguageEncodings` | `{ 15: string; 17: string; 18: string;...` | let/var | `{ 15: 'x-mac-icelandic', // langIcelandic 17: 'x-mac-turkish', // langTurkish...` | ✗ |
| `name` | `{}` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `stringOffset` | `any` | let/var | `p.offset + p.parseUShort()` | ✗ |
| `property` | `any` | let/var | `nameTableNames[nameID] \|\| nameID` | ✗ |
| `text` | `any` | let/var | `(void 0)` | ✗ |
| `translations` | `any` | let/var | `name[property]` | ✗ |
| `langTagCount` | `number` | let/var | `0` | ✗ |
| `result` | `{}` | let/var | `{}` | ✗ |
| `needleLength` | `any` | let/var | `needle.length` | ✗ |
| `limit` | `number` | let/var | `haystack.length - needleLength + 1` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len` | `any` | let/var | `s.length` | ✗ |
| `nameID` | `any` | let/var | `*not shown*` | ✗ |
| `nameIDs` | `any[]` | let/var | `[]` | ✗ |
| `namesWithNumericKeys` | `{}` | let/var | `{}` | ✗ |
| `id` | `any` | let/var | `nameTableIds[key]` | ✗ |
| `nameRecords` | `any[]` | let/var | `[]` | ✗ |
| `stringPool` | `any[]` | let/var | `[]` | ✗ |
| `translations` | `any` | let/var | `namesWithNumericKeys[nameID]` | ✗ |
| `text` | `any` | let/var | `translations[lang]` | ✗ |
| `macPlatform` | `number` | let/var | `1` | ✗ |
| `macLanguage` | `any` | let/var | `macLanguageIds[lang]` | ✗ |
| `macScript` | `any` | let/var | `macLanguageToScript[macLanguage]` | ✗ |
| `winLanguage` | `any` | let/var | `windowsLanguageIds[lang]` | ✗ |
| `t` | `Table` | let/var | `new table.Table('name', [ {name: 'format', type: 'USHORT', value: 0}, {name: ...` | ✗ |
| `_name` | `{ parse: (data: any, start: any, ltag...` | let/var | `{ parse: parseNameTable, make: makeNameTable }` | ✗ |
| `unicodeRanges` | `{ begin: number; end: number; }[]` | let/var | `[ {begin: 0x0000, end: 0x007F}, // Basic Latin {begin: 0x0080, end: 0x00FF}, ...` | ✗ |
| `range` | `{ begin: number; end: number; }` | let/var | `unicodeRanges[i]` | ✗ |
| `os2` | `{ version: any; xAvgCharWidth: any; u...` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `os2` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseOS2Table, make: makeOS2Table, unicodeRanges: unicodeRanges, get...` | ✗ |
| `post` | `{ version: any; italicAngle: any; und...` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `post` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parsePostTable, make: makePostTable }` | ✗ |
| `subtableParsers` | `any[]` | let/var | `new Array(9)` | ✗ |
| `start` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `lookupRecordDesc` | `{ sequenceIndex: any; lookupListIndex...` | let/var | `{ sequenceIndex: Parser.uShort, lookupListIndex: Parser.uShort }` | ✗ |
| `start` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `start` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `extensionParser` | `Parser` | let/var | `new Parser(this.data, this.offset + this.parseULong())` | ✗ |
| `p` | `Parser` | let/var | `new Parser(data, start)` | ✗ |
| `subtableMakers` | `any[]` | let/var | `new Array(9)` | ✗ |
| `returnTable` | `Table` | let/var | `new table.Table('chainContextTable', [ {name: 'substFormat', type: 'USHORT', ...` | ✗ |
| `tableData` | `{ name: string; type: string; value: ...` | let/var | `[ {name: 'substFormat', type: 'USHORT', value: subtable.substFormat} ]` | ✗ |
| `returnTable$1` | `Table` | let/var | `new table.Table('chainContextTable', tableData)` | ✗ |
| `gsub` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseGsubTable, make: makeGsubTable }` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `tags` | `{}` | let/var | `{}` | ✗ |
| `numTags` | `number` | let/var | `Object.keys(tags).length` | ✗ |
| `stringPool` | `string` | let/var | `''` | ✗ |
| `stringPoolOffset` | `number` | let/var | `16 + numTags * 12` | ✗ |
| `result` | `Table` | let/var | `new table.Table('meta', [ {name: 'version', type: 'ULONG', value: 1}, {name: ...` | ✗ |
| `pos` | `number` | let/var | `stringPool.length` | ✗ |
| `meta` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseMetaTable, make: makeMetaTable }` | ✗ |
| `p` | `Parser` | let/var | `new Parser(data, start)` | ✗ |
| `version` | `any` | let/var | `ref.version` | ✗ |
| `baseGlyphRecords` | `any` | let/var | `ref.baseGlyphRecords` | ✗ |
| `layerRecords` | `any` | let/var | `ref.layerRecords` | ✗ |
| `baseGlyphRecordsOffset` | `number` | let/var | `14` | ✗ |
| `layerRecordsOffset` | `number` | let/var | `baseGlyphRecordsOffset + (baseGlyphRecords.length * 6)` | ✗ |
| `colr` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseColrTable, make: makeColrTable }` | ✗ |
| `p` | `Parser` | let/var | `new Parser(data, start)` | ✗ |
| `version` | `any` | let/var | `ref.version` | ✗ |
| `numPaletteEntries` | `any` | let/var | `ref.numPaletteEntries` | ✗ |
| `colorRecords` | `any` | let/var | `ref.colorRecords` | ✗ |
| `colorRecordIndices` | `any` | let/var | `ref.colorRecordIndices` | ✗ |
| `cpal` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseCpalTable, make: makeCpalTable }` | ✗ |
| `sum` | `number` | let/var | `0` | ✗ |
| `sfnt` | `Table` | let/var | `new table.Table('sfnt', [ {name: 'version', type: 'TAG', value: 'OTTO'}, {nam...` | ✗ |
| `recordFields` | `any[]` | let/var | `[]` | ✗ |
| `tableFields` | `any[]` | let/var | `[]` | ✗ |
| `offset` | `number` | let/var | `sfnt.sizeOf() + (makeTableRecord().sizeOf() * sfnt.numTables)` | ✗ |
| `t` | `any` | let/var | `tables[i]` | ✗ |
| `sum` | `number` | let/var | `0` | ✗ |
| `xMins` | `any[]` | let/var | `[]` | ✗ |
| `yMins` | `any[]` | let/var | `[]` | ✗ |
| `xMaxs` | `any[]` | let/var | `[]` | ✗ |
| `yMaxs` | `any[]` | let/var | `[]` | ✗ |
| `advanceWidths` | `any[]` | let/var | `[]` | ✗ |
| `leftSideBearings` | `any[]` | let/var | `[]` | ✗ |
| `rightSideBearings` | `any[]` | let/var | `[]` | ✗ |
| `firstCharIndex` | `any` | let/var | `*not shown*` | ✗ |
| `lastCharIndex` | `number` | let/var | `0` | ✗ |
| `ulUnicodeRange1` | `number` | let/var | `0` | ✗ |
| `ulUnicodeRange2` | `number` | let/var | `0` | ✗ |
| `ulUnicodeRange3` | `number` | let/var | `0` | ✗ |
| `ulUnicodeRange4` | `number` | let/var | `0` | ✗ |
| `unicode` | `number` | let/var | `glyph.unicode \| 0` | ✗ |
| `globals` | `{ xMin: any; yMin: any; xMax: any; yM...` | let/var | `{ xMin: Math.min.apply(null, xMins), yMin: Math.min.apply(null, yMins), xMax:...` | ✗ |
| `englishFullName` | `string` | let/var | `englishFamilyName + ' ' + englishStyleName` | ✗ |
| `names` | `{ uniqueID: { en: string; }; postScri...` | let/var | `{}` | ✗ |
| `languageTags` | `any[]` | let/var | `[]` | ✗ |
| `ltagTable` | `Table` | let/var | `(languageTags.length > 0 ? ltag.make(languageTags) : undefined)` | ✗ |
| `metaTable` | `Table` | let/var | `(font.metas && Object.keys(font.metas).length > 0) ? meta.make(font.metas) : ...` | ✗ |
| `tables` | `Table[]` | let/var | `[headTable, hheaTable, maxpTable, os2Table, nameTable, cmapTable, postTable, ...` | ✗ |
| `tableFields` | `any[]` | let/var | `sfntTable.fields` | ✗ |
| `checkSumAdjusted` | `boolean` | let/var | `false` | ✗ |
| `sfnt` | `{ make: (tables: any) => Table; fontT...` | let/var | `{ make: makeSfntTable, fontToTable: fontToSfntTable, computeCheckSum: compute...` | ✗ |
| `imin` | `number` | let/var | `0` | ✗ |
| `imax` | `number` | let/var | `arr.length - 1` | ✗ |
| `imid` | `number` | let/var | `(imin + imax) >>> 1` | ✗ |
| `val` | `any` | let/var | `arr[imid].tag` | ✗ |
| `imin` | `number` | let/var | `0` | ✗ |
| `imax` | `number` | let/var | `arr.length - 1` | ✗ |
| `imid` | `number` | let/var | `(imin + imax) >>> 1` | ✗ |
| `val` | `any` | let/var | `arr[imid]` | ✗ |
| `range` | `any` | let/var | `*not shown*` | ✗ |
| `imin` | `number` | let/var | `0` | ✗ |
| `imax` | `number` | let/var | `ranges.length - 1` | ✗ |
| `imid` | `number` | let/var | `(imin + imax) >>> 1` | ✗ |
| `start` | `any` | let/var | `range.start` | ✗ |
| `layout` | `any` | let/var | `this.font.tables[this.tableName]` | ✗ |
| `hasLatn` | `boolean` | let/var | `false` | ✗ |
| `name` | `any` | let/var | `layout.scripts[i].tag` | ✗ |
| `scripts` | `any` | let/var | `layout.scripts` | ✗ |
| `scr` | `{ tag: string; script: { defaultLangS...` | let/var | `{ tag: script, script: { defaultLangSys: {reserved: 0, reqFeatureIndex: 0xfff...` | ✗ |
| `langSysRecord` | `{ tag: string; langSys: { reserved: n...` | let/var | `{ tag: language, langSys: {reserved: 0, reqFeatureIndex: 0xffff, featureIndex...` | ✗ |
| `featureRecord` | `any` | let/var | `*not shown*` | ✗ |
| `featIndexes` | `any` | let/var | `langSysTable.featureIndexes` | ✗ |
| `allFeatures` | `any` | let/var | `this.font.tables[this.tableName].features` | ✗ |
| `index` | `any` | let/var | `allFeatures.length` | ✗ |
| `tables` | `any[]` | let/var | `[]` | ✗ |
| `lookupTable` | `any` | let/var | `*not shown*` | ✗ |
| `lookupListIndexes` | `any` | let/var | `featureTable.lookupListIndexes` | ✗ |
| `allLookups` | `any` | let/var | `this.font.tables[this.tableName].lookups` | ✗ |
| `index` | `any` | let/var | `allLookups.length` | ✗ |
| `glyphs` | `any[]` | let/var | `[]` | ✗ |
| `ranges` | `any` | let/var | `coverageTable.ranges` | ✗ |
| `range` | `any` | let/var | `ranges[i]` | ✗ |
| `start` | `any` | let/var | `range.start` | ✗ |
| `end` | `any` | let/var | `range.end` | ✗ |
| `subtables` | `any` | let/var | `kerningLookups[i].subtables` | ✗ |
| `subtable` | `any` | let/var | `subtables[j]` | ✗ |
| `pairSet` | `any` | let/var | `subtable.pairSets[covIndex]` | ✗ |
| `pair` | `any` | let/var | `pairSet[k]` | ✗ |
| `pair$1` | `any` | let/var | `subtable.classRecords[class1][class2]` | ✗ |
| `n` | `any` | let/var | `ar1.length` | ✗ |
| `subtables` | `any` | let/var | `lookupTable.subtables` | ✗ |
| `subtable` | `any` | let/var | `subtables[i]` | ✗ |
| `substitutions` | `any[]` | let/var | `[]` | ✗ |
| `subtables` | `any` | let/var | `lookupTables[idx].subtables` | ✗ |
| `subtable` | `any` | let/var | `subtables[i]` | ✗ |
| `j` | `any` | let/var | `(void 0)` | ✗ |
| `delta` | `any` | let/var | `subtable.deltaGlyphId` | ✗ |
| `glyph` | `any` | let/var | `glyphs[j]` | ✗ |
| `substitute` | `any` | let/var | `subtable.substitute` | ✗ |
| `substitutions` | `any[]` | let/var | `[]` | ✗ |
| `subtables` | `any` | let/var | `lookupTables[idx].subtables` | ✗ |
| `subtable` | `any` | let/var | `subtables[i]` | ✗ |
| `j` | `any` | let/var | `(void 0)` | ✗ |
| `glyph` | `any` | let/var | `glyphs[j]` | ✗ |
| `replacements` | `any` | let/var | `subtable.sequences[j]` | ✗ |
| `alternates` | `any[]` | let/var | `[]` | ✗ |
| `subtables` | `any` | let/var | `lookupTables[idx].subtables` | ✗ |
| `subtable` | `any` | let/var | `subtables[i]` | ✗ |
| `alternateSets` | `any` | let/var | `subtable.alternateSets` | ✗ |
| `ligatures` | `any[]` | let/var | `[]` | ✗ |
| `subtables` | `any` | let/var | `lookupTables[idx].subtables` | ✗ |
| `subtable` | `any` | let/var | `subtables[i]` | ✗ |
| `ligatureSets` | `any` | let/var | `subtable.ligatureSets` | ✗ |
| `startGlyph` | `any` | let/var | `glyphs[j]` | ✗ |
| `ligSet` | `any` | let/var | `ligatureSets[j]` | ✗ |
| `lig` | `any` | let/var | `ligSet[k]` | ✗ |
| `lookupTable` | `any` | let/var | `this.getLookupTables(script, language, feature, 1, true)[0]` | ✗ |
| `coverageGlyph` | `any` | let/var | `substitution.sub` | ✗ |
| `lookupTable` | `any` | let/var | `this.getLookupTables(script, language, feature, 2, true)[0]` | ✗ |
| `coverageGlyph` | `any` | let/var | `substitution.sub` | ✗ |
| `lookupTable` | `any` | let/var | `this.getLookupTables(script, language, feature, 3, true)[0]` | ✗ |
| `coverageGlyph` | `any` | let/var | `substitution.sub` | ✗ |
| `lookupTable` | `any` | let/var | `this.getLookupTables(script, language, feature, 4, true)[0]` | ✗ |
| `subtable` | `any` | let/var | `lookupTable.subtables[0]` | ✗ |
| `coverageGlyph` | `any` | let/var | `ligature.sub[0]` | ✗ |
| `ligatureTable` | `{ ligGlyph: any; components: any; }` | let/var | `{ ligGlyph: ligature.by, components: ligComponents }` | ✗ |
| `ligatureSet` | `any` | let/var | `subtable.ligatureSets[pos]` | ✗ |
| `v` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `flags` | `any` | let/var | `*not shown*` | ✗ |
| `flag` | `any` | let/var | `*not shown*` | ✗ |
| `endPointIndices` | `any[]` | let/var | `glyph.endPointIndices = []` | ✗ |
| `numberOfCoordinates` | `any` | let/var | `endPointIndices[endPointIndices.length - 1] + 1` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `point` | `any` | let/var | `*not shown*` | ✗ |
| `px` | `number` | let/var | `0` | ✗ |
| `py` | `number` | let/var | `0` | ✗ |
| `moreComponents` | `boolean` | let/var | `true` | ✗ |
| `component` | `{ glyphIndex: any; xScale: number; sc...` | let/var | `{ glyphIndex: p.parseUShort(), xScale: 1, scale01: 0, scale10: 0, yScale: 1, ...` | ✗ |
| `newPoints` | `any[]` | let/var | `[]` | ✗ |
| `pt` | `any` | let/var | `points[i]` | ✗ |
| `newPt` | `{ x: any; y: any; onCurve: any; lastP...` | let/var | `{ x: transform.xScale * pt.x + transform.scale01 * pt.y + transform.dx, y: tr...` | ✗ |
| `contours` | `any[]` | let/var | `[]` | ✗ |
| `currentContour` | `any[]` | let/var | `[]` | ✗ |
| `pt` | `any` | let/var | `points[i]` | ✗ |
| `p` | `Path` | let/var | `new Path()` | ✗ |
| `contour` | `any[]` | let/var | `contours[contourIndex]` | ✗ |
| `prev` | `any` | let/var | `null` | ✗ |
| `curr` | `any` | let/var | `contour[contour.length - 1]` | ✗ |
| `next` | `any` | let/var | `contour[0]` | ✗ |
| `start` | `{ x: number; y: number; }` | let/var | `{x: (curr.x + next.x) * 0.5, y: (curr.y + next.y) * 0.5}` | ✗ |
| `prev2` | `any` | let/var | `prev` | ✗ |
| `next2` | `any` | let/var | `next` | ✗ |
| `component` | `any` | let/var | `glyph.components[j]` | ✗ |
| `transformedPoints` | `any` | let/var | `(void 0)` | ✗ |
| `firstPt` | `any` | let/var | `glyph.points[component.matchedPoints[0]]` | ✗ |
| `secondPt` | `any` | let/var | `componentGlyph.points[component.matchedPoints[1]]` | ✗ |
| `transform` | `{ xScale: any; scale01: any; scale10:...` | let/var | `{ xScale: component.xScale, scale01: component.scale01, scale10: component.sc...` | ✗ |
| `glyphs` | `GlyphSet` | let/var | `new glyphset.GlyphSet(font)` | ✗ |
| `offset` | `any` | let/var | `loca[i]` | ✗ |
| `nextOffset` | `any` | let/var | `loca[i + 1]` | ✗ |
| `glyphs` | `GlyphSet` | let/var | `new glyphset.GlyphSet(font)` | ✗ |
| `offset` | `any` | let/var | `loca[i]` | ✗ |
| `nextOffset` | `any` | let/var | `loca[i + 1]` | ✗ |
| `glyf` | `{ getPath: (points: any) => Path; par...` | let/var | `{ getPath: getPath, parse: parseGlyfTable}` | ✗ |
| `instructionTable` | `any` | let/var | `*not shown*` | ✗ |
| `exec` | `any` | let/var | `*not shown*` | ✗ |
| `execGlyph` | `any` | let/var | `*not shown*` | ✗ |
| `execComponent` | `any` | let/var | `*not shown*` | ✗ |
| `period` | `any` | let/var | `this.srPeriod` | ✗ |
| `phase` | `any` | let/var | `this.srPhase` | ✗ |
| `threshold` | `any` | let/var | `this.srThreshold` | ✗ |
| `sign` | `number` | let/var | `1` | ✗ |
| `do1` | `any` | let/var | `*not shown*` | ✗ |
| `do2` | `any` | let/var | `*not shown*` | ✗ |
| `doa1` | `any` | let/var | `*not shown*` | ✗ |
| `doa2` | `any` | let/var | `*not shown*` | ✗ |
| `dm1` | `any` | let/var | `*not shown*` | ✗ |
| `dm2` | `any` | let/var | `*not shown*` | ✗ |
| `dt` | `any` | let/var | `*not shown*` | ✗ |
| `rpx` | `any` | let/var | `org ? rp.xo : rp.x` | ✗ |
| `rpy` | `any` | let/var | `org ? rp.yo : rp.y` | ✗ |
| `rpdx` | `any` | let/var | `rpx + d * pv.x` | ✗ |
| `rpdy` | `any` | let/var | `rpy + d * pv.y` | ✗ |
| `xUnitVector` | `{ x: number; y: number; axis: string;...` | let/var | `{ x: 1, y: 0, axis: 'x', // Gets the projected distance between two points. /...` | ✗ |
| `do1` | `any` | let/var | `*not shown*` | ✗ |
| `do2` | `any` | let/var | `*not shown*` | ✗ |
| `doa1` | `any` | let/var | `*not shown*` | ✗ |
| `doa2` | `any` | let/var | `*not shown*` | ✗ |
| `dm1` | `any` | let/var | `*not shown*` | ✗ |
| `dm2` | `any` | let/var | `*not shown*` | ✗ |
| `dt` | `any` | let/var | `*not shown*` | ✗ |
| `rpx` | `any` | let/var | `org ? rp.xo : rp.x` | ✗ |
| `rpy` | `any` | let/var | `org ? rp.yo : rp.y` | ✗ |
| `rpdx` | `any` | let/var | `rpx + d * pv.x` | ✗ |
| `rpdy` | `any` | let/var | `rpy + d * pv.y` | ✗ |
| `yUnitVector` | `{ x: number; y: number; axis: string;...` | let/var | `{ x: 0, y: 1, axis: 'y', // Gets the projected distance between two points. /...` | ✗ |
| `dm1` | `any` | let/var | `*not shown*` | ✗ |
| `dm2` | `any` | let/var | `*not shown*` | ✗ |
| `do1` | `any` | let/var | `*not shown*` | ✗ |
| `do2` | `any` | let/var | `*not shown*` | ✗ |
| `doa1` | `any` | let/var | `*not shown*` | ✗ |
| `doa2` | `any` | let/var | `*not shown*` | ✗ |
| `dt` | `any` | let/var | `*not shown*` | ✗ |
| `rpx` | `any` | let/var | `org ? rp.xo : rp.x` | ✗ |
| `rpy` | `any` | let/var | `org ? rp.yo : rp.y` | ✗ |
| `rpdx` | `any` | let/var | `rpx + d * pv.x` | ✗ |
| `rpdy` | `any` | let/var | `rpy + d * pv.y` | ✗ |
| `pvns` | `any` | let/var | `pv.normalSlope` | ✗ |
| `fvs` | `number` | let/var | `this.slope` | ✗ |
| `px` | `any` | let/var | `p.x` | ✗ |
| `py` | `any` | let/var | `p.y` | ✗ |
| `p` | `any` | let/var | `this.nextPointOnContour` | ✗ |
| `p` | `any` | let/var | `this.prevPointOnContour` | ✗ |
| `defaultState` | `{ cvCutIn: number; deltaBase: number;...` | let/var | `{ cvCutIn: 17 / 16, // control value cut in deltaBase: 9, deltaShift: 0.125, ...` | ✗ |
| `font` | `any` | let/var | `this.font` | ✗ |
| `prepState` | `State` | let/var | `this._prepState` | ✗ |
| `fpgmState` | `State` | let/var | `this._fpgmState` | ✗ |
| `oCvt` | `any` | let/var | `font.tables.cvt` | ✗ |
| `cvt` | `any[]` | let/var | `prepState.cvt = new Array(oCvt.length)` | ✗ |
| `scale` | `number` | let/var | `ppem / font.unitsPerEm` | ✗ |
| `xScale` | `number` | let/var | `prepState.ppem / prepState.font.unitsPerEm` | ✗ |
| `yScale` | `number` | let/var | `xScale` | ✗ |
| `components` | `any` | let/var | `glyph.components` | ✗ |
| `contours` | `any` | let/var | `*not shown*` | ✗ |
| `gZone` | `any` | let/var | `*not shown*` | ✗ |
| `state` | `any` | let/var | `*not shown*` | ✗ |
| `font` | `any` | let/var | `prepState.font` | ✗ |
| `c` | `any` | let/var | `components[i]` | ✗ |
| `gz` | `any` | let/var | `state.gZone` | ✗ |
| `cc` | `any` | let/var | `state.contours` | ✗ |
| `p` | `any` | let/var | `gz[pi]` | ✗ |
| `gLen` | `number` | let/var | `gZone.length` | ✗ |
| `points` | `any` | let/var | `glyph.points \|\| []` | ✗ |
| `pLen` | `any` | let/var | `points.length` | ✗ |
| `gZone` | `any[]` | let/var | `state.gZone = state.z0 = state.z1 = state.z2 = []` | ✗ |
| `contours` | `any[]` | let/var | `state.contours = []` | ✗ |
| `cp` | `any` | let/var | `*not shown*` | ✗ |
| `sp` | `any` | let/var | `*not shown*` | ✗ |
| `np` | `any` | let/var | `*not shown*` | ✗ |
| `prog` | `any` | let/var | `state.prog` | ✗ |
| `pLen` | `any` | let/var | `prog.length` | ✗ |
| `ins` | `any` | let/var | `*not shown*` | ✗ |
| `tZone` | `any[]` | let/var | `state.tZone = new Array(state.gZone.length)` | ✗ |
| `prog` | `any` | let/var | `state.prog` | ✗ |
| `ip` | `any` | let/var | `state.ip` | ✗ |
| `nesting` | `number` | let/var | `1` | ✗ |
| `ins` | `any` | let/var | `*not shown*` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `p2` | `any` | let/var | `state.z2[p2i]` | ✗ |
| `p1` | `any` | let/var | `state.z1[p1i]` | ✗ |
| `dx` | `any` | let/var | `*not shown*` | ✗ |
| `dy` | `any` | let/var | `*not shown*` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `p2` | `any` | let/var | `state.z2[p2i]` | ✗ |
| `p1` | `any` | let/var | `state.z1[p1i]` | ✗ |
| `dx` | `any` | let/var | `*not shown*` | ✗ |
| `dy` | `any` | let/var | `*not shown*` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `z0` | `any` | let/var | `state.z0` | ✗ |
| `z1` | `any` | let/var | `state.z1` | ✗ |
| `pa0` | `any` | let/var | `z0[pa0i]` | ✗ |
| `pa1` | `any` | let/var | `z0[pa1i]` | ✗ |
| `pb0` | `any` | let/var | `z1[pb0i]` | ✗ |
| `pb1` | `any` | let/var | `z1[pb1i]` | ✗ |
| `p` | `any` | let/var | `state.z2[pi]` | ✗ |
| `x1` | `any` | let/var | `pa0.x` | ✗ |
| `y1` | `any` | let/var | `pa0.y` | ✗ |
| `x2` | `any` | let/var | `pa1.x` | ✗ |
| `y2` | `any` | let/var | `pa1.y` | ✗ |
| `x3` | `any` | let/var | `pb0.x` | ✗ |
| `y3` | `any` | let/var | `pb0.y` | ✗ |
| `x4` | `any` | let/var | `pb1.x` | ✗ |
| `y4` | `any` | let/var | `pb1.y` | ✗ |
| `div` | `number` | let/var | `(x1 - x2) * (y3 - y4) - (y1 - y2) * (x3 - x4)` | ✗ |
| `f1` | `number` | let/var | `x1 * y2 - y1 * x2` | ✗ |
| `f2` | `number` | let/var | `x3 * y4 - y3 * x4` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `cip` | `any` | let/var | `state.ip` | ✗ |
| `cprog` | `any` | let/var | `state.prog` | ✗ |
| `cip` | `any` | let/var | `state.ip` | ✗ |
| `cprog` | `any` | let/var | `state.prog` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `prog` | `any` | let/var | `state.prog` | ✗ |
| `ip` | `any` | let/var | `state.ip` | ✗ |
| `ipBegin` | `any` | let/var | `ip` | ✗ |
| `p` | `any` | let/var | `state.z0[pi]` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `z2` | `any` | let/var | `state.z2` | ✗ |
| `pLen` | `number` | let/var | `z2.length - 2` | ✗ |
| `cp` | `any` | let/var | `*not shown*` | ✗ |
| `pp` | `any` | let/var | `*not shown*` | ✗ |
| `np` | `any` | let/var | `*not shown*` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `rpi` | `any` | let/var | `a ? state.rp1 : state.rp2` | ✗ |
| `rp` | `any` | let/var | `(a ? state.z0 : state.z1)[rpi]` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `loop` | `any` | let/var | `state.loop` | ✗ |
| `z2` | `any` | let/var | `state.z2` | ✗ |
| `p` | `any` | let/var | `z2[pi]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `rpi` | `any` | let/var | `a ? state.rp1 : state.rp2` | ✗ |
| `rp` | `any` | let/var | `(a ? state.z0 : state.z1)[rpi]` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `sp` | `any` | let/var | `state.z2[state.contours[ci]]` | ✗ |
| `p` | `any` | let/var | `sp` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `rpi` | `any` | let/var | `a ? state.rp1 : state.rp2` | ✗ |
| `rp` | `any` | let/var | `(a ? state.z0 : state.z1)[rpi]` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `any` | let/var | `*not shown*` | ✗ |
| `pLen` | `number` | let/var | `z.length - 2` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `loop` | `any` | let/var | `state.loop` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `d` | `number` | let/var | `stack.pop() / 0x40` | ✗ |
| `z2` | `any` | let/var | `state.z2` | ✗ |
| `p` | `any` | let/var | `z2[pi]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `rp1i` | `any` | let/var | `state.rp1` | ✗ |
| `rp2i` | `any` | let/var | `state.rp2` | ✗ |
| `loop` | `any` | let/var | `state.loop` | ✗ |
| `rp1` | `any` | let/var | `state.z0[rp1i]` | ✗ |
| `rp2` | `any` | let/var | `state.z1[rp2i]` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.dpv` | ✗ |
| `z2` | `any` | let/var | `state.z2` | ✗ |
| `p` | `any` | let/var | `z2[pi]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `d` | `number` | let/var | `stack.pop() / 64` | ✗ |
| `p` | `any` | let/var | `state.z1[pi]` | ✗ |
| `rp0` | `any` | let/var | `state.z0[state.rp0]` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `rp0i` | `any` | let/var | `state.rp0` | ✗ |
| `rp0` | `any` | let/var | `state.z0[rp0i]` | ✗ |
| `loop` | `any` | let/var | `state.loop` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `z1` | `any` | let/var | `state.z1` | ✗ |
| `p` | `any` | let/var | `z1[pi]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `p` | `any` | let/var | `state.z0[pi]` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `cv` | `any` | let/var | `state.cvt[n]` | ✗ |
| `prog` | `any` | let/var | `state.prog` | ✗ |
| `ip` | `any` | let/var | `state.ip` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `n` | `any` | let/var | `prog[++ip]` | ✗ |
| `ip` | `any` | let/var | `state.ip` | ✗ |
| `prog` | `any` | let/var | `state.prog` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `n` | `any` | let/var | `prog[++ip]` | ✗ |
| `w` | `number` | let/var | `(prog[++ip] << 8) \| prog[++ip]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `store` | `any` | let/var | `state.store` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `store` | `any` | let/var | `state.store` | ✗ |
| `v` | `any` | let/var | `(store && store[l]) \|\| 0` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `p` | `any` | let/var | `state.z2[pi]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `p2` | `any` | let/var | `state.z1[pi2]` | ✗ |
| `p1` | `any` | let/var | `state.z0[pi1]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.pv` | ✗ |
| `ppem` | `any` | let/var | `state.ppem` | ✗ |
| `base` | `any` | let/var | `state.deltaBase + (b - 1) * 16` | ✗ |
| `ds` | `any` | let/var | `state.deltaShift` | ✗ |
| `z0` | `any` | let/var | `state.z0` | ✗ |
| `appem` | `any` | let/var | `base + ((arg & 0xF0) >> 4)` | ✗ |
| `mag` | `number` | let/var | `(arg & 0x0F) - 8` | ✗ |
| `p` | `any` | let/var | `z0[pi]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `ppem` | `any` | let/var | `state.ppem` | ✗ |
| `base` | `any` | let/var | `state.deltaBase + (b - 1) * 16` | ✗ |
| `ds` | `any` | let/var | `state.deltaShift` | ✗ |
| `appem` | `any` | let/var | `base + ((arg & 0xF0) >> 4)` | ✗ |
| `mag` | `number` | let/var | `(arg & 0x0F) - 8` | ✗ |
| `delta` | `number` | let/var | `mag * ds` | ✗ |
| `period` | `any` | let/var | `*not shown*` | ✗ |
| `period` | `any` | let/var | `*not shown*` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `p2` | `any` | let/var | `state.z2[p2i]` | ✗ |
| `p1` | `any` | let/var | `state.z1[p1i]` | ✗ |
| `dx` | `any` | let/var | `*not shown*` | ✗ |
| `dy` | `any` | let/var | `*not shown*` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `r` | `number` | let/var | `0` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `prog` | `any` | let/var | `state.prog` | ✗ |
| `ip` | `any` | let/var | `state.ip` | ✗ |
| `ip` | `any` | let/var | `state.ip` | ✗ |
| `prog` | `any` | let/var | `state.prog` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `w` | `number` | let/var | `(prog[++ip] << 8) \| prog[++ip]` | ✗ |
| `stack` | `any` | let/var | `state.stack` | ✗ |
| `cvte` | `any` | let/var | `indirect && stack.pop()` | ✗ |
| `rp0i` | `any` | let/var | `state.rp0` | ✗ |
| `rp` | `any` | let/var | `state.z0[rp0i]` | ✗ |
| `p` | `any` | let/var | `state.z1[pi]` | ✗ |
| `md` | `any` | let/var | `state.minDis` | ✗ |
| `fv` | `any` | let/var | `state.fv` | ✗ |
| `pv` | `any` | let/var | `state.dpv` | ✗ |
| `od` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `sign` | `any` | let/var | `*not shown*` | ✗ |
| `cv` | `any` | let/var | `*not shown*` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `coreEvents` | `string[]` | let/var | `[ 'start', 'end', 'next', 'newToken', 'contextStart', 'contextEnd', 'insertTo...` | ✗ |
| `event` | `any` | let/var | `events[eventId]` | ✗ |
| `requiresContextUpdate` | `string[]` | let/var | `[ 'insertToken', 'removeToken', 'removeRange', 'replaceToken', 'replaceRange'...` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `silent` | `boolean` | let/var | `true` | ✗ |
| `conditionParams` | `any[]` | let/var | `[token, contextParams]` | ✗ |
| `canApplyModifier` | `boolean` | let/var | `( condition === null \|\| condition.apply(this, conditionParams) === true )` | ✗ |
| `modifierParams` | `any[]` | let/var | `[token, contextParams]` | ✗ |
| `context` | `any` | let/var | `this.registeredContexts[contextName]` | ✗ |
| `event` | `any` | let/var | `this.events[eventName]` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `event` | `any` | let/var | `this.events[eventName]` | ✗ |
| `contextCheckers` | `ContextChecker` | let/var | `new ContextChecker( contextName, contextStartCheck, contextEndCheck )` | ✗ |
| `endIndex` | `any` | let/var | `range.startIndex + range.endOffset` | ✗ |
| `registeredContexts` | `{}` | let/var | `this.registeredContexts` | ✗ |
| `context` | `any` | let/var | `registeredContexts[contextName]` | ✗ |
| `contextParams` | `ContextParams` | let/var | `new ContextParams(chars, i)` | ✗ |
| `startIndex` | `any` | let/var | `this.getContext(contextName).openRange.startIndex` | ✗ |
| `range` | `ContextRange` | let/var | `new ContextRange(startIndex, offset, contextName)` | ✗ |
| `ranges` | `any` | let/var | `this.getContext(contextName).ranges` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `index` | `any` | let/var | `contextParams.index` | ✗ |
| `contextName` | `any` | let/var | `contextChecker.contextName` | ✗ |
| `openRange` | `any` | let/var | `this$1.getContext(contextName).openRange` | ✗ |
| `offset` | `number` | let/var | `(index - openRange.startIndex) + 1` | ✗ |
| `char` | `string` | let/var | `chars[i]` | ✗ |
| `contextParams` | `ContextParams` | let/var | `new ContextParams(chars, i)` | ✗ |
| `token` | `Token` | let/var | `new Token(char)` | ✗ |
| `ranges` | `any` | let/var | `coverage.ranges` | ✗ |
| `range` | `any` | let/var | `ranges[i]` | ✗ |
| `offset` | `number` | let/var | `glyphIndex - range.start` | ✗ |
| `lookupList` | `any[]` | let/var | `[]` | ✗ |
| `coverage` | `any` | let/var | `coverageList[i]` | ✗ |
| `glyphIndex` | `any` | let/var | `contextParams.current` | ✗ |
| `lookupsCount` | `any` | let/var | `( subtable.inputCoverage.length + subtable.lookaheadCoverage.length + subtabl...` | ✗ |
| `lookaheadOffset` | `number` | let/var | `subtable.inputCoverage.length - 1` | ✗ |
| `lookaheadParams` | `ContextParams` | let/var | `new ContextParams(lookaheadContext, 0)` | ✗ |
| `backtrackParams` | `ContextParams` | let/var | `new ContextParams(backtrackContext, 0)` | ✗ |
| `contextRulesMatch` | `boolean` | let/var | `( inputLookups.length === subtable.inputCoverage.length && lookaheadLookups.l...` | ✗ |
| `substitutions` | `any[]` | let/var | `[]` | ✗ |
| `lookupRecord` | `any` | let/var | `subtable.lookupRecords[i]` | ✗ |
| `lookupListIndex` | `any` | let/var | `lookupRecord.lookupListIndex` | ✗ |
| `subtable$1` | `any` | let/var | `lookupTable.subtables[s]` | ✗ |
| `glyphIndex` | `any` | let/var | `contextParams.current` | ✗ |
| `ligature` | `any` | let/var | `*not shown*` | ✗ |
| `ligatureSet` | `any` | let/var | `subtable.ligatureSets[ligSetIndex]` | ✗ |
| `lookaheadItem` | `any` | let/var | `contextParams.lookahead[l]` | ✗ |
| `component` | `any` | let/var | `ligature.components[l]` | ✗ |
| `scripts` | `any` | let/var | `this.font.tables.gsub.scripts` | ✗ |
| `script` | `any` | let/var | `scripts[s]` | ✗ |
| `tables` | `any` | let/var | `this.font.tables` | ✗ |
| `scripts` | `any` | let/var | `this.font.tables.gsub.scripts` | ✗ |
| `script` | `any` | let/var | `scripts[i]` | ✗ |
| `langSysRecords` | `any` | let/var | `script.langSysRecords` | ✗ |
| `langSysRecord` | `any` | let/var | `langSysRecords[j]` | ✗ |
| `langSys` | `any` | let/var | `langSysRecord.langSys` | ✗ |
| `tags` | `{}` | let/var | `{}` | ✗ |
| `tag` | `any` | let/var | `features[i].tag` | ✗ |
| `feature` | `any` | let/var | `features[i].feature` | ✗ |
| `features` | `any` | let/var | `this.features[scriptTag]` | ✗ |
| `gsub` | `any` | let/var | `this.font.tables.gsub` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `contextParams` | `any` | let/var | `query.contextParams` | ✗ |
| `currentIndex` | `any` | let/var | `contextParams.index` | ✗ |
| `lookupTable` | `any` | let/var | `lookups[l]` | ✗ |
| `subtable` | `any` | let/var | `subtables[s]` | ✗ |
| `substitution` | `any` | let/var | `(void 0)` | ✗ |
| `supportedFeature` | `any` | let/var | `( this.features[query.script].some(function (feature) { return feature.tag ==...` | ✗ |
| `lookups` | `any` | let/var | `this.font.tables.gsub.lookups` | ✗ |
| `scriptFeatures` | `any` | let/var | `this.features[query.script]` | ✗ |
| `char` | `any` | let/var | `contextParams.current` | ✗ |
| `arabicWordCheck` | `{ startCheck: (contextParams: any) =>...` | let/var | `{ startCheck: arabicWordStartCheck, endCheck: arabicWordEndCheck }` | ✗ |
| `char` | `any` | let/var | `contextParams.current` | ✗ |
| `arabicCharAhead` | `boolean` | let/var | `false` | ✗ |
| `arabicSentenceCheck` | `{ startCheck: (contextParams: any) =>...` | let/var | `{ startCheck: arabicSentenceStartCheck, endCheck: arabicSentenceEndCheck }` | ✗ |
| `token` | `any` | let/var | `tokens[index + offset]` | ✗ |
| `token` | `any` | let/var | `tokens[index]` | ✗ |
| `compsCount` | `any` | let/var | `action.substitution.components.length` | ✗ |
| `SUBSTITUTIONS` | `{ 11: (action: any, tokens: any, inde...` | let/var | `{ 11: singleSubstitutionFormat1$1, 12: singleSubstitutionFormat2$1, 63: chain...` | ✗ |
| `prevChar` | `any` | let/var | `backtrack[i]` | ✗ |
| `nextChar` | `any` | let/var | `charContextParams.lookahead[i]` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `script` | `string` | let/var | `'arab'` | ✗ |
| `tags` | `any` | let/var | `this.featuresTags[script]` | ✗ |
| `contextParams` | `ContextParams` | let/var | `new ContextParams( tokens.map(function (token) { return token.getState('glyph...` | ✗ |
| `charContextParams` | `ContextParams` | let/var | `new ContextParams( tokens.map(function (token) { return token.char; } ), 0)` | ✗ |
| `CONNECT` | `number` | let/var | `0` | ✗ |
| `tag` | `any` | let/var | `*not shown*` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `script` | `string` | let/var | `'arab'` | ✗ |
| `char` | `any` | let/var | `contextParams.current` | ✗ |
| `latinWordCheck` | `{ startCheck: (contextParams: any) =>...` | let/var | `{ startCheck: latinWordStartCheck, endCheck: latinWordEndCheck }` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `script` | `string` | let/var | `'latn'` | ✗ |
| `check` | `any` | let/var | `this.contextChecks[(checkId + "Check")]` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `feature` | `any` | let/var | `features[f]` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `script` | `string` | let/var | `'arab'` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `script` | `string` | let/var | `'arab'` | ✗ |
| `tags` | `any` | let/var | `this.featuresTags[script]` | ✗ |
| `this$1` | `any` | let/var | `this` | ✗ |
| `script` | `string` | let/var | `'latn'` | ✗ |
| `tags` | `any` | let/var | `this.featuresTags[script]` | ✗ |
| `indexes` | `any[]` | let/var | `[]` | ✗ |
| `token` | `any` | let/var | `this.tokenizer.tokens[i]` | ✗ |
| `index` | `any` | let/var | `token.activeState.value` | ✗ |
| `this$1` | `this` | let/var | `this` | ✗ |
| `bidi` | `Bidi` | let/var | `new Bidi()` | ✗ |
| `features` | `{ script: string; tags: string[]; }[]` | let/var | `options ? this.updateFeatures(options.features) : this.defaultRenderOptions.f...` | ✗ |
| `length` | `number` | let/var | `indexes.length` | ✗ |
| `glyphs` | `any[]` | let/var | `new Array(length)` | ✗ |
| `gposKerning` | `any[]` | let/var | `this.position.defaultKerningTables` | ✗ |
| `fontScale` | `number` | let/var | `1 / this.unitsPerEm * fontSize` | ✗ |
| `kerningLookups` | `any` | let/var | `*not shown*` | ✗ |
| `script` | `any` | let/var | `options.script \|\| this.position.getDefaultScriptName()` | ✗ |
| `glyph` | `opentype.Glyph` | let/var | `glyphs[i]` | ✗ |
| `kerningValue` | `any` | let/var | `kerningLookups ? this.position.getKerningValue(kerningLookups, glyph.index, g...` | ✗ |
| `fullPath` | `Path` | let/var | `new Path()` | ✗ |
| `glyphPaths` | `any[]` | let/var | `[]` | ✗ |
| `translations` | `any` | let/var | `this.names[name]` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `buffer` | `ArrayBuffer` | let/var | `new ArrayBuffer(bytes.length)` | ✗ |
| `intArray` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(buffer)` | ✗ |
| `dataView` | `DataView<ArrayBuffer>` | let/var | `new DataView(arrayBuffer)` | ✗ |
| `blob` | `Blob` | let/var | `new Blob([dataView], {type: 'font/opentype'})` | ✗ |
| `nameID` | `number` | let/var | `256` | ✗ |
| `axis` | `{ tag: string; minValue: any; default...` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `fields` | `{ name: string; type: string; value: ...` | let/var | `[ {name: 'nameID_' + n, type: 'USHORT', value: nameID}, {name: 'flags_' + n, ...` | ✗ |
| `axisTag` | `any` | let/var | `axes[i].tag` | ✗ |
| `inst` | `{ name: any; coordinates: {}; }` | let/var | `{}` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `result` | `Table` | let/var | `new table.Table('fvar', [ {name: 'version', type: 'ULONG', value: 0x10000}, {...` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `axes` | `any[]` | let/var | `[]` | ✗ |
| `instances` | `any[]` | let/var | `[]` | ✗ |
| `instanceStart` | `any` | let/var | `start + offsetToData + axisCount * axisSize` | ✗ |
| `fvar` | `{ make: (fvar: any, names: any) => Ta...` | let/var | `{ make: makeFvarTable, parse: parseFvarTable }` | ✗ |
| `p` | `Parser` | let/var | `new Parser(data, start)` | ✗ |
| `gdef` | `{ version: any; classDef: any; attach...` | let/var | `{ version: tableVersion, classDef: p.parsePointer(Parser.classDef), attachLis...` | ✗ |
| `gdef` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseGDEFTable }` | ✗ |
| `subtableParsers$1` | `any[]` | let/var | `new Array(10)` | ✗ |
| `start` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `start` | `any` | let/var | `this.offset + this.relativeOffset` | ✗ |
| `p` | `Parser` | let/var | `new Parser(data, start)` | ✗ |
| `subtableMakers$1` | `any[]` | let/var | `new Array(10)` | ✗ |
| `gpos` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseGposTable, make: makeGposTable }` | ✗ |
| `pairs` | `{}` | let/var | `{}` | ✗ |
| `pairs` | `{}` | let/var | `{}` | ✗ |
| `subtableVersion` | `number` | let/var | `coverage & 0xFF` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `kern` | `{ parse: (data: any, start: any) => {...` | let/var | `{ parse: parseKernTable }` | ✗ |
| `p` | `Parser` | let/var | `new parse.Parser(data, start)` | ✗ |
| `parseFn` | `() => any` | let/var | `shortVersion ? p.parseUShort : p.parseULong` | ✗ |
| `glyphOffsets` | `any[]` | let/var | `[]` | ✗ |
| `loca` | `{ parse: (data: any, start: any, numG...` | let/var | `{ parse: parseLocaTable }` | ✗ |
| `request` | `XMLHttpRequest` | let/var | `new XMLHttpRequest()` | ✗ |
| `tableEntries` | `any[]` | let/var | `[]` | ✗ |
| `p` | `number` | let/var | `12` | ✗ |
| `tableEntries` | `any[]` | let/var | `[]` | ✗ |
| `p` | `number` | let/var | `44` | ✗ |
| `compression` | `any` | let/var | `(void 0)` | ✗ |
| `inBuffer` | `Uint8Array<any>` | let/var | `new Uint8Array(data.buffer, tableEntry.offset + 2, tableEntry.compressedLengt...` | ✗ |
| `outBuffer` | `Uint8Array<any>` | let/var | `new Uint8Array(tableEntry.length)` | ✗ |
| `view` | `DataView<any>` | let/var | `new DataView(outBuffer.buffer, 0)` | ✗ |
| `indexToLocFormat` | `any` | let/var | `*not shown*` | ✗ |
| `ltagTable` | `any` | let/var | `*not shown*` | ✗ |
| `font` | `Font` | let/var | `new Font({empty: true})` | ✗ |
| `data` | `DataView<any>` | let/var | `new DataView(buffer, 0)` | ✗ |
| `numTables` | `any` | let/var | `*not shown*` | ✗ |
| `tableEntries` | `any[]` | let/var | `[]` | ✗ |
| `cffTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `fvarTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `glyfTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `gdefTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `gposTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `gsubTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `hmtxTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `kernTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `locaTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `nameTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `metaTableEntry` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `any` | let/var | `*not shown*` | ✗ |
| `tableEntry` | `any` | let/var | `tableEntries[i]` | ✗ |
| `table` | `any` | let/var | `(void 0)` | ✗ |
| `shortVersion` | `boolean` | let/var | `indexToLocFormat === 0` | ✗ |
| `font` | `any` | let/var | `*not shown*` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `load` | *none* | new Promise(...) |


---

## Functions

### `codePointAt(position: any): number`

**Parameters:**

- **`position`** `any`

**Returns:** `number`

**Calls:**

- `TypeError`
- `String`
- `Number`
- `string.charCodeAt`

**Internal Comments:**
```
// `ToInteger` (x2)
// Account for out-of-bounds indices:
// Get the first code unit (x2)
// https://mathiasbynens.be/notes/javascript-encoding#surrogate-formulae
```

<details><summary>Code</summary>

```typescript
function(position) {
			if (this == null) {
				throw TypeError();
			}
			var string = String(this);
			var size = string.length;
			// `ToInteger`
			var index = position ? Number(position) : 0;
			if (index != index) { // better `isNaN`
				index = 0;
			}
			// Account for out-of-bounds indices:
			if (index < 0 || index >= size) {
				return undefined;
			}
			// Get the first code unit
			var first = string.charCodeAt(index);
			var second;
			if ( // check if it’s the start of a surrogate pair
				first >= 0xD800 && first <= 0xDBFF && // high surrogate
				size > index + 1 // there is a next code unit
			) {
				second = string.charCodeAt(index + 1);
				if (second >= 0xDC00 && second <= 0xDFFF) { // low surrogate
					// https://mathiasbynens.be/notes/javascript-encoding#surrogate-formulae
					return (first - 0xD800) * 0x400 + second - 0xDC00 + 0x10000;
				}
			}
			return first;
		}
```
</details>

### `Tree(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Tree() {
  this.table = new Uint16Array(16);   /* table of code length counts */
  this.trans = new Uint16Array(288);  /* code -> symbol translation table */
}
```
</details>

### `Data(source: any, dest: any): void`

**Parameters:**

- **`source`** `any`
- **`dest`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Data(source, dest) {
  this.source = source;
  this.sourceIndex = 0;
  this.tag = 0;
  this.bitcount = 0;
  
  this.dest = dest;
  this.destLen = 0;
  
  this.ltree = new Tree();  /* dynamic length/symbol tree */
  this.dtree = new Tree();  /* dynamic distance tree */
}
```
</details>

### `tinf_build_bits_base(bits: any, base: any, delta: any, first: any): void`

**Parameters:**

- **`bits`** `any`
- **`base`** `any`
- **`delta`** `any`
- **`first`** `any`

**Returns:** `void`

**Internal Comments:**
```
/* build bits table */
/* build base table */
```

<details><summary>Code</summary>

```typescript
function tinf_build_bits_base(bits, base, delta, first) {
  var i, sum;

  /* build bits table */
  for (i = 0; i < delta; ++i) { bits[i] = 0; }
  for (i = 0; i < 30 - delta; ++i) { bits[i + delta] = i / delta | 0; }

  /* build base table */
  for (sum = first, i = 0; i < 30; ++i) {
    base[i] = sum;
    sum += 1 << bits[i];
  }
}
```
</details>

### `tinf_build_fixed_trees(lt: any, dt: any): void`

**Parameters:**

- **`lt`** `any`
- **`dt`** `any`

**Returns:** `void`

**Internal Comments:**
```
/* build fixed length tree */
/* build fixed distance tree */
```

<details><summary>Code</summary>

```typescript
function tinf_build_fixed_trees(lt, dt) {
  var i;

  /* build fixed length tree */
  for (i = 0; i < 7; ++i) { lt.table[i] = 0; }

  lt.table[7] = 24;
  lt.table[8] = 152;
  lt.table[9] = 112;

  for (i = 0; i < 24; ++i) { lt.trans[i] = 256 + i; }
  for (i = 0; i < 144; ++i) { lt.trans[24 + i] = i; }
  for (i = 0; i < 8; ++i) { lt.trans[24 + 144 + i] = 280 + i; }
  for (i = 0; i < 112; ++i) { lt.trans[24 + 144 + 8 + i] = 144 + i; }

  /* build fixed distance tree */
  for (i = 0; i < 5; ++i) { dt.table[i] = 0; }

  dt.table[5] = 32;

  for (i = 0; i < 32; ++i) { dt.trans[i] = i; }
}
```
</details>

### `tinf_build_tree(t: any, lengths: any, off: any, num: any): void`

**Parameters:**

- **`t`** `any`
- **`lengths`** `any`
- **`off`** `any`
- **`num`** `any`

**Returns:** `void`

**Internal Comments:**
```
/* clear code length count table */
/* scan symbol lengths, and sum code length counts */
/* compute offset table for distribution sort */
/* create code->symbol translation table (symbols sorted by code) */
```

<details><summary>Code</summary>

```typescript
function tinf_build_tree(t, lengths, off, num) {
  var i, sum;

  /* clear code length count table */
  for (i = 0; i < 16; ++i) { t.table[i] = 0; }

  /* scan symbol lengths, and sum code length counts */
  for (i = 0; i < num; ++i) { t.table[lengths[off + i]]++; }

  t.table[0] = 0;

  /* compute offset table for distribution sort */
  for (sum = 0, i = 0; i < 16; ++i) {
    offs[i] = sum;
    sum += t.table[i];
  }

  /* create code->symbol translation table (symbols sorted by code) */
  for (i = 0; i < num; ++i) {
    if (lengths[off + i]) { t.trans[offs[lengths[off + i]]++] = i; }
  }
}
```
</details>

### `tinf_getbit(d: any): number`

**Parameters:**

- **`d`** `any`

**Returns:** `number`

**Internal Comments:**
```
/* check if tag is empty */
/* load next tag */ (x4)
/* shift bit out of tag */ (x2)
```

<details><summary>Code</summary>

```typescript
function tinf_getbit(d) {
  /* check if tag is empty */
  if (!d.bitcount--) {
    /* load next tag */
    d.tag = d.source[d.sourceIndex++];
    d.bitcount = 7;
  }

  /* shift bit out of tag */
  var bit = d.tag & 1;
  d.tag >>>= 1;

  return bit;
}
```
</details>

### `tinf_read_bits(d: any, num: any, base: any): any`

**Parameters:**

- **`d`** `any`
- **`num`** `any`
- **`base`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function tinf_read_bits(d, num, base) {
  if (!num)
    { return base; }

  while (d.bitcount < 24) {
    d.tag |= d.source[d.sourceIndex++] << d.bitcount;
    d.bitcount += 8;
  }

  var val = d.tag & (0xffff >>> (16 - num));
  d.tag >>>= num;
  d.bitcount -= num;
  return val + base;
}
```
</details>

### `tinf_decode_symbol(d: any, t: any): any`

**Parameters:**

- **`d`** `any`
- **`t`** `any`

**Returns:** `any`

**Internal Comments:**
```
/* get more bits while code value is above sum */
```

<details><summary>Code</summary>

```typescript
function tinf_decode_symbol(d, t) {
  while (d.bitcount < 24) {
    d.tag |= d.source[d.sourceIndex++] << d.bitcount;
    d.bitcount += 8;
  }
  
  var sum = 0, cur = 0, len = 0;
  var tag = d.tag;

  /* get more bits while code value is above sum */
  do {
    cur = 2 * cur + (tag & 1);
    tag >>>= 1;
    ++len;

    sum += t.table[len];
    cur -= t.table[len];
  } while (cur >= 0);
  
  d.tag = tag;
  d.bitcount -= len;

  return t.trans[sum + cur];
}
```
</details>

### `tinf_decode_trees(d: any, lt: any, dt: any): void`

**Parameters:**

- **`d`** `any`
- **`lt`** `any`
- **`dt`** `any`

**Returns:** `void`

**Calls:**

- `tinf_read_bits`
- `tinf_build_tree`
- `tinf_decode_symbol`

**Internal Comments:**
```
/* get 5 bits HLIT (257-286) */ (x3)
/* get 5 bits HDIST (1-32) */ (x3)
/* get 4 bits HCLEN (4-19) */ (x3)
/* read code lengths for code length alphabet */
/* get 3 bits code length (0-7) */ (x2)
/* build code length tree */ (x3)
/* decode code lengths for the dynamic trees */
/* copy previous code length 3-6 times (read 2 bits) */ (x2)
/* repeat code length 0 for 3-10 times (read 3 bits) */
/* repeat code length 0 for 11-138 times (read 7 bits) */
/* values 0-15 represent the actual code lengths */ (x4)
/* build dynamic trees */ (x3)
```

<details><summary>Code</summary>

```typescript
function tinf_decode_trees(d, lt, dt) {
  var hlit, hdist, hclen;
  var i, num, length;

  /* get 5 bits HLIT (257-286) */
  hlit = tinf_read_bits(d, 5, 257);

  /* get 5 bits HDIST (1-32) */
  hdist = tinf_read_bits(d, 5, 1);

  /* get 4 bits HCLEN (4-19) */
  hclen = tinf_read_bits(d, 4, 4);

  for (i = 0; i < 19; ++i) { lengths[i] = 0; }

  /* read code lengths for code length alphabet */
  for (i = 0; i < hclen; ++i) {
    /* get 3 bits code length (0-7) */
    var clen = tinf_read_bits(d, 3, 0);
    lengths[clcidx[i]] = clen;
  }

  /* build code length tree */
  tinf_build_tree(code_tree, lengths, 0, 19);

  /* decode code lengths for the dynamic trees */
  for (num = 0; num < hlit + hdist;) {
    var sym = tinf_decode_symbol(d, code_tree);

    switch (sym) {
      case 16:
        /* copy previous code length 3-6 times (read 2 bits) */
        var prev = lengths[num - 1];
        for (length = tinf_read_bits(d, 2, 3); length; --length) {
          lengths[num++] = prev;
        }
        break;
      case 17:
        /* repeat code length 0 for 3-10 times (read 3 bits) */
        for (length = tinf_read_bits(d, 3, 3); length; --length) {
          lengths[num++] = 0;
        }
        break;
      case 18:
        /* repeat code length 0 for 11-138 times (read 7 bits) */
        for (length = tinf_read_bits(d, 7, 11); length; --length) {
          lengths[num++] = 0;
        }
        break;
      default:
        /* values 0-15 represent the actual code lengths */
        lengths[num++] = sym;
        break;
    }
  }

  /* build dynamic trees */
  tinf_build_tree(lt, lengths, 0, hlit);
  tinf_build_tree(dt, lengths, hlit, hdist);
}
```
</details>

### `tinf_inflate_block_data(d: any, lt: any, dt: any): number`

**Parameters:**

- **`d`** `any`
- **`lt`** `any`
- **`dt`** `any`

**Returns:** `number`

**Calls:**

- `tinf_decode_symbol`
- `tinf_read_bits`

**Internal Comments:**
```
/* check for end of block */
/* possibly get more bits from length code */ (x3)
/* possibly get more bits from distance code */ (x3)
/* copy match */
```

<details><summary>Code</summary>

```typescript
function tinf_inflate_block_data(d, lt, dt) {
  while (1) {
    var sym = tinf_decode_symbol(d, lt);

    /* check for end of block */
    if (sym === 256) {
      return TINF_OK;
    }

    if (sym < 256) {
      d.dest[d.destLen++] = sym;
    } else {
      var length, dist, offs;
      var i;

      sym -= 257;

      /* possibly get more bits from length code */
      length = tinf_read_bits(d, length_bits[sym], length_base[sym]);

      dist = tinf_decode_symbol(d, dt);

      /* possibly get more bits from distance code */
      offs = d.destLen - tinf_read_bits(d, dist_bits[dist], dist_base[dist]);

      /* copy match */
      for (i = offs; i < offs + length; ++i) {
        d.dest[d.destLen++] = d.dest[i];
      }
    }
  }
}
```
</details>

### `tinf_inflate_uncompressed_block(d: any): number`

**Parameters:**

- **`d`** `any`

**Returns:** `number`

**Internal Comments:**
```
/* unread from bitbuffer */
/* get length */ (x3)
/* get one's complement of length */ (x3)
/* check length */
/* copy block */
/* make sure we start next block on a byte boundary */ (x4)
```

<details><summary>Code</summary>

```typescript
function tinf_inflate_uncompressed_block(d) {
  var length, invlength;
  var i;
  
  /* unread from bitbuffer */
  while (d.bitcount > 8) {
    d.sourceIndex--;
    d.bitcount -= 8;
  }

  /* get length */
  length = d.source[d.sourceIndex + 1];
  length = 256 * length + d.source[d.sourceIndex];

  /* get one's complement of length */
  invlength = d.source[d.sourceIndex + 3];
  invlength = 256 * invlength + d.source[d.sourceIndex + 2];

  /* check length */
  if (length !== (~invlength & 0x0000ffff))
    { return TINF_DATA_ERROR; }

  d.sourceIndex += 4;

  /* copy block */
  for (i = length; i; --i)
    { d.dest[d.destLen++] = d.source[d.sourceIndex++]; }

  /* make sure we start next block on a byte boundary */
  d.bitcount = 0;

  return TINF_OK;
}
```
</details>

### `tinf_uncompress(source: any, dest: any): any`

**Parameters:**

- **`source`** `any`
- **`dest`** `any`

**Returns:** `any`

**Calls:**

- `tinf_getbit`
- `tinf_read_bits`
- `tinf_inflate_uncompressed_block`
- `tinf_inflate_block_data`
- `tinf_decode_trees`
- `d.dest.slice`
- `d.dest.subarray`

**Internal Comments:**
```
/* read final block flag */ (x3)
/* read block type (2 bits) */ (x3)
/* decompress block */
/* decompress uncompressed block */ (x3)
/* decompress block with fixed huffman trees */ (x3)
/* decompress block with dynamic huffman trees */ (x3)
```

<details><summary>Code</summary>

```typescript
function tinf_uncompress(source, dest) {
  var d = new Data(source, dest);
  var bfinal, btype, res;

  do {
    /* read final block flag */
    bfinal = tinf_getbit(d);

    /* read block type (2 bits) */
    btype = tinf_read_bits(d, 2, 0);

    /* decompress block */
    switch (btype) {
      case 0:
        /* decompress uncompressed block */
        res = tinf_inflate_uncompressed_block(d);
        break;
      case 1:
        /* decompress block with fixed huffman trees */
        res = tinf_inflate_block_data(d, sltree, sdtree);
        break;
      case 2:
        /* decompress block with dynamic huffman trees */
        tinf_decode_trees(d, d.ltree, d.dtree);
        res = tinf_inflate_block_data(d, d.ltree, d.dtree);
        break;
      default:
        res = TINF_DATA_ERROR;
    }

    if (res !== TINF_OK)
      { throw new Error('Data error'); }

  } while (!bfinal);

  if (d.destLen < d.dest.length) {
    if (typeof d.dest.slice === 'function')
      { return d.dest.slice(0, d.destLen); }
    else
      { return d.dest.subarray(0, d.destLen); }
  }
  
  return d.dest;
}
```
</details>

### `derive(v0: any, v1: any, v2: any, v3: any, t: any): number`

**Parameters:**

- **`v0`** `any`
- **`v1`** `any`
- **`v2`** `any`
- **`v3`** `any`
- **`t`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function derive(v0, v1, v2, v3, t) {
    return Math.pow(1 - t, 3) * v0 +
        3 * Math.pow(1 - t, 2) * t * v1 +
        3 * (1 - t) * Math.pow(t, 2) * v2 +
        Math.pow(t, 3) * v3;
}
```
</details>

### `BoundingBox(): void`

**JSDoc:**
```typescript
/**
 * A bounding box is an enclosing box that describes the smallest measure within which all the points lie.
 * It is used to calculate the bounding box of a glyph or text path.
 *
 * On initialization, x1/y1/x2/y2 will be NaN. Check if the bounding box is empty using `isEmpty()`.
 *
 * @exports opentype.BoundingBox
 * @class
 * @constructor
 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BoundingBox() {
    this.x1 = Number.NaN;
    this.y1 = Number.NaN;
    this.x2 = Number.NaN;
    this.y2 = Number.NaN;
}
```
</details>

### `Path(): void`

**JSDoc:**
```typescript
/**
 * A bézier path containing a set of path commands similar to a SVG path.
 * Paths can be drawn on a context using `draw`.
 * @exports opentype.Path
 * @class
 * @constructor
 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Path() {
    this.commands = [];
    this.fill = 'black';
    this.stroke = null;
    this.strokeWidth = 1;
}
```
</details>

### `floatToString(v: any): any`

**Parameters:**

- **`v`** `any`

**Returns:** `any`

**Calls:**

- `Math.round`
- `v.toFixed`

<details><summary>Code</summary>

```typescript
function floatToString(v) {
        if (Math.round(v) === v) {
            return '' + Math.round(v);
        } else {
            return v.toFixed(decimalPlaces);
        }
    }
```
</details>

### `packValues(): string`

**Returns:** `string`

**Calls:**

- `floatToString`

<details><summary>Code</summary>

```typescript
function packValues() {
        var arguments$1 = arguments;

        var s = '';
        for (var i = 0; i < arguments.length; i += 1) {
            var v = arguments$1[i];
            if (v >= 0 && i > 0) {
                s += ' ';
            }

            s += floatToString(v);
        }

        return s;
    }
```
</details>

### `fail(message: any): void`

**Parameters:**

- **`message`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function fail(message) {
    throw new Error(message);
}
```
</details>

### `argument(predicate: any, message: any): void`

**Parameters:**

- **`predicate`** `any`
- **`message`** `any`

**Returns:** `void`

**Calls:**

- `fail`

<details><summary>Code</summary>

```typescript
function argument(predicate, message) {
    if (!predicate) {
        fail(message);
    }
}
```
</details>

### `constant(v: any): () => any`

**Parameters:**

- **`v`** `any`

**Returns:** `() => any`

<details><summary>Code</summary>

```typescript
function constant(v) {
    return function() {
        return v;
    };
}
```
</details>

### `getMacEncodingTable(encoding: any): any`

**Parameters:**

- **`encoding`** `any`

**Returns:** `any`

**Calls:**

- `macEncodingTableCache.get`
- `decodingTable.charCodeAt`
- `macEncodingTableCache.set`

**Internal Comments:**
```
// Since we use encoding as a cache key for WeakMap, it has to be
// a String object and not a literal. And at least on NodeJS 2.10.1,
// WeakMap requires that the same String instance is passed for cache hits.
/*jshint -W053 */ (x4)
// Suppress "Do not use String as a constructor." (x4)
// We can't do "if (cache.has(key)) {return cache.get(key)}" here:
// since garbage collection may run at any time, it could also kick in
// between the calls to cache.has() and cache.get(). In that case,
// we would return 'undefined' even though we do support the encoding.
```

<details><summary>Code</summary>

```typescript
function (encoding) {
    // Since we use encoding as a cache key for WeakMap, it has to be
    // a String object and not a literal. And at least on NodeJS 2.10.1,
    // WeakMap requires that the same String instance is passed for cache hits.
    if (!macEncodingCacheKeys) {
        macEncodingCacheKeys = {};
        for (var e in eightBitMacEncodings) {
            /*jshint -W053 */  // Suppress "Do not use String as a constructor."
            macEncodingCacheKeys[e] = new String(e);
        }
    }

    var cacheKey = macEncodingCacheKeys[encoding];
    if (cacheKey === undefined) {
        return undefined;
    }

    // We can't do "if (cache.has(key)) {return cache.get(key)}" here:
    // since garbage collection may run at any time, it could also kick in
    // between the calls to cache.has() and cache.get(). In that case,
    // we would return 'undefined' even though we do support the encoding.
    if (macEncodingTableCache) {
        var cachedTable = macEncodingTableCache.get(cacheKey);
        if (cachedTable !== undefined) {
            return cachedTable;
        }
    }

    var decodingTable = eightBitMacEncodings[encoding];
    if (decodingTable === undefined) {
        return undefined;
    }

    var encodingTable = {};
    for (var i = 0; i < decodingTable.length; i++) {
        encodingTable[decodingTable.charCodeAt(i)] = i + 0x80;
    }

    if (macEncodingTableCache) {
        macEncodingTableCache.set(cacheKey, encodingTable);
    }

    return encodingTable;
}
```
</details>

### `isByteEncodable(value: any): boolean`

**Parameters:**

- **`value`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isByteEncodable(value) {
    return value >= -128 && value <= 127;
}
```
</details>

### `encodeVarDeltaRunAsZeroes(deltas: any, pos: any, result: any): any`

**Parameters:**

- **`deltas`** `any`
- **`pos`** `any`
- **`result`** `any`

**Returns:** `any`

**Calls:**

- `result.push`

<details><summary>Code</summary>

```typescript
function encodeVarDeltaRunAsZeroes(deltas, pos, result) {
    var runLength = 0;
    var numDeltas = deltas.length;
    while (pos < numDeltas && runLength < 64 && deltas[pos] === 0) {
        ++pos;
        ++runLength;
    }
    result.push(0x80 | (runLength - 1));
    return pos;
}
```
</details>

### `encodeVarDeltaRunAsBytes(deltas: any, offset: any, result: any): any`

**Parameters:**

- **`deltas`** `any`
- **`offset`** `any`
- **`result`** `any`

**Returns:** `any`

**Calls:**

- `isByteEncodable`
- `result.push`

**Internal Comments:**
```
// Within a byte-encoded run of deltas, a single zero is best
// stored literally as 0x00 value. However, if we have two or
// more zeroes in a sequence, it is better to start a new run.
// Fore example, the sequence of deltas [15, 15, 0, 15, 15]
// becomes 6 bytes (04 0F 0F 00 0F 0F) when storing the zero
// within the current run, but 7 bytes (01 0F 0F 80 01 0F 0F)
// when starting a new run.
```

<details><summary>Code</summary>

```typescript
function encodeVarDeltaRunAsBytes(deltas, offset, result) {
    var runLength = 0;
    var numDeltas = deltas.length;
    var pos = offset;
    while (pos < numDeltas && runLength < 64) {
        var value = deltas[pos];
        if (!isByteEncodable(value)) {
            break;
        }

        // Within a byte-encoded run of deltas, a single zero is best
        // stored literally as 0x00 value. However, if we have two or
        // more zeroes in a sequence, it is better to start a new run.
        // Fore example, the sequence of deltas [15, 15, 0, 15, 15]
        // becomes 6 bytes (04 0F 0F 00 0F 0F) when storing the zero
        // within the current run, but 7 bytes (01 0F 0F 80 01 0F 0F)
        // when starting a new run.
        if (value === 0 && pos + 1 < numDeltas && deltas[pos + 1] === 0) {
            break;
        }

        ++pos;
        ++runLength;
    }
    result.push(runLength - 1);
    for (var i = offset; i < pos; ++i) {
        result.push((deltas[i] + 256) & 0xff);
    }
    return pos;
}
```
</details>

### `encodeVarDeltaRunAsWords(deltas: any, offset: any, result: any): any`

**Parameters:**

- **`deltas`** `any`
- **`offset`** `any`
- **`result`** `any`

**Returns:** `any`

**Calls:**

- `isByteEncodable`
- `result.push`

**Internal Comments:**
```
// Within a word-encoded run of deltas, it is easiest to start
// a new run (with a different encoding) whenever we encounter
// a zero value. For example, the sequence [0x6666, 0, 0x7777]
// needs 7 bytes when storing the zero inside the current run
// (42 66 66 00 00 77 77), and equally 7 bytes when starting a
// new run (40 66 66 80 40 77 77).
// Within a word-encoded run of deltas, a single value in the
// range (-128..127) should be encoded within the current run
// because it is more compact. For example, the sequence
// [0x6666, 2, 0x7777] becomes 7 bytes when storing the value
// literally (42 66 66 00 02 77 77), but 8 bytes when starting
// a new run (40 66 66 00 02 40 77 77).
```

<details><summary>Code</summary>

```typescript
function encodeVarDeltaRunAsWords(deltas, offset, result) {
    var runLength = 0;
    var numDeltas = deltas.length;
    var pos = offset;
    while (pos < numDeltas && runLength < 64) {
        var value = deltas[pos];

        // Within a word-encoded run of deltas, it is easiest to start
        // a new run (with a different encoding) whenever we encounter
        // a zero value. For example, the sequence [0x6666, 0, 0x7777]
        // needs 7 bytes when storing the zero inside the current run
        // (42 66 66 00 00 77 77), and equally 7 bytes when starting a
        // new run (40 66 66 80 40 77 77).
        if (value === 0) {
            break;
        }

        // Within a word-encoded run of deltas, a single value in the
        // range (-128..127) should be encoded within the current run
        // because it is more compact. For example, the sequence
        // [0x6666, 2, 0x7777] becomes 7 bytes when storing the value
        // literally (42 66 66 00 02 77 77), but 8 bytes when starting
        // a new run (40 66 66 00 02 40 77 77).
        if (isByteEncodable(value) && pos + 1 < numDeltas && isByteEncodable(deltas[pos + 1])) {
            break;
        }

        ++pos;
        ++runLength;
    }
    result.push(0x40 | (runLength - 1));
    for (var i = offset; i < pos; ++i) {
        var val = deltas[i];
        result.push(((val + 0x10000) >> 8) & 0xff, (val + 0x100) & 0xff);
    }
    return pos;
}
```
</details>

### `Table(tableName: string, fields: any[], options: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.Table
 * @class
 * @param {string} tableName
 * @param {Array} fields
 * @param {Object} options
 * @constructor
 */
```

**Parameters:**

- **`tableName`** `string`
- **`fields`** `any[]`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `Object.keys`

**Internal Comments:**
```
// For coverage tables with coverage format 2, we do not want to add the coverage data directly to the table object,
// as this will result in wrong encoding order of the coverage data on serialization to bytes.
// The fallback of using the field values directly when not present on the table is handled in types.encode.TABLE() already.
```

<details><summary>Code</summary>

```typescript
function Table(tableName, fields, options) {
    // For coverage tables with coverage format 2, we do not want to add the coverage data directly to the table object,
    // as this will result in wrong encoding order of the coverage data on serialization to bytes.
    // The fallback of using the field values directly when not present on the table is handled in types.encode.TABLE() already.
    if (fields.length && (fields[0].name !== 'coverageFormat' || fields[0].value === 1)) {
        for (var i = 0; i < fields.length; i += 1) {
            var field = fields[i];
            this[field.name] = field.value;
        }
    }

    this.tableName = tableName;
    this.fields = fields;
    if (options) {
        var optionKeys = Object.keys(options);
        for (var i$1 = 0; i$1 < optionKeys.length; i$1 += 1) {
            var k = optionKeys[i$1];
            var v = options[k];
            if (this[k] !== undefined) {
                this[k] = v;
            }
        }
    }
}
```
</details>

### `ushortList(itemName: any, list: any, count: any): any[]`

**JSDoc:**
```typescript
/**
 * @private
 */
```

**Parameters:**

- **`itemName`** `any`
- **`list`** `any`
- **`count`** `any`

**Returns:** `any[]`

<details><summary>Code</summary>

```typescript
function ushortList(itemName, list, count) {
    if (count === undefined) {
        count = list.length;
    }
    var fields = new Array(list.length + 1);
    fields[0] = {name: itemName + 'Count', type: 'USHORT', value: count};
    for (var i = 0; i < list.length; i++) {
        fields[i + 1] = {name: itemName + i, type: 'USHORT', value: list[i]};
    }
    return fields;
}
```
</details>

### `tableList(itemName: any, records: any, itemCallback: any): any[]`

**JSDoc:**
```typescript
/**
 * @private
 */
```

**Parameters:**

- **`itemName`** `any`
- **`records`** `any`
- **`itemCallback`** `any`

**Returns:** `any[]`

**Calls:**

- `itemCallback`

<details><summary>Code</summary>

```typescript
function tableList(itemName, records, itemCallback) {
    var count = records.length;
    var fields = new Array(count + 1);
    fields[0] = {name: itemName + 'Count', type: 'USHORT', value: count};
    for (var i = 0; i < count; i++) {
        fields[i + 1] = {name: itemName + i, type: 'TABLE', value: itemCallback(records[i], i)};
    }
    return fields;
}
```
</details>

### `recordList(itemName: any, records: any, itemCallback: any): { name: string; type: string; value: any; }[]`

**JSDoc:**
```typescript
/**
 * @private
 */
```

**Parameters:**

- **`itemName`** `any`
- **`records`** `any`
- **`itemCallback`** `any`

**Returns:** `{ name: string; type: string; value: any; }[]`

**Calls:**

- `fields.concat`
- `itemCallback`

<details><summary>Code</summary>

```typescript
function recordList(itemName, records, itemCallback) {
    var count = records.length;
    var fields = [];
    fields[0] = {name: itemName + 'Count', type: 'USHORT', value: count};
    for (var i = 0; i < count; i++) {
        fields = fields.concat(itemCallback(records[i], i));
    }
    return fields;
}
```
</details>

### `Coverage(coverageTable: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.Coverage
 * @class
 * @param {opentype.Table}
 * @constructor
 * @extends opentype.Table
 */
```

**Parameters:**

- **`coverageTable`** `any`

**Returns:** `void`

**Calls:**

- `Table.call`
- `[{name: 'coverageFormat', type: 'USHORT', value: 1}]
            .concat`
- `ushortList`
- `[{name: 'coverageFormat', type: 'USHORT', value: 2}]
            .concat`
- `recordList`
- `check.assert`

<details><summary>Code</summary>

```typescript
function Coverage(coverageTable) {
    if (coverageTable.format === 1) {
        Table.call(this, 'coverageTable',
            [{name: 'coverageFormat', type: 'USHORT', value: 1}]
            .concat(ushortList('glyph', coverageTable.glyphs))
        );
    } else if (coverageTable.format === 2) {
        Table.call(this, 'coverageTable',
            [{name: 'coverageFormat', type: 'USHORT', value: 2}]
            .concat(recordList('rangeRecord', coverageTable.ranges, function(RangeRecord) {
                return [
                    {name: 'startGlyphID', type: 'USHORT', value: RangeRecord.start},
                    {name: 'endGlyphID', type: 'USHORT', value: RangeRecord.end},
                    {name: 'startCoverageIndex', type: 'USHORT', value: RangeRecord.index} ];
            }))
        );
    } else {
        check.assert(false, 'Coverage format must be 1 or 2.');
    }
}
```
</details>

### `ScriptList(scriptListTable: any): void`

**Parameters:**

- **`scriptListTable`** `any`

**Returns:** `void`

**Calls:**

- `Table.call`
- `recordList`
- `check.assert`
- `[
                    {name: 'defaultLangSys', type: 'TABLE', value: new Table('defaultLangSys', [
                        {name: 'lookupOrder', type: 'USHORT', value: 0},
                        {name: 'reqFeatureIndex', type: 'USHORT', value: defaultLangSys.reqFeatureIndex}]
                        .concat(ushortList('featureIndex', defaultLangSys.featureIndexes)))}
                    ].concat`
- `[
                        {name: 'lookupOrder', type: 'USHORT', value: 0},
                        {name: 'reqFeatureIndex', type: 'USHORT', value: defaultLangSys.reqFeatureIndex}]
                        .concat`
- `ushortList`
- `[
                                {name: 'lookupOrder', type: 'USHORT', value: 0},
                                {name: 'reqFeatureIndex', type: 'USHORT', value: langSys.reqFeatureIndex}
                                ].concat`

<details><summary>Code</summary>

```typescript
function ScriptList(scriptListTable) {
    Table.call(this, 'scriptListTable',
        recordList('scriptRecord', scriptListTable, function(scriptRecord, i) {
            var script = scriptRecord.script;
            var defaultLangSys = script.defaultLangSys;
            check.assert(!!defaultLangSys, 'Unable to write GSUB: script ' + scriptRecord.tag + ' has no default language system.');
            return [
                {name: 'scriptTag' + i, type: 'TAG', value: scriptRecord.tag},
                {name: 'script' + i, type: 'TABLE', value: new Table('scriptTable', [
                    {name: 'defaultLangSys', type: 'TABLE', value: new Table('defaultLangSys', [
                        {name: 'lookupOrder', type: 'USHORT', value: 0},
                        {name: 'reqFeatureIndex', type: 'USHORT', value: defaultLangSys.reqFeatureIndex}]
                        .concat(ushortList('featureIndex', defaultLangSys.featureIndexes)))}
                    ].concat(recordList('langSys', script.langSysRecords, function(langSysRecord, i) {
                        var langSys = langSysRecord.langSys;
                        return [
                            {name: 'langSysTag' + i, type: 'TAG', value: langSysRecord.tag},
                            {name: 'langSys' + i, type: 'TABLE', value: new Table('langSys', [
                                {name: 'lookupOrder', type: 'USHORT', value: 0},
                                {name: 'reqFeatureIndex', type: 'USHORT', value: langSys.reqFeatureIndex}
                                ].concat(ushortList('featureIndex', langSys.featureIndexes)))}
                        ];
                    })))}
            ];
        })
    );
}
```
</details>

### `FeatureList(featureListTable: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.FeatureList
 * @class
 * @param {opentype.Table}
 * @constructor
 * @extends opentype.Table
 */
```

**Parameters:**

- **`featureListTable`** `any`

**Returns:** `void`

**Calls:**

- `Table.call`
- `recordList`
- `[
                    {name: 'featureParams', type: 'USHORT', value: feature.featureParams} ].concat`
- `ushortList`

<details><summary>Code</summary>

```typescript
function FeatureList(featureListTable) {
    Table.call(this, 'featureListTable',
        recordList('featureRecord', featureListTable, function(featureRecord, i) {
            var feature = featureRecord.feature;
            return [
                {name: 'featureTag' + i, type: 'TAG', value: featureRecord.tag},
                {name: 'feature' + i, type: 'TABLE', value: new Table('featureTable', [
                    {name: 'featureParams', type: 'USHORT', value: feature.featureParams} ].concat(ushortList('lookupListIndex', feature.lookupListIndexes)))}
            ];
        })
    );
}
```
</details>

### `LookupList(lookupListTable: any, subtableMakers: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.LookupList
 * @class
 * @param {opentype.Table}
 * @param {Object}
 * @constructor
 * @extends opentype.Table
 */
```

**Parameters:**

- **`lookupListTable`** `any`
- **`subtableMakers`** `any`

**Returns:** `void`

**Calls:**

- `Table.call`
- `tableList`
- `check.assert`
- `[
            {name: 'lookupType', type: 'USHORT', value: lookupTable.lookupType},
            {name: 'lookupFlag', type: 'USHORT', value: lookupTable.lookupFlag}
        ].concat`

<details><summary>Code</summary>

```typescript
function LookupList(lookupListTable, subtableMakers) {
    Table.call(this, 'lookupListTable', tableList('lookup', lookupListTable, function(lookupTable) {
        var subtableCallback = subtableMakers[lookupTable.lookupType];
        check.assert(!!subtableCallback, 'Unable to write GSUB lookup type ' + lookupTable.lookupType + ' tables.');
        return new Table('lookupTable', [
            {name: 'lookupType', type: 'USHORT', value: lookupTable.lookupType},
            {name: 'lookupFlag', type: 'USHORT', value: lookupTable.lookupFlag}
        ].concat(tableList('subtable', lookupTable.subtables, subtableCallback)));
    }));
}
```
</details>

### `getByte(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getUint8`

<details><summary>Code</summary>

```typescript
function getByte(dataView, offset) {
    return dataView.getUint8(offset);
}
```
</details>

### `getUShort(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getUint16`

<details><summary>Code</summary>

```typescript
function getUShort(dataView, offset) {
    return dataView.getUint16(offset, false);
}
```
</details>

### `getShort(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getInt16`

<details><summary>Code</summary>

```typescript
function getShort(dataView, offset) {
    return dataView.getInt16(offset, false);
}
```
</details>

### `getULong(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getUint32`

<details><summary>Code</summary>

```typescript
function getULong(dataView, offset) {
    return dataView.getUint32(offset, false);
}
```
</details>

### `getFixed(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getInt16`
- `dataView.getUint16`

<details><summary>Code</summary>

```typescript
function getFixed(dataView, offset) {
    var decimal = dataView.getInt16(offset, false);
    var fraction = dataView.getUint16(offset + 2, false);
    return decimal + fraction / 65535;
}
```
</details>

### `getTag(dataView: any, offset: any): string`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`
- `dataView.getInt8`

<details><summary>Code</summary>

```typescript
function getTag(dataView, offset) {
    var tag = '';
    for (var i = offset; i < offset + 4; i += 1) {
        tag += String.fromCharCode(dataView.getInt8(i));
    }

    return tag;
}
```
</details>

### `getOffset(dataView: any, offset: any, offSize: any): number`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`
- **`offSize`** `any`

**Returns:** `number`

**Calls:**

- `dataView.getUint8`

<details><summary>Code</summary>

```typescript
function getOffset(dataView, offset, offSize) {
    var v = 0;
    for (var i = 0; i < offSize; i += 1) {
        v <<= 8;
        v += dataView.getUint8(offset + i);
    }

    return v;
}
```
</details>

### `getBytes(dataView: any, startOffset: any, endOffset: any): any[]`

**Parameters:**

- **`dataView`** `any`
- **`startOffset`** `any`
- **`endOffset`** `any`

**Returns:** `any[]`

**Calls:**

- `bytes.push`
- `dataView.getUint8`

<details><summary>Code</summary>

```typescript
function getBytes(dataView, startOffset, endOffset) {
    var bytes = [];
    for (var i = startOffset; i < endOffset; i += 1) {
        bytes.push(dataView.getUint8(i));
    }

    return bytes;
}
```
</details>

### `bytesToString(bytes: any): string`

**Parameters:**

- **`bytes`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function bytesToString(bytes) {
    var s = '';
    for (var i = 0; i < bytes.length; i += 1) {
        s += String.fromCharCode(bytes[i]);
    }

    return s;
}
```
</details>

### `Parser(data: any, offset: any): void`

**Parameters:**

- **`data`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Parser(data, offset) {
    this.data = data;
    this.offset = offset;
    this.relativeOffset = 0;
}
```
</details>

### `parseCmapTableFormat12(cmap: any, p: any): void`

**Parameters:**

- **`cmap`** `any`
- **`p`** `any`

**Returns:** `void`

**Calls:**

- `p.parseUShort`
- `p.parseULong`

**Internal Comments:**
```
//Skip reserved. (x4)
// Length in bytes of the sub-tables. (x4)
```

<details><summary>Code</summary>

```typescript
function parseCmapTableFormat12(cmap, p) {
    //Skip reserved.
    p.parseUShort();

    // Length in bytes of the sub-tables.
    cmap.length = p.parseULong();
    cmap.language = p.parseULong();

    var groupCount;
    cmap.groupCount = groupCount = p.parseULong();
    cmap.glyphIndexMap = {};

    for (var i = 0; i < groupCount; i += 1) {
        var startCharCode = p.parseULong();
        var endCharCode = p.parseULong();
        var startGlyphId = p.parseULong();

        for (var c = startCharCode; c <= endCharCode; c += 1) {
            cmap.glyphIndexMap[c] = startGlyphId;
            startGlyphId++;
        }
    }
}
```
</details>

### `parseCmapTableFormat4(cmap: any, p: any, data: any, start: any, offset: any): void`

**Parameters:**

- **`cmap`** `any`
- **`p`** `any`
- **`data`** `any`
- **`start`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `p.parseUShort`
- `p.skip`
- `endCountParser.parseUShort`
- `startCountParser.parseUShort`
- `idDeltaParser.parseShort`
- `idRangeOffsetParser.parseUShort`
- `parse.getUShort`

**Internal Comments:**
```
// Length in bytes of the sub-tables. (x4)
// segCount is stored x 2. (x2)
// Skip searchRange, entrySelector, rangeShift. (x4)
// The "unrolled" mapping from character codes to glyph indices. (x4)
// The idRangeOffset is relative to the current position in the idRangeOffset array. (x3)
// Take the current offset in the idRangeOffset array. (x3)
// Add the value of the idRangeOffset, which will move us into the glyphIndex array. (x3)
// Then add the character index of the current segment, multiplied by 2 for USHORTs. (x3)
```

<details><summary>Code</summary>

```typescript
function parseCmapTableFormat4(cmap, p, data, start, offset) {
    // Length in bytes of the sub-tables.
    cmap.length = p.parseUShort();
    cmap.language = p.parseUShort();

    // segCount is stored x 2.
    var segCount;
    cmap.segCount = segCount = p.parseUShort() >> 1;

    // Skip searchRange, entrySelector, rangeShift.
    p.skip('uShort', 3);

    // The "unrolled" mapping from character codes to glyph indices.
    cmap.glyphIndexMap = {};
    var endCountParser = new parse.Parser(data, start + offset + 14);
    var startCountParser = new parse.Parser(data, start + offset + 16 + segCount * 2);
    var idDeltaParser = new parse.Parser(data, start + offset + 16 + segCount * 4);
    var idRangeOffsetParser = new parse.Parser(data, start + offset + 16 + segCount * 6);
    var glyphIndexOffset = start + offset + 16 + segCount * 8;
    for (var i = 0; i < segCount - 1; i += 1) {
        var glyphIndex = (void 0);
        var endCount = endCountParser.parseUShort();
        var startCount = startCountParser.parseUShort();
        var idDelta = idDeltaParser.parseShort();
        var idRangeOffset = idRangeOffsetParser.parseUShort();
        for (var c = startCount; c <= endCount; c += 1) {
            if (idRangeOffset !== 0) {
                // The idRangeOffset is relative to the current position in the idRangeOffset array.
                // Take the current offset in the idRangeOffset array.
                glyphIndexOffset = (idRangeOffsetParser.offset + idRangeOffsetParser.relativeOffset - 2);

                // Add the value of the idRangeOffset, which will move us into the glyphIndex array.
                glyphIndexOffset += idRangeOffset;

                // Then add the character index of the current segment, multiplied by 2 for USHORTs.
                glyphIndexOffset += (c - startCount) * 2;
                glyphIndex = parse.getUShort(data, glyphIndexOffset);
                if (glyphIndex !== 0) {
                    glyphIndex = (glyphIndex + idDelta) & 0xFFFF;
                }
            } else {
                glyphIndex = (c + idDelta) & 0xFFFF;
            }

            cmap.glyphIndexMap[c] = glyphIndex;
        }
    }
}
```
</details>

### `parseCmapTable(data: any, start: any): { version: any; numTables: any; format: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; numTables: any; format: any; }`

**Calls:**

- `parse.getUShort`
- `check.argument`
- `parse.getULong`
- `p.parseUShort`
- `parseCmapTableFormat12`
- `parseCmapTableFormat4`

**Internal Comments:**
```
// The cmap table can contain many sub-tables, each with their own format. (x4)
// We're only interested in a "platform 0" (Unicode format) and "platform 3" (Windows format) table. (x4)
// There is no cmap table in the font that we support.
```

<details><summary>Code</summary>

```typescript
function parseCmapTable(data, start) {
    var cmap = {};
    cmap.version = parse.getUShort(data, start);
    check.argument(cmap.version === 0, 'cmap table version should be 0.');

    // The cmap table can contain many sub-tables, each with their own format.
    // We're only interested in a "platform 0" (Unicode format) and "platform 3" (Windows format) table.
    cmap.numTables = parse.getUShort(data, start + 2);
    var offset = -1;
    for (var i = cmap.numTables - 1; i >= 0; i -= 1) {
        var platformId = parse.getUShort(data, start + 4 + (i * 8));
        var encodingId = parse.getUShort(data, start + 4 + (i * 8) + 2);
        if ((platformId === 3 && (encodingId === 0 || encodingId === 1 || encodingId === 10)) ||
            (platformId === 0 && (encodingId === 0 || encodingId === 1 || encodingId === 2 || encodingId === 3 || encodingId === 4))) {
            offset = parse.getULong(data, start + 4 + (i * 8) + 4);
            break;
        }
    }

    if (offset === -1) {
        // There is no cmap table in the font that we support.
        throw new Error('No valid cmap sub-tables found.');
    }

    var p = new parse.Parser(data, start + offset);
    cmap.format = p.parseUShort();

    if (cmap.format === 12) {
        parseCmapTableFormat12(cmap, p);
    } else if (cmap.format === 4) {
        parseCmapTableFormat4(cmap, p, data, start, offset);
    } else {
        throw new Error('Only format 4 and 12 cmap tables are supported (found format ' + cmap.format + ').');
    }

    return cmap;
}
```
</details>

### `addSegment(t: any, code: any, glyphIndex: any): void`

**Parameters:**

- **`t`** `any`
- **`code`** `any`
- **`glyphIndex`** `any`

**Returns:** `void`

**Calls:**

- `t.segments.push`

<details><summary>Code</summary>

```typescript
function addSegment(t, code, glyphIndex) {
    t.segments.push({
        end: code,
        start: code,
        delta: -(code - glyphIndex),
        offset: 0,
        glyphIndex: glyphIndex
    });
}
```
</details>

### `addTerminatorSegment(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `t.segments.push`

<details><summary>Code</summary>

```typescript
function addTerminatorSegment(t) {
    t.segments.push({
        end: 0xFFFF,
        start: 0xFFFF,
        delta: 1,
        offset: 0
    });
}
```
</details>

### `makeCmapTable(glyphs: any): Table`

**Parameters:**

- **`glyphs`** `any`

**Returns:** `Table`

**Calls:**

- `glyphs.get`
- `console.log`
- `cmapTable.concat`
- `addSegment`
- `t.segments.sort`
- `addTerminatorSegment`
- `endCounts.concat`
- `startCounts.concat`
- `idDeltas.concat`
- `idRangeOffsets.concat`
- `glyphIds.concat`
- `cmap12Groups.concat`
- `Math.pow`
- `Math.floor`
- `Math.log`
- `t.fields.concat`
- `t.fields.push`

**Internal Comments:**
```
// Plan 0 is the base Unicode Plan but emojis, for example are on another plan, and needs cmap 12 format (with 32bit) (x2)
// Check if we need to add cmap format 12 or if format 4 only is fine
// CMAP 4 header
// CMAP 12 header
// CMAP 4 Subtable (x5)
// CMAP 4 (x3)
// Set up parallel segment arrays. (x2)
// CMAP 12 (x3)
// Reminder this loop is not following the specification at 100%
// The specification -> find suites of characters and make a group
// Here we're doing one group for each letter
// Doing as the spec can save 8 times (or more) space
// Skip Unicode > 65535 (16bit unsigned max) for CMAP 4, will be added in CMAP 12 (x3)
// Skip Terminator Segment
// CMAP 12 Subtable (x2)
```

<details><summary>Code</summary>

```typescript
function makeCmapTable(glyphs) {
    // Plan 0 is the base Unicode Plan but emojis, for example are on another plan, and needs cmap 12 format (with 32bit)
    var isPlan0Only = true;
    var i;

    // Check if we need to add cmap format 12 or if format 4 only is fine
    for (i = glyphs.length - 1; i > 0; i -= 1) {
        var g = glyphs.get(i);
        if (g.unicode > 65535) {
            console.log('Adding CMAP format 12 (needed!)');
            isPlan0Only = false;
            break;
        }
    }

    var cmapTable = [
        {name: 'version', type: 'USHORT', value: 0},
        {name: 'numTables', type: 'USHORT', value: isPlan0Only ? 1 : 2},

        // CMAP 4 header
        {name: 'platformID', type: 'USHORT', value: 3},
        {name: 'encodingID', type: 'USHORT', value: 1},
        {name: 'offset', type: 'ULONG', value: isPlan0Only ? 12 : (12 + 8)}
    ];

    if (!isPlan0Only)
        { cmapTable = cmapTable.concat([
            // CMAP 12 header
            {name: 'cmap12PlatformID', type: 'USHORT', value: 3}, // We encode only for PlatformID = 3 (Windows) because it is supported everywhere
            {name: 'cmap12EncodingID', type: 'USHORT', value: 10},
            {name: 'cmap12Offset', type: 'ULONG', value: 0}
        ]); }

    cmapTable = cmapTable.concat([
        // CMAP 4 Subtable
        {name: 'format', type: 'USHORT', value: 4},
        {name: 'cmap4Length', type: 'USHORT', value: 0},
        {name: 'language', type: 'USHORT', value: 0},
        {name: 'segCountX2', type: 'USHORT', value: 0},
        {name: 'searchRange', type: 'USHORT', value: 0},
        {name: 'entrySelector', type: 'USHORT', value: 0},
        {name: 'rangeShift', type: 'USHORT', value: 0}
    ]);

    var t = new table.Table('cmap', cmapTable);

    t.segments = [];
    for (i = 0; i < glyphs.length; i += 1) {
        var glyph = glyphs.get(i);
        for (var j = 0; j < glyph.unicodes.length; j += 1) {
            addSegment(t, glyph.unicodes[j], i);
        }

        t.segments = t.segments.sort(function (a, b) {
            return a.start - b.start;
        });
    }

    addTerminatorSegment(t);

    var segCount = t.segments.length;
    var segCountToRemove = 0;

    // CMAP 4
    // Set up parallel segment arrays.
    var endCounts = [];
    var startCounts = [];
    var idDeltas = [];
    var idRangeOffsets = [];
    var glyphIds = [];

    // CMAP 12
    var cmap12Groups = [];

    // Reminder this loop is not following the specification at 100%
    // The specification -> find suites of characters and make a group
    // Here we're doing one group for each letter
    // Doing as the spec can save 8 times (or more) space
    for (i = 0; i < segCount; i += 1) {
        var segment = t.segments[i];

        // CMAP 4
        if (segment.end <= 65535 && segment.start <= 65535) {
            endCounts = endCounts.concat({name: 'end_' + i, type: 'USHORT', value: segment.end});
            startCounts = startCounts.concat({name: 'start_' + i, type: 'USHORT', value: segment.start});
            idDeltas = idDeltas.concat({name: 'idDelta_' + i, type: 'SHORT', value: segment.delta});
            idRangeOffsets = idRangeOffsets.concat({name: 'idRangeOffset_' + i, type: 'USHORT', value: segment.offset});
            if (segment.glyphId !== undefined) {
                glyphIds = glyphIds.concat({name: 'glyph_' + i, type: 'USHORT', value: segment.glyphId});
            }
        } else {
            // Skip Unicode > 65535 (16bit unsigned max) for CMAP 4, will be added in CMAP 12
            segCountToRemove += 1;
        }

        // CMAP 12
        // Skip Terminator Segment
        if (!isPlan0Only && segment.glyphIndex !== undefined) {
            cmap12Groups = cmap12Groups.concat({name: 'cmap12Start_' + i, type: 'ULONG', value: segment.start});
            cmap12Groups = cmap12Groups.concat({name: 'cmap12End_' + i, type: 'ULONG', value: segment.end});
            cmap12Groups = cmap12Groups.concat({name: 'cmap12Glyph_' + i, type: 'ULONG', value: segment.glyphIndex});
        }
    }

    // CMAP 4 Subtable
    t.segCountX2 = (segCount - segCountToRemove) * 2;
    t.searchRange = Math.pow(2, Math.floor(Math.log((segCount - segCountToRemove)) / Math.log(2))) * 2;
    t.entrySelector = Math.log(t.searchRange / 2) / Math.log(2);
    t.rangeShift = t.segCountX2 - t.searchRange;

    t.fields = t.fields.concat(endCounts);
    t.fields.push({name: 'reservedPad', type: 'USHORT', value: 0});
    t.fields = t.fields.concat(startCounts);
    t.fields = t.fields.concat(idDeltas);
    t.fields = t.fields.concat(idRangeOffsets);
    t.fields = t.fields.concat(glyphIds);

    t.cmap4Length = 14 + // Subtable header
        endCounts.length * 2 +
        2 + // reservedPad
        startCounts.length * 2 +
        idDeltas.length * 2 +
        idRangeOffsets.length * 2 +
        glyphIds.length * 2;

    if (!isPlan0Only) {
        // CMAP 12 Subtable
        var cmap12Length = 16 + // Subtable header
            cmap12Groups.length * 4;

        t.cmap12Offset = 12 + (2 * 2) + 4 + t.cmap4Length;
        t.fields = t.fields.concat([
            {name: 'cmap12Format', type: 'USHORT', value: 12},
            {name: 'cmap12Reserved', type: 'USHORT', value: 0},
            {name: 'cmap12Length', type: 'ULONG', value: cmap12Length},
            {name: 'cmap12Language', type: 'ULONG', value: 0},
            {name: 'cmap12nGroups', type: 'ULONG', value: cmap12Groups.length / 3}
        ]);

        t.fields = t.fields.concat(cmap12Groups);
    }

    return t;
}
```
</details>

### `DefaultEncoding(font: any): void`

**JSDoc:**
```typescript
/**
 * This is the encoding used for fonts created from scratch.
 * It loops through all glyphs and finds the appropriate unicode value.
 * Since it's linear time, other encodings will be faster.
 * @exports opentype.DefaultEncoding
 * @class
 * @constructor
 * @param {opentype.Font}
 */
```

**Parameters:**

- **`font`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function DefaultEncoding(font) {
    this.font = font;
}
```
</details>

### `CmapEncoding(cmap: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.CmapEncoding
 * @class
 * @constructor
 * @param {Object} cmap - a object with the cmap encoded data
 */
```

**Parameters:**

- **`cmap`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CmapEncoding(cmap) {
    this.cmap = cmap;
}
```
</details>

### `CffEncoding(encoding: string, charset: any[]): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.CffEncoding
 * @class
 * @constructor
 * @param {string} encoding - The encoding
 * @param {Array} charset - The character set.
 */
```

**Parameters:**

- **`encoding`** `string`
- **`charset`** `any[]`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CffEncoding(encoding, charset) {
    this.encoding = encoding;
    this.charset = charset;
}
```
</details>

### `GlyphNames(post: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.GlyphNames
 * @class
 * @constructor
 * @param {Object} post
 */
```

**Parameters:**

- **`post`** `any`

**Returns:** `void`

**Calls:**

- `standardNames.slice`

<details><summary>Code</summary>

```typescript
function GlyphNames(post) {
    switch (post.version) {
        case 1:
            this.names = standardNames.slice();
            break;
        case 2:
            this.names = new Array(post.numberOfGlyphs);
            for (var i = 0; i < post.numberOfGlyphs; i++) {
                if (post.glyphNameIndex[i] < standardNames.length) {
                    this.names[i] = standardNames[post.glyphNameIndex[i]];
                } else {
                    this.names[i] = post.names[post.glyphNameIndex[i] - standardNames.length];
                }
            }

            break;
        case 2.5:
            this.names = new Array(post.numberOfGlyphs);
            for (var i$1 = 0; i$1 < post.numberOfGlyphs; i$1++) {
                this.names[i$1] = standardNames[i$1 + post.glyphNameIndex[i$1]];
            }

            break;
        case 3:
            this.names = [];
            break;
        default:
            this.names = [];
            break;
    }
}
```
</details>

### `addGlyphNamesAll(font: any): void`

**Parameters:**

- **`font`** `any`

**Returns:** `void`

**Calls:**

- `Object.keys`
- `font.glyphs.get`
- `glyph.addUnicode`
- `parseInt`
- `font.glyphNames.glyphIndexToName`

<details><summary>Code</summary>

```typescript
function addGlyphNamesAll(font) {
    var glyph;
    var glyphIndexMap = font.tables.cmap.glyphIndexMap;
    var charCodes = Object.keys(glyphIndexMap);

    for (var i = 0; i < charCodes.length; i += 1) {
        var c = charCodes[i];
        var glyphIndex = glyphIndexMap[c];
        glyph = font.glyphs.get(glyphIndex);
        glyph.addUnicode(parseInt(c));
    }

    for (var i$1 = 0; i$1 < font.glyphs.length; i$1 += 1) {
        glyph = font.glyphs.get(i$1);
        if (font.cffEncoding) {
            if (font.isCIDFont) {
                glyph.name = 'gid' + i$1;
            } else {
                glyph.name = font.cffEncoding.charset[i$1];
            }
        } else if (font.glyphNames.names) {
            glyph.name = font.glyphNames.glyphIndexToName(i$1);
        }
    }
}
```
</details>

### `addGlyphNamesToUnicodeMap(font: any): void`

**Parameters:**

- **`font`** `any`

**Returns:** `void`

**Calls:**

- `Object.keys`
- `parseInt`
- `font._IndexToUnicodeMap[glyphIndex].unicodes.push`

<details><summary>Code</summary>

```typescript
function addGlyphNamesToUnicodeMap(font) {
    font._IndexToUnicodeMap = {};

    var glyphIndexMap = font.tables.cmap.glyphIndexMap;
    var charCodes = Object.keys(glyphIndexMap);

    for (var i = 0; i < charCodes.length; i += 1) {
        var c = charCodes[i];
        var glyphIndex = glyphIndexMap[c];
        if (font._IndexToUnicodeMap[glyphIndex] === undefined) {
            font._IndexToUnicodeMap[glyphIndex] = {
                unicodes: [parseInt(c)]
            };
        } else {
            font._IndexToUnicodeMap[glyphIndex].unicodes.push(parseInt(c));
        }
    }
}
```
</details>

### `addGlyphNames(font: any, opt: any): void`

**JSDoc:**
```typescript
/**
 * @alias opentype.addGlyphNames
 * @param {opentype.Font}
 * @param {Object}
 */
```

**Parameters:**

- **`font`** `any`
- **`opt`** `any`

**Returns:** `void`

**Calls:**

- `addGlyphNamesToUnicodeMap`
- `addGlyphNamesAll`

<details><summary>Code</summary>

```typescript
function addGlyphNames(font, opt) {
    if (opt.lowMemory) {
        addGlyphNamesToUnicodeMap(font);
    } else {
        addGlyphNamesAll(font);
    }
}
```
</details>

### `line(ctx: any, x1: any, y1: any, x2: any, y2: any): void`

**Parameters:**

- **`ctx`** `any`
- **`x1`** `any`
- **`y1`** `any`
- **`x2`** `any`
- **`y2`** `any`

**Returns:** `void`

**Calls:**

- `ctx.beginPath`
- `ctx.moveTo`
- `ctx.lineTo`
- `ctx.stroke`

<details><summary>Code</summary>

```typescript
function line(ctx, x1, y1, x2, y2) {
    ctx.beginPath();
    ctx.moveTo(x1, y1);
    ctx.lineTo(x2, y2);
    ctx.stroke();
}
```
</details>

### `getPathDefinition(glyph: any, path: any): { configurable: boolean; get: () => any; set: (p: any) => void; }`

**Parameters:**

- **`glyph`** `any`
- **`path`** `any`

**Returns:** `{ configurable: boolean; get: () => any; set: (p: any) => void; }`

**Calls:**

- `_path`

<details><summary>Code</summary>

```typescript
function getPathDefinition(glyph, path) {
    var _path = path || new Path();
    return {
        configurable: true,

        get: function() {
            if (typeof _path === 'function') {
                _path = _path();
            }

            return _path;
        },

        set: function(p) {
            _path = p;
        }
    };
}
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `_path`

<details><summary>Code</summary>

```typescript
function() {
            if (typeof _path === 'function') {
                _path = _path();
            }

            return _path;
        }
```
</details>

### `set(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(p) {
            _path = p;
        }
```
</details>

### `get(): any`

**Returns:** `any`

**Calls:**

- `_path`

<details><summary>Code</summary>

```typescript
function() {
            if (typeof _path === 'function') {
                _path = _path();
            }

            return _path;
        }
```
</details>

### `set(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(p) {
            _path = p;
        }
```
</details>

### `Glyph(options: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.Glyph
 * @class
 * @param {GlyphOptions}
 * @constructor
 */
```

**Parameters:**

- **`options`** `any`

**Returns:** `void`

**Calls:**

- `this.bindConstructorValues`

**Internal Comments:**
```
// By putting all the code on a prototype function (which is only declared once) (x4)
// we reduce the memory requirements for larger fonts by some 2% (x4)
```

<details><summary>Code</summary>

```typescript
function Glyph(options) {
    // By putting all the code on a prototype function (which is only declared once)
    // we reduce the memory requirements for larger fonts by some 2%
    this.bindConstructorValues(options);
}
```
</details>

### `drawCircles(l: any, x: any, y: any, scale: any): void`

**Parameters:**

- **`l`** `any`
- **`x`** `any`
- **`y`** `any`
- **`scale`** `any`

**Returns:** `void`

**Calls:**

- `ctx.beginPath`
- `ctx.moveTo`
- `ctx.arc`
- `ctx.closePath`
- `ctx.fill`

<details><summary>Code</summary>

```typescript
function drawCircles(l, x, y, scale) {
        ctx.beginPath();
        for (var j = 0; j < l.length; j += 1) {
            ctx.moveTo(x + (l[j].x * scale), y + (l[j].y * scale));
            ctx.arc(x + (l[j].x * scale), y + (l[j].y * scale), 2, 0, Math.PI * 2, false);
        }

        ctx.closePath();
        ctx.fill();
    }
```
</details>

### `defineDependentProperty(glyph: any, externalName: any, internalName: any): void`

**Parameters:**

- **`glyph`** `any`
- **`externalName`** `any`
- **`internalName`** `any`

**Returns:** `void`

**Calls:**

- `Object.defineProperty`

**Internal Comments:**
```
// Request the path property to make sure the path is loaded. (x3)
```

<details><summary>Code</summary>

```typescript
function defineDependentProperty(glyph, externalName, internalName) {
    Object.defineProperty(glyph, externalName, {
        get: function() {
            // Request the path property to make sure the path is loaded.
            glyph.path; // jshint ignore:line
            return glyph[internalName];
        },
        set: function(newValue) {
            glyph[internalName] = newValue;
        },
        enumerable: true,
        configurable: true
    });
}
```
</details>

### `get(): any`

**Returns:** `any`

**Internal Comments:**
```
// Request the path property to make sure the path is loaded. (x3)
```

<details><summary>Code</summary>

```typescript
function() {
            // Request the path property to make sure the path is loaded.
            glyph.path; // jshint ignore:line
            return glyph[internalName];
        }
```
</details>

### `set(newValue: any): void`

**Parameters:**

- **`newValue`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(newValue) {
            glyph[internalName] = newValue;
        }
```
</details>

### `get(): any`

**Returns:** `any`

**Internal Comments:**
```
// Request the path property to make sure the path is loaded. (x3)
```

<details><summary>Code</summary>

```typescript
function() {
            // Request the path property to make sure the path is loaded.
            glyph.path; // jshint ignore:line
            return glyph[internalName];
        }
```
</details>

### `set(newValue: any): void`

**Parameters:**

- **`newValue`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(newValue) {
            glyph[internalName] = newValue;
        }
```
</details>

### `GlyphSet(font: any, glyphs: any): void`

**JSDoc:**
```typescript
/**
 * A GlyphSet represents all glyphs available in the font, but modelled using
 * a deferred glyph loader, for retrieving glyphs only once they are absolutely
 * necessary, to keep the memory footprint down.
 * @exports opentype.GlyphSet
 * @class
 * @param {opentype.Font}
 * @param {Array}
 */
```

**Parameters:**

- **`font`** `any`
- **`glyphs`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
function GlyphSet(font, glyphs) {
    this.font = font;
    this.glyphs = {};
    if (Array.isArray(glyphs)) {
        for (var i = 0; i < glyphs.length; i++) {
            var glyph = glyphs[i];
            glyph.path.unitsPerEm = font.unitsPerEm;
            this.glyphs[i] = glyph;
        }
    }

    this.length = (glyphs && glyphs.length) || 0;
}
```
</details>

### `glyphLoader(font: opentype.Font, index: number): opentype.Glyph`

**JSDoc:**
```typescript
/**
 * @alias opentype.glyphLoader
 * @param  {opentype.Font} font
 * @param  {number} index
 * @return {opentype.Glyph}
 */
```

**Parameters:**

- **`font`** `opentype.Font`
- **`index`** `number`

**Returns:** `opentype.Glyph`

<details><summary>Code</summary>

```typescript
function glyphLoader(font, index) {
    return new Glyph({index: index, font: font});
}
```
</details>

### `ttfGlyphLoader(font: opentype.Font, index: number, parseGlyph: Function, data: any, position: number, buildPath: Function): opentype.Glyph`

**JSDoc:**
```typescript
/**
 * Generate a stub glyph that can be filled with all metadata *except*
 * the "points" and "path" properties, which must be loaded only once
 * the glyph's path is actually requested for text shaping.
 * @alias opentype.ttfGlyphLoader
 * @param  {opentype.Font} font
 * @param  {number} index
 * @param  {Function} parseGlyph
 * @param  {Object} data
 * @param  {number} position
 * @param  {Function} buildPath
 * @return {opentype.Glyph}
 */
```

**Parameters:**

- **`font`** `opentype.Font`
- **`index`** `number`
- **`parseGlyph`** `Function`
- **`data`** `any`
- **`position`** `number`
- **`buildPath`** `Function`

**Returns:** `opentype.Glyph`

**Calls:**

- `parseGlyph`
- `buildPath`
- `defineDependentProperty`

<details><summary>Code</summary>

```typescript
function ttfGlyphLoader(font, index, parseGlyph, data, position, buildPath) {
    return function() {
        var glyph = new Glyph({index: index, font: font});

        glyph.path = function() {
            parseGlyph(glyph, data, position);
            var path = buildPath(font.glyphs, glyph);
            path.unitsPerEm = font.unitsPerEm;
            return path;
        };

        defineDependentProperty(glyph, 'xMin', '_xMin');
        defineDependentProperty(glyph, 'xMax', '_xMax');
        defineDependentProperty(glyph, 'yMin', '_yMin');
        defineDependentProperty(glyph, 'yMax', '_yMax');

        return glyph;
    };
}
```
</details>

### `cffGlyphLoader(font: opentype.Font, index: number, parseCFFCharstring: Function, charstring: string): opentype.Glyph`

**JSDoc:**
```typescript
/**
 * @alias opentype.cffGlyphLoader
 * @param  {opentype.Font} font
 * @param  {number} index
 * @param  {Function} parseCFFCharstring
 * @param  {string} charstring
 * @return {opentype.Glyph}
 */
```

**Parameters:**

- **`font`** `opentype.Font`
- **`index`** `number`
- **`parseCFFCharstring`** `Function`
- **`charstring`** `string`

**Returns:** `opentype.Glyph`

**Calls:**

- `parseCFFCharstring`

<details><summary>Code</summary>

```typescript
function cffGlyphLoader(font, index, parseCFFCharstring, charstring) {
    return function() {
        var glyph = new Glyph({index: index, font: font});

        glyph.path = function() {
            var path = parseCFFCharstring(font, glyph, charstring);
            path.unitsPerEm = font.unitsPerEm;
            return path;
        };

        return glyph;
    };
}
```
</details>

### `equals(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

**Calls:**

- `Array.isArray`
- `equals`

<details><summary>Code</summary>

```typescript
function equals(a, b) {
    if (a === b) {
        return true;
    } else if (Array.isArray(a) && Array.isArray(b)) {
        if (a.length !== b.length) {
            return false;
        }

        for (var i = 0; i < a.length; i += 1) {
            if (!equals(a[i], b[i])) {
                return false;
            }
        }

        return true;
    } else {
        return false;
    }
}
```
</details>

### `calcCFFSubroutineBias(subrs: any): number`

**Parameters:**

- **`subrs`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function calcCFFSubroutineBias(subrs) {
    var bias;
    if (subrs.length < 1240) {
        bias = 107;
    } else if (subrs.length < 33900) {
        bias = 1131;
    } else {
        bias = 32768;
    }

    return bias;
}
```
</details>

### `parseCFFIndex(data: any, start: any, conversionFn: any): { objects: any[][]; startOffset: any; endOffset: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`conversionFn`** `any`

**Returns:** `{ objects: any[][]; startOffset: any; endOffset: any; }`

**Calls:**

- `parse.getCard16`
- `parse.getByte`
- `offsets.push`
- `parse.getOffset`
- `parse.getBytes`
- `conversionFn`
- `objects.push`

**Internal Comments:**
```
// The total size of the index array is 4 header bytes + the value of the last offset. (x3)
```

<details><summary>Code</summary>

```typescript
function parseCFFIndex(data, start, conversionFn) {
    var offsets = [];
    var objects = [];
    var count = parse.getCard16(data, start);
    var objectOffset;
    var endOffset;
    if (count !== 0) {
        var offsetSize = parse.getByte(data, start + 2);
        objectOffset = start + ((count + 1) * offsetSize) + 2;
        var pos = start + 3;
        for (var i = 0; i < count + 1; i += 1) {
            offsets.push(parse.getOffset(data, pos, offsetSize));
            pos += offsetSize;
        }

        // The total size of the index array is 4 header bytes + the value of the last offset.
        endOffset = objectOffset + offsets[count];
    } else {
        endOffset = start + 2;
    }

    for (var i$1 = 0; i$1 < offsets.length - 1; i$1 += 1) {
        var value = parse.getBytes(data, objectOffset + offsets[i$1], objectOffset + offsets[i$1 + 1]);
        if (conversionFn) {
            value = conversionFn(value);
        }

        objects.push(value);
    }

    return {objects: objects, startOffset: start, endOffset: endOffset};
}
```
</details>

### `parseCFFIndexLowMemory(data: any, start: any): { offsets: number[]; startOffset: any; endOffset: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ offsets: number[]; startOffset: any; endOffset: any; }`

**Calls:**

- `parse.getCard16`
- `parse.getByte`
- `offsets.push`
- `parse.getOffset`

**Internal Comments:**
```
// The total size of the index array is 4 header bytes + the value of the last offset. (x3)
```

<details><summary>Code</summary>

```typescript
function parseCFFIndexLowMemory(data, start) {
    var offsets = [];
    var count = parse.getCard16(data, start);
    var objectOffset;
    var endOffset;
    if (count !== 0) {
        var offsetSize = parse.getByte(data, start + 2);
        objectOffset = start + ((count + 1) * offsetSize) + 2;
        var pos = start + 3;
        for (var i = 0; i < count + 1; i += 1) {
            offsets.push(parse.getOffset(data, pos, offsetSize));
            pos += offsetSize;
        }

        // The total size of the index array is 4 header bytes + the value of the last offset.
        endOffset = objectOffset + offsets[count];
    } else {
        endOffset = start + 2;
    }

    return {offsets: offsets, startOffset: start, endOffset: endOffset};
}
```
</details>

### `getCffIndexObject(i: any, offsets: any, data: any, start: any, conversionFn: any): any[]`

**Parameters:**

- **`i`** `any`
- **`offsets`** `any`
- **`data`** `any`
- **`start`** `any`
- **`conversionFn`** `any`

**Returns:** `any[]`

**Calls:**

- `parse.getCard16`
- `parse.getByte`
- `parse.getBytes`
- `conversionFn`

<details><summary>Code</summary>

```typescript
function getCffIndexObject(i, offsets, data, start, conversionFn) {
    var count = parse.getCard16(data, start);
    var objectOffset = 0;
    if (count !== 0) {
        var offsetSize = parse.getByte(data, start + 2);
        objectOffset = start + ((count + 1) * offsetSize) + 2;
    }

    var value = parse.getBytes(data, objectOffset + offsets[i], objectOffset + offsets[i + 1]);
    if (conversionFn) {
        value = conversionFn(value);
    }
    return value;
}
```
</details>

### `parseFloatOperand(parser: any): number`

**Parameters:**

- **`parser`** `any`

**Returns:** `number`

**Calls:**

- `parser.parseByte`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function parseFloatOperand(parser) {
    var s = '';
    var eof = 15;
    var lookup = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '.', 'E', 'E-', null, '-'];
    while (true) {
        var b = parser.parseByte();
        var n1 = b >> 4;
        var n2 = b & 15;

        if (n1 === eof) {
            break;
        }

        s += lookup[n1];

        if (n2 === eof) {
            break;
        }

        s += lookup[n2];
    }

    return parseFloat(s);
}
```
</details>

### `parseOperand(parser: any, b0: any): any`

**Parameters:**

- **`parser`** `any`
- **`b0`** `any`

**Returns:** `any`

**Calls:**

- `parser.parseByte`
- `parseFloatOperand`

<details><summary>Code</summary>

```typescript
function parseOperand(parser, b0) {
    var b1;
    var b2;
    var b3;
    var b4;
    if (b0 === 28) {
        b1 = parser.parseByte();
        b2 = parser.parseByte();
        return b1 << 8 | b2;
    }

    if (b0 === 29) {
        b1 = parser.parseByte();
        b2 = parser.parseByte();
        b3 = parser.parseByte();
        b4 = parser.parseByte();
        return b1 << 24 | b2 << 16 | b3 << 8 | b4;
    }

    if (b0 === 30) {
        return parseFloatOperand(parser);
    }

    if (b0 >= 32 && b0 <= 246) {
        return b0 - 139;
    }

    if (b0 >= 247 && b0 <= 250) {
        b1 = parser.parseByte();
        return (b0 - 247) * 256 + b1 + 108;
    }

    if (b0 >= 251 && b0 <= 254) {
        b1 = parser.parseByte();
        return -(b0 - 251) * 256 - b1 - 108;
    }

    throw new Error('Invalid b0 ' + b0);
}
```
</details>

### `entriesToObject(entries: any): {}`

**Parameters:**

- **`entries`** `any`

**Returns:** `{}`

**Calls:**

- `o.hasOwnProperty`
- `isNaN`

<details><summary>Code</summary>

```typescript
function entriesToObject(entries) {
    var o = {};
    for (var i = 0; i < entries.length; i += 1) {
        var key = entries[i][0];
        var values = entries[i][1];
        var value = (void 0);
        if (values.length === 1) {
            value = values[0];
        } else {
            value = values;
        }

        if (o.hasOwnProperty(key) && !isNaN(o[key])) {
            throw new Error('Object ' + o + ' already has key ' + key);
        }

        o[key] = value;
    }

    return o;
}
```
</details>

### `parseCFFDict(data: any, start: any, size: any): {}`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`size`** `any`

**Returns:** `{}`

**Calls:**

- `parser.parseByte`
- `entries.push`
- `operands.push`
- `parseOperand`
- `entriesToObject`

**Internal Comments:**
```
// The first byte for each dict item distinguishes between operator (key) and operand (value).
// Values <= 21 are operators.
// Two-byte operators have an initial escape byte of 12.
// Since the operands (values) come before the operators (keys), we store all operands in a list (x4)
// until we encounter an operator. (x4)
```

<details><summary>Code</summary>

```typescript
function parseCFFDict(data, start, size) {
    start = start !== undefined ? start : 0;
    var parser = new parse.Parser(data, start);
    var entries = [];
    var operands = [];
    size = size !== undefined ? size : data.length;

    while (parser.relativeOffset < size) {
        var op = parser.parseByte();

        // The first byte for each dict item distinguishes between operator (key) and operand (value).
        // Values <= 21 are operators.
        if (op <= 21) {
            // Two-byte operators have an initial escape byte of 12.
            if (op === 12) {
                op = 1200 + parser.parseByte();
            }

            entries.push([op, operands]);
            operands = [];
        } else {
            // Since the operands (values) come before the operators (keys), we store all operands in a list
            // until we encounter an operator.
            operands.push(parseOperand(parser, op));
        }
    }

    return entriesToObject(entries);
}
```
</details>

### `getCFFString(strings: any, index: any): any`

**Parameters:**

- **`strings`** `any`
- **`index`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getCFFString(strings, index) {
    if (index <= 390) {
        index = cffStandardStrings[index];
    } else {
        index = strings[index - 391];
    }

    return index;
}
```
</details>

### `interpretDict(dict: any, meta: any, strings: any): {}`

**Parameters:**

- **`dict`** `any`
- **`meta`** `any`
- **`strings`** `any`

**Returns:** `{}`

**Calls:**

- `Array.isArray`
- `getCFFString`

**Internal Comments:**
```
// Because we also want to include missing values, we start out from the meta list
// and lookup values in the dict.
```

<details><summary>Code</summary>

```typescript
function interpretDict(dict, meta, strings) {
    var newDict = {};
    var value;

    // Because we also want to include missing values, we start out from the meta list
    // and lookup values in the dict.
    for (var i = 0; i < meta.length; i += 1) {
        var m = meta[i];

        if (Array.isArray(m.type)) {
            var values = [];
            values.length = m.type.length;
            for (var j = 0; j < m.type.length; j++) {
                value = dict[m.op] !== undefined ? dict[m.op][j] : undefined;
                if (value === undefined) {
                    value = m.value !== undefined && m.value[j] !== undefined ? m.value[j] : null;
                }
                if (m.type[j] === 'SID') {
                    value = getCFFString(strings, value);
                }
                values[j] = value;
            }
            newDict[m.name] = values;
        } else {
            value = dict[m.op];
            if (value === undefined) {
                value = m.value !== undefined ? m.value : null;
            }

            if (m.type === 'SID') {
                value = getCFFString(strings, value);
            }
            newDict[m.name] = value;
        }
    }

    return newDict;
}
```
</details>

### `parseCFFHeader(data: any, start: any): { formatMajor: any; formatMinor: any; size: any; offsetSize: any; startOffset: any; endOffset: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ formatMajor: any; formatMinor: any; size: any; offsetSize: any; startOffset: any; endOffset: any; }`

**Calls:**

- `parse.getCard8`

<details><summary>Code</summary>

```typescript
function parseCFFHeader(data, start) {
    var header = {};
    header.formatMajor = parse.getCard8(data, start);
    header.formatMinor = parse.getCard8(data, start + 1);
    header.size = parse.getCard8(data, start + 2);
    header.offsetSize = parse.getCard8(data, start + 3);
    header.startOffset = start;
    header.endOffset = start + 4;
    return header;
}
```
</details>

### `parseCFFTopDict(data: any, strings: any): {}`

**Parameters:**

- **`data`** `any`
- **`strings`** `any`

**Returns:** `{}`

**Calls:**

- `parseCFFDict`
- `interpretDict`

<details><summary>Code</summary>

```typescript
function parseCFFTopDict(data, strings) {
    var dict = parseCFFDict(data, 0, data.byteLength);
    return interpretDict(dict, TOP_DICT_META, strings);
}
```
</details>

### `parseCFFPrivateDict(data: any, start: any, size: any, strings: any): {}`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`size`** `any`
- **`strings`** `any`

**Returns:** `{}`

**Calls:**

- `parseCFFDict`
- `interpretDict`

<details><summary>Code</summary>

```typescript
function parseCFFPrivateDict(data, start, size, strings) {
    var dict = parseCFFDict(data, start, size);
    return interpretDict(dict, PRIVATE_DICT_META, strings);
}
```
</details>

### `gatherCFFTopDicts(data: any, start: any, cffIndex: any, strings: any): {}[]`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`cffIndex`** `any`
- **`strings`** `any`

**Returns:** `{}[]`

**Calls:**

- `parseCFFTopDict`
- `parseCFFPrivateDict`
- `parseCFFIndex`
- `calcCFFSubroutineBias`
- `topDictArray.push`

<details><summary>Code</summary>

```typescript
function gatherCFFTopDicts(data, start, cffIndex, strings) {
    var topDictArray = [];
    for (var iTopDict = 0; iTopDict < cffIndex.length; iTopDict += 1) {
        var topDictData = new DataView(new Uint8Array(cffIndex[iTopDict]).buffer);
        var topDict = parseCFFTopDict(topDictData, strings);
        topDict._subrs = [];
        topDict._subrsBias = 0;
        topDict._defaultWidthX = 0;
        topDict._nominalWidthX = 0;
        var privateSize = topDict.private[0];
        var privateOffset = topDict.private[1];
        if (privateSize !== 0 && privateOffset !== 0) {
            var privateDict = parseCFFPrivateDict(data, privateOffset + start, privateSize, strings);
            topDict._defaultWidthX = privateDict.defaultWidthX;
            topDict._nominalWidthX = privateDict.nominalWidthX;
            if (privateDict.subrs !== 0) {
                var subrOffset = privateOffset + privateDict.subrs;
                var subrIndex = parseCFFIndex(data, subrOffset + start);
                topDict._subrs = subrIndex.objects;
                topDict._subrsBias = calcCFFSubroutineBias(topDict._subrs);
            }
            topDict._privateDict = privateDict;
        }
        topDictArray.push(topDict);
    }
    return topDictArray;
}
```
</details>

### `parseCFFCharset(data: any, start: any, nGlyphs: any, strings: any): string[]`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`nGlyphs`** `any`
- **`strings`** `any`

**Returns:** `string[]`

**Calls:**

- `parser.parseCard8`
- `parser.parseSID`
- `charset.push`
- `getCFFString`
- `parser.parseCard16`

**Internal Comments:**
```
// The .notdef glyph is not included, so subtract 1. (x3)
```

<details><summary>Code</summary>

```typescript
function parseCFFCharset(data, start, nGlyphs, strings) {
    var sid;
    var count;
    var parser = new parse.Parser(data, start);

    // The .notdef glyph is not included, so subtract 1.
    nGlyphs -= 1;
    var charset = ['.notdef'];

    var format = parser.parseCard8();
    if (format === 0) {
        for (var i = 0; i < nGlyphs; i += 1) {
            sid = parser.parseSID();
            charset.push(getCFFString(strings, sid));
        }
    } else if (format === 1) {
        while (charset.length <= nGlyphs) {
            sid = parser.parseSID();
            count = parser.parseCard8();
            for (var i$1 = 0; i$1 <= count; i$1 += 1) {
                charset.push(getCFFString(strings, sid));
                sid += 1;
            }
        }
    } else if (format === 2) {
        while (charset.length <= nGlyphs) {
            sid = parser.parseSID();
            count = parser.parseCard16();
            for (var i$2 = 0; i$2 <= count; i$2 += 1) {
                charset.push(getCFFString(strings, sid));
                sid += 1;
            }
        }
    } else {
        throw new Error('Unknown charset format ' + format);
    }

    return charset;
}
```
</details>

### `parseCFFEncoding(data: any, start: any, charset: any): CffEncoding`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`charset`** `any`

**Returns:** `CffEncoding`

**Calls:**

- `parser.parseCard8`

<details><summary>Code</summary>

```typescript
function parseCFFEncoding(data, start, charset) {
    var code;
    var enc = {};
    var parser = new parse.Parser(data, start);
    var format = parser.parseCard8();
    if (format === 0) {
        var nCodes = parser.parseCard8();
        for (var i = 0; i < nCodes; i += 1) {
            code = parser.parseCard8();
            enc[code] = i;
        }
    } else if (format === 1) {
        var nRanges = parser.parseCard8();
        code = 1;
        for (var i$1 = 0; i$1 < nRanges; i$1 += 1) {
            var first = parser.parseCard8();
            var nLeft = parser.parseCard8();
            for (var j = first; j <= first + nLeft; j += 1) {
                enc[j] = code;
                code += 1;
            }
        }
    } else {
        throw new Error('Unknown encoding format ' + format);
    }

    return new CffEncoding(enc, charset);
}
```
</details>

### `parseCFFCharstring(font: any, glyph: any, code: any): Path`

**Parameters:**

- **`font`** `any`
- **`glyph`** `any`
- **`code`** `any`

**Returns:** `Path`

**Calls:**

- `p.closePath`
- `p.moveTo`
- `stack.shift`
- `parseStems`
- `stack.pop`
- `newContour`
- `p.lineTo`
- `p.curveTo`
- `parse`
- `Math.abs`
- `console.log`
- `stack.push`

**Internal Comments:**
```
// The number of stem operators on the stack is always even. (x3)
// If the value is uneven, that means a width is specified. (x3)
// |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 dx6 dy6 fd flex (12 35) |- (x3)
// |- dx1 dx2 dy2 dx3 dx4 dx5 dx6 hflex (12 34) |- (x3)
// |- dx1 dy1 dx2 dy2 dx3 dx4 dx5 dy5 dx6 hflex1 (12 36) |- (x3)
// |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 d6 flex1 (12 37) |- (x3)
```

<details><summary>Code</summary>

```typescript
function parseCFFCharstring(font, glyph, code) {
    var c1x;
    var c1y;
    var c2x;
    var c2y;
    var p = new Path();
    var stack = [];
    var nStems = 0;
    var haveWidth = false;
    var open = false;
    var x = 0;
    var y = 0;
    var subrs;
    var subrsBias;
    var defaultWidthX;
    var nominalWidthX;
    if (font.isCIDFont) {
        var fdIndex = font.tables.cff.topDict._fdSelect[glyph.index];
        var fdDict = font.tables.cff.topDict._fdArray[fdIndex];
        subrs = fdDict._subrs;
        subrsBias = fdDict._subrsBias;
        defaultWidthX = fdDict._defaultWidthX;
        nominalWidthX = fdDict._nominalWidthX;
    } else {
        subrs = font.tables.cff.topDict._subrs;
        subrsBias = font.tables.cff.topDict._subrsBias;
        defaultWidthX = font.tables.cff.topDict._defaultWidthX;
        nominalWidthX = font.tables.cff.topDict._nominalWidthX;
    }
    var width = defaultWidthX;

    function newContour(x, y) {
        if (open) {
            p.closePath();
        }

        p.moveTo(x, y);
        open = true;
    }

    function parseStems() {
        var hasWidthArg;

        // The number of stem operators on the stack is always even.
        // If the value is uneven, that means a width is specified.
        hasWidthArg = stack.length % 2 !== 0;
        if (hasWidthArg && !haveWidth) {
            width = stack.shift() + nominalWidthX;
        }

        nStems += stack.length >> 1;
        stack.length = 0;
        haveWidth = true;
    }

    function parse(code) {
        var b1;
        var b2;
        var b3;
        var b4;
        var codeIndex;
        var subrCode;
        var jpx;
        var jpy;
        var c3x;
        var c3y;
        var c4x;
        var c4y;

        var i = 0;
        while (i < code.length) {
            var v = code[i];
            i += 1;
            switch (v) {
                case 1: // hstem
                    parseStems();
                    break;
                case 3: // vstem
                    parseStems();
                    break;
                case 4: // vmoveto
                    if (stack.length > 1 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    y += stack.pop();
                    newContour(x, y);
                    break;
                case 5: // rlineto
                    while (stack.length > 0) {
                        x += stack.shift();
                        y += stack.shift();
                        p.lineTo(x, y);
                    }

                    break;
                case 6: // hlineto
                    while (stack.length > 0) {
                        x += stack.shift();
                        p.lineTo(x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        y += stack.shift();
                        p.lineTo(x, y);
                    }

                    break;
                case 7: // vlineto
                    while (stack.length > 0) {
                        y += stack.shift();
                        p.lineTo(x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        x += stack.shift();
                        p.lineTo(x, y);
                    }

                    break;
                case 8: // rrcurveto
                    while (stack.length > 0) {
                        c1x = x + stack.shift();
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + stack.shift();
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 10: // callsubr
                    codeIndex = stack.pop() + subrsBias;
                    subrCode = subrs[codeIndex];
                    if (subrCode) {
                        parse(subrCode);
                    }

                    break;
                case 11: // return
                    return;
                case 12: // flex operators
                    v = code[i];
                    i += 1;
                    switch (v) {
                        case 35: // flex
                            // |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 dx6 dy6 fd flex (12 35) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y   + stack.shift();    // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y + stack.shift();    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = jpy + stack.shift();    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = c3y + stack.shift();    // dy5
                            x = c4x   + stack.shift();    // dx6
                            y = c4y   + stack.shift();    // dy6
                            stack.shift();                // flex depth
                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        case 34: // hflex
                            // |- dx1 dx2 dy2 dx3 dx4 dx5 dx6 hflex (12 34) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y;                      // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y;                    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = c2y;                    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = y;                      // dy5
                            x = c4x + stack.shift();      // dx6
                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        case 36: // hflex1
                            // |- dx1 dy1 dx2 dy2 dx3 dx4 dx5 dy5 dx6 hflex1 (12 36) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y   + stack.shift();    // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y;                    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = c2y;                    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = c3y + stack.shift();    // dy5
                            x = c4x + stack.shift();      // dx6
                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        case 37: // flex1
                            // |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 d6 flex1 (12 37) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y   + stack.shift();    // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y + stack.shift();    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = jpy + stack.shift();    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = c3y + stack.shift();    // dy5
                            if (Math.abs(c4x - x) > Math.abs(c4y - y)) {
                                x = c4x + stack.shift();
                            } else {
                                y = c4y + stack.shift();
                            }

                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        default:
                            console.log('Glyph ' + glyph.index + ': unknown operator ' + 1200 + v);
                            stack.length = 0;
                    }
                    break;
                case 14: // endchar
                    if (stack.length > 0 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    if (open) {
                        p.closePath();
                        open = false;
                    }

                    break;
                case 18: // hstemhm
                    parseStems();
                    break;
                case 19: // hintmask
                case 20: // cntrmask
                    parseStems();
                    i += (nStems + 7) >> 3;
                    break;
                case 21: // rmoveto
                    if (stack.length > 2 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    y += stack.pop();
                    x += stack.pop();
                    newContour(x, y);
                    break;
                case 22: // hmoveto
                    if (stack.length > 1 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    x += stack.pop();
                    newContour(x, y);
                    break;
                case 23: // vstemhm
                    parseStems();
                    break;
                case 24: // rcurveline
                    while (stack.length > 2) {
                        c1x = x + stack.shift();
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + stack.shift();
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    x += stack.shift();
                    y += stack.shift();
                    p.lineTo(x, y);
                    break;
                case 25: // rlinecurve
                    while (stack.length > 6) {
                        x += stack.shift();
                        y += stack.shift();
                        p.lineTo(x, y);
                    }

                    c1x = x + stack.shift();
                    c1y = y + stack.shift();
                    c2x = c1x + stack.shift();
                    c2y = c1y + stack.shift();
                    x = c2x + stack.shift();
                    y = c2y + stack.shift();
                    p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    break;
                case 26: // vvcurveto
                    if (stack.length % 2) {
                        x += stack.shift();
                    }

                    while (stack.length > 0) {
                        c1x = x;
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x;
                        y = c2y + stack.shift();
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 27: // hhcurveto
                    if (stack.length % 2) {
                        y += stack.shift();
                    }

                    while (stack.length > 0) {
                        c1x = x + stack.shift();
                        c1y = y;
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y;
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 28: // shortint
                    b1 = code[i];
                    b2 = code[i + 1];
                    stack.push(((b1 << 24) | (b2 << 16)) >> 16);
                    i += 2;
                    break;
                case 29: // callgsubr
                    codeIndex = stack.pop() + font.gsubrsBias;
                    subrCode = font.gsubrs[codeIndex];
                    if (subrCode) {
                        parse(subrCode);
                    }

                    break;
                case 30: // vhcurveto
                    while (stack.length > 0) {
                        c1x = x;
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        c1x = x + stack.shift();
                        c1y = y;
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        y = c2y + stack.shift();
                        x = c2x + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 31: // hvcurveto
                    while (stack.length > 0) {
                        c1x = x + stack.shift();
                        c1y = y;
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        y = c2y + stack.shift();
                        x = c2x + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        c1x = x;
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                default:
                    if (v < 32) {
                        console.log('Glyph ' + glyph.index + ': unknown operator ' + v);
                    } else if (v < 247) {
                        stack.push(v - 139);
                    } else if (v < 251) {
                        b1 = code[i];
                        i += 1;
                        stack.push((v - 247) * 256 + b1 + 108);
                    } else if (v < 255) {
                        b1 = code[i];
                        i += 1;
                        stack.push(-(v - 251) * 256 - b1 - 108);
                    } else {
                        b1 = code[i];
                        b2 = code[i + 1];
                        b3 = code[i + 2];
                        b4 = code[i + 3];
                        i += 4;
                        stack.push(((b1 << 24) | (b2 << 16) | (b3 << 8) | b4) / 65536);
                    }
            }
        }
    }

    parse(code);

    glyph.advanceWidth = width;
    return p;
}
```
</details>

### `newContour(x: any, y: any): void`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `void`

**Calls:**

- `p.closePath`
- `p.moveTo`

<details><summary>Code</summary>

```typescript
function newContour(x, y) {
        if (open) {
            p.closePath();
        }

        p.moveTo(x, y);
        open = true;
    }
```
</details>

### `parseStems(): void`

**Returns:** `void`

**Calls:**

- `stack.shift`

**Internal Comments:**
```
// The number of stem operators on the stack is always even. (x3)
// If the value is uneven, that means a width is specified. (x3)
```

<details><summary>Code</summary>

```typescript
function parseStems() {
        var hasWidthArg;

        // The number of stem operators on the stack is always even.
        // If the value is uneven, that means a width is specified.
        hasWidthArg = stack.length % 2 !== 0;
        if (hasWidthArg && !haveWidth) {
            width = stack.shift() + nominalWidthX;
        }

        nStems += stack.length >> 1;
        stack.length = 0;
        haveWidth = true;
    }
```
</details>

### `parse(code: any): void`

**Parameters:**

- **`code`** `any`

**Returns:** `void`

**Calls:**

- `parseStems`
- `stack.shift`
- `stack.pop`
- `newContour`
- `p.lineTo`
- `p.curveTo`
- `parse`
- `Math.abs`
- `console.log`
- `p.closePath`
- `stack.push`

**Internal Comments:**
```
// |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 dx6 dy6 fd flex (12 35) |- (x3)
// |- dx1 dx2 dy2 dx3 dx4 dx5 dx6 hflex (12 34) |- (x3)
// |- dx1 dy1 dx2 dy2 dx3 dx4 dx5 dy5 dx6 hflex1 (12 36) |- (x3)
// |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 d6 flex1 (12 37) |- (x3)
```

<details><summary>Code</summary>

```typescript
function parse(code) {
        var b1;
        var b2;
        var b3;
        var b4;
        var codeIndex;
        var subrCode;
        var jpx;
        var jpy;
        var c3x;
        var c3y;
        var c4x;
        var c4y;

        var i = 0;
        while (i < code.length) {
            var v = code[i];
            i += 1;
            switch (v) {
                case 1: // hstem
                    parseStems();
                    break;
                case 3: // vstem
                    parseStems();
                    break;
                case 4: // vmoveto
                    if (stack.length > 1 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    y += stack.pop();
                    newContour(x, y);
                    break;
                case 5: // rlineto
                    while (stack.length > 0) {
                        x += stack.shift();
                        y += stack.shift();
                        p.lineTo(x, y);
                    }

                    break;
                case 6: // hlineto
                    while (stack.length > 0) {
                        x += stack.shift();
                        p.lineTo(x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        y += stack.shift();
                        p.lineTo(x, y);
                    }

                    break;
                case 7: // vlineto
                    while (stack.length > 0) {
                        y += stack.shift();
                        p.lineTo(x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        x += stack.shift();
                        p.lineTo(x, y);
                    }

                    break;
                case 8: // rrcurveto
                    while (stack.length > 0) {
                        c1x = x + stack.shift();
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + stack.shift();
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 10: // callsubr
                    codeIndex = stack.pop() + subrsBias;
                    subrCode = subrs[codeIndex];
                    if (subrCode) {
                        parse(subrCode);
                    }

                    break;
                case 11: // return
                    return;
                case 12: // flex operators
                    v = code[i];
                    i += 1;
                    switch (v) {
                        case 35: // flex
                            // |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 dx6 dy6 fd flex (12 35) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y   + stack.shift();    // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y + stack.shift();    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = jpy + stack.shift();    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = c3y + stack.shift();    // dy5
                            x = c4x   + stack.shift();    // dx6
                            y = c4y   + stack.shift();    // dy6
                            stack.shift();                // flex depth
                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        case 34: // hflex
                            // |- dx1 dx2 dy2 dx3 dx4 dx5 dx6 hflex (12 34) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y;                      // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y;                    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = c2y;                    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = y;                      // dy5
                            x = c4x + stack.shift();      // dx6
                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        case 36: // hflex1
                            // |- dx1 dy1 dx2 dy2 dx3 dx4 dx5 dy5 dx6 hflex1 (12 36) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y   + stack.shift();    // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y;                    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = c2y;                    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = c3y + stack.shift();    // dy5
                            x = c4x + stack.shift();      // dx6
                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        case 37: // flex1
                            // |- dx1 dy1 dx2 dy2 dx3 dy3 dx4 dy4 dx5 dy5 d6 flex1 (12 37) |-
                            c1x = x   + stack.shift();    // dx1
                            c1y = y   + stack.shift();    // dy1
                            c2x = c1x + stack.shift();    // dx2
                            c2y = c1y + stack.shift();    // dy2
                            jpx = c2x + stack.shift();    // dx3
                            jpy = c2y + stack.shift();    // dy3
                            c3x = jpx + stack.shift();    // dx4
                            c3y = jpy + stack.shift();    // dy4
                            c4x = c3x + stack.shift();    // dx5
                            c4y = c3y + stack.shift();    // dy5
                            if (Math.abs(c4x - x) > Math.abs(c4y - y)) {
                                x = c4x + stack.shift();
                            } else {
                                y = c4y + stack.shift();
                            }

                            p.curveTo(c1x, c1y, c2x, c2y, jpx, jpy);
                            p.curveTo(c3x, c3y, c4x, c4y, x, y);
                            break;
                        default:
                            console.log('Glyph ' + glyph.index + ': unknown operator ' + 1200 + v);
                            stack.length = 0;
                    }
                    break;
                case 14: // endchar
                    if (stack.length > 0 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    if (open) {
                        p.closePath();
                        open = false;
                    }

                    break;
                case 18: // hstemhm
                    parseStems();
                    break;
                case 19: // hintmask
                case 20: // cntrmask
                    parseStems();
                    i += (nStems + 7) >> 3;
                    break;
                case 21: // rmoveto
                    if (stack.length > 2 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    y += stack.pop();
                    x += stack.pop();
                    newContour(x, y);
                    break;
                case 22: // hmoveto
                    if (stack.length > 1 && !haveWidth) {
                        width = stack.shift() + nominalWidthX;
                        haveWidth = true;
                    }

                    x += stack.pop();
                    newContour(x, y);
                    break;
                case 23: // vstemhm
                    parseStems();
                    break;
                case 24: // rcurveline
                    while (stack.length > 2) {
                        c1x = x + stack.shift();
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + stack.shift();
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    x += stack.shift();
                    y += stack.shift();
                    p.lineTo(x, y);
                    break;
                case 25: // rlinecurve
                    while (stack.length > 6) {
                        x += stack.shift();
                        y += stack.shift();
                        p.lineTo(x, y);
                    }

                    c1x = x + stack.shift();
                    c1y = y + stack.shift();
                    c2x = c1x + stack.shift();
                    c2y = c1y + stack.shift();
                    x = c2x + stack.shift();
                    y = c2y + stack.shift();
                    p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    break;
                case 26: // vvcurveto
                    if (stack.length % 2) {
                        x += stack.shift();
                    }

                    while (stack.length > 0) {
                        c1x = x;
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x;
                        y = c2y + stack.shift();
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 27: // hhcurveto
                    if (stack.length % 2) {
                        y += stack.shift();
                    }

                    while (stack.length > 0) {
                        c1x = x + stack.shift();
                        c1y = y;
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y;
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 28: // shortint
                    b1 = code[i];
                    b2 = code[i + 1];
                    stack.push(((b1 << 24) | (b2 << 16)) >> 16);
                    i += 2;
                    break;
                case 29: // callgsubr
                    codeIndex = stack.pop() + font.gsubrsBias;
                    subrCode = font.gsubrs[codeIndex];
                    if (subrCode) {
                        parse(subrCode);
                    }

                    break;
                case 30: // vhcurveto
                    while (stack.length > 0) {
                        c1x = x;
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        c1x = x + stack.shift();
                        c1y = y;
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        y = c2y + stack.shift();
                        x = c2x + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                case 31: // hvcurveto
                    while (stack.length > 0) {
                        c1x = x + stack.shift();
                        c1y = y;
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        y = c2y + stack.shift();
                        x = c2x + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                        if (stack.length === 0) {
                            break;
                        }

                        c1x = x;
                        c1y = y + stack.shift();
                        c2x = c1x + stack.shift();
                        c2y = c1y + stack.shift();
                        x = c2x + stack.shift();
                        y = c2y + (stack.length === 1 ? stack.shift() : 0);
                        p.curveTo(c1x, c1y, c2x, c2y, x, y);
                    }

                    break;
                default:
                    if (v < 32) {
                        console.log('Glyph ' + glyph.index + ': unknown operator ' + v);
                    } else if (v < 247) {
                        stack.push(v - 139);
                    } else if (v < 251) {
                        b1 = code[i];
                        i += 1;
                        stack.push((v - 247) * 256 + b1 + 108);
                    } else if (v < 255) {
                        b1 = code[i];
                        i += 1;
                        stack.push(-(v - 251) * 256 - b1 - 108);
                    } else {
                        b1 = code[i];
                        b2 = code[i + 1];
                        b3 = code[i + 2];
                        b4 = code[i + 3];
                        i += 4;
                        stack.push(((b1 << 24) | (b2 << 16) | (b3 << 8) | b4) / 65536);
                    }
            }
        }
    }
```
</details>

### `parseCFFFDSelect(data: any, start: any, nGlyphs: any, fdArrayCount: any): any[]`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`nGlyphs`** `any`
- **`fdArrayCount`** `any`

**Returns:** `any[]`

**Calls:**

- `parser.parseCard8`
- `fdSelect.push`
- `parser.parseCard16`

**Internal Comments:**
```
// Simple list of nGlyphs elements
// Ranges (x2)
```

<details><summary>Code</summary>

```typescript
function parseCFFFDSelect(data, start, nGlyphs, fdArrayCount) {
    var fdSelect = [];
    var fdIndex;
    var parser = new parse.Parser(data, start);
    var format = parser.parseCard8();
    if (format === 0) {
        // Simple list of nGlyphs elements
        for (var iGid = 0; iGid < nGlyphs; iGid++) {
            fdIndex = parser.parseCard8();
            if (fdIndex >= fdArrayCount) {
                throw new Error('CFF table CID Font FDSelect has bad FD index value ' + fdIndex + ' (FD count ' + fdArrayCount + ')');
            }
            fdSelect.push(fdIndex);
        }
    } else if (format === 3) {
        // Ranges
        var nRanges = parser.parseCard16();
        var first = parser.parseCard16();
        if (first !== 0) {
            throw new Error('CFF Table CID Font FDSelect format 3 range has bad initial GID ' + first);
        }
        var next;
        for (var iRange = 0; iRange < nRanges; iRange++) {
            fdIndex = parser.parseCard8();
            next = parser.parseCard16();
            if (fdIndex >= fdArrayCount) {
                throw new Error('CFF table CID Font FDSelect has bad FD index value ' + fdIndex + ' (FD count ' + fdArrayCount + ')');
            }
            if (next > nGlyphs) {
                throw new Error('CFF Table CID Font FDSelect format 3 range has bad GID ' + next);
            }
            for (; first < next; first++) {
                fdSelect.push(fdIndex);
            }
            first = next;
        }
        if (next !== nGlyphs) {
            throw new Error('CFF Table CID Font FDSelect format 3 range has bad final GID ' + next);
        }
    } else {
        throw new Error('CFF Table CID Font FDSelect table has unsupported format ' + format);
    }
    return fdSelect;
}
```
</details>

### `parseCFFTable(data: any, start: any, font: any, opt: any): void`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`font`** `any`
- **`opt`** `any`

**Returns:** `void`

**Calls:**

- `parseCFFHeader`
- `parseCFFIndex`
- `calcCFFSubroutineBias`
- `gatherCFFTopDicts`
- `parseCFFFDSelect`
- `parseCFFPrivateDict`
- `parseCFFIndexLowMemory`
- `parseCFFCharset`
- `parseCFFEncoding`
- `getCffIndexObject`
- `font.glyphs.push`
- `glyphset.cffGlyphLoader`

**Internal Comments:**
```
// Offsets in the top dict are relative to the beginning of the CFF data, so add the CFF start offset. (x2)
// Standard encoding (x4)
// Expert encoding (x4)
// Prefer the CMAP encoding to the CFF encoding. (x4)
```

<details><summary>Code</summary>

```typescript
function parseCFFTable(data, start, font, opt) {
    font.tables.cff = {};
    var header = parseCFFHeader(data, start);
    var nameIndex = parseCFFIndex(data, header.endOffset, parse.bytesToString);
    var topDictIndex = parseCFFIndex(data, nameIndex.endOffset);
    var stringIndex = parseCFFIndex(data, topDictIndex.endOffset, parse.bytesToString);
    var globalSubrIndex = parseCFFIndex(data, stringIndex.endOffset);
    font.gsubrs = globalSubrIndex.objects;
    font.gsubrsBias = calcCFFSubroutineBias(font.gsubrs);

    var topDictArray = gatherCFFTopDicts(data, start, topDictIndex.objects, stringIndex.objects);
    if (topDictArray.length !== 1) {
        throw new Error('CFF table has too many fonts in \'FontSet\' - count of fonts NameIndex.length = ' + topDictArray.length);
    }

    var topDict = topDictArray[0];
    font.tables.cff.topDict = topDict;

    if (topDict._privateDict) {
        font.defaultWidthX = topDict._privateDict.defaultWidthX;
        font.nominalWidthX = topDict._privateDict.nominalWidthX;
    }

    if (topDict.ros[0] !== undefined && topDict.ros[1] !== undefined) {
        font.isCIDFont = true;
    }

    if (font.isCIDFont) {
        var fdArrayOffset = topDict.fdArray;
        var fdSelectOffset = topDict.fdSelect;
        if (fdArrayOffset === 0 || fdSelectOffset === 0) {
            throw new Error('Font is marked as a CID font, but FDArray and/or FDSelect information is missing');
        }
        fdArrayOffset += start;
        var fdArrayIndex = parseCFFIndex(data, fdArrayOffset);
        var fdArray = gatherCFFTopDicts(data, start, fdArrayIndex.objects, stringIndex.objects);
        topDict._fdArray = fdArray;
        fdSelectOffset += start;
        topDict._fdSelect = parseCFFFDSelect(data, fdSelectOffset, font.numGlyphs, fdArray.length);
    }

    var privateDictOffset = start + topDict.private[1];
    var privateDict = parseCFFPrivateDict(data, privateDictOffset, topDict.private[0], stringIndex.objects);
    font.defaultWidthX = privateDict.defaultWidthX;
    font.nominalWidthX = privateDict.nominalWidthX;

    if (privateDict.subrs !== 0) {
        var subrOffset = privateDictOffset + privateDict.subrs;
        var subrIndex = parseCFFIndex(data, subrOffset);
        font.subrs = subrIndex.objects;
        font.subrsBias = calcCFFSubroutineBias(font.subrs);
    } else {
        font.subrs = [];
        font.subrsBias = 0;
    }

    // Offsets in the top dict are relative to the beginning of the CFF data, so add the CFF start offset.
    var charStringsIndex;
    if (opt.lowMemory) {
        charStringsIndex = parseCFFIndexLowMemory(data, start + topDict.charStrings);
        font.nGlyphs = charStringsIndex.offsets.length;
    } else {
        charStringsIndex = parseCFFIndex(data, start + topDict.charStrings);
        font.nGlyphs = charStringsIndex.objects.length;
    }

    var charset = parseCFFCharset(data, start + topDict.charset, font.nGlyphs, stringIndex.objects);
    if (topDict.encoding === 0) {
        // Standard encoding
        font.cffEncoding = new CffEncoding(cffStandardEncoding, charset);
    } else if (topDict.encoding === 1) {
        // Expert encoding
        font.cffEncoding = new CffEncoding(cffExpertEncoding, charset);
    } else {
        font.cffEncoding = parseCFFEncoding(data, start + topDict.encoding, charset);
    }

    // Prefer the CMAP encoding to the CFF encoding.
    font.encoding = font.encoding || font.cffEncoding;

    font.glyphs = new glyphset.GlyphSet(font);
    if (opt.lowMemory) {
        font._push = function(i) {
            var charString = getCffIndexObject(i, charStringsIndex.offsets, data, start + topDict.charStrings);
            font.glyphs.push(i, glyphset.cffGlyphLoader(font, i, parseCFFCharstring, charString));
        };
    } else {
        for (var i = 0; i < font.nGlyphs; i += 1) {
            var charString = charStringsIndex.objects[i];
            font.glyphs.push(i, glyphset.cffGlyphLoader(font, i, parseCFFCharstring, charString));
        }
    }
}
```
</details>

### `encodeString(s: any, strings: any): any`

**Parameters:**

- **`s`** `any`
- **`strings`** `any`

**Returns:** `any`

**Calls:**

- `cffStandardStrings.indexOf`
- `strings.indexOf`
- `strings.push`

**Internal Comments:**
```
// Is the string in the CFF standard strings? (x2)
// Is the string already in the string index? (x3)
```

<details><summary>Code</summary>

```typescript
function encodeString(s, strings) {
    var sid;

    // Is the string in the CFF standard strings?
    var i = cffStandardStrings.indexOf(s);
    if (i >= 0) {
        sid = i;
    }

    // Is the string already in the string index?
    i = strings.indexOf(s);
    if (i >= 0) {
        sid = i + cffStandardStrings.length;
    } else {
        sid = cffStandardStrings.length + strings.length;
        strings.push(s);
    }

    return sid;
}
```
</details>

### `makeHeader(): Table`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeHeader() {
    return new table.Record('Header', [
        {name: 'major', type: 'Card8', value: 1},
        {name: 'minor', type: 'Card8', value: 0},
        {name: 'hdrSize', type: 'Card8', value: 4},
        {name: 'major', type: 'Card8', value: 1}
    ]);
}
```
</details>

### `makeNameIndex(fontNames: any): Table`

**Parameters:**

- **`fontNames`** `any`

**Returns:** `Table`

**Calls:**

- `t.names.push`

<details><summary>Code</summary>

```typescript
function makeNameIndex(fontNames) {
    var t = new table.Record('Name INDEX', [
        {name: 'names', type: 'INDEX', value: []}
    ]);
    t.names = [];
    for (var i = 0; i < fontNames.length; i += 1) {
        t.names.push({name: 'name_' + i, type: 'NAME', value: fontNames[i]});
    }

    return t;
}
```
</details>

### `makeDict(meta: any, attrs: any, strings: any): {}`

**Parameters:**

- **`meta`** `any`
- **`attrs`** `any`
- **`strings`** `any`

**Returns:** `{}`

**Calls:**

- `equals`
- `encodeString`

<details><summary>Code</summary>

```typescript
function makeDict(meta, attrs, strings) {
    var m = {};
    for (var i = 0; i < meta.length; i += 1) {
        var entry = meta[i];
        var value = attrs[entry.name];
        if (value !== undefined && !equals(value, entry.value)) {
            if (entry.type === 'SID') {
                value = encodeString(value, strings);
            }

            m[entry.op] = {name: entry.name, type: entry.type, value: value};
        }
    }

    return m;
}
```
</details>

### `makeTopDict(attrs: any, strings: any): Table`

**Parameters:**

- **`attrs`** `any`
- **`strings`** `any`

**Returns:** `Table`

**Calls:**

- `makeDict`

<details><summary>Code</summary>

```typescript
function makeTopDict(attrs, strings) {
    var t = new table.Record('Top DICT', [
        {name: 'dict', type: 'DICT', value: {}}
    ]);
    t.dict = makeDict(TOP_DICT_META, attrs, strings);
    return t;
}
```
</details>

### `makeTopDictIndex(topDict: any): Table`

**Parameters:**

- **`topDict`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeTopDictIndex(topDict) {
    var t = new table.Record('Top DICT INDEX', [
        {name: 'topDicts', type: 'INDEX', value: []}
    ]);
    t.topDicts = [{name: 'topDict_0', type: 'TABLE', value: topDict}];
    return t;
}
```
</details>

### `makeStringIndex(strings: any): Table`

**Parameters:**

- **`strings`** `any`

**Returns:** `Table`

**Calls:**

- `t.strings.push`

<details><summary>Code</summary>

```typescript
function makeStringIndex(strings) {
    var t = new table.Record('String INDEX', [
        {name: 'strings', type: 'INDEX', value: []}
    ]);
    t.strings = [];
    for (var i = 0; i < strings.length; i += 1) {
        t.strings.push({name: 'string_' + i, type: 'STRING', value: strings[i]});
    }

    return t;
}
```
</details>

### `makeGlobalSubrIndex(): Table`

**Returns:** `Table`

**Internal Comments:**
```
// Currently we don't use subroutines.
```

<details><summary>Code</summary>

```typescript
function makeGlobalSubrIndex() {
    // Currently we don't use subroutines.
    return new table.Record('Global Subr INDEX', [
        {name: 'subrs', type: 'INDEX', value: []}
    ]);
}
```
</details>

### `makeCharsets(glyphNames: any, strings: any): Table`

**Parameters:**

- **`glyphNames`** `any`
- **`strings`** `any`

**Returns:** `Table`

**Calls:**

- `encodeString`
- `t.fields.push`

<details><summary>Code</summary>

```typescript
function makeCharsets(glyphNames, strings) {
    var t = new table.Record('Charsets', [
        {name: 'format', type: 'Card8', value: 0}
    ]);
    for (var i = 0; i < glyphNames.length; i += 1) {
        var glyphName = glyphNames[i];
        var glyphSID = encodeString(glyphName, strings);
        t.fields.push({name: 'glyph_' + i, type: 'SID', value: glyphSID});
    }

    return t;
}
```
</details>

### `glyphToOps(glyph: any): { name: string; type: string; value: any; }[]`

**Parameters:**

- **`glyph`** `any`

**Returns:** `{ name: string; type: string; value: any; }[]`

**Calls:**

- `ops.push`
- `Math.round`

**Internal Comments:**
```
// CFF only supports bézier curves, so convert the quad to a bézier. (x2)
// We're going to create a new command so we don't change the original path. (x3)
// Since all coordinates are relative, we round() them ASAP to avoid propagating errors. (x3)
```

<details><summary>Code</summary>

```typescript
function glyphToOps(glyph) {
    var ops = [];
    var path = glyph.path;
    ops.push({name: 'width', type: 'NUMBER', value: glyph.advanceWidth});
    var x = 0;
    var y = 0;
    for (var i = 0; i < path.commands.length; i += 1) {
        var dx = (void 0);
        var dy = (void 0);
        var cmd = path.commands[i];
        if (cmd.type === 'Q') {
            // CFF only supports bézier curves, so convert the quad to a bézier.
            var _13 = 1 / 3;
            var _23 = 2 / 3;

            // We're going to create a new command so we don't change the original path.
            // Since all coordinates are relative, we round() them ASAP to avoid propagating errors.
            cmd = {
                type: 'C',
                x: cmd.x,
                y: cmd.y,
                x1: Math.round(_13 * x + _23 * cmd.x1),
                y1: Math.round(_13 * y + _23 * cmd.y1),
                x2: Math.round(_13 * cmd.x + _23 * cmd.x1),
                y2: Math.round(_13 * cmd.y + _23 * cmd.y1)
            };
        }

        if (cmd.type === 'M') {
            dx = Math.round(cmd.x - x);
            dy = Math.round(cmd.y - y);
            ops.push({name: 'dx', type: 'NUMBER', value: dx});
            ops.push({name: 'dy', type: 'NUMBER', value: dy});
            ops.push({name: 'rmoveto', type: 'OP', value: 21});
            x = Math.round(cmd.x);
            y = Math.round(cmd.y);
        } else if (cmd.type === 'L') {
            dx = Math.round(cmd.x - x);
            dy = Math.round(cmd.y - y);
            ops.push({name: 'dx', type: 'NUMBER', value: dx});
            ops.push({name: 'dy', type: 'NUMBER', value: dy});
            ops.push({name: 'rlineto', type: 'OP', value: 5});
            x = Math.round(cmd.x);
            y = Math.round(cmd.y);
        } else if (cmd.type === 'C') {
            var dx1 = Math.round(cmd.x1 - x);
            var dy1 = Math.round(cmd.y1 - y);
            var dx2 = Math.round(cmd.x2 - cmd.x1);
            var dy2 = Math.round(cmd.y2 - cmd.y1);
            dx = Math.round(cmd.x - cmd.x2);
            dy = Math.round(cmd.y - cmd.y2);
            ops.push({name: 'dx1', type: 'NUMBER', value: dx1});
            ops.push({name: 'dy1', type: 'NUMBER', value: dy1});
            ops.push({name: 'dx2', type: 'NUMBER', value: dx2});
            ops.push({name: 'dy2', type: 'NUMBER', value: dy2});
            ops.push({name: 'dx', type: 'NUMBER', value: dx});
            ops.push({name: 'dy', type: 'NUMBER', value: dy});
            ops.push({name: 'rrcurveto', type: 'OP', value: 8});
            x = Math.round(cmd.x);
            y = Math.round(cmd.y);
        }

        // Contours are closed automatically.
    }

    ops.push({name: 'endchar', type: 'OP', value: 14});
    return ops;
}
```
</details>

### `makeCharStringsIndex(glyphs: any): Table`

**Parameters:**

- **`glyphs`** `any`

**Returns:** `Table`

**Calls:**

- `glyphs.get`
- `glyphToOps`
- `t.charStrings.push`

<details><summary>Code</summary>

```typescript
function makeCharStringsIndex(glyphs) {
    var t = new table.Record('CharStrings INDEX', [
        {name: 'charStrings', type: 'INDEX', value: []}
    ]);

    for (var i = 0; i < glyphs.length; i += 1) {
        var glyph = glyphs.get(i);
        var ops = glyphToOps(glyph);
        t.charStrings.push({name: glyph.name, type: 'CHARSTRING', value: ops});
    }

    return t;
}
```
</details>

### `makePrivateDict(attrs: any, strings: any): Table`

**Parameters:**

- **`attrs`** `any`
- **`strings`** `any`

**Returns:** `Table`

**Calls:**

- `makeDict`

<details><summary>Code</summary>

```typescript
function makePrivateDict(attrs, strings) {
    var t = new table.Record('Private DICT', [
        {name: 'dict', type: 'DICT', value: {}}
    ]);
    t.dict = makeDict(PRIVATE_DICT_META, attrs, strings);
    return t;
}
```
</details>

### `makeCFFTable(glyphs: any, options: any): Table`

**Parameters:**

- **`glyphs`** `any`
- **`options`** `any`

**Returns:** `Table`

**Calls:**

- `glyphs.get`
- `glyphNames.push`
- `makeHeader`
- `makeNameIndex`
- `makeTopDict`
- `makeTopDictIndex`
- `makeGlobalSubrIndex`
- `makeCharsets`
- `makeCharStringsIndex`
- `makePrivateDict`
- `makeStringIndex`
- `t.header.sizeOf`
- `t.nameIndex.sizeOf`
- `t.topDictIndex.sizeOf`
- `t.stringIndex.sizeOf`
- `t.globalSubrIndex.sizeOf`
- `t.charsets.sizeOf`
- `t.charStringsIndex.sizeOf`

**Internal Comments:**
```
// We use non-zero values for the offsets so that the DICT encodes them. (x2)
// This is important because the size of the Top DICT plays a role in offset calculation, (x2)
// and the size shouldn't change after we've written correct offsets. (x2)
// Skip first glyph (.notdef)
// Needs to come at the end, to encode all custom strings used in the font. (x4)
// We use the CFF standard encoding; proper encoding will be handled in cmap. (x4)
// Recreate the Top DICT INDEX with the correct offsets. (x3)
```

<details><summary>Code</summary>

```typescript
function makeCFFTable(glyphs, options) {
    var t = new table.Table('CFF ', [
        {name: 'header', type: 'RECORD'},
        {name: 'nameIndex', type: 'RECORD'},
        {name: 'topDictIndex', type: 'RECORD'},
        {name: 'stringIndex', type: 'RECORD'},
        {name: 'globalSubrIndex', type: 'RECORD'},
        {name: 'charsets', type: 'RECORD'},
        {name: 'charStringsIndex', type: 'RECORD'},
        {name: 'privateDict', type: 'RECORD'}
    ]);

    var fontScale = 1 / options.unitsPerEm;
    // We use non-zero values for the offsets so that the DICT encodes them.
    // This is important because the size of the Top DICT plays a role in offset calculation,
    // and the size shouldn't change after we've written correct offsets.
    var attrs = {
        version: options.version,
        fullName: options.fullName,
        familyName: options.familyName,
        weight: options.weightName,
        fontBBox: options.fontBBox || [0, 0, 0, 0],
        fontMatrix: [fontScale, 0, 0, fontScale, 0, 0],
        charset: 999,
        encoding: 0,
        charStrings: 999,
        private: [0, 999]
    };

    var privateAttrs = {};

    var glyphNames = [];
    var glyph;

    // Skip first glyph (.notdef)
    for (var i = 1; i < glyphs.length; i += 1) {
        glyph = glyphs.get(i);
        glyphNames.push(glyph.name);
    }

    var strings = [];

    t.header = makeHeader();
    t.nameIndex = makeNameIndex([options.postScriptName]);
    var topDict = makeTopDict(attrs, strings);
    t.topDictIndex = makeTopDictIndex(topDict);
    t.globalSubrIndex = makeGlobalSubrIndex();
    t.charsets = makeCharsets(glyphNames, strings);
    t.charStringsIndex = makeCharStringsIndex(glyphs);
    t.privateDict = makePrivateDict(privateAttrs, strings);

    // Needs to come at the end, to encode all custom strings used in the font.
    t.stringIndex = makeStringIndex(strings);

    var startOffset = t.header.sizeOf() +
        t.nameIndex.sizeOf() +
        t.topDictIndex.sizeOf() +
        t.stringIndex.sizeOf() +
        t.globalSubrIndex.sizeOf();
    attrs.charset = startOffset;

    // We use the CFF standard encoding; proper encoding will be handled in cmap.
    attrs.encoding = 0;
    attrs.charStrings = attrs.charset + t.charsets.sizeOf();
    attrs.private[1] = attrs.charStrings + t.charStringsIndex.sizeOf();

    // Recreate the Top DICT INDEX with the correct offsets.
    topDict = makeTopDict(attrs, strings);
    t.topDictIndex = makeTopDictIndex(topDict);

    return t;
}
```
</details>

### `parseHeadTable(data: any, start: any): { version: any; fontRevision: number; checkSumAdjustment: any; magicNumber: any; flags: any; unitsPerEm: any; created: any; modified: any; xMin: any; yMin: any; xMax: any; yMax: any; macStyle: any; lowestRecPPEM: any; fontDirectionHint: any; indexToLocFormat: any; glyphDataFormat: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; fontRevision: number; checkSumAdjustment: any; magicNumber: any; flags: any; unitsPerEm: any; created: any; modified: any; xMin: any; yMin: any; xMax: any; yMax: any; macStyle: any; lowestRecPPEM: any; fontDirectionHint: any; indexToLocFormat: any; glyphDataFormat: any; }`

**Calls:**

- `p.parseVersion`
- `Math.round`
- `p.parseFixed`
- `p.parseULong`
- `check.argument`
- `p.parseUShort`
- `p.parseLongDateTime`
- `p.parseShort`

<details><summary>Code</summary>

```typescript
function parseHeadTable(data, start) {
    var head = {};
    var p = new parse.Parser(data, start);
    head.version = p.parseVersion();
    head.fontRevision = Math.round(p.parseFixed() * 1000) / 1000;
    head.checkSumAdjustment = p.parseULong();
    head.magicNumber = p.parseULong();
    check.argument(head.magicNumber === 0x5F0F3CF5, 'Font header has wrong magic number.');
    head.flags = p.parseUShort();
    head.unitsPerEm = p.parseUShort();
    head.created = p.parseLongDateTime();
    head.modified = p.parseLongDateTime();
    head.xMin = p.parseShort();
    head.yMin = p.parseShort();
    head.xMax = p.parseShort();
    head.yMax = p.parseShort();
    head.macStyle = p.parseUShort();
    head.lowestRecPPEM = p.parseUShort();
    head.fontDirectionHint = p.parseShort();
    head.indexToLocFormat = p.parseShort();
    head.glyphDataFormat = p.parseShort();
    return head;
}
```
</details>

### `makeHeadTable(options: any): Table`

**Parameters:**

- **`options`** `any`

**Returns:** `Table`

**Calls:**

- `Math.round`
- `new Date().getTime`

**Internal Comments:**
```
// Apple Mac timestamp epoch is 01/01/1904 not 01/01/1970 (x2)
```

<details><summary>Code</summary>

```typescript
function makeHeadTable(options) {
    // Apple Mac timestamp epoch is 01/01/1904 not 01/01/1970
    var timestamp = Math.round(new Date().getTime() / 1000) + 2082844800;
    var createdTimestamp = timestamp;

    if (options.createdTimestamp) {
        createdTimestamp = options.createdTimestamp + 2082844800;
    }

    return new table.Table('head', [
        {name: 'version', type: 'FIXED', value: 0x00010000},
        {name: 'fontRevision', type: 'FIXED', value: 0x00010000},
        {name: 'checkSumAdjustment', type: 'ULONG', value: 0},
        {name: 'magicNumber', type: 'ULONG', value: 0x5F0F3CF5},
        {name: 'flags', type: 'USHORT', value: 0},
        {name: 'unitsPerEm', type: 'USHORT', value: 1000},
        {name: 'created', type: 'LONGDATETIME', value: createdTimestamp},
        {name: 'modified', type: 'LONGDATETIME', value: timestamp},
        {name: 'xMin', type: 'SHORT', value: 0},
        {name: 'yMin', type: 'SHORT', value: 0},
        {name: 'xMax', type: 'SHORT', value: 0},
        {name: 'yMax', type: 'SHORT', value: 0},
        {name: 'macStyle', type: 'USHORT', value: 0},
        {name: 'lowestRecPPEM', type: 'USHORT', value: 0},
        {name: 'fontDirectionHint', type: 'SHORT', value: 2},
        {name: 'indexToLocFormat', type: 'SHORT', value: 0},
        {name: 'glyphDataFormat', type: 'SHORT', value: 0}
    ], options);
}
```
</details>

### `parseHheaTable(data: any, start: any): { version: any; ascender: any; descender: any; lineGap: any; advanceWidthMax: any; minLeftSideBearing: any; minRightSideBearing: any; xMaxExtent: any; caretSlopeRise: any; caretSlopeRun: any; caretOffset: any; metricDataFormat: any; numberOfHMetrics: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; ascender: any; descender: any; lineGap: any; advanceWidthMax: any; minLeftSideBearing: any; minRightSideBearing: any; xMaxExtent: any; caretSlopeRise: any; caretSlopeRun: any; caretOffset: any; metricDataFormat: any; numberOfHMetrics: any; }`

**Calls:**

- `p.parseVersion`
- `p.parseShort`
- `p.parseUShort`

<details><summary>Code</summary>

```typescript
function parseHheaTable(data, start) {
    var hhea = {};
    var p = new parse.Parser(data, start);
    hhea.version = p.parseVersion();
    hhea.ascender = p.parseShort();
    hhea.descender = p.parseShort();
    hhea.lineGap = p.parseShort();
    hhea.advanceWidthMax = p.parseUShort();
    hhea.minLeftSideBearing = p.parseShort();
    hhea.minRightSideBearing = p.parseShort();
    hhea.xMaxExtent = p.parseShort();
    hhea.caretSlopeRise = p.parseShort();
    hhea.caretSlopeRun = p.parseShort();
    hhea.caretOffset = p.parseShort();
    p.relativeOffset += 8;
    hhea.metricDataFormat = p.parseShort();
    hhea.numberOfHMetrics = p.parseUShort();
    return hhea;
}
```
</details>

### `makeHheaTable(options: any): Table`

**Parameters:**

- **`options`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeHheaTable(options) {
    return new table.Table('hhea', [
        {name: 'version', type: 'FIXED', value: 0x00010000},
        {name: 'ascender', type: 'FWORD', value: 0},
        {name: 'descender', type: 'FWORD', value: 0},
        {name: 'lineGap', type: 'FWORD', value: 0},
        {name: 'advanceWidthMax', type: 'UFWORD', value: 0},
        {name: 'minLeftSideBearing', type: 'FWORD', value: 0},
        {name: 'minRightSideBearing', type: 'FWORD', value: 0},
        {name: 'xMaxExtent', type: 'FWORD', value: 0},
        {name: 'caretSlopeRise', type: 'SHORT', value: 1},
        {name: 'caretSlopeRun', type: 'SHORT', value: 0},
        {name: 'caretOffset', type: 'SHORT', value: 0},
        {name: 'reserved1', type: 'SHORT', value: 0},
        {name: 'reserved2', type: 'SHORT', value: 0},
        {name: 'reserved3', type: 'SHORT', value: 0},
        {name: 'reserved4', type: 'SHORT', value: 0},
        {name: 'metricDataFormat', type: 'SHORT', value: 0},
        {name: 'numberOfHMetrics', type: 'USHORT', value: 0}
    ], options);
}
```
</details>

### `parseHmtxTableAll(data: any, start: any, numMetrics: any, numGlyphs: any, glyphs: any): void`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`numMetrics`** `any`
- **`numGlyphs`** `any`
- **`glyphs`** `any`

**Returns:** `void`

**Calls:**

- `p.parseUShort`
- `p.parseShort`
- `glyphs.get`

**Internal Comments:**
```
// If the font is monospaced, only one entry is needed. This last entry applies to all subsequent glyphs.
```

<details><summary>Code</summary>

```typescript
function parseHmtxTableAll(data, start, numMetrics, numGlyphs, glyphs) {
    var advanceWidth;
    var leftSideBearing;
    var p = new parse.Parser(data, start);
    for (var i = 0; i < numGlyphs; i += 1) {
        // If the font is monospaced, only one entry is needed. This last entry applies to all subsequent glyphs.
        if (i < numMetrics) {
            advanceWidth = p.parseUShort();
            leftSideBearing = p.parseShort();
        }

        var glyph = glyphs.get(i);
        glyph.advanceWidth = advanceWidth;
        glyph.leftSideBearing = leftSideBearing;
    }
}
```
</details>

### `parseHmtxTableOnLowMemory(font: any, data: any, start: any, numMetrics: any, numGlyphs: any): void`

**Parameters:**

- **`font`** `any`
- **`data`** `any`
- **`start`** `any`
- **`numMetrics`** `any`
- **`numGlyphs`** `any`

**Returns:** `void`

**Calls:**

- `p.parseUShort`
- `p.parseShort`

**Internal Comments:**
```
// If the font is monospaced, only one entry is needed. This last entry applies to all subsequent glyphs.
```

<details><summary>Code</summary>

```typescript
function parseHmtxTableOnLowMemory(font, data, start, numMetrics, numGlyphs) {
    font._hmtxTableData = {};

    var advanceWidth;
    var leftSideBearing;
    var p = new parse.Parser(data, start);
    for (var i = 0; i < numGlyphs; i += 1) {
        // If the font is monospaced, only one entry is needed. This last entry applies to all subsequent glyphs.
        if (i < numMetrics) {
            advanceWidth = p.parseUShort();
            leftSideBearing = p.parseShort();
        }

        font._hmtxTableData[i] = {
            advanceWidth: advanceWidth,
            leftSideBearing: leftSideBearing
        };
    }
}
```
</details>

### `parseHmtxTable(font: any, data: any, start: any, numMetrics: any, numGlyphs: any, glyphs: any, opt: any): void`

**Parameters:**

- **`font`** `any`
- **`data`** `any`
- **`start`** `any`
- **`numMetrics`** `any`
- **`numGlyphs`** `any`
- **`glyphs`** `any`
- **`opt`** `any`

**Returns:** `void`

**Calls:**

- `parseHmtxTableOnLowMemory`
- `parseHmtxTableAll`

<details><summary>Code</summary>

```typescript
function parseHmtxTable(font, data, start, numMetrics, numGlyphs, glyphs, opt) {
    if (opt.lowMemory)
        { parseHmtxTableOnLowMemory(font, data, start, numMetrics, numGlyphs); }
    else
        { parseHmtxTableAll(data, start, numMetrics, numGlyphs, glyphs); }
}
```
</details>

### `makeHmtxTable(glyphs: any): Table`

**Parameters:**

- **`glyphs`** `any`

**Returns:** `Table`

**Calls:**

- `glyphs.get`
- `t.fields.push`

<details><summary>Code</summary>

```typescript
function makeHmtxTable(glyphs) {
    var t = new table.Table('hmtx', []);
    for (var i = 0; i < glyphs.length; i += 1) {
        var glyph = glyphs.get(i);
        var advanceWidth = glyph.advanceWidth || 0;
        var leftSideBearing = glyph.leftSideBearing || 0;
        t.fields.push({name: 'advanceWidth_' + i, type: 'USHORT', value: advanceWidth});
        t.fields.push({name: 'leftSideBearing_' + i, type: 'SHORT', value: leftSideBearing});
    }

    return t;
}
```
</details>

### `makeLtagTable(tags: any): Table`

**Parameters:**

- **`tags`** `any`

**Returns:** `Table`

**Calls:**

- `stringPool.indexOf`
- `result.fields.push`

<details><summary>Code</summary>

```typescript
function makeLtagTable(tags) {
    var result = new table.Table('ltag', [
        {name: 'version', type: 'ULONG', value: 1},
        {name: 'flags', type: 'ULONG', value: 0},
        {name: 'numTags', type: 'ULONG', value: tags.length}
    ]);

    var stringPool = '';
    var stringPoolOffset = 12 + tags.length * 4;
    for (var i = 0; i < tags.length; ++i) {
        var pos = stringPool.indexOf(tags[i]);
        if (pos < 0) {
            pos = stringPool.length;
            stringPool += tags[i];
        }

        result.fields.push({name: 'offset ' + i, type: 'USHORT', value: stringPoolOffset + pos});
        result.fields.push({name: 'length ' + i, type: 'USHORT', value: tags[i].length});
    }

    result.fields.push({name: 'stringPool', type: 'CHARARRAY', value: stringPool});
    return result;
}
```
</details>

### `parseLtagTable(data: any, start: any): string[]`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `string[]`

**Calls:**

- `p.parseULong`
- `check.argument`
- `p.skip`
- `p.parseUShort`
- `String.fromCharCode`
- `data.getInt8`
- `tags.push`

**Internal Comments:**
```
// The 'ltag' specification does not define any flags; skip the field. (x4)
```

<details><summary>Code</summary>

```typescript
function parseLtagTable(data, start) {
    var p = new parse.Parser(data, start);
    var tableVersion = p.parseULong();
    check.argument(tableVersion === 1, 'Unsupported ltag table version.');
    // The 'ltag' specification does not define any flags; skip the field.
    p.skip('uLong', 1);
    var numTags = p.parseULong();

    var tags = [];
    for (var i = 0; i < numTags; i++) {
        var tag = '';
        var offset = start + p.parseUShort();
        var length = p.parseUShort();
        for (var j = offset; j < offset + length; ++j) {
            tag += String.fromCharCode(data.getInt8(j));
        }

        tags.push(tag);
    }

    return tags;
}
```
</details>

### `parseMaxpTable(data: any, start: any): { version: any; numGlyphs: any; maxPoints: any; maxContours: any; maxCompositePoints: any; maxCompositeContours: any; maxZones: any; maxTwilightPoints: any; maxStorage: any; maxFunctionDefs: any; ... 4 more ...; maxComponentDepth: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; numGlyphs: any; maxPoints: any; maxContours: any; maxCompositePoints: any; maxCompositeContours: any; maxZones: any; maxTwilightPoints: any; maxStorage: any; maxFunctionDefs: any; ... 4 more ...; maxComponentDepth: any; }`

**Calls:**

- `p.parseVersion`
- `p.parseUShort`

<details><summary>Code</summary>

```typescript
function parseMaxpTable(data, start) {
    var maxp = {};
    var p = new parse.Parser(data, start);
    maxp.version = p.parseVersion();
    maxp.numGlyphs = p.parseUShort();
    if (maxp.version === 1.0) {
        maxp.maxPoints = p.parseUShort();
        maxp.maxContours = p.parseUShort();
        maxp.maxCompositePoints = p.parseUShort();
        maxp.maxCompositeContours = p.parseUShort();
        maxp.maxZones = p.parseUShort();
        maxp.maxTwilightPoints = p.parseUShort();
        maxp.maxStorage = p.parseUShort();
        maxp.maxFunctionDefs = p.parseUShort();
        maxp.maxInstructionDefs = p.parseUShort();
        maxp.maxStackElements = p.parseUShort();
        maxp.maxSizeOfInstructions = p.parseUShort();
        maxp.maxComponentElements = p.parseUShort();
        maxp.maxComponentDepth = p.parseUShort();
    }

    return maxp;
}
```
</details>

### `makeMaxpTable(numGlyphs: any): Table`

**Parameters:**

- **`numGlyphs`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeMaxpTable(numGlyphs) {
    return new table.Table('maxp', [
        {name: 'version', type: 'FIXED', value: 0x00005000},
        {name: 'numGlyphs', type: 'USHORT', value: numGlyphs}
    ]);
}
```
</details>

### `getLanguageCode(platformID: any, languageID: any, ltag: any): any`

**Parameters:**

- **`platformID`** `any`
- **`languageID`** `any`
- **`ltag`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getLanguageCode(platformID, languageID, ltag) {
    switch (platformID) {
        case 0:  // Unicode
            if (languageID === 0xFFFF) {
                return 'und';
            } else if (ltag) {
                return ltag[languageID];
            }

            break;

        case 1:  // Macintosh
            return macLanguages[languageID];

        case 3:  // Windows
            return windowsLanguages[languageID];
    }

    return undefined;
}
```
</details>

### `getEncoding(platformID: any, encodingID: any, languageID: any): any`

**Parameters:**

- **`platformID`** `any`
- **`encodingID`** `any`
- **`languageID`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getEncoding(platformID, encodingID, languageID) {
    switch (platformID) {
        case 0:  // Unicode
            return utf16;

        case 1:  // Apple Macintosh
            return macLanguageEncodings[languageID] || macScriptEncodings[encodingID];

        case 3:  // Microsoft Windows
            if (encodingID === 1 || encodingID === 10) {
                return utf16;
            }

            break;
    }

    return undefined;
}
```
</details>

### `parseNameTable(data: any, start: any, ltag: any): {}`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`ltag`** `any`

**Returns:** `{}`

**Calls:**

- `p.parseUShort`
- `getLanguageCode`
- `getEncoding`
- `decode.UTF16`
- `decode.MACSTRING`

**Internal Comments:**
```
// FIXME: Also handle Microsoft's 'name' table 1. (x3)
```

<details><summary>Code</summary>

```typescript
function parseNameTable(data, start, ltag) {
    var name = {};
    var p = new parse.Parser(data, start);
    var format = p.parseUShort();
    var count = p.parseUShort();
    var stringOffset = p.offset + p.parseUShort();
    for (var i = 0; i < count; i++) {
        var platformID = p.parseUShort();
        var encodingID = p.parseUShort();
        var languageID = p.parseUShort();
        var nameID = p.parseUShort();
        var property = nameTableNames[nameID] || nameID;
        var byteLength = p.parseUShort();
        var offset = p.parseUShort();
        var language = getLanguageCode(platformID, languageID, ltag);
        var encoding = getEncoding(platformID, encodingID, languageID);
        if (encoding !== undefined && language !== undefined) {
            var text = (void 0);
            if (encoding === utf16) {
                text = decode.UTF16(data, stringOffset + offset, byteLength);
            } else {
                text = decode.MACSTRING(data, stringOffset + offset, byteLength, encoding);
            }

            if (text) {
                var translations = name[property];
                if (translations === undefined) {
                    translations = name[property] = {};
                }

                translations[language] = text;
            }
        }
    }

    var langTagCount = 0;
    if (format === 1) {
        // FIXME: Also handle Microsoft's 'name' table 1.
        langTagCount = p.parseUShort();
    }

    return name;
}
```
</details>

### `reverseDict(dict: any): {}`

**Parameters:**

- **`dict`** `any`

**Returns:** `{}`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function reverseDict(dict) {
    var result = {};
    for (var key in dict) {
        result[dict[key]] = parseInt(key);
    }

    return result;
}
```
</details>

### `makeNameRecord(platformID: any, encodingID: any, languageID: any, nameID: any, length: any, offset: any): Table`

**Parameters:**

- **`platformID`** `any`
- **`encodingID`** `any`
- **`languageID`** `any`
- **`nameID`** `any`
- **`length`** `any`
- **`offset`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeNameRecord(platformID, encodingID, languageID, nameID, length, offset) {
    return new table.Record('NameRecord', [
        {name: 'platformID', type: 'USHORT', value: platformID},
        {name: 'encodingID', type: 'USHORT', value: encodingID},
        {name: 'languageID', type: 'USHORT', value: languageID},
        {name: 'nameID', type: 'USHORT', value: nameID},
        {name: 'length', type: 'USHORT', value: length},
        {name: 'offset', type: 'USHORT', value: offset}
    ]);
}
```
</details>

### `findSubArray(needle: any, haystack: any): number`

**Parameters:**

- **`needle`** `any`
- **`haystack`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function findSubArray(needle, haystack) {
    var needleLength = needle.length;
    var limit = haystack.length - needleLength + 1;

    loop:
    for (var pos = 0; pos < limit; pos++) {
        for (; pos < limit; pos++) {
            for (var k = 0; k < needleLength; k++) {
                if (haystack[pos + k] !== needle[k]) {
                    continue loop;
                }
            }

            return pos;
        }
    }

    return -1;
}
```
</details>

### `addStringToPool(s: any, pool: any): number`

**Parameters:**

- **`s`** `any`
- **`pool`** `any`

**Returns:** `number`

**Calls:**

- `findSubArray`
- `pool.push`

<details><summary>Code</summary>

```typescript
function addStringToPool(s, pool) {
    var offset = findSubArray(s, pool);
    if (offset < 0) {
        offset = pool.length;
        var i = 0;
        var len = s.length;
        for (; i < len; ++i) {
            pool.push(s[i]);
        }

    }

    return offset;
}
```
</details>

### `makeNameTable(names: any, ltag: any): Table`

**Parameters:**

- **`names`** `any`
- **`ltag`** `any`

**Returns:** `Table`

**Calls:**

- `reverseDict`
- `parseInt`
- `isNaN`
- `nameIDs.push`
- `getEncoding`
- `encode.MACSTRING`
- `ltag.indexOf`
- `ltag.push`
- `encode.UTF16`
- `addStringToPool`
- `nameRecords.push`
- `makeNameRecord`
- `nameRecords.sort`
- `t.fields.push`

**Internal Comments:**
```
// For MacOS, we try to emit the name in the form that was introduced (x2)
// in the initial version of the TrueType spec (in the late 1980s). (x2)
// However, this can fail for various reasons: the requested BCP 47 (x2)
// language code might not have an old-style Mac equivalent; (x2)
// we might not have a codec for the needed character encoding; (x2)
// or the name might contain characters that cannot be expressed (x2)
// in the old-style Macintosh encoding. In case of failure, we emit (x2)
// the name in a more modern fashion (Unicode encoding with BCP 47 (x2)
// language tags) that is recognized by MacOS 10.5, released in 2009. (x2)
// If fonts were only read by operating systems, we could simply (x2)
// emit all names in the modern form; this would be much easier. (x2)
// However, there are many applications and libraries that read (x2)
// 'name' tables directly, and these will usually only recognize (x2)
// the ancient form (silently skipping the unrecognized names). (x2)
```

<details><summary>Code</summary>

```typescript
function makeNameTable(names, ltag) {
    var nameID;
    var nameIDs = [];

    var namesWithNumericKeys = {};
    var nameTableIds = reverseDict(nameTableNames);
    for (var key in names) {
        var id = nameTableIds[key];
        if (id === undefined) {
            id = key;
        }

        nameID = parseInt(id);

        if (isNaN(nameID)) {
            throw new Error('Name table entry "' + key + '" does not exist, see nameTableNames for complete list.');
        }

        namesWithNumericKeys[nameID] = names[key];
        nameIDs.push(nameID);
    }

    var macLanguageIds = reverseDict(macLanguages);
    var windowsLanguageIds = reverseDict(windowsLanguages);

    var nameRecords = [];
    var stringPool = [];

    for (var i = 0; i < nameIDs.length; i++) {
        nameID = nameIDs[i];
        var translations = namesWithNumericKeys[nameID];
        for (var lang in translations) {
            var text = translations[lang];

            // For MacOS, we try to emit the name in the form that was introduced
            // in the initial version of the TrueType spec (in the late 1980s).
            // However, this can fail for various reasons: the requested BCP 47
            // language code might not have an old-style Mac equivalent;
            // we might not have a codec for the needed character encoding;
            // or the name might contain characters that cannot be expressed
            // in the old-style Macintosh encoding. In case of failure, we emit
            // the name in a more modern fashion (Unicode encoding with BCP 47
            // language tags) that is recognized by MacOS 10.5, released in 2009.
            // If fonts were only read by operating systems, we could simply
            // emit all names in the modern form; this would be much easier.
            // However, there are many applications and libraries that read
            // 'name' tables directly, and these will usually only recognize
            // the ancient form (silently skipping the unrecognized names).
            var macPlatform = 1;  // Macintosh
            var macLanguage = macLanguageIds[lang];
            var macScript = macLanguageToScript[macLanguage];
            var macEncoding = getEncoding(macPlatform, macScript, macLanguage);
            var macName = encode.MACSTRING(text, macEncoding);
            if (macName === undefined) {
                macPlatform = 0;  // Unicode
                macLanguage = ltag.indexOf(lang);
                if (macLanguage < 0) {
                    macLanguage = ltag.length;
                    ltag.push(lang);
                }

                macScript = 4;  // Unicode 2.0 and later
                macName = encode.UTF16(text);
            }

            var macNameOffset = addStringToPool(macName, stringPool);
            nameRecords.push(makeNameRecord(macPlatform, macScript, macLanguage,
                                            nameID, macName.length, macNameOffset));

            var winLanguage = windowsLanguageIds[lang];
            if (winLanguage !== undefined) {
                var winName = encode.UTF16(text);
                var winNameOffset = addStringToPool(winName, stringPool);
                nameRecords.push(makeNameRecord(3, 1, winLanguage,
                                                nameID, winName.length, winNameOffset));
            }
        }
    }

    nameRecords.sort(function(a, b) {
        return ((a.platformID - b.platformID) ||
                (a.encodingID - b.encodingID) ||
                (a.languageID - b.languageID) ||
                (a.nameID - b.nameID));
    });

    var t = new table.Table('name', [
        {name: 'format', type: 'USHORT', value: 0},
        {name: 'count', type: 'USHORT', value: nameRecords.length},
        {name: 'stringOffset', type: 'USHORT', value: 6 + nameRecords.length * 12}
    ]);

    for (var r = 0; r < nameRecords.length; r++) {
        t.fields.push({name: 'record_' + r, type: 'RECORD', value: nameRecords[r]});
    }

    t.fields.push({name: 'strings', type: 'LITERAL', value: stringPool});
    return t;
}
```
</details>

### `getUnicodeRange(unicode: any): number`

**Parameters:**

- **`unicode`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function getUnicodeRange(unicode) {
    for (var i = 0; i < unicodeRanges.length; i += 1) {
        var range = unicodeRanges[i];
        if (unicode >= range.begin && unicode < range.end) {
            return i;
        }
    }

    return -1;
}
```
</details>

### `parseOS2Table(data: any, start: any): { version: any; xAvgCharWidth: any; usWeightClass: any; usWidthClass: any; fsType: any; ySubscriptXSize: any; ySubscriptYSize: any; ySubscriptXOffset: any; ySubscriptYOffset: any; ySuperscriptXSize: any; ... 26 more ...; usMaxContent: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; xAvgCharWidth: any; usWeightClass: any; usWidthClass: any; fsType: any; ySubscriptXSize: any; ySubscriptYSize: any; ySubscriptXOffset: any; ySubscriptYOffset: any; ySuperscriptXSize: any; ... 26 more ...; usMaxContent: any; }`

**Calls:**

- `p.parseUShort`
- `p.parseShort`
- `p.parseByte`
- `p.parseULong`
- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function parseOS2Table(data, start) {
    var os2 = {};
    var p = new parse.Parser(data, start);
    os2.version = p.parseUShort();
    os2.xAvgCharWidth = p.parseShort();
    os2.usWeightClass = p.parseUShort();
    os2.usWidthClass = p.parseUShort();
    os2.fsType = p.parseUShort();
    os2.ySubscriptXSize = p.parseShort();
    os2.ySubscriptYSize = p.parseShort();
    os2.ySubscriptXOffset = p.parseShort();
    os2.ySubscriptYOffset = p.parseShort();
    os2.ySuperscriptXSize = p.parseShort();
    os2.ySuperscriptYSize = p.parseShort();
    os2.ySuperscriptXOffset = p.parseShort();
    os2.ySuperscriptYOffset = p.parseShort();
    os2.yStrikeoutSize = p.parseShort();
    os2.yStrikeoutPosition = p.parseShort();
    os2.sFamilyClass = p.parseShort();
    os2.panose = [];
    for (var i = 0; i < 10; i++) {
        os2.panose[i] = p.parseByte();
    }

    os2.ulUnicodeRange1 = p.parseULong();
    os2.ulUnicodeRange2 = p.parseULong();
    os2.ulUnicodeRange3 = p.parseULong();
    os2.ulUnicodeRange4 = p.parseULong();
    os2.achVendID = String.fromCharCode(p.parseByte(), p.parseByte(), p.parseByte(), p.parseByte());
    os2.fsSelection = p.parseUShort();
    os2.usFirstCharIndex = p.parseUShort();
    os2.usLastCharIndex = p.parseUShort();
    os2.sTypoAscender = p.parseShort();
    os2.sTypoDescender = p.parseShort();
    os2.sTypoLineGap = p.parseShort();
    os2.usWinAscent = p.parseUShort();
    os2.usWinDescent = p.parseUShort();
    if (os2.version >= 1) {
        os2.ulCodePageRange1 = p.parseULong();
        os2.ulCodePageRange2 = p.parseULong();
    }

    if (os2.version >= 2) {
        os2.sxHeight = p.parseShort();
        os2.sCapHeight = p.parseShort();
        os2.usDefaultChar = p.parseUShort();
        os2.usBreakChar = p.parseUShort();
        os2.usMaxContent = p.parseUShort();
    }

    return os2;
}
```
</details>

### `makeOS2Table(options: any): Table`

**Parameters:**

- **`options`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeOS2Table(options) {
    return new table.Table('OS/2', [
        {name: 'version', type: 'USHORT', value: 0x0003},
        {name: 'xAvgCharWidth', type: 'SHORT', value: 0},
        {name: 'usWeightClass', type: 'USHORT', value: 0},
        {name: 'usWidthClass', type: 'USHORT', value: 0},
        {name: 'fsType', type: 'USHORT', value: 0},
        {name: 'ySubscriptXSize', type: 'SHORT', value: 650},
        {name: 'ySubscriptYSize', type: 'SHORT', value: 699},
        {name: 'ySubscriptXOffset', type: 'SHORT', value: 0},
        {name: 'ySubscriptYOffset', type: 'SHORT', value: 140},
        {name: 'ySuperscriptXSize', type: 'SHORT', value: 650},
        {name: 'ySuperscriptYSize', type: 'SHORT', value: 699},
        {name: 'ySuperscriptXOffset', type: 'SHORT', value: 0},
        {name: 'ySuperscriptYOffset', type: 'SHORT', value: 479},
        {name: 'yStrikeoutSize', type: 'SHORT', value: 49},
        {name: 'yStrikeoutPosition', type: 'SHORT', value: 258},
        {name: 'sFamilyClass', type: 'SHORT', value: 0},
        {name: 'bFamilyType', type: 'BYTE', value: 0},
        {name: 'bSerifStyle', type: 'BYTE', value: 0},
        {name: 'bWeight', type: 'BYTE', value: 0},
        {name: 'bProportion', type: 'BYTE', value: 0},
        {name: 'bContrast', type: 'BYTE', value: 0},
        {name: 'bStrokeVariation', type: 'BYTE', value: 0},
        {name: 'bArmStyle', type: 'BYTE', value: 0},
        {name: 'bLetterform', type: 'BYTE', value: 0},
        {name: 'bMidline', type: 'BYTE', value: 0},
        {name: 'bXHeight', type: 'BYTE', value: 0},
        {name: 'ulUnicodeRange1', type: 'ULONG', value: 0},
        {name: 'ulUnicodeRange2', type: 'ULONG', value: 0},
        {name: 'ulUnicodeRange3', type: 'ULONG', value: 0},
        {name: 'ulUnicodeRange4', type: 'ULONG', value: 0},
        {name: 'achVendID', type: 'CHARARRAY', value: 'XXXX'},
        {name: 'fsSelection', type: 'USHORT', value: 0},
        {name: 'usFirstCharIndex', type: 'USHORT', value: 0},
        {name: 'usLastCharIndex', type: 'USHORT', value: 0},
        {name: 'sTypoAscender', type: 'SHORT', value: 0},
        {name: 'sTypoDescender', type: 'SHORT', value: 0},
        {name: 'sTypoLineGap', type: 'SHORT', value: 0},
        {name: 'usWinAscent', type: 'USHORT', value: 0},
        {name: 'usWinDescent', type: 'USHORT', value: 0},
        {name: 'ulCodePageRange1', type: 'ULONG', value: 0},
        {name: 'ulCodePageRange2', type: 'ULONG', value: 0},
        {name: 'sxHeight', type: 'SHORT', value: 0},
        {name: 'sCapHeight', type: 'SHORT', value: 0},
        {name: 'usDefaultChar', type: 'USHORT', value: 0},
        {name: 'usBreakChar', type: 'USHORT', value: 0},
        {name: 'usMaxContext', type: 'USHORT', value: 0}
    ], options);
}
```
</details>

### `parsePostTable(data: any, start: any): { version: any; italicAngle: any; underlinePosition: any; underlineThickness: any; isFixedPitch: any; minMemType42: any; maxMemType42: any; minMemType1: any; maxMemType1: any; names: any[] | string[]; numberOfGlyphs: any; glyphNameIndex: any[]; offset: any[]; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; italicAngle: any; underlinePosition: any; underlineThickness: any; isFixedPitch: any; minMemType42: any; maxMemType42: any; minMemType1: any; maxMemType1: any; names: any[] | string[]; numberOfGlyphs: any; glyphNameIndex: any[]; offset: any[]; }`

**Calls:**

- `p.parseVersion`
- `p.parseFixed`
- `p.parseShort`
- `p.parseULong`
- `standardNames.slice`
- `p.parseUShort`
- `p.parseChar`
- `post.names.push`
- `p.parseString`

<details><summary>Code</summary>

```typescript
function parsePostTable(data, start) {
    var post = {};
    var p = new parse.Parser(data, start);
    post.version = p.parseVersion();
    post.italicAngle = p.parseFixed();
    post.underlinePosition = p.parseShort();
    post.underlineThickness = p.parseShort();
    post.isFixedPitch = p.parseULong();
    post.minMemType42 = p.parseULong();
    post.maxMemType42 = p.parseULong();
    post.minMemType1 = p.parseULong();
    post.maxMemType1 = p.parseULong();
    switch (post.version) {
        case 1:
            post.names = standardNames.slice();
            break;
        case 2:
            post.numberOfGlyphs = p.parseUShort();
            post.glyphNameIndex = new Array(post.numberOfGlyphs);
            for (var i = 0; i < post.numberOfGlyphs; i++) {
                post.glyphNameIndex[i] = p.parseUShort();
            }

            post.names = [];
            for (var i$1 = 0; i$1 < post.numberOfGlyphs; i$1++) {
                if (post.glyphNameIndex[i$1] >= standardNames.length) {
                    var nameLength = p.parseChar();
                    post.names.push(p.parseString(nameLength));
                }
            }

            break;
        case 2.5:
            post.numberOfGlyphs = p.parseUShort();
            post.offset = new Array(post.numberOfGlyphs);
            for (var i$2 = 0; i$2 < post.numberOfGlyphs; i$2++) {
                post.offset[i$2] = p.parseChar();
            }

            break;
    }
    return post;
}
```
</details>

### `makePostTable(): Table`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makePostTable() {
    return new table.Table('post', [
        {name: 'version', type: 'FIXED', value: 0x00030000},
        {name: 'italicAngle', type: 'FIXED', value: 0},
        {name: 'underlinePosition', type: 'FWORD', value: 0},
        {name: 'underlineThickness', type: 'FWORD', value: 0},
        {name: 'isFixedPitch', type: 'ULONG', value: 0},
        {name: 'minMemType42', type: 'ULONG', value: 0},
        {name: 'maxMemType42', type: 'ULONG', value: 0},
        {name: 'minMemType1', type: 'ULONG', value: 0},
        {name: 'maxMemType1', type: 'ULONG', value: 0}
    ]);
}
```
</details>

### `parseGsubTable(data: any, start: any): { version: any; scripts: any; features: any; lookups: any; variations?: undefined; } | { version: any; scripts: any; features: any; lookups: any; variations: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; scripts: any; features: any; lookups: any; variations?: undefined; } | { version: any; scripts: any; features: any; lookups: any; variations: any; }`

**Calls:**

- `p.parseVersion`
- `check.argument`
- `p.parseScriptList`
- `p.parseFeatureList`
- `p.parseLookupList`
- `p.parseFeatureVariationsList`

<details><summary>Code</summary>

```typescript
function parseGsubTable(data, start) {
    start = start || 0;
    var p = new Parser(data, start);
    var tableVersion = p.parseVersion(1);
    check.argument(tableVersion === 1 || tableVersion === 1.1, 'Unsupported GSUB table version.');
    if (tableVersion === 1) {
        return {
            version: tableVersion,
            scripts: p.parseScriptList(),
            features: p.parseFeatureList(),
            lookups: p.parseLookupList(subtableParsers)
        };
    } else {
        return {
            version: tableVersion,
            scripts: p.parseScriptList(),
            features: p.parseFeatureList(),
            lookups: p.parseLookupList(subtableParsers),
            variations: p.parseFeatureVariationsList()
        };
    }

}
```
</details>

### `makeGsubTable(gsub: any): Table`

**Parameters:**

- **`gsub`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeGsubTable(gsub) {
    return new table.Table('GSUB', [
        {name: 'version', type: 'ULONG', value: 0x10000},
        {name: 'scripts', type: 'TABLE', value: new table.ScriptList(gsub.scripts)},
        {name: 'features', type: 'TABLE', value: new table.FeatureList(gsub.features)},
        {name: 'lookups', type: 'TABLE', value: new table.LookupList(gsub.lookups, subtableMakers)}
    ]);
}
```
</details>

### `parseMetaTable(data: any, start: any): {}`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{}`

**Calls:**

- `p.parseULong`
- `check.argument`
- `p.parseTag`
- `decode.UTF8`

<details><summary>Code</summary>

```typescript
function parseMetaTable(data, start) {
    var p = new parse.Parser(data, start);
    var tableVersion = p.parseULong();
    check.argument(tableVersion === 1, 'Unsupported META table version.');
    p.parseULong(); // flags - currently unused and set to 0
    p.parseULong(); // tableOffset
    var numDataMaps = p.parseULong();

    var tags = {};
    for (var i = 0; i < numDataMaps; i++) {
        var tag = p.parseTag();
        var dataOffset = p.parseULong();
        var dataLength = p.parseULong();
        var text = decode.UTF8(data, start + dataOffset, dataLength);

        tags[tag] = text;
    }
    return tags;
}
```
</details>

### `makeMetaTable(tags: any): Table`

**Parameters:**

- **`tags`** `any`

**Returns:** `Table`

**Calls:**

- `Object.keys`
- `result.fields.push`

<details><summary>Code</summary>

```typescript
function makeMetaTable(tags) {
    var numTags = Object.keys(tags).length;
    var stringPool = '';
    var stringPoolOffset = 16 + numTags * 12;

    var result = new table.Table('meta', [
        {name: 'version', type: 'ULONG', value: 1},
        {name: 'flags', type: 'ULONG', value: 0},
        {name: 'offset', type: 'ULONG', value: stringPoolOffset},
        {name: 'numTags', type: 'ULONG', value: numTags}
    ]);

    for (var tag in tags) {
        var pos = stringPool.length;
        stringPool += tags[tag];

        result.fields.push({name: 'tag ' + tag, type: 'TAG', value: tag});
        result.fields.push({name: 'offset ' + tag, type: 'ULONG', value: stringPoolOffset + pos});
        result.fields.push({name: 'length ' + tag, type: 'ULONG', value: tags[tag].length});
    }

    result.fields.push({name: 'stringPool', type: 'CHARARRAY', value: stringPool});

    return result;
}
```
</details>

### `parseColrTable(data: any, start: any): { version: any; baseGlyphRecords: any[]; layerRecords: any[]; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; baseGlyphRecords: any[]; layerRecords: any[]; }`

**Calls:**

- `p.parseUShort`
- `check.argument`
- `p.parseOffset32`
- `p.parseRecordList`

<details><summary>Code</summary>

```typescript
function parseColrTable(data, start) {
    var p = new Parser(data, start);
    var version = p.parseUShort();
    check.argument(version === 0x0000, 'Only COLRv0 supported.');
    var numBaseGlyphRecords = p.parseUShort();
    var baseGlyphRecordsOffset = p.parseOffset32();
    var layerRecordsOffset = p.parseOffset32();
    var numLayerRecords = p.parseUShort();
    p.relativeOffset = baseGlyphRecordsOffset;
    var baseGlyphRecords = p.parseRecordList(numBaseGlyphRecords, {
        glyphID: Parser.uShort,
        firstLayerIndex: Parser.uShort,
        numLayers: Parser.uShort,
    });
    p.relativeOffset = layerRecordsOffset;
    var layerRecords = p.parseRecordList(numLayerRecords, {
        glyphID: Parser.uShort,
        paletteIndex: Parser.uShort
    });

    return {
        version: version,
        baseGlyphRecords: baseGlyphRecords,
        layerRecords: layerRecords,
    };
}
```
</details>

### `makeColrTable(ref: any): Table`

**Parameters:**

- **`ref`** `any`

**Returns:** `Table`

**Calls:**

- `check.argument`
- `[
        { name: 'version', type: 'USHORT', value: version },
        { name: 'numBaseGlyphRecords', type: 'USHORT', value: baseGlyphRecords.length },
        { name: 'baseGlyphRecordsOffset', type: 'ULONG', value: baseGlyphRecordsOffset },
        { name: 'layerRecordsOffset', type: 'ULONG', value: layerRecordsOffset },
        { name: 'numLayerRecords', type: 'USHORT', value: layerRecords.length } ].concat`
- `baseGlyphRecords.map(function (glyph, i) { return [
            { name: 'glyphID_' + i, type: 'USHORT', value: glyph.glyphID },
            { name: 'firstLayerIndex_' + i, type: 'USHORT', value: glyph.firstLayerIndex },
            { name: 'numLayers_' + i, type: 'USHORT', value: glyph.numLayers } ]; }).flat`
- `layerRecords.map(function (layer, i) { return [
            { name: 'LayerGlyphID_' + i, type: 'USHORT', value: layer.glyphID },
            { name: 'paletteIndex_' + i, type: 'USHORT', value: layer.paletteIndex } ]; }).flat`

<details><summary>Code</summary>

```typescript
function makeColrTable(ref) {
    var version = ref.version; if ( version === void 0 ) version = 0x0000;
    var baseGlyphRecords = ref.baseGlyphRecords; if ( baseGlyphRecords === void 0 ) baseGlyphRecords = [];
    var layerRecords = ref.layerRecords; if ( layerRecords === void 0 ) layerRecords = [];

    check.argument(version === 0x0000, 'Only COLRv0 supported.');
    var baseGlyphRecordsOffset = 14;
    var layerRecordsOffset = baseGlyphRecordsOffset + (baseGlyphRecords.length * 6);
    return new table.Table('COLR', [
        { name: 'version', type: 'USHORT', value: version },
        { name: 'numBaseGlyphRecords', type: 'USHORT', value: baseGlyphRecords.length },
        { name: 'baseGlyphRecordsOffset', type: 'ULONG', value: baseGlyphRecordsOffset },
        { name: 'layerRecordsOffset', type: 'ULONG', value: layerRecordsOffset },
        { name: 'numLayerRecords', type: 'USHORT', value: layerRecords.length } ].concat( baseGlyphRecords.map(function (glyph, i) { return [
            { name: 'glyphID_' + i, type: 'USHORT', value: glyph.glyphID },
            { name: 'firstLayerIndex_' + i, type: 'USHORT', value: glyph.firstLayerIndex },
            { name: 'numLayers_' + i, type: 'USHORT', value: glyph.numLayers } ]; }).flat(),
        layerRecords.map(function (layer, i) { return [
            { name: 'LayerGlyphID_' + i, type: 'USHORT', value: layer.glyphID },
            { name: 'paletteIndex_' + i, type: 'USHORT', value: layer.paletteIndex } ]; }).flat() ));
}
```
</details>

### `parseCpalTable(data: any, start: any): { version: any; numPaletteEntries: any; colorRecords: any[]; colorRecordIndices: any[]; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; numPaletteEntries: any; colorRecords: any[]; colorRecordIndices: any[]; }`

**Calls:**

- `p.parseShort`
- `p.parseOffset32`
- `p.parseUShortList`
- `p.parseULongList`

<details><summary>Code</summary>

```typescript
function parseCpalTable(data, start) {
  var p = new Parser(data, start);
  var version = p.parseShort();
  var numPaletteEntries = p.parseShort();
  var numPalettes = p.parseShort();
  var numColorRecords = p.parseShort();
  var colorRecordsArrayOffset = p.parseOffset32();
  var colorRecordIndices = p.parseUShortList(numPalettes);
  p.relativeOffset = colorRecordsArrayOffset;
  var colorRecords = p.parseULongList(numColorRecords);
  return {
    version: version,
    numPaletteEntries: numPaletteEntries,
    colorRecords: colorRecords,
    colorRecordIndices: colorRecordIndices,
  };
}
```
</details>

### `makeCpalTable(ref: any): Table`

**Parameters:**

- **`ref`** `any`

**Returns:** `Table`

**Calls:**

- `check.argument`
- `[
    { name: 'version', type: 'USHORT', value: version },
    { name: 'numPaletteEntries', type: 'USHORT', value: numPaletteEntries || colorRecords.length },
    { name: 'numPalettes', type: 'USHORT', value: colorRecordIndices.length },
    { name: 'numColorRecords', type: 'USHORT', value: colorRecords.length },
    { name: 'colorRecordsArrayOffset', type: 'ULONG', value: 12 + 2 * colorRecordIndices.length } ].concat`
- `colorRecordIndices.map`
- `colorRecords.map`

<details><summary>Code</summary>

```typescript
function makeCpalTable(ref) {
  var version = ref.version; if ( version === void 0 ) version = 0;
  var numPaletteEntries = ref.numPaletteEntries; if ( numPaletteEntries === void 0 ) numPaletteEntries = 0;
  var colorRecords = ref.colorRecords; if ( colorRecords === void 0 ) colorRecords = [];
  var colorRecordIndices = ref.colorRecordIndices; if ( colorRecordIndices === void 0 ) colorRecordIndices = [0];

  check.argument(version === 0, 'Only CPALv0 are supported.');
  check.argument(colorRecords.length, 'No colorRecords given.');
  check.argument(colorRecordIndices.length, 'No colorRecordIndices given.');
  check.argument(!numPaletteEntries && colorRecordIndices.length == 1, 'Can\'t infer numPaletteEntries on multiple colorRecordIndices');
  return new table.Table('CPAL', [
    { name: 'version', type: 'USHORT', value: version },
    { name: 'numPaletteEntries', type: 'USHORT', value: numPaletteEntries || colorRecords.length },
    { name: 'numPalettes', type: 'USHORT', value: colorRecordIndices.length },
    { name: 'numColorRecords', type: 'USHORT', value: colorRecords.length },
    { name: 'colorRecordsArrayOffset', type: 'ULONG', value: 12 + 2 * colorRecordIndices.length } ].concat( colorRecordIndices.map(function (palette, i) { return ({ name: 'colorRecordIndices_' + i, type: 'USHORT', value: palette }); }),
    colorRecords.map(function (color, i) { return ({ name: 'colorRecords_' + i, type: 'ULONG', value: color }); }) ));
}
```
</details>

### `log2(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.log`

<details><summary>Code</summary>

```typescript
function log2(v) {
    return Math.log(v) / Math.log(2) | 0;
}
```
</details>

### `computeCheckSum(bytes: any): number`

**Parameters:**

- **`bytes`** `any`

**Returns:** `number`

**Calls:**

- `bytes.push`
- `Math.pow`

<details><summary>Code</summary>

```typescript
function computeCheckSum(bytes) {
    while (bytes.length % 4 !== 0) {
        bytes.push(0);
    }

    var sum = 0;
    for (var i = 0; i < bytes.length; i += 4) {
        sum += (bytes[i] << 24) +
            (bytes[i + 1] << 16) +
            (bytes[i + 2] << 8) +
            (bytes[i + 3]);
    }

    sum %= Math.pow(2, 32);
    return sum;
}
```
</details>

### `makeTableRecord(tag: any, checkSum: any, offset: any, length: any): Table`

**Parameters:**

- **`tag`** `any`
- **`checkSum`** `any`
- **`offset`** `any`
- **`length`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeTableRecord(tag, checkSum, offset, length) {
    return new table.Record('Table Record', [
        {name: 'tag', type: 'TAG', value: tag !== undefined ? tag : ''},
        {name: 'checkSum', type: 'ULONG', value: checkSum !== undefined ? checkSum : 0},
        {name: 'offset', type: 'ULONG', value: offset !== undefined ? offset : 0},
        {name: 'length', type: 'ULONG', value: length !== undefined ? length : 0}
    ]);
}
```
</details>

### `makeSfntTable(tables: any): Table`

**Parameters:**

- **`tables`** `any`

**Returns:** `Table`

**Calls:**

- `Math.pow`
- `log2`
- `sfnt.sizeOf`
- `makeTableRecord().sizeOf`
- `tableFields.push`
- `check.argument`
- `t.sizeOf`
- `makeTableRecord`
- `computeCheckSum`
- `t.encode`
- `recordFields.push`
- `isNaN`
- `recordFields.sort`
- `sfnt.fields.concat`

**Internal Comments:**
```
// Table records need to be sorted alphabetically. (x4)
```

<details><summary>Code</summary>

```typescript
function makeSfntTable(tables) {
    var sfnt = new table.Table('sfnt', [
        {name: 'version', type: 'TAG', value: 'OTTO'},
        {name: 'numTables', type: 'USHORT', value: 0},
        {name: 'searchRange', type: 'USHORT', value: 0},
        {name: 'entrySelector', type: 'USHORT', value: 0},
        {name: 'rangeShift', type: 'USHORT', value: 0}
    ]);
    sfnt.tables = tables;
    sfnt.numTables = tables.length;
    var highestPowerOf2 = Math.pow(2, log2(sfnt.numTables));
    sfnt.searchRange = 16 * highestPowerOf2;
    sfnt.entrySelector = log2(highestPowerOf2);
    sfnt.rangeShift = sfnt.numTables * 16 - sfnt.searchRange;

    var recordFields = [];
    var tableFields = [];

    var offset = sfnt.sizeOf() + (makeTableRecord().sizeOf() * sfnt.numTables);
    while (offset % 4 !== 0) {
        offset += 1;
        tableFields.push({name: 'padding', type: 'BYTE', value: 0});
    }

    for (var i = 0; i < tables.length; i += 1) {
        var t = tables[i];
        check.argument(t.tableName.length === 4, 'Table name' + t.tableName + ' is invalid.');
        var tableLength = t.sizeOf();
        var tableRecord = makeTableRecord(t.tableName, computeCheckSum(t.encode()), offset, tableLength);
        recordFields.push({name: tableRecord.tag + ' Table Record', type: 'RECORD', value: tableRecord});
        tableFields.push({name: t.tableName + ' table', type: 'RECORD', value: t});
        offset += tableLength;
        check.argument(!isNaN(offset), 'Something went wrong calculating the offset.');
        while (offset % 4 !== 0) {
            offset += 1;
            tableFields.push({name: 'padding', type: 'BYTE', value: 0});
        }
    }

    // Table records need to be sorted alphabetically.
    recordFields.sort(function(r1, r2) {
        if (r1.value.tag > r2.value.tag) {
            return 1;
        } else {
            return -1;
        }
    });

    sfnt.fields = sfnt.fields.concat(recordFields);
    sfnt.fields = sfnt.fields.concat(tableFields);
    return sfnt;
}
```
</details>

### `metricsForChar(font: any, chars: any, notFoundMetrics: any): any`

**Parameters:**

- **`font`** `any`
- **`chars`** `any`
- **`notFoundMetrics`** `any`

**Returns:** `any`

**Calls:**

- `font.charToGlyphIndex`
- `font.glyphs.get`
- `glyph.getMetrics`

<details><summary>Code</summary>

```typescript
function metricsForChar(font, chars, notFoundMetrics) {
    for (var i = 0; i < chars.length; i += 1) {
        var glyphIndex = font.charToGlyphIndex(chars[i]);
        if (glyphIndex > 0) {
            var glyph = font.glyphs.get(glyphIndex);
            return glyph.getMetrics();
        }
    }

    return notFoundMetrics;
}
```
</details>

### `average(vs: any): number`

**Parameters:**

- **`vs`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function average(vs) {
    var sum = 0;
    for (var i = 0; i < vs.length; i += 1) {
        sum += vs[i];
    }

    return sum / vs.length;
}
```
</details>

### `fontToSfntTable(font: any): Table`

**Parameters:**

- **`font`** `any`

**Returns:** `Table`

**Calls:**

- `font.glyphs.get`
- `isNaN`
- `os2.getUnicodeRange`
- `glyph.getMetrics`
- `xMins.push`
- `yMins.push`
- `xMaxs.push`
- `yMaxs.push`
- `leftSideBearings.push`
- `rightSideBearings.push`
- `advanceWidths.push`
- `Math.min.apply`
- `Math.max.apply`
- `average`
- `head.make`
- `hhea.make`
- `maxp.make`
- `os2.make`
- `Object.assign`
- `Math.round`
- `Math.abs`
- `metricsForChar`
- `font.hasChar`
- `hmtx.make`
- `cmap.make`
- `font.getEnglishName`
- `englishFamilyName.replace`
- `_name.make`
- `ltag.make`
- `post.make`
- `cff.make`
- `Object.keys`
- `meta.make`
- `tables.push`
- `gsub.make`
- `cpal.make`
- `colr.make`
- `makeSfntTable`
- `sfntTable.encode`
- `computeCheckSum`

**Internal Comments:**
```
// ignore .notdef char
// Skip non-important characters.
// See http://typophile.com/node/13081 for more info on vertical metrics. (x2)
// We get metrics for typical characters (such as "x" for xHeight). (x2)
// We provide some fallback characters if characters are unavailable: their (x2)
// ordering was chosen experimentally. (x2)
// The order does not matter because makeSfntTable() will sort them. (x2)
// Optional tables
// Compute the font's checkSum and store it in head.checkSumAdjustment. (x2)
```

<details><summary>Code</summary>

```typescript
function fontToSfntTable(font) {
    var xMins = [];
    var yMins = [];
    var xMaxs = [];
    var yMaxs = [];
    var advanceWidths = [];
    var leftSideBearings = [];
    var rightSideBearings = [];
    var firstCharIndex;
    var lastCharIndex = 0;
    var ulUnicodeRange1 = 0;
    var ulUnicodeRange2 = 0;
    var ulUnicodeRange3 = 0;
    var ulUnicodeRange4 = 0;

    for (var i = 0; i < font.glyphs.length; i += 1) {
        var glyph = font.glyphs.get(i);
        var unicode = glyph.unicode | 0;

        if (isNaN(glyph.advanceWidth)) {
            throw new Error('Glyph ' + glyph.name + ' (' + i + '): advanceWidth is not a number.');
        }

        if (firstCharIndex > unicode || firstCharIndex === undefined) {
            // ignore .notdef char
            if (unicode > 0) {
                firstCharIndex = unicode;
            }
        }

        if (lastCharIndex < unicode) {
            lastCharIndex = unicode;
        }

        var position = os2.getUnicodeRange(unicode);
        if (position < 32) {
            ulUnicodeRange1 |= 1 << position;
        } else if (position < 64) {
            ulUnicodeRange2 |= 1 << position - 32;
        } else if (position < 96) {
            ulUnicodeRange3 |= 1 << position - 64;
        } else if (position < 123) {
            ulUnicodeRange4 |= 1 << position - 96;
        } else {
            throw new Error('Unicode ranges bits > 123 are reserved for internal usage');
        }
        // Skip non-important characters.
        if (glyph.name === '.notdef') { continue; }
        var metrics = glyph.getMetrics();
        xMins.push(metrics.xMin);
        yMins.push(metrics.yMin);
        xMaxs.push(metrics.xMax);
        yMaxs.push(metrics.yMax);
        leftSideBearings.push(metrics.leftSideBearing);
        rightSideBearings.push(metrics.rightSideBearing);
        advanceWidths.push(glyph.advanceWidth);
    }

    var globals = {
        xMin: Math.min.apply(null, xMins),
        yMin: Math.min.apply(null, yMins),
        xMax: Math.max.apply(null, xMaxs),
        yMax: Math.max.apply(null, yMaxs),
        advanceWidthMax: Math.max.apply(null, advanceWidths),
        advanceWidthAvg: average(advanceWidths),
        minLeftSideBearing: Math.min.apply(null, leftSideBearings),
        maxLeftSideBearing: Math.max.apply(null, leftSideBearings),
        minRightSideBearing: Math.min.apply(null, rightSideBearings)
    };
    globals.ascender = font.ascender;
    globals.descender = font.descender;

    var headTable = head.make({
        flags: 3, // 00000011 (baseline for font at y=0; left sidebearing point at x=0)
        unitsPerEm: font.unitsPerEm,
        xMin: globals.xMin,
        yMin: globals.yMin,
        xMax: globals.xMax,
        yMax: globals.yMax,
        lowestRecPPEM: 3,
        createdTimestamp: font.createdTimestamp
    });

    var hheaTable = hhea.make({
        ascender: globals.ascender,
        descender: globals.descender,
        advanceWidthMax: globals.advanceWidthMax,
        minLeftSideBearing: globals.minLeftSideBearing,
        minRightSideBearing: globals.minRightSideBearing,
        xMaxExtent: globals.maxLeftSideBearing + (globals.xMax - globals.xMin),
        numberOfHMetrics: font.glyphs.length
    });

    var maxpTable = maxp.make(font.glyphs.length);

    var os2Table = os2.make(Object.assign({
        xAvgCharWidth: Math.round(globals.advanceWidthAvg),
        usFirstCharIndex: firstCharIndex,
        usLastCharIndex: lastCharIndex,
        ulUnicodeRange1: ulUnicodeRange1,
        ulUnicodeRange2: ulUnicodeRange2,
        ulUnicodeRange3: ulUnicodeRange3,
        ulUnicodeRange4: ulUnicodeRange4,
        // See http://typophile.com/node/13081 for more info on vertical metrics.
        // We get metrics for typical characters (such as "x" for xHeight).
        // We provide some fallback characters if characters are unavailable: their
        // ordering was chosen experimentally.
        sTypoAscender: globals.ascender,
        sTypoDescender: globals.descender,
        sTypoLineGap: 0,
        usWinAscent: globals.yMax,
        usWinDescent: Math.abs(globals.yMin),
        ulCodePageRange1: 1, // FIXME: hard-code Latin 1 support for now
        sxHeight: metricsForChar(font, 'xyvw', {yMax: Math.round(globals.ascender / 2)}).yMax,
        sCapHeight: metricsForChar(font, 'HIKLEFJMNTZBDPRAGOQSUVWXY', globals).yMax,
        usDefaultChar: font.hasChar(' ') ? 32 : 0, // Use space as the default character, if available.
        usBreakChar: font.hasChar(' ') ? 32 : 0, // Use space as the break character, if available.
    }, font.tables.os2));

    var hmtxTable = hmtx.make(font.glyphs);
    var cmapTable = cmap.make(font.glyphs);

    var englishFamilyName = font.getEnglishName('fontFamily');
    var englishStyleName = font.getEnglishName('fontSubfamily');
    var englishFullName = englishFamilyName + ' ' + englishStyleName;
    var postScriptName = font.getEnglishName('postScriptName');
    if (!postScriptName) {
        postScriptName = englishFamilyName.replace(/\s/g, '') + '-' + englishStyleName;
    }

    var names = {};
    for (var n in font.names) {
        names[n] = font.names[n];
    }

    if (!names.uniqueID) {
        names.uniqueID = {en: font.getEnglishName('manufacturer') + ':' + englishFullName};
    }

    if (!names.postScriptName) {
        names.postScriptName = {en: postScriptName};
    }

    if (!names.preferredFamily) {
        names.preferredFamily = font.names.fontFamily;
    }

    if (!names.preferredSubfamily) {
        names.preferredSubfamily = font.names.fontSubfamily;
    }

    var languageTags = [];
    var nameTable = _name.make(names, languageTags);
    var ltagTable = (languageTags.length > 0 ? ltag.make(languageTags) : undefined);

    var postTable = post.make();
    var cffTable = cff.make(font.glyphs, {
        version: font.getEnglishName('version'),
        fullName: englishFullName,
        familyName: englishFamilyName,
        weightName: englishStyleName,
        postScriptName: postScriptName,
        unitsPerEm: font.unitsPerEm,
        fontBBox: [0, globals.yMin, globals.ascender, globals.advanceWidthMax]
    });

    var metaTable = (font.metas && Object.keys(font.metas).length > 0) ? meta.make(font.metas) : undefined;

    // The order does not matter because makeSfntTable() will sort them.
    var tables = [headTable, hheaTable, maxpTable, os2Table, nameTable, cmapTable, postTable, cffTable, hmtxTable];
    if (ltagTable) {
        tables.push(ltagTable);
    }
    // Optional tables
    if (font.tables.gsub) {
        tables.push(gsub.make(font.tables.gsub));
    }
    if (font.tables.cpal) {
        tables.push(cpal.make(font.tables.cpal));
    }
    if (font.tables.colr) {
        tables.push(colr.make(font.tables.colr));
    }
    if (metaTable) {
        tables.push(metaTable);
    }

    var sfntTable = makeSfntTable(tables);

    // Compute the font's checkSum and store it in head.checkSumAdjustment.
    var bytes = sfntTable.encode();
    var checkSum = computeCheckSum(bytes);
    var tableFields = sfntTable.fields;
    var checkSumAdjusted = false;
    for (var i$1 = 0; i$1 < tableFields.length; i$1 += 1) {
        if (tableFields[i$1].name === 'head table') {
            tableFields[i$1].value.checkSumAdjustment = 0xB1B0AFBA - checkSum;
            checkSumAdjusted = true;
            break;
        }
    }

    if (!checkSumAdjusted) {
        throw new Error('Could not find head table with checkSum to adjust.');
    }

    return sfntTable;
}
```
</details>

### `searchTag(arr: any, tag: any): number`

**Parameters:**

- **`arr`** `any`
- **`tag`** `any`

**Returns:** `number`

**Internal Comments:**
```
/* jshint bitwise: false */ (x2)
// Not found: return -1-insertion point
```

<details><summary>Code</summary>

```typescript
function searchTag(arr, tag) {
    /* jshint bitwise: false */
    var imin = 0;
    var imax = arr.length - 1;
    while (imin <= imax) {
        var imid = (imin + imax) >>> 1;
        var val = arr[imid].tag;
        if (val === tag) {
            return imid;
        } else if (val < tag) {
            imin = imid + 1;
        } else { imax = imid - 1; }
    }
    // Not found: return -1-insertion point
    return -imin - 1;
}
```
</details>

### `binSearch(arr: any, value: any): number`

**Parameters:**

- **`arr`** `any`
- **`value`** `any`

**Returns:** `number`

**Internal Comments:**
```
/* jshint bitwise: false */ (x2)
// Not found: return -1-insertion point
```

<details><summary>Code</summary>

```typescript
function binSearch(arr, value) {
    /* jshint bitwise: false */
    var imin = 0;
    var imax = arr.length - 1;
    while (imin <= imax) {
        var imid = (imin + imax) >>> 1;
        var val = arr[imid];
        if (val === value) {
            return imid;
        } else if (val < value) {
            imin = imid + 1;
        } else { imax = imid - 1; }
    }
    // Not found: return -1-insertion point
    return -imin - 1;
}
```
</details>

### `searchRange(ranges: any, value: any): any`

**Parameters:**

- **`ranges`** `any`
- **`value`** `any`

**Returns:** `any`

**Internal Comments:**
```
// jshint bitwise: false (x2)
```

<details><summary>Code</summary>

```typescript
function searchRange(ranges, value) {
    // jshint bitwise: false
    var range;
    var imin = 0;
    var imax = ranges.length - 1;
    while (imin <= imax) {
        var imid = (imin + imax) >>> 1;
        range = ranges[imid];
        var start = range.start;
        if (start === value) {
            return range;
        } else if (start < value) {
            imin = imid + 1;
        } else { imax = imid - 1; }
    }
    if (imin > 0) {
        range = ranges[imin - 1];
        if (value > range.end) { return 0; }
        return range;
    }
}
```
</details>

### `Layout(font: any, tableName: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.Layout
 * @class
 */
```

**Parameters:**

- **`font`** `any`
- **`tableName`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Layout(font, tableName) {
    this.font = font;
    this.tableName = tableName;
}
```
</details>

### `getTable(create: boolean): any`

**Parameters:**

- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.createDefaultTable`

<details><summary>Code</summary>

```typescript
function(create) {
        var layout = this.font.tables[this.tableName];
        if (!layout && create) {
            layout = this.font.tables[this.tableName] = this.createDefaultTable();
        }
        return layout;
    }
```
</details>

### `getScriptNames(): any[]`

**Returns:** `any[]`

**Calls:**

- `this.getTable`
- `layout.scripts.map`

<details><summary>Code</summary>

```typescript
function() {
        var layout = this.getTable();
        if (!layout) { return []; }
        return layout.scripts.map(function(script) {
            return script.tag;
        });
    }
```
</details>

### `getDefaultScriptName(): any`

**Returns:** `any`

**Calls:**

- `this.getTable`

<details><summary>Code</summary>

```typescript
function() {
        var layout = this.getTable();
        if (!layout) { return; }
        var hasLatn = false;
        for (var i = 0; i < layout.scripts.length; i++) {
            var name = layout.scripts[i].tag;
            if (name === 'DFLT') { return name; }
            if (name === 'latn') { hasLatn = true; }
        }
        if (hasLatn) { return 'latn'; }
    }
```
</details>

### `getScriptTable(script: string, create: boolean): any`

**Parameters:**

- **`script`** `string`
- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.getTable`
- `searchTag`
- `scripts.splice`

<details><summary>Code</summary>

```typescript
function(script, create) {
        var layout = this.getTable(create);
        if (layout) {
            script = script || 'DFLT';
            var scripts = layout.scripts;
            var pos = searchTag(layout.scripts, script);
            if (pos >= 0) {
                return scripts[pos].script;
            } else if (create) {
                var scr = {
                    tag: script,
                    script: {
                        defaultLangSys: {reserved: 0, reqFeatureIndex: 0xffff, featureIndexes: []},
                        langSysRecords: []
                    }
                };
                scripts.splice(-1 - pos, 0, scr);
                return scr.script;
            }
        }
    }
```
</details>

### `getLangSysTable(script: string, language: string, create: boolean): any`

**Parameters:**

- **`script`** `string`
- **`language`** `string`
- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.getScriptTable`
- `searchTag`
- `scriptTable.langSysRecords.splice`

<details><summary>Code</summary>

```typescript
function(script, language, create) {
        var scriptTable = this.getScriptTable(script, create);
        if (scriptTable) {
            if (!language || language === 'dflt' || language === 'DFLT') {
                return scriptTable.defaultLangSys;
            }
            var pos = searchTag(scriptTable.langSysRecords, language);
            if (pos >= 0) {
                return scriptTable.langSysRecords[pos].langSys;
            } else if (create) {
                var langSysRecord = {
                    tag: language,
                    langSys: {reserved: 0, reqFeatureIndex: 0xffff, featureIndexes: []}
                };
                scriptTable.langSysRecords.splice(-1 - pos, 0, langSysRecord);
                return langSysRecord.langSys;
            }
        }
    }
```
</details>

### `getFeatureTable(script: string, language: string, feature: string, create: boolean): any`

**Parameters:**

- **`script`** `string`
- **`language`** `string`
- **`feature`** `string`
- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.getLangSysTable`
- `check.assert`
- `allFeatures.push`
- `featIndexes.push`

**Internal Comments:**
```
// The FeatureIndex array of indices is in arbitrary order,
// even if allFeatures is sorted alphabetically by feature tag.
// Automatic ordering of features would require to shift feature indexes in the script list. (x4)
```

<details><summary>Code</summary>

```typescript
function(script, language, feature, create) {
        var langSysTable = this.getLangSysTable(script, language, create);
        if (langSysTable) {
            var featureRecord;
            var featIndexes = langSysTable.featureIndexes;
            var allFeatures = this.font.tables[this.tableName].features;
            // The FeatureIndex array of indices is in arbitrary order,
            // even if allFeatures is sorted alphabetically by feature tag.
            for (var i = 0; i < featIndexes.length; i++) {
                featureRecord = allFeatures[featIndexes[i]];
                if (featureRecord.tag === feature) {
                    return featureRecord.feature;
                }
            }
            if (create) {
                var index = allFeatures.length;
                // Automatic ordering of features would require to shift feature indexes in the script list.
                check.assert(index === 0 || feature >= allFeatures[index - 1].tag, 'Features must be added in alphabetical order.');
                featureRecord = {
                    tag: feature,
                    feature: { params: 0, lookupListIndexes: [] }
                };
                allFeatures.push(featureRecord);
                featIndexes.push(index);
                return featureRecord.feature;
            }
        }
    }
```
</details>

### `getLookupTables(script: string, language: string, feature: string, lookupType: number, create: boolean): any[]`

**Parameters:**

- **`script`** `string`
- **`language`** `string`
- **`feature`** `string`
- **`lookupType`** `number`
- **`create`** `boolean`

**Returns:** `any[]`

**Calls:**

- `this.getFeatureTable`
- `tables.push`
- `allLookups.push`
- `lookupListIndexes.push`

**Internal Comments:**
```
// lookupListIndexes are in no particular order, so use naive search.
```

<details><summary>Code</summary>

```typescript
function(script, language, feature, lookupType, create) {
        var featureTable = this.getFeatureTable(script, language, feature, create);
        var tables = [];
        if (featureTable) {
            var lookupTable;
            var lookupListIndexes = featureTable.lookupListIndexes;
            var allLookups = this.font.tables[this.tableName].lookups;
            // lookupListIndexes are in no particular order, so use naive search.
            for (var i = 0; i < lookupListIndexes.length; i++) {
                lookupTable = allLookups[lookupListIndexes[i]];
                if (lookupTable.lookupType === lookupType) {
                    tables.push(lookupTable);
                }
            }
            if (tables.length === 0 && create) {
                lookupTable = {
                    lookupType: lookupType,
                    lookupFlag: 0,
                    subtables: [],
                    markFilteringSet: undefined
                };
                var index = allLookups.length;
                allLookups.push(lookupTable);
                lookupListIndexes.push(index);
                return [lookupTable];
            }
        }
        return tables;
    }
```
</details>

### `getGlyphClass(classDefTable: any, glyphIndex: number): number`

**Parameters:**

- **`classDefTable`** `any`
- **`glyphIndex`** `number`

**Returns:** `number`

**Calls:**

- `searchRange`

<details><summary>Code</summary>

```typescript
function(classDefTable, glyphIndex) {
        switch (classDefTable.format) {
            case 1:
                if (classDefTable.startGlyph <= glyphIndex && glyphIndex < classDefTable.startGlyph + classDefTable.classes.length) {
                    return classDefTable.classes[glyphIndex - classDefTable.startGlyph];
                }
                return 0;
            case 2:
                var range = searchRange(classDefTable.ranges, glyphIndex);
                return range ? range.classId : 0;
        }
    }
```
</details>

### `getCoverageIndex(coverageTable: any, glyphIndex: number): number`

**Parameters:**

- **`coverageTable`** `any`
- **`glyphIndex`** `number`

**Returns:** `number`

**Calls:**

- `binSearch`
- `searchRange`

<details><summary>Code</summary>

```typescript
function(coverageTable, glyphIndex) {
        switch (coverageTable.format) {
            case 1:
                var index = binSearch(coverageTable.glyphs, glyphIndex);
                return index >= 0 ? index : -1;
            case 2:
                var range = searchRange(coverageTable.ranges, glyphIndex);
                return range ? range.index + glyphIndex - range.start : -1;
        }
    }
```
</details>

### `expandCoverage(coverageTable: any): any[]`

**Parameters:**

- **`coverageTable`** `any`

**Returns:** `any[]`

**Calls:**

- `glyphs.push`

<details><summary>Code</summary>

```typescript
function(coverageTable) {
        if (coverageTable.format === 1) {
            return coverageTable.glyphs;
        } else {
            var glyphs = [];
            var ranges = coverageTable.ranges;
            for (var i = 0; i < ranges.length; i++) {
                var range = ranges[i];
                var start = range.start;
                var end = range.end;
                for (var j = start; j <= end; j++) {
                    glyphs.push(j);
                }
            }
            return glyphs;
        }
    }
```
</details>

### `getTable(create: boolean): any`

**Parameters:**

- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.createDefaultTable`

<details><summary>Code</summary>

```typescript
function(create) {
        var layout = this.font.tables[this.tableName];
        if (!layout && create) {
            layout = this.font.tables[this.tableName] = this.createDefaultTable();
        }
        return layout;
    }
```
</details>

### `getScriptNames(): any[]`

**Returns:** `any[]`

**Calls:**

- `this.getTable`
- `layout.scripts.map`

<details><summary>Code</summary>

```typescript
function() {
        var layout = this.getTable();
        if (!layout) { return []; }
        return layout.scripts.map(function(script) {
            return script.tag;
        });
    }
```
</details>

### `getDefaultScriptName(): any`

**Returns:** `any`

**Calls:**

- `this.getTable`

<details><summary>Code</summary>

```typescript
function() {
        var layout = this.getTable();
        if (!layout) { return; }
        var hasLatn = false;
        for (var i = 0; i < layout.scripts.length; i++) {
            var name = layout.scripts[i].tag;
            if (name === 'DFLT') { return name; }
            if (name === 'latn') { hasLatn = true; }
        }
        if (hasLatn) { return 'latn'; }
    }
```
</details>

### `getScriptTable(script: string, create: boolean): any`

**Parameters:**

- **`script`** `string`
- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.getTable`
- `searchTag`
- `scripts.splice`

<details><summary>Code</summary>

```typescript
function(script, create) {
        var layout = this.getTable(create);
        if (layout) {
            script = script || 'DFLT';
            var scripts = layout.scripts;
            var pos = searchTag(layout.scripts, script);
            if (pos >= 0) {
                return scripts[pos].script;
            } else if (create) {
                var scr = {
                    tag: script,
                    script: {
                        defaultLangSys: {reserved: 0, reqFeatureIndex: 0xffff, featureIndexes: []},
                        langSysRecords: []
                    }
                };
                scripts.splice(-1 - pos, 0, scr);
                return scr.script;
            }
        }
    }
```
</details>

### `getLangSysTable(script: string, language: string, create: boolean): any`

**Parameters:**

- **`script`** `string`
- **`language`** `string`
- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.getScriptTable`
- `searchTag`
- `scriptTable.langSysRecords.splice`

<details><summary>Code</summary>

```typescript
function(script, language, create) {
        var scriptTable = this.getScriptTable(script, create);
        if (scriptTable) {
            if (!language || language === 'dflt' || language === 'DFLT') {
                return scriptTable.defaultLangSys;
            }
            var pos = searchTag(scriptTable.langSysRecords, language);
            if (pos >= 0) {
                return scriptTable.langSysRecords[pos].langSys;
            } else if (create) {
                var langSysRecord = {
                    tag: language,
                    langSys: {reserved: 0, reqFeatureIndex: 0xffff, featureIndexes: []}
                };
                scriptTable.langSysRecords.splice(-1 - pos, 0, langSysRecord);
                return langSysRecord.langSys;
            }
        }
    }
```
</details>

### `getFeatureTable(script: string, language: string, feature: string, create: boolean): any`

**Parameters:**

- **`script`** `string`
- **`language`** `string`
- **`feature`** `string`
- **`create`** `boolean`

**Returns:** `any`

**Calls:**

- `this.getLangSysTable`
- `check.assert`
- `allFeatures.push`
- `featIndexes.push`

**Internal Comments:**
```
// The FeatureIndex array of indices is in arbitrary order,
// even if allFeatures is sorted alphabetically by feature tag.
// Automatic ordering of features would require to shift feature indexes in the script list. (x4)
```

<details><summary>Code</summary>

```typescript
function(script, language, feature, create) {
        var langSysTable = this.getLangSysTable(script, language, create);
        if (langSysTable) {
            var featureRecord;
            var featIndexes = langSysTable.featureIndexes;
            var allFeatures = this.font.tables[this.tableName].features;
            // The FeatureIndex array of indices is in arbitrary order,
            // even if allFeatures is sorted alphabetically by feature tag.
            for (var i = 0; i < featIndexes.length; i++) {
                featureRecord = allFeatures[featIndexes[i]];
                if (featureRecord.tag === feature) {
                    return featureRecord.feature;
                }
            }
            if (create) {
                var index = allFeatures.length;
                // Automatic ordering of features would require to shift feature indexes in the script list.
                check.assert(index === 0 || feature >= allFeatures[index - 1].tag, 'Features must be added in alphabetical order.');
                featureRecord = {
                    tag: feature,
                    feature: { params: 0, lookupListIndexes: [] }
                };
                allFeatures.push(featureRecord);
                featIndexes.push(index);
                return featureRecord.feature;
            }
        }
    }
```
</details>

### `getLookupTables(script: string, language: string, feature: string, lookupType: number, create: boolean): any[]`

**Parameters:**

- **`script`** `string`
- **`language`** `string`
- **`feature`** `string`
- **`lookupType`** `number`
- **`create`** `boolean`

**Returns:** `any[]`

**Calls:**

- `this.getFeatureTable`
- `tables.push`
- `allLookups.push`
- `lookupListIndexes.push`

**Internal Comments:**
```
// lookupListIndexes are in no particular order, so use naive search.
```

<details><summary>Code</summary>

```typescript
function(script, language, feature, lookupType, create) {
        var featureTable = this.getFeatureTable(script, language, feature, create);
        var tables = [];
        if (featureTable) {
            var lookupTable;
            var lookupListIndexes = featureTable.lookupListIndexes;
            var allLookups = this.font.tables[this.tableName].lookups;
            // lookupListIndexes are in no particular order, so use naive search.
            for (var i = 0; i < lookupListIndexes.length; i++) {
                lookupTable = allLookups[lookupListIndexes[i]];
                if (lookupTable.lookupType === lookupType) {
                    tables.push(lookupTable);
                }
            }
            if (tables.length === 0 && create) {
                lookupTable = {
                    lookupType: lookupType,
                    lookupFlag: 0,
                    subtables: [],
                    markFilteringSet: undefined
                };
                var index = allLookups.length;
                allLookups.push(lookupTable);
                lookupListIndexes.push(index);
                return [lookupTable];
            }
        }
        return tables;
    }
```
</details>

### `getGlyphClass(classDefTable: any, glyphIndex: number): number`

**Parameters:**

- **`classDefTable`** `any`
- **`glyphIndex`** `number`

**Returns:** `number`

**Calls:**

- `searchRange`

<details><summary>Code</summary>

```typescript
function(classDefTable, glyphIndex) {
        switch (classDefTable.format) {
            case 1:
                if (classDefTable.startGlyph <= glyphIndex && glyphIndex < classDefTable.startGlyph + classDefTable.classes.length) {
                    return classDefTable.classes[glyphIndex - classDefTable.startGlyph];
                }
                return 0;
            case 2:
                var range = searchRange(classDefTable.ranges, glyphIndex);
                return range ? range.classId : 0;
        }
    }
```
</details>

### `getCoverageIndex(coverageTable: any, glyphIndex: number): number`

**Parameters:**

- **`coverageTable`** `any`
- **`glyphIndex`** `number`

**Returns:** `number`

**Calls:**

- `binSearch`
- `searchRange`

<details><summary>Code</summary>

```typescript
function(coverageTable, glyphIndex) {
        switch (coverageTable.format) {
            case 1:
                var index = binSearch(coverageTable.glyphs, glyphIndex);
                return index >= 0 ? index : -1;
            case 2:
                var range = searchRange(coverageTable.ranges, glyphIndex);
                return range ? range.index + glyphIndex - range.start : -1;
        }
    }
```
</details>

### `expandCoverage(coverageTable: any): any[]`

**Parameters:**

- **`coverageTable`** `any`

**Returns:** `any[]`

**Calls:**

- `glyphs.push`

<details><summary>Code</summary>

```typescript
function(coverageTable) {
        if (coverageTable.format === 1) {
            return coverageTable.glyphs;
        } else {
            var glyphs = [];
            var ranges = coverageTable.ranges;
            for (var i = 0; i < ranges.length; i++) {
                var range = ranges[i];
                var start = range.start;
                var end = range.end;
                for (var j = start; j <= end; j++) {
                    glyphs.push(j);
                }
            }
            return glyphs;
        }
    }
```
</details>

### `Position(font: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.Position
 * @class
 * @extends opentype.Layout
 * @param {opentype.Font}
 * @constructor
 */
```

**Parameters:**

- **`font`** `any`

**Returns:** `void`

**Calls:**

- `Layout.call`

<details><summary>Code</summary>

```typescript
function Position(font) {
    Layout.call(this, font, 'gpos');
}
```
</details>

### `Substitution(font: any): void`

**JSDoc:**
```typescript
/**
 * @exports opentype.Substitution
 * @class
 * @extends opentype.Layout
 * @param {opentype.Font}
 * @constructor
 */
```

**Parameters:**

- **`font`** `any`

**Returns:** `void`

**Calls:**

- `Layout.call`

<details><summary>Code</summary>

```typescript
function Substitution(font) {
    Layout.call(this, font, 'gsub');
}
```
</details>

### `arraysEqual(ar1: any, ar2: any): boolean`

**Parameters:**

- **`ar1`** `any`
- **`ar2`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function arraysEqual(ar1, ar2) {
    var n = ar1.length;
    if (n !== ar2.length) { return false; }
    for (var i = 0; i < n; i++) {
        if (ar1[i] !== ar2[i]) { return false; }
    }
    return true;
}
```
</details>

### `getSubstFormat(lookupTable: any, format: any, defaultSubtable: any): any`

**Parameters:**

- **`lookupTable`** `any`
- **`format`** `any`
- **`defaultSubtable`** `any`

**Returns:** `any`

**Calls:**

- `subtables.push`

<details><summary>Code</summary>

```typescript
function getSubstFormat(lookupTable, format, defaultSubtable) {
    var subtables = lookupTable.subtables;
    for (var i = 0; i < subtables.length; i++) {
        var subtable = subtables[i];
        if (subtable.substFormat === format) {
            return subtable;
        }
    }
    if (defaultSubtable) {
        subtables.push(defaultSubtable);
        return defaultSubtable;
    }
    return undefined;
}
```
</details>

### `checkArgument(expression: any, message: any): void`

**Parameters:**

- **`expression`** `any`
- **`message`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function checkArgument(expression, message) {
    if (!expression) {
        throw message;
    }
}
```
</details>

### `parseGlyphCoordinate(p: any, flag: any, previousValue: any, shortVectorBitMask: any, sameBitMask: any): any`

**Parameters:**

- **`p`** `any`
- **`flag`** `any`
- **`previousValue`** `any`
- **`shortVectorBitMask`** `any`
- **`sameBitMask`** `any`

**Returns:** `any`

**Calls:**

- `p.parseByte`
- `p.parseShort`

**Internal Comments:**
```
// The coordinate is 1 byte long. (x3)
// The `same` bit is re-used for short values to signify the sign of the value.
//  The coordinate is 2 bytes long.
// If the `same` bit is set, the coordinate is the same as the previous coordinate.
// Parse the coordinate as a signed 16-bit delta value. (x3)
```

<details><summary>Code</summary>

```typescript
function parseGlyphCoordinate(p, flag, previousValue, shortVectorBitMask, sameBitMask) {
    var v;
    if ((flag & shortVectorBitMask) > 0) {
        // The coordinate is 1 byte long.
        v = p.parseByte();
        // The `same` bit is re-used for short values to signify the sign of the value.
        if ((flag & sameBitMask) === 0) {
            v = -v;
        }

        v = previousValue + v;
    } else {
        //  The coordinate is 2 bytes long.
        // If the `same` bit is set, the coordinate is the same as the previous coordinate.
        if ((flag & sameBitMask) > 0) {
            v = previousValue;
        } else {
            // Parse the coordinate as a signed 16-bit delta value.
            v = previousValue + p.parseShort();
        }
    }

    return v;
}
```
</details>

### `parseGlyph(glyph: any, data: any, start: any): void`

**Parameters:**

- **`glyph`** `any`
- **`data`** `any`
- **`start`** `any`

**Returns:** `void`

**Calls:**

- `p.parseShort`
- `endPointIndices.push`
- `p.parseUShort`
- `glyph.instructions.push`
- `p.parseByte`
- `flags.push`
- `check.argument`
- `endPointIndices.indexOf`
- `points.push`
- `parseGlyphCoordinate`
- `p.parseChar`
- `p.parseF2Dot14`
- `glyph.components.push`

**Internal Comments:**
```
// This glyph is not a composite. (x2)
// If bit 3 is set, we repeat this flag n times, where n is the next byte.
// X/Y coordinates are relative to the previous point, except for the first point which is relative to 0,0.
// The arguments are words
// values are offset (x8)
// values are matched points (x8)
// The arguments are bytes
// We have a scale (x4)
// We have an X / Y scale (x4)
// We have a 2x2 transformation (x4)
// We have instructions (x4)
```

<details><summary>Code</summary>

```typescript
function parseGlyph(glyph, data, start) {
    var p = new parse.Parser(data, start);
    glyph.numberOfContours = p.parseShort();
    glyph._xMin = p.parseShort();
    glyph._yMin = p.parseShort();
    glyph._xMax = p.parseShort();
    glyph._yMax = p.parseShort();
    var flags;
    var flag;

    if (glyph.numberOfContours > 0) {
        // This glyph is not a composite.
        var endPointIndices = glyph.endPointIndices = [];
        for (var i = 0; i < glyph.numberOfContours; i += 1) {
            endPointIndices.push(p.parseUShort());
        }

        glyph.instructionLength = p.parseUShort();
        glyph.instructions = [];
        for (var i$1 = 0; i$1 < glyph.instructionLength; i$1 += 1) {
            glyph.instructions.push(p.parseByte());
        }

        var numberOfCoordinates = endPointIndices[endPointIndices.length - 1] + 1;
        flags = [];
        for (var i$2 = 0; i$2 < numberOfCoordinates; i$2 += 1) {
            flag = p.parseByte();
            flags.push(flag);
            // If bit 3 is set, we repeat this flag n times, where n is the next byte.
            if ((flag & 8) > 0) {
                var repeatCount = p.parseByte();
                for (var j = 0; j < repeatCount; j += 1) {
                    flags.push(flag);
                    i$2 += 1;
                }
            }
        }

        check.argument(flags.length === numberOfCoordinates, 'Bad flags.');

        if (endPointIndices.length > 0) {
            var points = [];
            var point;
            // X/Y coordinates are relative to the previous point, except for the first point which is relative to 0,0.
            if (numberOfCoordinates > 0) {
                for (var i$3 = 0; i$3 < numberOfCoordinates; i$3 += 1) {
                    flag = flags[i$3];
                    point = {};
                    point.onCurve = !!(flag & 1);
                    point.lastPointOfContour = endPointIndices.indexOf(i$3) >= 0;
                    points.push(point);
                }

                var px = 0;
                for (var i$4 = 0; i$4 < numberOfCoordinates; i$4 += 1) {
                    flag = flags[i$4];
                    point = points[i$4];
                    point.x = parseGlyphCoordinate(p, flag, px, 2, 16);
                    px = point.x;
                }

                var py = 0;
                for (var i$5 = 0; i$5 < numberOfCoordinates; i$5 += 1) {
                    flag = flags[i$5];
                    point = points[i$5];
                    point.y = parseGlyphCoordinate(p, flag, py, 4, 32);
                    py = point.y;
                }
            }

            glyph.points = points;
        } else {
            glyph.points = [];
        }
    } else if (glyph.numberOfContours === 0) {
        glyph.points = [];
    } else {
        glyph.isComposite = true;
        glyph.points = [];
        glyph.components = [];
        var moreComponents = true;
        while (moreComponents) {
            flags = p.parseUShort();
            var component = {
                glyphIndex: p.parseUShort(),
                xScale: 1,
                scale01: 0,
                scale10: 0,
                yScale: 1,
                dx: 0,
                dy: 0
            };
            if ((flags & 1) > 0) {
                // The arguments are words
                if ((flags & 2) > 0) {
                    // values are offset
                    component.dx = p.parseShort();
                    component.dy = p.parseShort();
                } else {
                    // values are matched points
                    component.matchedPoints = [p.parseUShort(), p.parseUShort()];
                }

            } else {
                // The arguments are bytes
                if ((flags & 2) > 0) {
                    // values are offset
                    component.dx = p.parseChar();
                    component.dy = p.parseChar();
                } else {
                    // values are matched points
                    component.matchedPoints = [p.parseByte(), p.parseByte()];
                }
            }

            if ((flags & 8) > 0) {
                // We have a scale
                component.xScale = component.yScale = p.parseF2Dot14();
            } else if ((flags & 64) > 0) {
                // We have an X / Y scale
                component.xScale = p.parseF2Dot14();
                component.yScale = p.parseF2Dot14();
            } else if ((flags & 128) > 0) {
                // We have a 2x2 transformation
                component.xScale = p.parseF2Dot14();
                component.scale01 = p.parseF2Dot14();
                component.scale10 = p.parseF2Dot14();
                component.yScale = p.parseF2Dot14();
            }

            glyph.components.push(component);
            moreComponents = !!(flags & 32);
        }
        if (flags & 0x100) {
            // We have instructions
            glyph.instructionLength = p.parseUShort();
            glyph.instructions = [];
            for (var i$6 = 0; i$6 < glyph.instructionLength; i$6 += 1) {
                glyph.instructions.push(p.parseByte());
            }
        }
    }
}
```
</details>

### `transformPoints(points: any, transform: any): { x: any; y: any; onCurve: any; lastPointOfContour: any; }[]`

**Parameters:**

- **`points`** `any`
- **`transform`** `any`

**Returns:** `{ x: any; y: any; onCurve: any; lastPointOfContour: any; }[]`

**Calls:**

- `newPoints.push`

<details><summary>Code</summary>

```typescript
function transformPoints(points, transform) {
    var newPoints = [];
    for (var i = 0; i < points.length; i += 1) {
        var pt = points[i];
        var newPt = {
            x: transform.xScale * pt.x + transform.scale01 * pt.y + transform.dx,
            y: transform.scale10 * pt.x + transform.yScale * pt.y + transform.dy,
            onCurve: pt.onCurve,
            lastPointOfContour: pt.lastPointOfContour
        };
        newPoints.push(newPt);
    }

    return newPoints;
}
```
</details>

### `getContours(points: any): any[][]`

**Parameters:**

- **`points`** `any`

**Returns:** `any[][]`

**Calls:**

- `currentContour.push`
- `contours.push`
- `check.argument`

<details><summary>Code</summary>

```typescript
function getContours(points) {
    var contours = [];
    var currentContour = [];
    for (var i = 0; i < points.length; i += 1) {
        var pt = points[i];
        currentContour.push(pt);
        if (pt.lastPointOfContour) {
            contours.push(currentContour);
            currentContour = [];
        }
    }

    check.argument(currentContour.length === 0, 'There are still points left in the current contour.');
    return contours;
}
```
</details>

### `getPath(points: any): Path`

**Parameters:**

- **`points`** `any`

**Returns:** `Path`

**Calls:**

- `getContours`
- `p.moveTo`
- `p.lineTo`
- `p.quadraticCurveTo`
- `p.closePath`

**Internal Comments:**
```
// If both first and last points are off-curve, start at their middle. (x2)
// This is a straight line. (x4)
```

<details><summary>Code</summary>

```typescript
function getPath(points) {
    var p = new Path();
    if (!points) {
        return p;
    }

    var contours = getContours(points);

    for (var contourIndex = 0; contourIndex < contours.length; ++contourIndex) {
        var contour = contours[contourIndex];

        var prev = null;
        var curr = contour[contour.length - 1];
        var next = contour[0];

        if (curr.onCurve) {
            p.moveTo(curr.x, curr.y);
        } else {
            if (next.onCurve) {
                p.moveTo(next.x, next.y);
            } else {
                // If both first and last points are off-curve, start at their middle.
                var start = {x: (curr.x + next.x) * 0.5, y: (curr.y + next.y) * 0.5};
                p.moveTo(start.x, start.y);
            }
        }

        for (var i = 0; i < contour.length; ++i) {
            prev = curr;
            curr = next;
            next = contour[(i + 1) % contour.length];

            if (curr.onCurve) {
                // This is a straight line.
                p.lineTo(curr.x, curr.y);
            } else {
                var prev2 = prev;
                var next2 = next;

                if (!prev.onCurve) {
                    prev2 = { x: (curr.x + prev.x) * 0.5, y: (curr.y + prev.y) * 0.5 };
                }

                if (!next.onCurve) {
                    next2 = { x: (curr.x + next.x) * 0.5, y: (curr.y + next.y) * 0.5 };
                }

                p.quadraticCurveTo(curr.x, curr.y, next2.x, next2.y);
            }
        }

        p.closePath();
    }
    return p;
}
```
</details>

### `buildPath(glyphs: any, glyph: any): Path`

**Parameters:**

- **`glyphs`** `any`
- **`glyph`** `any`

**Returns:** `Path`

**Calls:**

- `glyphs.get`
- `componentGlyph.getPath`
- `transformPoints`
- `Error`
- `glyph.points.concat`
- `getPath`

**Internal Comments:**
```
// Force the ttfGlyphLoader to parse the glyph. (x4)
// component positioned by offset (x3)
// component positioned by matched points
```

<details><summary>Code</summary>

```typescript
function buildPath(glyphs, glyph) {
    if (glyph.isComposite) {
        for (var j = 0; j < glyph.components.length; j += 1) {
            var component = glyph.components[j];
            var componentGlyph = glyphs.get(component.glyphIndex);
            // Force the ttfGlyphLoader to parse the glyph.
            componentGlyph.getPath();
            if (componentGlyph.points) {
                var transformedPoints = (void 0);
                if (component.matchedPoints === undefined) {
                    // component positioned by offset
                    transformedPoints = transformPoints(componentGlyph.points, component);
                } else {
                    // component positioned by matched points
                    if ((component.matchedPoints[0] > glyph.points.length - 1) ||
                        (component.matchedPoints[1] > componentGlyph.points.length - 1)) {
                        throw Error('Matched points out of range in ' + glyph.name);
                    }
                    var firstPt = glyph.points[component.matchedPoints[0]];
                    var secondPt = componentGlyph.points[component.matchedPoints[1]];
                    var transform = {
                        xScale: component.xScale, scale01: component.scale01,
                        scale10: component.scale10, yScale: component.yScale,
                        dx: 0, dy: 0
                    };
                    secondPt = transformPoints([secondPt], transform)[0];
                    transform.dx = firstPt.x - secondPt.x;
                    transform.dy = firstPt.y - secondPt.y;
                    transformedPoints = transformPoints(componentGlyph.points, transform);
                }
                glyph.points = glyph.points.concat(transformedPoints);
            }
        }
    }

    return getPath(glyph.points);
}
```
</details>

### `parseGlyfTableAll(data: any, start: any, loca: any, font: any): GlyphSet`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`loca`** `any`
- **`font`** `any`

**Returns:** `GlyphSet`

**Calls:**

- `glyphs.push`
- `glyphset.ttfGlyphLoader`
- `glyphset.glyphLoader`

**Internal Comments:**
```
// The last element of the loca table is invalid.
```

<details><summary>Code</summary>

```typescript
function parseGlyfTableAll(data, start, loca, font) {
    var glyphs = new glyphset.GlyphSet(font);

    // The last element of the loca table is invalid.
    for (var i = 0; i < loca.length - 1; i += 1) {
        var offset = loca[i];
        var nextOffset = loca[i + 1];
        if (offset !== nextOffset) {
            glyphs.push(i, glyphset.ttfGlyphLoader(font, i, parseGlyph, data, start + offset, buildPath));
        } else {
            glyphs.push(i, glyphset.glyphLoader(font, i));
        }
    }

    return glyphs;
}
```
</details>

### `parseGlyfTableOnLowMemory(data: any, start: any, loca: any, font: any): GlyphSet`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`loca`** `any`
- **`font`** `any`

**Returns:** `GlyphSet`

**Calls:**

- `glyphs.push`
- `glyphset.ttfGlyphLoader`
- `glyphset.glyphLoader`

<details><summary>Code</summary>

```typescript
function parseGlyfTableOnLowMemory(data, start, loca, font) {
    var glyphs = new glyphset.GlyphSet(font);

    font._push = function(i) {
        var offset = loca[i];
        var nextOffset = loca[i + 1];
        if (offset !== nextOffset) {
            glyphs.push(i, glyphset.ttfGlyphLoader(font, i, parseGlyph, data, start + offset, buildPath));
        } else {
            glyphs.push(i, glyphset.glyphLoader(font, i));
        }
    };

    return glyphs;
}
```
</details>

### `parseGlyfTable(data: any, start: any, loca: any, font: any, opt: any): GlyphSet`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`loca`** `any`
- **`font`** `any`
- **`opt`** `any`

**Returns:** `GlyphSet`

**Calls:**

- `parseGlyfTableOnLowMemory`
- `parseGlyfTableAll`

<details><summary>Code</summary>

```typescript
function parseGlyfTable(data, start, loca, font, opt) {
    if (opt.lowMemory)
        { return parseGlyfTableOnLowMemory(data, start, loca, font); }
    else
        { return parseGlyfTableAll(data, start, loca, font); }
}
```
</details>

### `Hinting(font: any): void`

**Parameters:**

- **`font`** `any`

**Returns:** `void`

**Calls:**

- `glyf.getPath`

**Internal Comments:**
```
// the font this hinting object is for (x4)
// cached states (x4)
// errorState (x4)
// 0 ... all okay (x4)
// 1 ... had an error in a glyf, (x4)
//       continue working but stop spamming (x4)
//       the console (x4)
// 2 ... error at prep, stop hinting at this ppem (x4)
// 3 ... error at fpeg, stop hinting for this font at all (x4)
```

<details><summary>Code</summary>

```typescript
function Hinting(font) {
    // the font this hinting object is for
    this.font = font;

    this.getCommands = function (hPoints) {
        return glyf.getPath(hPoints).commands;
    };

    // cached states
    this._fpgmState  =
    this._prepState  =
        undefined;

    // errorState
    // 0 ... all okay
    // 1 ... had an error in a glyf,
    //       continue working but stop spamming
    //       the console
    // 2 ... error at prep, stop hinting at this ppem
    // 3 ... error at fpeg, stop hinting for this font at all
    this._errorState = 0;
}
```
</details>

### `roundOff(v: any): any`

**Parameters:**

- **`v`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function roundOff(v) {
    return v;
}
```
</details>

### `roundToGrid(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.sign`
- `Math.round`
- `Math.abs`

**Internal Comments:**
```
//Rounding in TT is supposed to "symmetrical around zero"
```

<details><summary>Code</summary>

```typescript
function roundToGrid(v) {
    //Rounding in TT is supposed to "symmetrical around zero"
    return Math.sign(v) * Math.round(Math.abs(v));
}
```
</details>

### `roundToDoubleGrid(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.sign`
- `Math.round`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function roundToDoubleGrid(v) {
    return Math.sign(v) * Math.round(Math.abs(v * 2)) / 2;
}
```
</details>

### `roundToHalfGrid(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.sign`
- `Math.round`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function roundToHalfGrid(v) {
    return Math.sign(v) * (Math.round(Math.abs(v) + 0.5) - 0.5);
}
```
</details>

### `roundUpToGrid(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.sign`
- `Math.ceil`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function roundUpToGrid(v) {
    return Math.sign(v) * Math.ceil(Math.abs(v));
}
```
</details>

### `roundDownToGrid(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.sign`
- `Math.floor`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function roundDownToGrid(v) {
    return Math.sign(v) * Math.floor(Math.abs(v));
}
```
</details>

### `roundSuper(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.trunc`

**Internal Comments:**
```
// according to http://xgridfit.sourceforge.net/round.html
```

<details><summary>Code</summary>

```typescript
function (v) {
    var period = this.srPeriod;
    var phase = this.srPhase;
    var threshold = this.srThreshold;
    var sign = 1;

    if (v < 0) {
        v = -v;
        sign = -1;
    }

    v += threshold - phase;

    v = Math.trunc(v / period) * period;

    v += phase;

    // according to http://xgridfit.sourceforge.net/round.html
    if (v < 0) { return phase * sign; }

    return v * sign;
}
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.xo : p1.x) - (o2 ? p2.xo : p2.x);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `xUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.xo - rp1.xo;
            do2 = p.xo - rp2.xo;
            dm1 = rp1.x - rp1.xo;
            dm2 = rp2.x - rp2.xo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.x = p.xo + (dm1 + dm2) / 2;
                return;
            }

            p.x = p.xo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            xUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        xUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.x = (org ? rp.xo : rp.x) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.x = rpdx + (p.y - rpdy) / pv.normalSlope;
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.xTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.xo : p1.x) - (o2 ? p2.xo : p2.x);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `xUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.xo - rp1.xo;
            do2 = p.xo - rp2.xo;
            dm1 = rp1.x - rp1.xo;
            dm2 = rp2.x - rp2.xo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.x = p.xo + (dm1 + dm2) / 2;
                return;
            }

            p.x = p.xo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            xUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        xUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.x = (org ? rp.xo : rp.x) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.x = rpdx + (p.y - rpdy) / pv.normalSlope;
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.xTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.xo : p1.x) - (o2 ? p2.xo : p2.x);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `xUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.xo - rp1.xo;
            do2 = p.xo - rp2.xo;
            dm1 = rp1.x - rp1.xo;
            dm2 = rp2.x - rp2.xo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.x = p.xo + (dm1 + dm2) / 2;
                return;
            }

            p.x = p.xo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            xUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        xUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.x = (org ? rp.xo : rp.x) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.x = rpdx + (p.y - rpdy) / pv.normalSlope;
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.xTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.xo : p1.x) - (o2 ? p2.xo : p2.x);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `xUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.xo - rp1.xo;
            do2 = p.xo - rp2.xo;
            dm1 = rp1.x - rp1.xo;
            dm2 = rp2.x - rp2.xo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.x = p.xo + (dm1 + dm2) / 2;
                return;
            }

            p.x = p.xo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            xUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        xUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.x = (org ? rp.xo : rp.x) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.x = rpdx + (p.y - rpdy) / pv.normalSlope;
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.xTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.xo : p1.x) - (o2 ? p2.xo : p2.x);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `xUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.xo - rp1.xo;
            do2 = p.xo - rp2.xo;
            dm1 = rp1.x - rp1.xo;
            dm2 = rp2.x - rp2.xo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.x = p.xo + (dm1 + dm2) / 2;
                return;
            }

            p.x = p.xo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            xUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        xUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.x = (org ? rp.xo : rp.x) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.x = rpdx + (p.y - rpdy) / pv.normalSlope;
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.xTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.xo : p1.x) - (o2 ? p2.xo : p2.x);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `xUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.xo - rp1.xo;
            do2 = p.xo - rp2.xo;
            dm1 = rp1.x - rp1.xo;
            dm2 = rp2.x - rp2.xo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.x = p.xo + (dm1 + dm2) / 2;
                return;
            }

            p.x = p.xo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            xUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        xUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.x = (org ? rp.xo : rp.x) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.x = rpdx + (p.y - rpdy) / pv.normalSlope;
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.xTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.xTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.yo : p1.y) - (o2 ? p2.yo : p2.y);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `yUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.yo - rp1.yo;
            do2 = p.yo - rp2.yo;
            dm1 = rp1.y - rp1.yo;
            dm2 = rp2.y - rp2.yo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.y = p.yo + (dm1 + dm2) / 2;
                return;
            }

            p.y = p.yo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            yUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        yUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.y = (org ? rp.yo : rp.y) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.y = rpdy + pv.normalSlope * (p.x - rpdx);
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.yTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.yo : p1.y) - (o2 ? p2.yo : p2.y);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `yUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.yo - rp1.yo;
            do2 = p.yo - rp2.yo;
            dm1 = rp1.y - rp1.yo;
            dm2 = rp2.y - rp2.yo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.y = p.yo + (dm1 + dm2) / 2;
                return;
            }

            p.y = p.yo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            yUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        yUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.y = (org ? rp.yo : rp.y) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.y = rpdy + pv.normalSlope * (p.x - rpdx);
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.yTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.yo : p1.y) - (o2 ? p2.yo : p2.y);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `yUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.yo - rp1.yo;
            do2 = p.yo - rp2.yo;
            dm1 = rp1.y - rp1.yo;
            dm2 = rp2.y - rp2.yo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.y = p.yo + (dm1 + dm2) / 2;
                return;
            }

            p.y = p.yo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            yUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        yUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.y = (org ? rp.yo : rp.y) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.y = rpdy + pv.normalSlope * (p.x - rpdx);
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.yTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.yo : p1.y) - (o2 ? p2.yo : p2.y);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `yUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.yo - rp1.yo;
            do2 = p.yo - rp2.yo;
            dm1 = rp1.y - rp1.yo;
            dm2 = rp2.y - rp2.yo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.y = p.yo + (dm1 + dm2) / 2;
                return;
            }

            p.y = p.yo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            yUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        yUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.y = (org ? rp.yo : rp.y) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.y = rpdy + pv.normalSlope * (p.x - rpdx);
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.yTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.yo : p1.y) - (o2 ? p2.yo : p2.y);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `yUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.yo - rp1.yo;
            do2 = p.yo - rp2.yo;
            dm1 = rp1.y - rp1.yo;
            dm2 = rp2.y - rp2.yo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.y = p.yo + (dm1 + dm2) / 2;
                return;
            }

            p.y = p.yo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            yUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        yUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.y = (org ? rp.yo : rp.y) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.y = rpdy + pv.normalSlope * (p.x - rpdx);
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.yTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = false;
    }
```
</details>

### `distance(p1: any, p2: any, o1: any, o2: any): number`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`o1`** `any`
- **`o2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p1, p2, o1, o2) {
        return (o1 ? p1.yo : p1.y) - (o2 ? p2.yo : p2.y);
    }
```
</details>

### `interpolate(p: any, rp1: any, rp2: any, pv: any): void`

**Parameters:**

- **`p`** `any`
- **`rp1`** `any`
- **`rp2`** `any`
- **`pv`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `pv.distance`
- `yUnitVector.setRelative`

<details><summary>Code</summary>

```typescript
function (p, rp1, rp2, pv) {
        var do1;
        var do2;
        var doa1;
        var doa2;
        var dm1;
        var dm2;
        var dt;

        if (!pv || pv === this) {
            do1 = p.yo - rp1.yo;
            do2 = p.yo - rp2.yo;
            dm1 = rp1.y - rp1.yo;
            dm2 = rp2.y - rp2.yo;
            doa1 = Math.abs(do1);
            doa2 = Math.abs(do2);
            dt = doa1 + doa2;

            if (dt === 0) {
                p.y = p.yo + (dm1 + dm2) / 2;
                return;
            }

            p.y = p.yo + (dm1 * doa2 + dm2 * doa1) / dt;
            return;
        }

        do1 = pv.distance(p, rp1, true, true);
        do2 = pv.distance(p, rp2, true, true);
        dm1 = pv.distance(rp1, rp1, false, true);
        dm2 = pv.distance(rp2, rp2, false, true);
        doa1 = Math.abs(do1);
        doa2 = Math.abs(do2);
        dt = doa1 + doa2;

        if (dt === 0) {
            yUnitVector.setRelative(p, p, (dm1 + dm2) / 2, pv, true);
            return;
        }

        yUnitVector.setRelative(p, p, (dm1 * doa2 + dm2 * doa1) / dt, pv, true);
    }
```
</details>

### `setRelative(p: any, rp: any, d: any, pv: any, org: any): void`

**Parameters:**

- **`p`** `any`
- **`rp`** `any`
- **`d`** `any`
- **`pv`** `any`
- **`org`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p, rp, d, pv, org) {
        if (!pv || pv === this) {
            p.y = (org ? rp.yo : rp.y) + d;
            return;
        }

        var rpx = org ? rp.xo : rp.x;
        var rpy = org ? rp.yo : rp.y;
        var rpdx = rpx + d * pv.x;
        var rpdy = rpy + d * pv.y;

        p.y = rpdy + pv.normalSlope * (p.x - rpdx);
    }
```
</details>

### `touch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = true;
    }
```
</details>

### `touched(p: any): any`

**Parameters:**

- **`p`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p) {
        return p.yTouched;
    }
```
</details>

### `untouch(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (p) {
        p.yTouched = false;
    }
```
</details>

### `UnitVector(x: any, y: any): void`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `void`

**Calls:**

- `Object.freeze`

<details><summary>Code</summary>

```typescript
function UnitVector(x, y) {
    this.x = x;
    this.y = y;
    this.axis = undefined;
    this.slope = y / x;
    this.normalSlope = -x / y;
    Object.freeze(this);
}
```
</details>

### `getUnitVector(x: any, y: any): UnitVector`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `UnitVector`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function getUnitVector(x, y) {
    var d = Math.sqrt(x * x + y * y);

    x /= d;
    y /= d;

    if (x === 1 && y === 0) { return xUnitVector; }
    else if (x === 0 && y === 1) { return yUnitVector; }
    else { return new UnitVector(x, y); }
}
```
</details>

### `HPoint(x: any, y: any, lastPointOfContour: any, onCurve: any): void`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`lastPointOfContour`** `any`
- **`onCurve`** `any`

**Returns:** `void`

**Calls:**

- `Math.round`
- `Object.preventExtensions`

<details><summary>Code</summary>

```typescript
function HPoint(
    x,
    y,
    lastPointOfContour,
    onCurve
) {
    this.x = this.xo = Math.round(x * 64) / 64; // hinted x value and original x-value
    this.y = this.yo = Math.round(y * 64) / 64; // hinted y value and original y-value

    this.lastPointOfContour = lastPointOfContour;
    this.onCurve = onCurve;
    this.prevPointOnContour = undefined;
    this.nextPointOnContour = undefined;
    this.xTouched = false;
    this.yTouched = false;

    Object.preventExtensions(this);
}
```
</details>

### `State(env: any, prog: any): void`

**Parameters:**

- **`env`** `any`
- **`prog`** `any`

**Returns:** `void`

**Internal Comments:**
```
/* fall through */
```

<details><summary>Code</summary>

```typescript
function State(env, prog) {
    this.env = env;
    this.stack = [];
    this.prog = prog;

    switch (env) {
        case 'glyf' :
            this.zp0 = this.zp1 = this.zp2 = 1;
            this.rp0 = this.rp1 = this.rp2 = 0;
            /* fall through */
        case 'prep' :
            this.fv = this.pv = this.dpv = xUnitVector;
            this.round = roundToGrid;
    }
}
```
</details>

### `initTZone(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Internal Comments:**
```
// no idea if this is actually correct...
```

<details><summary>Code</summary>

```typescript
function initTZone(state)
{
    var tZone = state.tZone = new Array(state.gZone.length);

    // no idea if this is actually correct...
    for (var i = 0; i < tZone.length; i++)
    {
        tZone[i] = new HPoint(0, 0);
    }
}
```
</details>

### `skip(state: any, handleElse: any): void`

**Parameters:**

- **`state`** `any`
- **`handleElse`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function skip(state, handleElse)
{
    var prog = state.prog;
    var ip = state.ip;
    var nesting = 1;
    var ins;

    do {
        ins = prog[++ip];
        if (ins === 0x58) // IF
            { nesting++; }
        else if (ins === 0x59) // EIF
            { nesting--; }
        else if (ins === 0x40) // NPUSHB
            { ip += prog[ip + 1] + 1; }
        else if (ins === 0x41) // NPUSHW
            { ip += 2 * prog[ip + 1] + 1; }
        else if (ins >= 0xB0 && ins <= 0xB7) // PUSHB
            { ip += ins - 0xB0 + 1; }
        else if (ins >= 0xB8 && ins <= 0xBF) // PUSHW
            { ip += (ins - 0xB8 + 1) * 2; }
        else if (handleElse && nesting === 1 && ins === 0x1B) // ELSE
            { break; }
    } while (nesting > 0);

    state.ip = ip;
}
```
</details>

### `SVTCA(v: any, state: any): void`

**Parameters:**

- **`v`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function SVTCA(v, state) {
    if (exports.DEBUG) { console.log(state.step, 'SVTCA[' + v.axis + ']'); }

    state.fv = state.pv = state.dpv = v;
}
```
</details>

### `SPVTCA(v: any, state: any): void`

**Parameters:**

- **`v`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function SPVTCA(v, state) {
    if (exports.DEBUG) { console.log(state.step, 'SPVTCA[' + v.axis + ']'); }

    state.pv = state.dpv = v;
}
```
</details>

### `SFVTCA(v: any, state: any): void`

**Parameters:**

- **`v`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function SFVTCA(v, state) {
    if (exports.DEBUG) { console.log(state.step, 'SFVTCA[' + v.axis + ']'); }

    state.fv = v;
}
```
</details>

### `SPVTL(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `getUnitVector`

<details><summary>Code</summary>

```typescript
function SPVTL(a, state) {
    var stack = state.stack;
    var p2i = stack.pop();
    var p1i = stack.pop();
    var p2 = state.z2[p2i];
    var p1 = state.z1[p1i];

    if (exports.DEBUG) { console.log('SPVTL[' + a + ']', p2i, p1i); }

    var dx;
    var dy;

    if (!a) {
        dx = p1.x - p2.x;
        dy = p1.y - p2.y;
    } else {
        dx = p2.y - p1.y;
        dy = p1.x - p2.x;
    }

    state.pv = state.dpv = getUnitVector(dx, dy);
}
```
</details>

### `SFVTL(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `getUnitVector`

<details><summary>Code</summary>

```typescript
function SFVTL(a, state) {
    var stack = state.stack;
    var p2i = stack.pop();
    var p1i = stack.pop();
    var p2 = state.z2[p2i];
    var p1 = state.z1[p1i];

    if (exports.DEBUG) { console.log('SFVTL[' + a + ']', p2i, p1i); }

    var dx;
    var dy;

    if (!a) {
        dx = p1.x - p2.x;
        dy = p1.y - p2.y;
    } else {
        dx = p2.y - p1.y;
        dy = p1.x - p2.x;
    }

    state.fv = getUnitVector(dx, dy);
}
```
</details>

### `SPVFS(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `getUnitVector`

<details><summary>Code</summary>

```typescript
function SPVFS(state) {
    var stack = state.stack;
    var y = stack.pop();
    var x = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SPVFS[]', y, x); }

    state.pv = state.dpv = getUnitVector(x, y);
}
```
</details>

### `SFVFS(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `getUnitVector`

<details><summary>Code</summary>

```typescript
function SFVFS(state) {
    var stack = state.stack;
    var y = stack.pop();
    var x = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SPVFS[]', y, x); }

    state.fv = getUnitVector(x, y);
}
```
</details>

### `GPV(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function GPV(state) {
    var stack = state.stack;
    var pv = state.pv;

    if (exports.DEBUG) { console.log(state.step, 'GPV[]'); }

    stack.push(pv.x * 0x4000);
    stack.push(pv.y * 0x4000);
}
```
</details>

### `GFV(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function GFV(state) {
    var stack = state.stack;
    var fv = state.fv;

    if (exports.DEBUG) { console.log(state.step, 'GFV[]'); }

    stack.push(fv.x * 0x4000);
    stack.push(fv.y * 0x4000);
}
```
</details>

### `SFVTPV(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function SFVTPV(state) {
    state.fv = state.pv;

    if (exports.DEBUG) { console.log(state.step, 'SFVTPV[]'); }
}
```
</details>

### `ISECT(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`

**Internal Comments:**
```
// math from (x2)
// en.wikipedia.org/wiki/Line%E2%80%93line_intersection#Given_two_points_on_each_line (x2)
```

<details><summary>Code</summary>

```typescript
function ISECT(state)
{
    var stack = state.stack;
    var pa0i = stack.pop();
    var pa1i = stack.pop();
    var pb0i = stack.pop();
    var pb1i = stack.pop();
    var pi = stack.pop();
    var z0 = state.z0;
    var z1 = state.z1;
    var pa0 = z0[pa0i];
    var pa1 = z0[pa1i];
    var pb0 = z1[pb0i];
    var pb1 = z1[pb1i];
    var p = state.z2[pi];

    if (exports.DEBUG) { console.log('ISECT[], ', pa0i, pa1i, pb0i, pb1i, pi); }

    // math from
    // en.wikipedia.org/wiki/Line%E2%80%93line_intersection#Given_two_points_on_each_line

    var x1 = pa0.x;
    var y1 = pa0.y;
    var x2 = pa1.x;
    var y2 = pa1.y;
    var x3 = pb0.x;
    var y3 = pb0.y;
    var x4 = pb1.x;
    var y4 = pb1.y;

    var div = (x1 - x2) * (y3 - y4) - (y1 - y2) * (x3 - x4);
    var f1 = x1 * y2 - y1 * x2;
    var f2 = x3 * y4 - y3 * x4;

    p.x = (f1 * (x3 - x4) - f2 * (x1 - x2)) / div;
    p.y = (f1 * (y3 - y4) - f2 * (y1 - y2)) / div;
}
```
</details>

### `SRP0(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SRP0(state) {
    state.rp0 = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SRP0[]', state.rp0); }
}
```
</details>

### `SRP1(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SRP1(state) {
    state.rp1 = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SRP1[]', state.rp1); }
}
```
</details>

### `SRP2(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SRP2(state) {
    state.rp2 = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SRP2[]', state.rp2); }
}
```
</details>

### `SZP0(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `initTZone`

<details><summary>Code</summary>

```typescript
function SZP0(state) {
    var n = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SZP0[]', n); }

    state.zp0 = n;

    switch (n) {
        case 0:
            if (!state.tZone) { initTZone(state); }
            state.z0 = state.tZone;
            break;
        case 1 :
            state.z0 = state.gZone;
            break;
        default :
            throw new Error('Invalid zone pointer');
    }
}
```
</details>

### `SZP1(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `initTZone`

<details><summary>Code</summary>

```typescript
function SZP1(state) {
    var n = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SZP1[]', n); }

    state.zp1 = n;

    switch (n) {
        case 0:
            if (!state.tZone) { initTZone(state); }
            state.z1 = state.tZone;
            break;
        case 1 :
            state.z1 = state.gZone;
            break;
        default :
            throw new Error('Invalid zone pointer');
    }
}
```
</details>

### `SZP2(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `initTZone`

<details><summary>Code</summary>

```typescript
function SZP2(state) {
    var n = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SZP2[]', n); }

    state.zp2 = n;

    switch (n) {
        case 0:
            if (!state.tZone) { initTZone(state); }
            state.z2 = state.tZone;
            break;
        case 1 :
            state.z2 = state.gZone;
            break;
        default :
            throw new Error('Invalid zone pointer');
    }
}
```
</details>

### `SZPS(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `initTZone`

<details><summary>Code</summary>

```typescript
function SZPS(state) {
    var n = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SZPS[]', n); }

    state.zp0 = state.zp1 = state.zp2 = n;

    switch (n) {
        case 0:
            if (!state.tZone) { initTZone(state); }
            state.z0 = state.z1 = state.z2 = state.tZone;
            break;
        case 1 :
            state.z0 = state.z1 = state.z2 = state.gZone;
            break;
        default :
            throw new Error('Invalid zone pointer');
    }
}
```
</details>

### `SLOOP(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SLOOP(state) {
    state.loop = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SLOOP[]', state.loop); }
}
```
</details>

### `RTG(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function RTG(state) {
    if (exports.DEBUG) { console.log(state.step, 'RTG[]'); }

    state.round = roundToGrid;
}
```
</details>

### `RTHG(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function RTHG(state) {
    if (exports.DEBUG) { console.log(state.step, 'RTHG[]'); }

    state.round = roundToHalfGrid;
}
```
</details>

### `SMD(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SMD(state) {
    var d = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SMD[]', d); }

    state.minDis = d / 0x40;
}
```
</details>

### `ELSE(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `skip`

**Internal Comments:**
```
// This instruction has been reached by executing a then branch
// so it just skips ahead until matching EIF.
//
// In case the IF was negative the IF[] instruction already
// skipped forward over the ELSE[]
```

<details><summary>Code</summary>

```typescript
function ELSE(state) {
    // This instruction has been reached by executing a then branch
    // so it just skips ahead until matching EIF.
    //
    // In case the IF was negative the IF[] instruction already
    // skipped forward over the ELSE[]

    if (exports.DEBUG) { console.log(state.step, 'ELSE[]'); }

    skip(state, false);
}
```
</details>

### `JMPR(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

**Internal Comments:**
```
// A jump by 1 would do nothing. (x4)
```

<details><summary>Code</summary>

```typescript
function JMPR(state) {
    var o = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'JMPR[]', o); }

    // A jump by 1 would do nothing.
    state.ip += o - 1;
}
```
</details>

### `SCVTCI(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SCVTCI(state) {
    var n = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SCVTCI[]', n); }

    state.cvCutIn = n / 0x40;
}
```
</details>

### `DUP(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function DUP(state) {
    var stack = state.stack;

    if (exports.DEBUG) { console.log(state.step, 'DUP[]'); }

    stack.push(stack[stack.length - 1]);
}
```
</details>

### `POP(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `state.stack.pop`

<details><summary>Code</summary>

```typescript
function POP(state) {
    if (exports.DEBUG) { console.log(state.step, 'POP[]'); }

    state.stack.pop();
}
```
</details>

### `CLEAR(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function CLEAR(state) {
    if (exports.DEBUG) { console.log(state.step, 'CLEAR[]'); }

    state.stack.length = 0;
}
```
</details>

### `SWAP(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function SWAP(state) {
    var stack = state.stack;

    var a = stack.pop();
    var b = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SWAP[]'); }

    stack.push(a);
    stack.push(b);
}
```
</details>

### `DEPTH(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function DEPTH(state) {
    var stack = state.stack;

    if (exports.DEBUG) { console.log(state.step, 'DEPTH[]'); }

    stack.push(stack.length);
}
```
</details>

### `LOOPCALL(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `exec`

**Internal Comments:**
```
// saves callers program (x2)
// executes the function
// restores the callers program (x4)
```

<details><summary>Code</summary>

```typescript
function LOOPCALL(state) {
    var stack = state.stack;
    var fn = stack.pop();
    var c = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'LOOPCALL[]', fn, c); }

    // saves callers program
    var cip = state.ip;
    var cprog = state.prog;

    state.prog = state.funcs[fn];

    // executes the function
    for (var i = 0; i < c; i++) {
        exec(state);

        if (exports.DEBUG) { console.log(
            ++state.step,
            i + 1 < c ? 'next loopcall' : 'done loopcall',
            i
        ); }
    }

    // restores the callers program
    state.ip = cip;
    state.prog = cprog;
}
```
</details>

### `CALL(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `exec`

**Internal Comments:**
```
// saves callers program (x2)
// executes the function (x3)
// restores the callers program (x4)
```

<details><summary>Code</summary>

```typescript
function CALL(state) {
    var fn = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'CALL[]', fn); }

    // saves callers program
    var cip = state.ip;
    var cprog = state.prog;

    state.prog = state.funcs[fn];

    // executes the function
    exec(state);

    // restores the callers program
    state.ip = cip;
    state.prog = cprog;

    if (exports.DEBUG) { console.log(++state.step, 'returning from', fn); }
}
```
</details>

### `CINDEX(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

**Internal Comments:**
```
// In case of k == 1, it copies the last element after popping (x4)
// thus stack.length - k. (x4)
```

<details><summary>Code</summary>

```typescript
function CINDEX(state) {
    var stack = state.stack;
    var k = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'CINDEX[]', k); }

    // In case of k == 1, it copies the last element after popping
    // thus stack.length - k.
    stack.push(stack[stack.length - k]);
}
```
</details>

### `MINDEX(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `stack.splice`

<details><summary>Code</summary>

```typescript
function MINDEX(state) {
    var stack = state.stack;
    var k = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'MINDEX[]', k); }

    stack.push(stack.splice(stack.length - k, 1)[0]);
}
```
</details>

### `FDEF(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `prog.slice`

<details><summary>Code</summary>

```typescript
function FDEF(state) {
    if (state.env !== 'fpgm') { throw new Error('FDEF not allowed here'); }
    var stack = state.stack;
    var prog = state.prog;
    var ip = state.ip;

    var fn = stack.pop();
    var ipBegin = ip;

    if (exports.DEBUG) { console.log(state.step, 'FDEF[]', fn); }

    while (prog[++ip] !== 0x2D){ }

    state.ip = ip;
    state.funcs[fn] = prog.slice(ipBegin + 1, ip);
}
```
</details>

### `MDAP(round: any, state: any): void`

**Parameters:**

- **`round`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `pv.distance`
- `state.round`
- `fv.setRelative`
- `fv.touch`

<details><summary>Code</summary>

```typescript
function MDAP(round, state) {
    var pi = state.stack.pop();
    var p = state.z0[pi];
    var fv = state.fv;
    var pv = state.pv;

    if (exports.DEBUG) { console.log(state.step, 'MDAP[' + round + ']', pi); }

    var d = pv.distance(p, HPZero);

    if (round) { d = state.round(d); }

    fv.setRelative(p, HPZero, d, pv);
    fv.touch(p);

    state.rp0 = state.rp1 = pi;
}
```
</details>

### `IUP(v: any, state: any): void`

**Parameters:**

- **`v`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `v.touched`
- `cp.prevTouched`
- `cp.nextTouched`
- `v.setRelative`
- `v.distance`
- `v.interpolate`

**Internal Comments:**
```
// if this point has been touched go on
// no point on the contour has been touched?
// only one point on the contour has been touched (x4)
// so simply moves the point like that (x4)
```

<details><summary>Code</summary>

```typescript
function IUP(v, state) {
    var z2 = state.z2;
    var pLen = z2.length - 2;
    var cp;
    var pp;
    var np;

    if (exports.DEBUG) { console.log(state.step, 'IUP[' + v.axis + ']'); }

    for (var i = 0; i < pLen; i++) {
        cp = z2[i]; // current point

        // if this point has been touched go on
        if (v.touched(cp)) { continue; }

        pp = cp.prevTouched(v);

        // no point on the contour has been touched?
        if (pp === cp) { continue; }

        np = cp.nextTouched(v);

        if (pp === np) {
            // only one point on the contour has been touched
            // so simply moves the point like that

            v.setRelative(cp, cp, v.distance(pp, pp, false, true), v, true);
        }

        v.interpolate(cp, pp, np, v);
    }
}
```
</details>

### `SHP(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `pv.distance`
- `fv.setRelative`
- `fv.touch`
- `console.log`

<details><summary>Code</summary>

```typescript
function SHP(a, state) {
    var stack = state.stack;
    var rpi = a ? state.rp1 : state.rp2;
    var rp = (a ? state.z0 : state.z1)[rpi];
    var fv = state.fv;
    var pv = state.pv;
    var loop = state.loop;
    var z2 = state.z2;

    while (loop--)
    {
        var pi = stack.pop();
        var p = z2[pi];

        var d = pv.distance(rp, rp, false, true);
        fv.setRelative(p, p, d, pv);
        fv.touch(p);

        if (exports.DEBUG) {
            console.log(
                state.step,
                (state.loop > 1 ?
                   'loop ' + (state.loop - loop) + ': ' :
                   ''
                ) +
                'SHP[' + (a ? 'rp1' : 'rp2') + ']', pi
            );
        }
    }

    state.loop = 1;
}
```
</details>

### `SHC(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `pv.distance`
- `fv.setRelative`

<details><summary>Code</summary>

```typescript
function SHC(a, state) {
    var stack = state.stack;
    var rpi = a ? state.rp1 : state.rp2;
    var rp = (a ? state.z0 : state.z1)[rpi];
    var fv = state.fv;
    var pv = state.pv;
    var ci = stack.pop();
    var sp = state.z2[state.contours[ci]];
    var p = sp;

    if (exports.DEBUG) { console.log(state.step, 'SHC[' + a + ']', ci); }

    var d = pv.distance(rp, rp, false, true);

    do {
        if (p !== rp) { fv.setRelative(p, p, d, pv); }
        p = p.nextPointOnContour;
    } while (p !== sp);
}
```
</details>

### `SHZ(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `pv.distance`
- `fv.setRelative`

<details><summary>Code</summary>

```typescript
function SHZ(a, state) {
    var stack = state.stack;
    var rpi = a ? state.rp1 : state.rp2;
    var rp = (a ? state.z0 : state.z1)[rpi];
    var fv = state.fv;
    var pv = state.pv;

    var e = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SHZ[' + a + ']', e); }

    var z;
    switch (e) {
        case 0 : z = state.tZone; break;
        case 1 : z = state.gZone; break;
        default : throw new Error('Invalid zone');
    }

    var p;
    var d = pv.distance(rp, rp, false, true);
    var pLen = z.length - 2;
    for (var i = 0; i < pLen; i++)
    {
        p = z[i];
        fv.setRelative(p, p, d, pv);
        //if (p !== rp) fv.setRelative(p, p, d, pv);
    }
}
```
</details>

### `SHPIX(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `fv.setRelative`
- `fv.touch`

<details><summary>Code</summary>

```typescript
function SHPIX(state) {
    var stack = state.stack;
    var loop = state.loop;
    var fv = state.fv;
    var d = stack.pop() / 0x40;
    var z2 = state.z2;

    while (loop--) {
        var pi = stack.pop();
        var p = z2[pi];

        if (exports.DEBUG) {
            console.log(
                state.step,
                (state.loop > 1 ? 'loop ' + (state.loop - loop) + ': ' : '') +
                'SHPIX[]', pi, d
            );
        }

        fv.setRelative(p, p, d);
        fv.touch(p);
    }

    state.loop = 1;
}
```
</details>

### `IP(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `fv.interpolate`
- `fv.touch`

<details><summary>Code</summary>

```typescript
function IP(state) {
    var stack = state.stack;
    var rp1i = state.rp1;
    var rp2i = state.rp2;
    var loop = state.loop;
    var rp1 = state.z0[rp1i];
    var rp2 = state.z1[rp2i];
    var fv = state.fv;
    var pv = state.dpv;
    var z2 = state.z2;

    while (loop--) {
        var pi = stack.pop();
        var p = z2[pi];

        if (exports.DEBUG) {
            console.log(
                state.step,
                (state.loop > 1 ? 'loop ' + (state.loop - loop) + ': ' : '') +
                'IP[]', pi, rp1i, '<->', rp2i
            );
        }

        fv.interpolate(p, rp1, rp2, pv);

        fv.touch(p);
    }

    state.loop = 1;
}
```
</details>

### `MSIRP(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `fv.setRelative`
- `fv.touch`
- `console.log`

<details><summary>Code</summary>

```typescript
function MSIRP(a, state) {
    var stack = state.stack;
    var d = stack.pop() / 64;
    var pi = stack.pop();
    var p = state.z1[pi];
    var rp0 = state.z0[state.rp0];
    var fv = state.fv;
    var pv = state.pv;

    fv.setRelative(p, rp0, d, pv);
    fv.touch(p);

    if (exports.DEBUG) { console.log(state.step, 'MSIRP[' + a + ']', d, pi); }

    state.rp1 = state.rp0;
    state.rp2 = pi;
    if (a) { state.rp0 = pi; }
}
```
</details>

### `ALIGNRP(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `fv.setRelative`
- `fv.touch`

<details><summary>Code</summary>

```typescript
function ALIGNRP(state) {
    var stack = state.stack;
    var rp0i = state.rp0;
    var rp0 = state.z0[rp0i];
    var loop = state.loop;
    var fv = state.fv;
    var pv = state.pv;
    var z1 = state.z1;

    while (loop--) {
        var pi = stack.pop();
        var p = z1[pi];

        if (exports.DEBUG) {
            console.log(
                state.step,
                (state.loop > 1 ? 'loop ' + (state.loop - loop) + ': ' : '') +
                'ALIGNRP[]', pi
            );
        }

        fv.setRelative(p, rp0, 0, pv);
        fv.touch(p);
    }

    state.loop = 1;
}
```
</details>

### `RTDG(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function RTDG(state) {
    if (exports.DEBUG) { console.log(state.step, 'RTDG[]'); }

    state.round = roundToDoubleGrid;
}
```
</details>

### `MIAP(round: any, state: any): void`

**Parameters:**

- **`round`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `pv.distance`
- `Math.abs`
- `state.round`
- `fv.setRelative`
- `fv.touch`

<details><summary>Code</summary>

```typescript
function MIAP(round, state) {
    var stack = state.stack;
    var n = stack.pop();
    var pi = stack.pop();
    var p = state.z0[pi];
    var fv = state.fv;
    var pv = state.pv;
    var cv = state.cvt[n];

    if (exports.DEBUG) {
        console.log(
            state.step,
            'MIAP[' + round + ']',
            n, '(', cv, ')', pi
        );
    }

    var d = pv.distance(p, HPZero);

    if (round) {
        if (Math.abs(d - cv) < state.cvCutIn) { d = cv; }

        d = state.round(d);
    }

    fv.setRelative(p, HPZero, d, pv);

    if (state.zp0 === 0) {
        p.xo = p.x;
        p.yo = p.y;
    }

    fv.touch(p);

    state.rp0 = state.rp1 = pi;
}
```
</details>

### `NPUSHB(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function NPUSHB(state) {
    var prog = state.prog;
    var ip = state.ip;
    var stack = state.stack;

    var n = prog[++ip];

    if (exports.DEBUG) { console.log(state.step, 'NPUSHB[]', n); }

    for (var i = 0; i < n; i++) { stack.push(prog[++ip]); }

    state.ip = ip;
}
```
</details>

### `NPUSHW(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function NPUSHW(state) {
    var ip = state.ip;
    var prog = state.prog;
    var stack = state.stack;
    var n = prog[++ip];

    if (exports.DEBUG) { console.log(state.step, 'NPUSHW[]', n); }

    for (var i = 0; i < n; i++) {
        var w = (prog[++ip] << 8) | prog[++ip];
        if (w & 0x8000) { w = -((w ^ 0xffff) + 1); }
        stack.push(w);
    }

    state.ip = ip;
}
```
</details>

### `WS(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function WS(state) {
    var stack = state.stack;
    var store = state.store;

    if (!store) { store = state.store = []; }

    var v = stack.pop();
    var l = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'WS', v, l); }

    store[l] = v;
}
```
</details>

### `RS(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function RS(state) {
    var stack = state.stack;
    var store = state.store;

    var l = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'RS', l); }

    var v = (store && store[l]) || 0;

    stack.push(v);
}
```
</details>

### `WCVTP(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function WCVTP(state) {
    var stack = state.stack;

    var v = stack.pop();
    var l = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'WCVTP', v, l); }

    state.cvt[l] = v / 0x40;
}
```
</details>

### `RCVT(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function RCVT(state) {
    var stack = state.stack;
    var cvte = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'RCVT', cvte); }

    stack.push(state.cvt[cvte] * 0x40);
}
```
</details>

### `GC(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `state.dpv.distance`

<details><summary>Code</summary>

```typescript
function GC(a, state) {
    var stack = state.stack;
    var pi = stack.pop();
    var p = state.z2[pi];

    if (exports.DEBUG) { console.log(state.step, 'GC[' + a + ']', pi); }

    stack.push(state.dpv.distance(p, HPZero, a, false) * 0x40);
}
```
</details>

### `MD(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `state.dpv.distance`
- `console.log`
- `state.stack.push`
- `Math.round`

<details><summary>Code</summary>

```typescript
function MD(a, state) {
    var stack = state.stack;
    var pi2 = stack.pop();
    var pi1 = stack.pop();
    var p2 = state.z1[pi2];
    var p1 = state.z0[pi1];
    var d = state.dpv.distance(p1, p2, a, a);

    if (exports.DEBUG) { console.log(state.step, 'MD[' + a + ']', pi2, pi1, '->', d); }

    state.stack.push(Math.round(d * 64));
}
```
</details>

### `MPPEM(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `state.stack.push`

<details><summary>Code</summary>

```typescript
function MPPEM(state) {
    if (exports.DEBUG) { console.log(state.step, 'MPPEM[]'); }
    state.stack.push(state.ppem);
}
```
</details>

### `FLIPON(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function FLIPON(state) {
    if (exports.DEBUG) { console.log(state.step, 'FLIPON[]'); }
    state.autoFlip = true;
}
```
</details>

### `LT(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function LT(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'LT[]', e2, e1); }

    stack.push(e1 < e2 ? 1 : 0);
}
```
</details>

### `LTEQ(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function LTEQ(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'LTEQ[]', e2, e1); }

    stack.push(e1 <= e2 ? 1 : 0);
}
```
</details>

### `GT(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function GT(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'GT[]', e2, e1); }

    stack.push(e1 > e2 ? 1 : 0);
}
```
</details>

### `GTEQ(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function GTEQ(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'GTEQ[]', e2, e1); }

    stack.push(e1 >= e2 ? 1 : 0);
}
```
</details>

### `EQ(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function EQ(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'EQ[]', e2, e1); }

    stack.push(e2 === e1 ? 1 : 0);
}
```
</details>

### `NEQ(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function NEQ(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'NEQ[]', e2, e1); }

    stack.push(e2 !== e1 ? 1 : 0);
}
```
</details>

### `ODD(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `Math.trunc`

<details><summary>Code</summary>

```typescript
function ODD(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'ODD[]', n); }

    stack.push(Math.trunc(n) % 2 ? 1 : 0);
}
```
</details>

### `EVEN(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `Math.trunc`

<details><summary>Code</summary>

```typescript
function EVEN(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'EVEN[]', n); }

    stack.push(Math.trunc(n) % 2 ? 0 : 1);
}
```
</details>

### `IF(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `skip`

**Internal Comments:**
```
// if test is true it just continues
// if not the ip is skipped until matching ELSE or EIF
```

<details><summary>Code</summary>

```typescript
function IF(state) {
    var test = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'IF[]', test); }

    // if test is true it just continues
    // if not the ip is skipped until matching ELSE or EIF
    if (!test) {
        skip(state, true);

        if (exports.DEBUG) { console.log(state.step,  'EIF[]'); }
    }
}
```
</details>

### `EIF(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

**Internal Comments:**
```
// this can be reached normally when
// executing an else branch.
// -> just ignore it
```

<details><summary>Code</summary>

```typescript
function EIF(state) {
    // this can be reached normally when
    // executing an else branch.
    // -> just ignore it

    if (exports.DEBUG) { console.log(state.step, 'EIF[]'); }
}
```
</details>

### `AND(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function AND(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'AND[]', e2, e1); }

    stack.push(e2 && e1 ? 1 : 0);
}
```
</details>

### `OR(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function OR(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'OR[]', e2, e1); }

    stack.push(e2 || e1 ? 1 : 0);
}
```
</details>

### `NOT(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function NOT(state) {
    var stack = state.stack;
    var e = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'NOT[]', e); }

    stack.push(e ? 0 : 1);
}
```
</details>

### `DELTAP123(b: any, state: any): void`

**Parameters:**

- **`b`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `fv.setRelative`

<details><summary>Code</summary>

```typescript
function DELTAP123(b, state) {
    var stack = state.stack;
    var n = stack.pop();
    var fv = state.fv;
    var pv = state.pv;
    var ppem = state.ppem;
    var base = state.deltaBase + (b - 1) * 16;
    var ds = state.deltaShift;
    var z0 = state.z0;

    if (exports.DEBUG) { console.log(state.step, 'DELTAP[' + b + ']', n, stack); }

    for (var i = 0; i < n; i++) {
        var pi = stack.pop();
        var arg = stack.pop();
        var appem = base + ((arg & 0xF0) >> 4);
        if (appem !== ppem) { continue; }

        var mag = (arg & 0x0F) - 8;
        if (mag >= 0) { mag++; }
        if (exports.DEBUG) { console.log(state.step, 'DELTAPFIX', pi, 'by', mag * ds); }

        var p = z0[pi];
        fv.setRelative(p, p, mag * ds, pv);
    }
}
```
</details>

### `SDB(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SDB(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SDB[]', n); }

    state.deltaBase = n;
}
```
</details>

### `SDS(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `Math.pow`

<details><summary>Code</summary>

```typescript
function SDS(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SDS[]', n); }

    state.deltaShift = Math.pow(0.5, n);
}
```
</details>

### `ADD(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function ADD(state) {
    var stack = state.stack;
    var n2 = stack.pop();
    var n1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'ADD[]', n2, n1); }

    stack.push(n1 + n2);
}
```
</details>

### `SUB(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function SUB(state) {
    var stack = state.stack;
    var n2 = stack.pop();
    var n1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SUB[]', n2, n1); }

    stack.push(n1 - n2);
}
```
</details>

### `DIV(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function DIV(state) {
    var stack = state.stack;
    var n2 = stack.pop();
    var n1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'DIV[]', n2, n1); }

    stack.push(n1 * 64 / n2);
}
```
</details>

### `MUL(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function MUL(state) {
    var stack = state.stack;
    var n2 = stack.pop();
    var n1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'MUL[]', n2, n1); }

    stack.push(n1 * n2 / 64);
}
```
</details>

### `ABS(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function ABS(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'ABS[]', n); }

    stack.push(Math.abs(n));
}
```
</details>

### `NEG(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function NEG(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'NEG[]', n); }

    stack.push(-n);
}
```
</details>

### `FLOOR(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `Math.floor`

<details><summary>Code</summary>

```typescript
function FLOOR(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'FLOOR[]', n); }

    stack.push(Math.floor(n / 0x40) * 0x40);
}
```
</details>

### `CEILING(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `Math.ceil`

<details><summary>Code</summary>

```typescript
function CEILING(state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'CEILING[]', n); }

    stack.push(Math.ceil(n / 0x40) * 0x40);
}
```
</details>

### `ROUND(dt: any, state: any): void`

**Parameters:**

- **`dt`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `state.round`

<details><summary>Code</summary>

```typescript
function ROUND(dt, state) {
    var stack = state.stack;
    var n = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'ROUND[]'); }

    stack.push(state.round(n / 0x40) * 0x40);
}
```
</details>

### `WCVTF(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function WCVTF(state) {
    var stack = state.stack;
    var v = stack.pop();
    var l = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'WCVTF[]', v, l); }

    state.cvt[l] = v * state.ppem / state.font.unitsPerEm;
}
```
</details>

### `DELTAC123(b: any, state: any): void`

**Parameters:**

- **`b`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function DELTAC123(b, state) {
    var stack = state.stack;
    var n = stack.pop();
    var ppem = state.ppem;
    var base = state.deltaBase + (b - 1) * 16;
    var ds = state.deltaShift;

    if (exports.DEBUG) { console.log(state.step, 'DELTAC[' + b + ']', n, stack); }

    for (var i = 0; i < n; i++) {
        var c = stack.pop();
        var arg = stack.pop();
        var appem = base + ((arg & 0xF0) >> 4);
        if (appem !== ppem) { continue; }

        var mag = (arg & 0x0F) - 8;
        if (mag >= 0) { mag++; }

        var delta = mag * ds;

        if (exports.DEBUG) { console.log(state.step, 'DELTACFIX', c, 'by', delta); }

        state.cvt[c] += delta;
    }
}
```
</details>

### `SROUND(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function SROUND(state) {
    var n = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'SROUND[]', n); }

    state.round = roundSuper;

    var period;

    switch (n & 0xC0) {
        case 0x00:
            period = 0.5;
            break;
        case 0x40:
            period = 1;
            break;
        case 0x80:
            period = 2;
            break;
        default:
            throw new Error('invalid SROUND value');
    }

    state.srPeriod = period;

    switch (n & 0x30) {
        case 0x00:
            state.srPhase = 0;
            break;
        case 0x10:
            state.srPhase = 0.25 * period;
            break;
        case 0x20:
            state.srPhase = 0.5  * period;
            break;
        case 0x30:
            state.srPhase = 0.75 * period;
            break;
        default: throw new Error('invalid SROUND value');
    }

    n &= 0x0F;

    if (n === 0) { state.srThreshold = 0; }
    else { state.srThreshold = (n / 8 - 0.5) * period; }
}
```
</details>

### `S45ROUND(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function S45ROUND(state) {
    var n = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'S45ROUND[]', n); }

    state.round = roundSuper;

    var period;

    switch (n & 0xC0) {
        case 0x00:
            period = Math.sqrt(2) / 2;
            break;
        case 0x40:
            period = Math.sqrt(2);
            break;
        case 0x80:
            period = 2 * Math.sqrt(2);
            break;
        default:
            throw new Error('invalid S45ROUND value');
    }

    state.srPeriod = period;

    switch (n & 0x30) {
        case 0x00:
            state.srPhase = 0;
            break;
        case 0x10:
            state.srPhase = 0.25 * period;
            break;
        case 0x20:
            state.srPhase = 0.5  * period;
            break;
        case 0x30:
            state.srPhase = 0.75 * period;
            break;
        default:
            throw new Error('invalid S45ROUND value');
    }

    n &= 0x0F;

    if (n === 0) { state.srThreshold = 0; }
    else { state.srThreshold = (n / 8 - 0.5) * period; }
}
```
</details>

### `ROFF(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function ROFF(state) {
    if (exports.DEBUG) { console.log(state.step, 'ROFF[]'); }

    state.round = roundOff;
}
```
</details>

### `RUTG(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function RUTG(state) {
    if (exports.DEBUG) { console.log(state.step, 'RUTG[]'); }

    state.round = roundUpToGrid;
}
```
</details>

### `RDTG(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
function RDTG(state) {
    if (exports.DEBUG) { console.log(state.step, 'RDTG[]'); }

    state.round = roundDownToGrid;
}
```
</details>

### `SCANCTRL(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

**Internal Comments:**
```
// ignored by opentype.js
```

<details><summary>Code</summary>

```typescript
function SCANCTRL(state) {
    var n = state.stack.pop();

    // ignored by opentype.js

    if (exports.DEBUG) { console.log(state.step, 'SCANCTRL[]', n); }
}
```
</details>

### `SDPVTL(a: any, state: any): void`

**Parameters:**

- **`a`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `getUnitVector`

<details><summary>Code</summary>

```typescript
function SDPVTL(a, state) {
    var stack = state.stack;
    var p2i = stack.pop();
    var p1i = stack.pop();
    var p2 = state.z2[p2i];
    var p1 = state.z1[p1i];

    if (exports.DEBUG) { console.log(state.step, 'SDPVTL[' + a + ']', p2i, p1i); }

    var dx;
    var dy;

    if (!a) {
        dx = p1.x - p2.x;
        dy = p1.y - p2.y;
    } else {
        dx = p2.y - p1.y;
        dy = p1.x - p2.x;
    }

    state.dpv = getUnitVector(dx, dy);
}
```
</details>

### `GETINFO(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

**Internal Comments:**
```
// v35 as in no subpixel hinting
// TODO rotation and stretch currently not supported
// and thus those GETINFO are always 0.
// opentype.js is always gray scaling
```

<details><summary>Code</summary>

```typescript
function GETINFO(state) {
    var stack = state.stack;
    var sel = stack.pop();
    var r = 0;

    if (exports.DEBUG) { console.log(state.step, 'GETINFO[]', sel); }

    // v35 as in no subpixel hinting
    if (sel & 0x01) { r = 35; }

    // TODO rotation and stretch currently not supported
    // and thus those GETINFO are always 0.

    // opentype.js is always gray scaling
    if (sel & 0x20) { r |= 0x1000; }

    stack.push(r);
}
```
</details>

### `ROLL(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function ROLL(state) {
    var stack = state.stack;
    var a = stack.pop();
    var b = stack.pop();
    var c = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'ROLL[]'); }

    stack.push(b);
    stack.push(a);
    stack.push(c);
}
```
</details>

### `MAX(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `Math.max`

<details><summary>Code</summary>

```typescript
function MAX(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'MAX[]', e2, e1); }

    stack.push(Math.max(e1, e2));
}
```
</details>

### `MIN(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `console.log`
- `stack.push`
- `Math.min`

<details><summary>Code</summary>

```typescript
function MIN(state) {
    var stack = state.stack;
    var e2 = stack.pop();
    var e1 = stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'MIN[]', e2, e1); }

    stack.push(Math.min(e1, e2));
}
```
</details>

### `SCANTYPE(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

**Internal Comments:**
```
// ignored by opentype.js
```

<details><summary>Code</summary>

```typescript
function SCANTYPE(state) {
    var n = state.stack.pop();
    // ignored by opentype.js
    if (exports.DEBUG) { console.log(state.step, 'SCANTYPE[]', n); }
}
```
</details>

### `INSTCTRL(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `state.stack.pop`
- `console.log`

<details><summary>Code</summary>

```typescript
function INSTCTRL(state) {
    var s = state.stack.pop();
    var v = state.stack.pop();

    if (exports.DEBUG) { console.log(state.step, 'INSTCTRL[]', s, v); }

    switch (s) {
        case 1 : state.inhibitGridFit = !!v; return;
        case 2 : state.ignoreCvt = !!v; return;
        default: throw new Error('invalid INSTCTRL[] selector');
    }
}
```
</details>

### `PUSHB(n: any, state: any): void`

**Parameters:**

- **`n`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function PUSHB(n, state) {
    var stack = state.stack;
    var prog = state.prog;
    var ip = state.ip;

    if (exports.DEBUG) { console.log(state.step, 'PUSHB[' + n + ']'); }

    for (var i = 0; i < n; i++) { stack.push(prog[++ip]); }

    state.ip = ip;
}
```
</details>

### `PUSHW(n: any, state: any): void`

**Parameters:**

- **`n`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `stack.push`

<details><summary>Code</summary>

```typescript
function PUSHW(n, state) {
    var ip = state.ip;
    var prog = state.prog;
    var stack = state.stack;

    if (exports.DEBUG) { console.log(state.ip, 'PUSHW[' + n + ']'); }

    for (var i = 0; i < n; i++) {
        var w = (prog[++ip] << 8) | prog[++ip];
        if (w & 0x8000) { w = -((w ^ 0xffff) + 1); }
        stack.push(w);
    }

    state.ip = ip;
}
```
</details>

### `MDRP_MIRP(indirect: any, setRp0: any, keepD: any, ro: any, dt: any, state: any): void`

**Parameters:**

- **`indirect`** `any`
- **`setRp0`** `any`
- **`keepD`** `any`
- **`ro`** `any`
- **`dt`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stack.pop`
- `pv.distance`
- `Math.abs`
- `state.round`
- `fv.setRelative`
- `fv.touch`
- `console.log`

**Internal Comments:**
```
// TODO consider autoFlip (x3)
```

<details><summary>Code</summary>

```typescript
function MDRP_MIRP(indirect, setRp0, keepD, ro, dt, state) {
    var stack = state.stack;
    var cvte = indirect && stack.pop();
    var pi = stack.pop();
    var rp0i = state.rp0;
    var rp = state.z0[rp0i];
    var p = state.z1[pi];

    var md = state.minDis;
    var fv = state.fv;
    var pv = state.dpv;
    var od; // original distance
    var d; // moving distance
    var sign; // sign of distance
    var cv;

    d = od = pv.distance(p, rp, true, true);
    sign = d >= 0 ? 1 : -1; // Math.sign would be 0 in case of 0

    // TODO consider autoFlip
    d = Math.abs(d);

    if (indirect) {
        cv = state.cvt[cvte];

        if (ro && Math.abs(d - cv) < state.cvCutIn) { d = cv; }
    }

    if (keepD && d < md) { d = md; }

    if (ro) { d = state.round(d); }

    fv.setRelative(p, rp, sign * d, pv);
    fv.touch(p);

    if (exports.DEBUG) {
        console.log(
            state.step,
            (indirect ? 'MIRP[' : 'MDRP[') +
            (setRp0 ? 'M' : 'm') +
            (keepD ? '>' : '_') +
            (ro ? 'R' : '_') +
            (dt === 0 ? 'Gr' : (dt === 1 ? 'Bl' : (dt === 2 ? 'Wh' : ''))) +
            ']',
            indirect ?
                cvte + '(' + state.cvt[cvte] + ',' +  cv + ')' :
                '',
            pi,
            '(d =', od, '->', sign * d, ')'
        );
    }

    state.rp1 = state.rp0;
    state.rp2 = pi;
    if (setRp0) { state.rp0 = pi; }
}
```
</details>

### `Token(char: string): void`

**JSDoc:**
```typescript
/**
 * Create a new token
 * @param {string} char a single char
 */
```

**Parameters:**

- **`char`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Token(char) {
    this.char = char;
    this.state = {};
    this.activeState = null;
}
```
</details>

### `ContextRange(startIndex: number, endOffset: number, contextName: string): void`

**JSDoc:**
```typescript
/**
 * Create a new context range
 * @param {number} startIndex range start index
 * @param {number} endOffset range end index offset
 * @param {string} contextName owner context name
 */
```

**Parameters:**

- **`startIndex`** `number`
- **`endOffset`** `number`
- **`contextName`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ContextRange(startIndex, endOffset, contextName) {
    this.contextName = contextName;
    this.startIndex = startIndex;
    this.endOffset = endOffset;
}
```
</details>

### `ContextChecker(contextName: string, checkStart: Function, checkEnd: Function): void`

**JSDoc:**
```typescript
/**
 * Check context start and end
 * @param {string} contextName a unique context name
 * @param {function} checkStart a predicate function the indicates a context's start
 * @param {function} checkEnd a predicate function the indicates a context's end
 */
```

**Parameters:**

- **`contextName`** `string`
- **`checkStart`** `Function`
- **`checkEnd`** `Function`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ContextChecker(contextName, checkStart, checkEnd) {
    this.contextName = contextName;
    this.openRange = null;
    this.ranges = [];
    this.checkStart = checkStart;
    this.checkEnd = checkEnd;
}
```
</details>

### `ContextParams(context: any[], currentIndex: number): void`

**JSDoc:**
```typescript
/**
 * Create a context params
 * @param {array} context a list of items
 * @param {number} currentIndex current item index
 */
```

**Parameters:**

- **`context`** `any[]`
- **`currentIndex`** `number`

**Returns:** `void`

**Calls:**

- `context.slice`

<details><summary>Code</summary>

```typescript
function ContextParams(context, currentIndex) {
    this.context = context;
    this.index = currentIndex;
    this.length = context.length;
    this.current = context[currentIndex];
    this.backtrack = context.slice(0, currentIndex);
    this.lookahead = context.slice(currentIndex + 1);
}
```
</details>

### `Event(eventId: string): void`

**JSDoc:**
```typescript
/**
 * Create an event instance
 * @param {string} eventId event unique id
 */
```

**Parameters:**

- **`eventId`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Event(eventId) {
    this.eventId = eventId;
    this.subscribers = [];
}
```
</details>

### `initializeCoreEvents(events: any): void`

**JSDoc:**
```typescript
/**
 * Initialize a core events and auto subscribe required event handlers
 * @param {any} events an object that enlists core events handlers
 */
```

**Parameters:**

- **`events`** `any`

**Returns:** `void`

**Calls:**

- `coreEvents.forEach`
- `Object.defineProperty`
- `this$1.events[eventId].subscribe`
- `requiresContextUpdate.forEach`

<details><summary>Code</summary>

```typescript
function initializeCoreEvents(events) {
    var this$1 = this;

    var coreEvents = [
        'start', 'end', 'next', 'newToken', 'contextStart',
        'contextEnd', 'insertToken', 'removeToken', 'removeRange',
        'replaceToken', 'replaceRange', 'composeRUD', 'updateContextsRanges'
    ];

    coreEvents.forEach(function (eventId) {
        Object.defineProperty(this$1.events, eventId, {
            value: new Event(eventId)
        });
    });

    if (!!events) {
        coreEvents.forEach(function (eventId) {
            var event = events[eventId];
            if (typeof event === 'function') {
                this$1.events[eventId].subscribe(event);
            }
        });
    }
    var requiresContextUpdate = [
        'insertToken', 'removeToken', 'removeRange',
        'replaceToken', 'replaceRange', 'composeRUD'
    ];
    requiresContextUpdate.forEach(function (eventId) {
        this$1.events[eventId].subscribe(
            this$1.updateContextsRanges
        );
    });
}
```
</details>

### `Tokenizer(events: any): void`

**JSDoc:**
```typescript
/**
 * Converts a string into a list of tokens
 * @param {any} events tokenizer core events
 */
```

**Parameters:**

- **`events`** `any`

**Returns:** `void`

**Calls:**

- `initializeCoreEvents.call`

<details><summary>Code</summary>

```typescript
function Tokenizer(events) {
    this.tokens = [];
    this.registeredContexts = {};
    this.contextCheckers = [];
    this.events = {};
    this.registeredModifiers = [];

    initializeCoreEvents.call(this, events);
}
```
</details>

### `hasFAILObject(obj: any): any`

**Parameters:**

- **`obj`** `any`

**Returns:** `any`

**Calls:**

- `obj.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function (obj) { return (
        typeof obj === 'object' &&
        obj.hasOwnProperty('FAIL')
    ); }
```
</details>

### `isArabicChar(c: string): boolean`

**JSDoc:**
```typescript
/**
 * Check if a char is Arabic
 * @param {string} c a single char
 */
```

**Parameters:**

- **`c`** `string`

**Returns:** `boolean`

**Calls:**

- `/[\u0600-\u065F\u066A-\u06D2\u06FA-\u06FF]/.test`

<details><summary>Code</summary>

```typescript
function isArabicChar(c) {
    return /[\u0600-\u065F\u066A-\u06D2\u06FA-\u06FF]/.test(c);
}
```
</details>

### `isIsolatedArabicChar(char: any): boolean`

**JSDoc:**
```typescript
/**
 * Check if a char is an isolated arabic char
 * @param {string} c a single char
 */
```

**Parameters:**

- **`char`** `any`

**Returns:** `boolean`

**Calls:**

- `/[\u0630\u0690\u0621\u0631\u0661\u0671\u0622\u0632\u0672\u0692\u06C2\u0623\u0673\u0693\u06C3\u0624\u0694\u06C4\u0625\u0675\u0695\u06C5\u06E5\u0676\u0696\u06C6\u0627\u0677\u0697\u06C7\u0648\u0688\u0698\u06C8\u0689\u0699\u06C9\u068A\u06CA\u066B\u068B\u06CB\u068C\u068D\u06CD\u06FD\u068E\u06EE\u06FE\u062F\u068F\u06CF\u06EF]/.test`

<details><summary>Code</summary>

```typescript
function isIsolatedArabicChar(char) {
    return /[\u0630\u0690\u0621\u0631\u0661\u0671\u0622\u0632\u0672\u0692\u06C2\u0623\u0673\u0693\u06C3\u0624\u0694\u06C4\u0625\u0675\u0695\u06C5\u06E5\u0676\u0696\u06C6\u0627\u0677\u0697\u06C7\u0648\u0688\u0698\u06C8\u0689\u0699\u06C9\u068A\u06CA\u066B\u068B\u06CB\u068C\u068D\u06CD\u06FD\u068E\u06EE\u06FE\u062F\u068F\u06CF\u06EF]/.test(char);
}
```
</details>

### `isTashkeelArabicChar(char: any): boolean`

**JSDoc:**
```typescript
/**
 * Check if a char is an Arabic Tashkeel char
 * @param {string} c a single char
 */
```

**Parameters:**

- **`char`** `any`

**Returns:** `boolean`

**Calls:**

- `/[\u0600-\u0605\u060C-\u060E\u0610-\u061B\u061E\u064B-\u065F\u0670\u06D6-\u06DC\u06DF-\u06E4\u06E7\u06E8\u06EA-\u06ED]/.test`

<details><summary>Code</summary>

```typescript
function isTashkeelArabicChar(char) {
    return /[\u0600-\u0605\u060C-\u060E\u0610-\u061B\u061E\u064B-\u065F\u0670\u06D6-\u06DC\u06DF-\u06E4\u06E7\u06E8\u06EA-\u06ED]/.test(char);
}
```
</details>

### `isLatinChar(c: string): boolean`

**JSDoc:**
```typescript
/**
 * Check if a char is Latin
 * @param {string} c a single char
 */
```

**Parameters:**

- **`c`** `string`

**Returns:** `boolean`

**Calls:**

- `/[A-z]/.test`

<details><summary>Code</summary>

```typescript
function isLatinChar(c) {
    return /[A-z]/.test(c);
}
```
</details>

### `isWhiteSpace(c: string): boolean`

**JSDoc:**
```typescript
/**
 * Check if a char is whitespace char
 * @param {string} c a single char
 */
```

**Parameters:**

- **`c`** `string`

**Returns:** `boolean`

**Calls:**

- `/\s/.test`

<details><summary>Code</summary>

```typescript
function isWhiteSpace(c) {
    return /\s/.test(c);
}
```
</details>

### `FeatureQuery(font: Font): void`

**JSDoc:**
```typescript
/**
 * Create feature query instance
 * @param {Font} font opentype font instance
 */
```

**Parameters:**

- **`font`** `Font`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function FeatureQuery(font) {
    this.font = font;
    this.features = {};
}
```
</details>

### `SubstitutionAction(action: SubstitutionAction): void`

**JSDoc:**
```typescript
/**
 * Create a substitution action instance
 * @param {SubstitutionAction} action
 */
```

**Parameters:**

- **`action`** `SubstitutionAction`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SubstitutionAction(action) {
    this.id = action.id;
    this.tag = action.tag;
    this.substitution = action.substitution;
}
```
</details>

### `lookupCoverage(glyphIndex: number, coverage: CoverageTable): any`

**JSDoc:**
```typescript
/**
 * Lookup a coverage table
 * @param {number} glyphIndex glyph index
 * @param {CoverageTable} coverage coverage table
 */
```

**Parameters:**

- **`glyphIndex`** `number`
- **`coverage`** `CoverageTable`

**Returns:** `any`

**Calls:**

- `coverage.glyphs.indexOf`

<details><summary>Code</summary>

```typescript
function lookupCoverage(glyphIndex, coverage) {
    if (!glyphIndex) { return -1; }
    switch (coverage.format) {
        case 1:
            return coverage.glyphs.indexOf(glyphIndex);

        case 2:
            var ranges = coverage.ranges;
            for (var i = 0; i < ranges.length; i++) {
                var range = ranges[i];
                if (glyphIndex >= range.start && glyphIndex <= range.end) {
                    var offset = glyphIndex - range.start;
                    return range.index + offset;
                }
            }
            break;
        default:
            return -1; // not found
    }
    return -1;
}
```
</details>

### `singleSubstitutionFormat1(glyphIndex: any, subtable: any): any`

**JSDoc:**
```typescript
/**
 * Handle a single substitution - format 1
 * @param {ContextParams} contextParams context params to lookup
 */
```

**Parameters:**

- **`glyphIndex`** `any`
- **`subtable`** `any`

**Returns:** `any`

**Calls:**

- `lookupCoverage`

<details><summary>Code</summary>

```typescript
function singleSubstitutionFormat1(glyphIndex, subtable) {
    var substituteIndex = lookupCoverage(glyphIndex, subtable.coverage);
    if (substituteIndex === -1) { return null; }
    return glyphIndex + subtable.deltaGlyphId;
}
```
</details>

### `singleSubstitutionFormat2(glyphIndex: any, subtable: any): any`

**JSDoc:**
```typescript
/**
 * Handle a single substitution - format 2
 * @param {ContextParams} contextParams context params to lookup
 */
```

**Parameters:**

- **`glyphIndex`** `any`
- **`subtable`** `any`

**Returns:** `any`

**Calls:**

- `lookupCoverage`

<details><summary>Code</summary>

```typescript
function singleSubstitutionFormat2(glyphIndex, subtable) {
    var substituteIndex = lookupCoverage(glyphIndex, subtable.coverage);
    if (substituteIndex === -1) { return null; }
    return subtable.substitute[substituteIndex];
}
```
</details>

### `lookupCoverageList(coverageList: any, contextParams: ContextParams): -1 | any[]`

**JSDoc:**
```typescript
/**
 * Lookup a list of coverage tables
 * @param {any} coverageList a list of coverage tables
 * @param {ContextParams} contextParams context params to lookup
 */
```

**Parameters:**

- **`coverageList`** `any`
- **`contextParams`** `ContextParams`

**Returns:** `-1 | any[]`

**Calls:**

- `Array.isArray`
- `lookupCoverage`
- `lookupList.push`

<details><summary>Code</summary>

```typescript
function lookupCoverageList(coverageList, contextParams) {
    var lookupList = [];
    for (var i = 0; i < coverageList.length; i++) {
        var coverage = coverageList[i];
        var glyphIndex = contextParams.current;
        glyphIndex = Array.isArray(glyphIndex) ? glyphIndex[0] : glyphIndex;
        var lookupIndex = lookupCoverage(glyphIndex, coverage);
        if (lookupIndex !== -1) {
            lookupList.push(lookupIndex);
        }
    }
    if (lookupList.length !== coverageList.length) { return -1; }
    return lookupList;
}
```
</details>

### `chainingSubstitutionFormat3(contextParams: ContextParams, subtable: any): any[]`

**JSDoc:**
```typescript
/**
 * Handle chaining context substitution - format 3
 * @param {ContextParams} contextParams context params to lookup
 */
```

**Parameters:**

- **`contextParams`** `ContextParams`
- **`subtable`** `any`

**Returns:** `any[]`

**Calls:**

- `lookupCoverageList`
- `contextParams.lookahead.slice`
- `isTashkeelArabicChar`
- `lookaheadContext.shift`
- `[].concat`
- `backtrackContext.reverse`
- `backtrackContext.shift`
- `this.getLookupByIndex`
- `this.getLookupMethod`
- `this.getSubstitutionType`
- `contextParams.get`
- `lookup`
- `substitutions.push`

**Internal Comments:**
```
// INPUT LOOKUP // (x2)
// LOOKAHEAD LOOKUP // (x2)
// BACKTRACK LOOKUP // (x2)
```

<details><summary>Code</summary>

```typescript
function chainingSubstitutionFormat3(contextParams, subtable) {
    var lookupsCount = (
        subtable.inputCoverage.length +
        subtable.lookaheadCoverage.length +
        subtable.backtrackCoverage.length
    );
    if (contextParams.context.length < lookupsCount) { return []; }
    // INPUT LOOKUP //
    var inputLookups = lookupCoverageList(
        subtable.inputCoverage, contextParams
    );
    if (inputLookups === -1) { return []; }
    // LOOKAHEAD LOOKUP //
    var lookaheadOffset = subtable.inputCoverage.length - 1;
    if (contextParams.lookahead.length < subtable.lookaheadCoverage.length) { return []; }
    var lookaheadContext = contextParams.lookahead.slice(lookaheadOffset);
    while (lookaheadContext.length && isTashkeelArabicChar(lookaheadContext[0].char)) {
        lookaheadContext.shift();
    }
    var lookaheadParams = new ContextParams(lookaheadContext, 0);
    var lookaheadLookups = lookupCoverageList(
        subtable.lookaheadCoverage, lookaheadParams
    );
    // BACKTRACK LOOKUP //
    var backtrackContext = [].concat(contextParams.backtrack);
    backtrackContext.reverse();
    while (backtrackContext.length && isTashkeelArabicChar(backtrackContext[0].char)) {
        backtrackContext.shift();
    }
    if (backtrackContext.length < subtable.backtrackCoverage.length) { return []; }
    var backtrackParams = new ContextParams(backtrackContext, 0);
    var backtrackLookups = lookupCoverageList(
        subtable.backtrackCoverage, backtrackParams
    );
    var contextRulesMatch = (
        inputLookups.length === subtable.inputCoverage.length &&
        lookaheadLookups.length === subtable.lookaheadCoverage.length &&
        backtrackLookups.length === subtable.backtrackCoverage.length
    );
    var substitutions = [];
    if (contextRulesMatch) {
        for (var i = 0; i < subtable.lookupRecords.length; i++) {
            var lookupRecord = subtable.lookupRecords[i];
            var lookupListIndex = lookupRecord.lookupListIndex;
            var lookupTable = this.getLookupByIndex(lookupListIndex);
            for (var s = 0; s < lookupTable.subtables.length; s++) {
                var subtable$1 = lookupTable.subtables[s];
                var lookup = this.getLookupMethod(lookupTable, subtable$1);
                var substitutionType = this.getSubstitutionType(lookupTable, subtable$1);
                if (substitutionType === '12') {
                    for (var n = 0; n < inputLookups.length; n++) {
                        var glyphIndex = contextParams.get(n);
                        var substitution = lookup(glyphIndex);
                        if (substitution) { substitutions.push(substitution); }
                    }
                }
            }
        }
    }
    return substitutions;
}
```
</details>

### `ligatureSubstitutionFormat1(contextParams: ContextParams, subtable: any): any`

**JSDoc:**
```typescript
/**
 * Handle ligature substitution - format 1
 * @param {ContextParams} contextParams context params to lookup
 */
```

**Parameters:**

- **`contextParams`** `ContextParams`
- **`subtable`** `any`

**Returns:** `any`

**Calls:**

- `lookupCoverage`

**Internal Comments:**
```
// COVERAGE LOOKUP // (x2)
// COMPONENTS LOOKUP (x2)
// (!) note, components are ordered in the written direction. (x2)
```

<details><summary>Code</summary>

```typescript
function ligatureSubstitutionFormat1(contextParams, subtable) {
    // COVERAGE LOOKUP //
    var glyphIndex = contextParams.current;
    var ligSetIndex = lookupCoverage(glyphIndex, subtable.coverage);
    if (ligSetIndex === -1) { return null; }
    // COMPONENTS LOOKUP
    // (!) note, components are ordered in the written direction.
    var ligature;
    var ligatureSet = subtable.ligatureSets[ligSetIndex];
    for (var s = 0; s < ligatureSet.length; s++) {
        ligature = ligatureSet[s];
        for (var l = 0; l < ligature.components.length; l++) {
            var lookaheadItem = contextParams.lookahead[l];
            var component = ligature.components[l];
            if (lookaheadItem !== component) { break; }
            if (l === ligature.components.length - 1) { return ligature; }
        }
    }
    return null;
}
```
</details>

### `decompositionSubstitutionFormat1(glyphIndex: number, subtable: any): any`

**JSDoc:**
```typescript
/**
 * Handle decomposition substitution - format 1
 * @param {number} glyphIndex glyph index
 * @param {any} subtable subtable
 */
```

**Parameters:**

- **`glyphIndex`** `number`
- **`subtable`** `any`

**Returns:** `any`

**Calls:**

- `lookupCoverage`

<details><summary>Code</summary>

```typescript
function decompositionSubstitutionFormat1(glyphIndex, subtable) {
    var substituteIndex = lookupCoverage(glyphIndex, subtable.coverage);
    if (substituteIndex === -1) { return null; }
    return subtable.sequences[substituteIndex];
}
```
</details>

### `arabicWordStartCheck(contextParams: any): boolean`

**JSDoc:**
```typescript
/**
 * Arabic word context checkers
 */
```

**Parameters:**

- **`contextParams`** `any`

**Returns:** `boolean`

**Calls:**

- `contextParams.get`
- `isArabicChar`

**Internal Comments:**
```
// ? arabic first char (x2)
// ? arabic char preceded with a non arabic char
```

<details><summary>Code</summary>

```typescript
function arabicWordStartCheck(contextParams) {
    var char = contextParams.current;
    var prevChar = contextParams.get(-1);
    return (
        // ? arabic first char
        (prevChar === null && isArabicChar(char)) ||
        // ? arabic char preceded with a non arabic char
        (!isArabicChar(prevChar) && isArabicChar(char))
    );
}
```
</details>

### `arabicWordEndCheck(contextParams: any): boolean`

**Parameters:**

- **`contextParams`** `any`

**Returns:** `boolean`

**Calls:**

- `contextParams.get`
- `isArabicChar`

**Internal Comments:**
```
// ? last arabic char (x2)
// ? next char is not arabic
```

<details><summary>Code</summary>

```typescript
function arabicWordEndCheck(contextParams) {
    var nextChar = contextParams.get(1);
    return (
        // ? last arabic char
        (nextChar === null) ||
        // ? next char is not arabic
        (!isArabicChar(nextChar))
    );
}
```
</details>

### `arabicSentenceStartCheck(contextParams: any): boolean`

**JSDoc:**
```typescript
/**
 * Arabic sentence context checkers
 */
```

**Parameters:**

- **`contextParams`** `any`

**Returns:** `boolean`

**Calls:**

- `contextParams.get`
- `isArabicChar`
- `isTashkeelArabicChar`

**Internal Comments:**
```
// ? an arabic char preceded with a non arabic char (x2)
```

<details><summary>Code</summary>

```typescript
function arabicSentenceStartCheck(contextParams) {
    var char = contextParams.current;
    var prevChar = contextParams.get(-1);
    return (
        // ? an arabic char preceded with a non arabic char
        (isArabicChar(char) || isTashkeelArabicChar(char)) &&
        !isArabicChar(prevChar)
    );
}
```
</details>

### `arabicSentenceEndCheck(contextParams: any): boolean`

**Parameters:**

- **`contextParams`** `any`

**Returns:** `boolean`

**Calls:**

- `contextParams.get`
- `isArabicChar`
- `isTashkeelArabicChar`
- `isWhiteSpace`
- `contextParams.lookahead.some`

<details><summary>Code</summary>

```typescript
function arabicSentenceEndCheck(contextParams) {
    var nextChar = contextParams.get(1);
    switch (true) {
        case nextChar === null:
            return true;
        case (!isArabicChar(nextChar) && !isTashkeelArabicChar(nextChar)):
            var nextIsWhitespace = isWhiteSpace(nextChar);
            if (!nextIsWhitespace) { return true; }
            if (nextIsWhitespace) {
                var arabicCharAhead = false;
                arabicCharAhead = (
                    contextParams.lookahead.some(
                        function (c) { return isArabicChar(c) || isTashkeelArabicChar(c); }
                    )
                );
                if (!arabicCharAhead) { return true; }
            }
            break;
        default:
            return false;
    }
}
```
</details>

### `singleSubstitutionFormat1$1(action: any, tokens: any, index: number): void`

**JSDoc:**
```typescript
/**
 * Apply single substitution format 1
 * @param {Array} substitutions substitutions
 * @param {any} tokens a list of tokens
 * @param {number} index token index
 */
```

**Parameters:**

- **`action`** `any`
- **`tokens`** `any`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `tokens[index].setState`

<details><summary>Code</summary>

```typescript
function singleSubstitutionFormat1$1(action, tokens, index) {
    tokens[index].setState(action.tag, action.substitution);
}
```
</details>

### `singleSubstitutionFormat2$1(action: any, tokens: any, index: number): void`

**JSDoc:**
```typescript
/**
 * Apply single substitution format 2
 * @param {Array} substitutions substitutions
 * @param {any} tokens a list of tokens
 * @param {number} index token index
 */
```

**Parameters:**

- **`action`** `any`
- **`tokens`** `any`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `tokens[index].setState`

<details><summary>Code</summary>

```typescript
function singleSubstitutionFormat2$1(action, tokens, index) {
    tokens[index].setState(action.tag, action.substitution);
}
```
</details>

### `chainingSubstitutionFormat3$1(action: any, tokens: any, index: number): void`

**JSDoc:**
```typescript
/**
 * Apply chaining context substitution format 3
 * @param {Array} substitutions substitutions
 * @param {any} tokens a list of tokens
 * @param {number} index token index
 */
```

**Parameters:**

- **`action`** `any`
- **`tokens`** `any`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `action.substitution.forEach`
- `token.setState`

<details><summary>Code</summary>

```typescript
function chainingSubstitutionFormat3$1(action, tokens, index) {
    action.substitution.forEach(function (subst, offset) {
        var token = tokens[index + offset];
        token.setState(action.tag, subst);
    });
}
```
</details>

### `ligatureSubstitutionFormat1$1(action: any, tokens: any, index: number): void`

**JSDoc:**
```typescript
/**
 * Apply ligature substitution format 1
 * @param {Array} substitutions substitutions
 * @param {any} tokens a list of tokens
 * @param {number} index token index
 */
```

**Parameters:**

- **`action`** `any`
- **`tokens`** `any`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `token.setState`

<details><summary>Code</summary>

```typescript
function ligatureSubstitutionFormat1$1(action, tokens, index) {
    var token = tokens[index];
    token.setState(action.tag, action.substitution.ligGlyph);
    var compsCount = action.substitution.components.length;
    for (var i = 0; i < compsCount; i++) {
        token = tokens[index + i + 1];
        token.setState('deleted', true);
    }
}
```
</details>

### `applySubstitution(action: any, tokens: any, index: number): void`

**JSDoc:**
```typescript
/**
 * Apply substitutions to a list of tokens
 * @param {Array} substitutions substitutions
 * @param {any} tokens a list of tokens
 * @param {number} index token index
 */
```

**Parameters:**

- **`action`** `any`
- **`tokens`** `any`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `complex_call_404564`

<details><summary>Code</summary>

```typescript
function applySubstitution(action, tokens, index) {
    if (action instanceof SubstitutionAction && SUBSTITUTIONS[action.id]) {
        SUBSTITUTIONS[action.id](action, tokens, index);
    }
}
```
</details>

### `willConnectPrev(charContextParams: ContextParams): boolean`

**JSDoc:**
```typescript
/**
 * Check if a char can be connected to it's preceding char
 * @param {ContextParams} charContextParams context params of a char
 */
```

**Parameters:**

- **`charContextParams`** `ContextParams`

**Returns:** `boolean`

**Calls:**

- `[].concat`
- `isIsolatedArabicChar`
- `isTashkeelArabicChar`

<details><summary>Code</summary>

```typescript
function willConnectPrev(charContextParams) {
    var backtrack = [].concat(charContextParams.backtrack);
    for (var i = backtrack.length - 1; i >= 0; i--) {
        var prevChar = backtrack[i];
        var isolated = isIsolatedArabicChar(prevChar);
        var tashkeel = isTashkeelArabicChar(prevChar);
        if (!isolated && !tashkeel) { return true; }
        if (isolated) { return false; }
    }
    return false;
}
```
</details>

### `willConnectNext(charContextParams: ContextParams): boolean`

**JSDoc:**
```typescript
/**
 * Check if a char can be connected to it's proceeding char
 * @param {ContextParams} charContextParams context params of a char
 */
```

**Parameters:**

- **`charContextParams`** `ContextParams`

**Returns:** `boolean`

**Calls:**

- `isIsolatedArabicChar`
- `isTashkeelArabicChar`

<details><summary>Code</summary>

```typescript
function willConnectNext(charContextParams) {
    if (isIsolatedArabicChar(charContextParams.current)) { return false; }
    for (var i = 0; i < charContextParams.lookahead.length; i++) {
        var nextChar = charContextParams.lookahead[i];
        var tashkeel = isTashkeelArabicChar(nextChar);
        if (!tashkeel) { return true; }
    }
    return false;
}
```
</details>

### `arabicPresentationForms(range: ContextRange): void`

**JSDoc:**
```typescript
/**
 * Apply arabic presentation forms to a list of tokens
 * @param {ContextRange} range a range of tokens
 */
```

**Parameters:**

- **`range`** `ContextRange`

**Returns:** `void`

**Calls:**

- `this.tokenizer.getRangeTokens`
- `tokens.map`
- `token.getState`
- `tokens.forEach`
- `isTashkeelArabicChar`
- `contextParams.setCurrentIndex`
- `charContextParams.setCurrentIndex`
- `willConnectPrev`
- `willConnectNext`
- `tags.indexOf`
- `this$1.query.lookupFeature`
- `console.info`
- `substitutions.forEach`
- `applySubstitution`

<details><summary>Code</summary>

```typescript
function arabicPresentationForms(range) {
    var this$1 = this;

    var script = 'arab';
    var tags = this.featuresTags[script];
    var tokens = this.tokenizer.getRangeTokens(range);
    if (tokens.length === 1) { return; }
    var contextParams = new ContextParams(
        tokens.map(function (token) { return token.getState('glyphIndex'); }
    ), 0);
    var charContextParams = new ContextParams(
        tokens.map(function (token) { return token.char; }
    ), 0);
    tokens.forEach(function (token, index) {
        if (isTashkeelArabicChar(token.char)) { return; }
        contextParams.setCurrentIndex(index);
        charContextParams.setCurrentIndex(index);
        var CONNECT = 0; // 2 bits 00 (10: can connect next) (01: can connect prev)
        if (willConnectPrev(charContextParams)) { CONNECT |= 1; }
        if (willConnectNext(charContextParams)) { CONNECT |= 2; }
        var tag;
        switch (CONNECT) {
            case 1: (tag = 'fina'); break;
            case 2: (tag = 'init'); break;
            case 3: (tag = 'medi'); break;
        }
        if (tags.indexOf(tag) === -1) { return; }
        var substitutions = this$1.query.lookupFeature({
            tag: tag, script: script, contextParams: contextParams
        });
        if (substitutions instanceof Error) { return console.info(substitutions.message); }
        substitutions.forEach(function (action, index) {
            if (action instanceof SubstitutionAction) {
                applySubstitution(action, tokens, index);
                contextParams.context[index] = action.substitution;
            }
        });
    });
}
```
</details>

### `getContextParams(tokens: any, index: number): ContextParams`

**JSDoc:**
```typescript
/**
 * Update context params
 * @param {any} tokens a list of tokens
 * @param {number} index current item index
 */
```

**Parameters:**

- **`tokens`** `any`
- **`index`** `number`

**Returns:** `ContextParams`

**Calls:**

- `tokens.map`

<details><summary>Code</summary>

```typescript
function getContextParams(tokens, index) {
    var context = tokens.map(function (token) { return token.activeState.value; });
    return new ContextParams(context, index || 0);
}
```
</details>

### `arabicRequiredLigatures(range: ContextRange): void`

**JSDoc:**
```typescript
/**
 * Apply Arabic required ligatures to a context range
 * @param {ContextRange} range a range of tokens
 */
```

**Parameters:**

- **`range`** `ContextRange`

**Returns:** `void`

**Calls:**

- `this.tokenizer.getRangeTokens`
- `getContextParams`
- `contextParams.context.forEach`
- `contextParams.setCurrentIndex`
- `this$1.query.lookupFeature`
- `substitutions.forEach`
- `applySubstitution`

<details><summary>Code</summary>

```typescript
function arabicRequiredLigatures(range) {
    var this$1 = this;

    var script = 'arab';
    var tokens = this.tokenizer.getRangeTokens(range);
    var contextParams = getContextParams(tokens);
    contextParams.context.forEach(function (glyphIndex, index) {
        contextParams.setCurrentIndex(index);
        var substitutions = this$1.query.lookupFeature({
            tag: 'rlig', script: script, contextParams: contextParams
        });
        if (substitutions.length) {
            substitutions.forEach(
                function (action) { return applySubstitution(action, tokens, index); }
            );
            contextParams = getContextParams(tokens);
        }
    });
}
```
</details>

### `latinWordStartCheck(contextParams: any): boolean`

**JSDoc:**
```typescript
/**
 * Latin word context checkers
 */
```

**Parameters:**

- **`contextParams`** `any`

**Returns:** `boolean`

**Calls:**

- `contextParams.get`
- `isLatinChar`

**Internal Comments:**
```
// ? latin first char (x2)
// ? latin char preceded with a non latin char
```

<details><summary>Code</summary>

```typescript
function latinWordStartCheck(contextParams) {
    var char = contextParams.current;
    var prevChar = contextParams.get(-1);
    return (
        // ? latin first char
        (prevChar === null && isLatinChar(char)) ||
        // ? latin char preceded with a non latin char
        (!isLatinChar(prevChar) && isLatinChar(char))
    );
}
```
</details>

### `latinWordEndCheck(contextParams: any): boolean`

**Parameters:**

- **`contextParams`** `any`

**Returns:** `boolean`

**Calls:**

- `contextParams.get`
- `isLatinChar`

**Internal Comments:**
```
// ? last latin char (x2)
// ? next char is not latin
```

<details><summary>Code</summary>

```typescript
function latinWordEndCheck(contextParams) {
    var nextChar = contextParams.get(1);
    return (
        // ? last latin char
        (nextChar === null) ||
        // ? next char is not latin
        (!isLatinChar(nextChar))
    );
}
```
</details>

### `getContextParams$1(tokens: any, index: number): ContextParams`

**JSDoc:**
```typescript
/**
 * Update context params
 * @param {any} tokens a list of tokens
 * @param {number} index current item index
 */
```

**Parameters:**

- **`tokens`** `any`
- **`index`** `number`

**Returns:** `ContextParams`

**Calls:**

- `tokens.map`

<details><summary>Code</summary>

```typescript
function getContextParams$1(tokens, index) {
    var context = tokens.map(function (token) { return token.activeState.value; });
    return new ContextParams(context, index || 0);
}
```
</details>

### `latinLigature(range: ContextRange): void`

**JSDoc:**
```typescript
/**
 * Apply Arabic required ligatures to a context range
 * @param {ContextRange} range a range of tokens
 */
```

**Parameters:**

- **`range`** `ContextRange`

**Returns:** `void`

**Calls:**

- `this.tokenizer.getRangeTokens`
- `getContextParams$1`
- `contextParams.context.forEach`
- `contextParams.setCurrentIndex`
- `this$1.query.lookupFeature`
- `substitutions.forEach`
- `applySubstitution`

<details><summary>Code</summary>

```typescript
function latinLigature(range) {
    var this$1 = this;

    var script = 'latn';
    var tokens = this.tokenizer.getRangeTokens(range);
    var contextParams = getContextParams$1(tokens);
    contextParams.context.forEach(function (glyphIndex, index) {
        contextParams.setCurrentIndex(index);
        var substitutions = this$1.query.lookupFeature({
            tag: 'liga', script: script, contextParams: contextParams
        });
        if (substitutions.length) {
            substitutions.forEach(
                function (action) { return applySubstitution(action, tokens, index); }
            );
            contextParams = getContextParams$1(tokens);
        }
    });
}
```
</details>

### `Bidi(baseDir: string): void`

**JSDoc:**
```typescript
/**
 * Create Bidi. features
 * @param {string} baseDir text base direction. value either 'ltr' or 'rtl'
 */
```

**Parameters:**

- **`baseDir`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Bidi(baseDir) {
    this.baseDir = baseDir || 'ltr';
    this.tokenizer = new Tokenizer();
    this.featuresTags = {};
}
```
</details>

### `registerContextChecker(checkId: any): any`

**JSDoc:**
```typescript
/**
 * Register arabic word check
 */
```

**Parameters:**

- **`checkId`** `any`

**Returns:** `any`

**Calls:**

- `this.tokenizer.registerContextChecker`

<details><summary>Code</summary>

```typescript
function registerContextChecker(checkId) {
    var check = this.contextChecks[(checkId + "Check")];
    return this.tokenizer.registerContextChecker(
        checkId, check.startCheck, check.endCheck
    );
}
```
</details>

### `tokenizeText(): any`

**JSDoc:**
```typescript
/**
 * Perform pre tokenization procedure then
 * tokenize text input
 */
```

**Returns:** `any`

**Calls:**

- `registerContextChecker.call`
- `this.tokenizer.tokenize`

<details><summary>Code</summary>

```typescript
function tokenizeText() {
    registerContextChecker.call(this, 'latinWord');
    registerContextChecker.call(this, 'arabicWord');
    registerContextChecker.call(this, 'arabicSentence');
    return this.tokenizer.tokenize(this.text);
}
```
</details>

### `reverseArabicSentences(): void`

**JSDoc:**
```typescript
/**
 * Reverse arabic sentence layout
 * TODO: check base dir before applying adjustments - priority low
 */
```

**Returns:** `void`

**Calls:**

- `this.tokenizer.getContextRanges`
- `ranges.forEach`
- `this$1.tokenizer.getRangeTokens`
- `this$1.tokenizer.replaceRange`
- `rangeTokens.reverse`

<details><summary>Code</summary>

```typescript
function reverseArabicSentences() {
    var this$1 = this;

    var ranges = this.tokenizer.getContextRanges('arabicSentence');
    ranges.forEach(function (range) {
        var rangeTokens = this$1.tokenizer.getRangeTokens(range);
        this$1.tokenizer.replaceRange(
            range.startIndex,
            range.endOffset,
            rangeTokens.reverse()
        );
    });
}
```
</details>

### `checkGlyphIndexStatus(): void`

**JSDoc:**
```typescript
/**
 * Check if 'glyphIndex' is registered
 */
```

**Returns:** `void`

**Calls:**

- `this.tokenizer.registeredModifiers.indexOf`

<details><summary>Code</summary>

```typescript
function checkGlyphIndexStatus() {
    if (this.tokenizer.registeredModifiers.indexOf('glyphIndex') === -1) {
        throw new Error(
            'glyphIndex modifier is required to apply ' +
            'arabic presentation features.'
        );
    }
}
```
</details>

### `applyArabicPresentationForms(): void`

**JSDoc:**
```typescript
/**
 * Apply arabic presentation forms features
 */
```

**Returns:** `void`

**Calls:**

- `this.featuresTags.hasOwnProperty`
- `checkGlyphIndexStatus.call`
- `this.tokenizer.getContextRanges`
- `ranges.forEach`
- `arabicPresentationForms.call`

<details><summary>Code</summary>

```typescript
function applyArabicPresentationForms() {
    var this$1 = this;

    var script = 'arab';
    if (!this.featuresTags.hasOwnProperty(script)) { return; }
    checkGlyphIndexStatus.call(this);
    var ranges = this.tokenizer.getContextRanges('arabicWord');
    ranges.forEach(function (range) {
        arabicPresentationForms.call(this$1, range);
    });
}
```
</details>

### `applyArabicRequireLigatures(): void`

**JSDoc:**
```typescript
/**
 * Apply required arabic ligatures
 */
```

**Returns:** `void`

**Calls:**

- `this.featuresTags.hasOwnProperty`
- `tags.indexOf`
- `checkGlyphIndexStatus.call`
- `this.tokenizer.getContextRanges`
- `ranges.forEach`
- `arabicRequiredLigatures.call`

<details><summary>Code</summary>

```typescript
function applyArabicRequireLigatures() {
    var this$1 = this;

    var script = 'arab';
    if (!this.featuresTags.hasOwnProperty(script)) { return; }
    var tags = this.featuresTags[script];
    if (tags.indexOf('rlig') === -1) { return; }
    checkGlyphIndexStatus.call(this);
    var ranges = this.tokenizer.getContextRanges('arabicWord');
    ranges.forEach(function (range) {
        arabicRequiredLigatures.call(this$1, range);
    });
}
```
</details>

### `applyLatinLigatures(): void`

**JSDoc:**
```typescript
/**
 * Apply required arabic ligatures
 */
```

**Returns:** `void`

**Calls:**

- `this.featuresTags.hasOwnProperty`
- `tags.indexOf`
- `checkGlyphIndexStatus.call`
- `this.tokenizer.getContextRanges`
- `ranges.forEach`
- `latinLigature.call`

<details><summary>Code</summary>

```typescript
function applyLatinLigatures() {
    var this$1 = this;

    var script = 'latn';
    if (!this.featuresTags.hasOwnProperty(script)) { return; }
    var tags = this.featuresTags[script];
    if (tags.indexOf('liga') === -1) { return; }
    checkGlyphIndexStatus.call(this);
    var ranges = this.tokenizer.getContextRanges('latinWord');
    ranges.forEach(function (range) {
        latinLigature.call(this$1, range);
    });
}
```
</details>

### `Font(options: any): void`

**JSDoc:**
```typescript
/**
 * A Font represents a loaded OpenType font file.
 * It contains a set of glyphs and methods to draw text on a drawing context,
 * or to get a path representing the text.
 * @exports opentype.Font
 * @class
 * @param {FontOptions}
 * @constructor
 */
```

**Parameters:**

- **`options`** `any`

**Returns:** `void`

**Calls:**

- `checkArgument`
- `(options.familyName + options.styleName).replace`
- `Object.assign`
- `Object.defineProperty`

**Internal Comments:**
```
// Check that we've provided the minimum set of names. (x3)
// OS X will complain if the names are empty, so we put a single space everywhere by default. (x4)
// postScriptName may not contain any whitespace (x2)
// needed for low memory mode only. (x4)
```

<details><summary>Code</summary>

```typescript
function Font(options) {
    options = options || {};
    options.tables = options.tables || {};

    if (!options.empty) {
        // Check that we've provided the minimum set of names.
        checkArgument(options.familyName, 'When creating a new Font object, familyName is required.');
        checkArgument(options.styleName, 'When creating a new Font object, styleName is required.');
        checkArgument(options.unitsPerEm, 'When creating a new Font object, unitsPerEm is required.');
        checkArgument(options.ascender, 'When creating a new Font object, ascender is required.');
        checkArgument(options.descender <= 0, 'When creating a new Font object, negative descender value is required.');

        // OS X will complain if the names are empty, so we put a single space everywhere by default.
        this.names = {
            fontFamily: {en: options.familyName || ' '},
            fontSubfamily: {en: options.styleName || ' '},
            fullName: {en: options.fullName || options.familyName + ' ' + options.styleName},
            // postScriptName may not contain any whitespace
            postScriptName: {en: options.postScriptName || (options.familyName + options.styleName).replace(/\s/g, '')},
            designer: {en: options.designer || ' '},
            designerURL: {en: options.designerURL || ' '},
            manufacturer: {en: options.manufacturer || ' '},
            manufacturerURL: {en: options.manufacturerURL || ' '},
            license: {en: options.license || ' '},
            licenseURL: {en: options.licenseURL || ' '},
            version: {en: options.version || 'Version 0.1'},
            description: {en: options.description || ' '},
            copyright: {en: options.copyright || ' '},
            trademark: {en: options.trademark || ' '}
        };
        this.unitsPerEm = options.unitsPerEm || 1000;
        this.ascender = options.ascender;
        this.descender = options.descender;
        this.createdTimestamp = options.createdTimestamp;
        this.tables = Object.assign(options.tables, {
            os2: Object.assign({
                usWeightClass: options.weightClass || this.usWeightClasses.MEDIUM,
                usWidthClass: options.widthClass || this.usWidthClasses.MEDIUM,
                fsSelection: options.fsSelection || this.fsSelectionValues.REGULAR,
            }, options.tables.os2)
        });
    }

    this.supported = true; // Deprecated: parseBuffer will throw an error if font is not supported.
    this.glyphs = new glyphset.GlyphSet(this, options.glyphs || []);
    this.encoding = new DefaultEncoding(this);
    this.position = new Position(this);
    this.substitution = new Substitution(this);
    this.tables = this.tables || {};

    // needed for low memory mode only.
    this._push = null;
    this._hmtxTableData = {};

    Object.defineProperty(this, 'hinting', {
        get: function() {
            if (this._hinting) { return this._hinting; }
            if (this.outlinesFormat === 'truetype') {
                return (this._hinting = new Hinting(this));
            }
        }
    });
}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
            if (this._hinting) { return this._hinting; }
            if (this.outlinesFormat === 'truetype') {
                return (this._hinting = new Hinting(this));
            }
        }
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
            if (this._hinting) { return this._hinting; }
            if (this.outlinesFormat === 'truetype') {
                return (this._hinting = new Hinting(this));
            }
        }
```
</details>

### `charToGlyphIndexMod(token: any): number`

**Parameters:**

- **`token`** `any`

**Returns:** `number`

**Calls:**

- `this$1.charToGlyphIndex`

<details><summary>Code</summary>

```typescript
function (token) { return this$1.charToGlyphIndex(token.char); }
```
</details>

### `assert(predicate: any, message: any): void`

**Parameters:**

- **`predicate`** `any`
- **`message`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function assert(predicate, message) {
    }
```
</details>

### `assertNamePresent(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

**Calls:**

- `_this.getEnglishName`
- `assert`
- `englishName.trim`

<details><summary>Code</summary>

```typescript
function assertNamePresent(name) {
        var englishName = _this.getEnglishName(name);
        assert(englishName && englishName.trim().length > 0);
    }
```
</details>

### `addName(name: any, names: any): number`

**Parameters:**

- **`name`** `any`
- **`names`** `any`

**Returns:** `number`

**Calls:**

- `JSON.stringify`
- `parseInt`

<details><summary>Code</summary>

```typescript
function addName(name, names) {
    var nameString = JSON.stringify(name);
    var nameID = 256;
    for (var nameKey in names) {
        var n = parseInt(nameKey);
        if (!n || n < 256) {
            continue;
        }

        if (JSON.stringify(names[nameKey]) === nameString) {
            return n;
        }

        if (nameID <= n) {
            nameID = n + 1;
        }
    }

    names[nameID] = name;
    return nameID;
}
```
</details>

### `makeFvarAxis(n: any, axis: any, names: any): { name: string; type: string; value: any; }[]`

**Parameters:**

- **`n`** `any`
- **`axis`** `any`
- **`names`** `any`

**Returns:** `{ name: string; type: string; value: any; }[]`

**Calls:**

- `addName`

<details><summary>Code</summary>

```typescript
function makeFvarAxis(n, axis, names) {
    var nameID = addName(axis.name, names);
    return [
        {name: 'tag_' + n, type: 'TAG', value: axis.tag},
        {name: 'minValue_' + n, type: 'FIXED', value: axis.minValue << 16},
        {name: 'defaultValue_' + n, type: 'FIXED', value: axis.defaultValue << 16},
        {name: 'maxValue_' + n, type: 'FIXED', value: axis.maxValue << 16},
        {name: 'flags_' + n, type: 'USHORT', value: 0},
        {name: 'nameID_' + n, type: 'USHORT', value: nameID}
    ];
}
```
</details>

### `parseFvarAxis(data: any, start: any, names: any): { tag: string; minValue: any; defaultValue: any; maxValue: any; name: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`names`** `any`

**Returns:** `{ tag: string; minValue: any; defaultValue: any; maxValue: any; name: any; }`

**Calls:**

- `p.parseTag`
- `p.parseFixed`
- `p.skip`
- `p.parseUShort`

<details><summary>Code</summary>

```typescript
function parseFvarAxis(data, start, names) {
    var axis = {};
    var p = new parse.Parser(data, start);
    axis.tag = p.parseTag();
    axis.minValue = p.parseFixed();
    axis.defaultValue = p.parseFixed();
    axis.maxValue = p.parseFixed();
    p.skip('uShort', 1);  // reserved for flags; no values defined
    axis.name = names[p.parseUShort()] || {};
    return axis;
}
```
</details>

### `makeFvarInstance(n: any, inst: any, axes: any, names: any): { name: string; type: string; value: number; }[]`

**Parameters:**

- **`n`** `any`
- **`inst`** `any`
- **`axes`** `any`
- **`names`** `any`

**Returns:** `{ name: string; type: string; value: number; }[]`

**Calls:**

- `addName`
- `fields.push`

<details><summary>Code</summary>

```typescript
function makeFvarInstance(n, inst, axes, names) {
    var nameID = addName(inst.name, names);
    var fields = [
        {name: 'nameID_' + n, type: 'USHORT', value: nameID},
        {name: 'flags_' + n, type: 'USHORT', value: 0}
    ];

    for (var i = 0; i < axes.length; ++i) {
        var axisTag = axes[i].tag;
        fields.push({
            name: 'axis_' + n + ' ' + axisTag,
            type: 'FIXED',
            value: inst.coordinates[axisTag] << 16
        });
    }

    return fields;
}
```
</details>

### `parseFvarInstance(data: any, start: any, axes: any, names: any): { name: any; coordinates: {}; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`axes`** `any`
- **`names`** `any`

**Returns:** `{ name: any; coordinates: {}; }`

**Calls:**

- `p.parseUShort`
- `p.skip`
- `p.parseFixed`

<details><summary>Code</summary>

```typescript
function parseFvarInstance(data, start, axes, names) {
    var inst = {};
    var p = new parse.Parser(data, start);
    inst.name = names[p.parseUShort()] || {};
    p.skip('uShort', 1);  // reserved for flags; no values defined

    inst.coordinates = {};
    for (var i = 0; i < axes.length; ++i) {
        inst.coordinates[axes[i].tag] = p.parseFixed();
    }

    return inst;
}
```
</details>

### `makeFvarTable(fvar: any, names: any): Table`

**Parameters:**

- **`fvar`** `any`
- **`names`** `any`

**Returns:** `Table`

**Calls:**

- `result.sizeOf`
- `result.fields.concat`
- `makeFvarAxis`
- `makeFvarInstance`

<details><summary>Code</summary>

```typescript
function makeFvarTable(fvar, names) {
    var result = new table.Table('fvar', [
        {name: 'version', type: 'ULONG', value: 0x10000},
        {name: 'offsetToData', type: 'USHORT', value: 0},
        {name: 'countSizePairs', type: 'USHORT', value: 2},
        {name: 'axisCount', type: 'USHORT', value: fvar.axes.length},
        {name: 'axisSize', type: 'USHORT', value: 20},
        {name: 'instanceCount', type: 'USHORT', value: fvar.instances.length},
        {name: 'instanceSize', type: 'USHORT', value: 4 + fvar.axes.length * 4}
    ]);
    result.offsetToData = result.sizeOf();

    for (var i = 0; i < fvar.axes.length; i++) {
        result.fields = result.fields.concat(makeFvarAxis(i, fvar.axes[i], names));
    }

    for (var j = 0; j < fvar.instances.length; j++) {
        result.fields = result.fields.concat(makeFvarInstance(j, fvar.instances[j], fvar.axes, names));
    }

    return result;
}
```
</details>

### `parseFvarTable(data: any, start: any, names: any): { axes: { tag: string; minValue: any; defaultValue: any; maxValue: any; name: any; }[]; instances: { name: any; coordinates: {}; }[]; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`names`** `any`

**Returns:** `{ axes: { tag: string; minValue: any; defaultValue: any; maxValue: any; name: any; }[]; instances: { name: any; coordinates: {}; }[]; }`

**Calls:**

- `p.parseULong`
- `check.argument`
- `p.parseOffset16`
- `p.skip`
- `p.parseUShort`
- `axes.push`
- `parseFvarAxis`
- `instances.push`
- `parseFvarInstance`

**Internal Comments:**
```
// Skip countSizePairs. (x4)
```

<details><summary>Code</summary>

```typescript
function parseFvarTable(data, start, names) {
    var p = new parse.Parser(data, start);
    var tableVersion = p.parseULong();
    check.argument(tableVersion === 0x00010000, 'Unsupported fvar table version.');
    var offsetToData = p.parseOffset16();
    // Skip countSizePairs.
    p.skip('uShort', 1);
    var axisCount = p.parseUShort();
    var axisSize = p.parseUShort();
    var instanceCount = p.parseUShort();
    var instanceSize = p.parseUShort();

    var axes = [];
    for (var i = 0; i < axisCount; i++) {
        axes.push(parseFvarAxis(data, start + offsetToData + i * axisSize, names));
    }

    var instances = [];
    var instanceStart = start + offsetToData + axisCount * axisSize;
    for (var j = 0; j < instanceCount; j++) {
        instances.push(parseFvarInstance(data, instanceStart + j * instanceSize, axes, names));
    }

    return {axes: axes, instances: instances};
}
```
</details>

### `attachList(): { coverage: any; attachPoints: any; }`

**Returns:** `{ coverage: any; attachPoints: any; }`

**Calls:**

- `this.parsePointer`
- `this.parseList`
- `Parser.pointer`

<details><summary>Code</summary>

```typescript
function() {
    return {
        coverage: this.parsePointer(Parser.coverage),
        attachPoints: this.parseList(Parser.pointer(Parser.uShortList))
    };
}
```
</details>

### `caretValue(): { coordinate: any; pointindex?: undefined; } | { pointindex: any; coordinate?: undefined; }`

**Returns:** `{ coordinate: any; pointindex?: undefined; } | { pointindex: any; coordinate?: undefined; }`

**Calls:**

- `this.parseUShort`
- `check.argument`
- `this.parseShort`

**Internal Comments:**
```
// Device / Variation Index tables unsupported
```

<details><summary>Code</summary>

```typescript
function() {
    var format = this.parseUShort();
    check.argument(format === 1 || format === 2 || format === 3,
        'Unsupported CaretValue table version.');
    if (format === 1) {
        return { coordinate: this.parseShort() };
    } else if (format === 2) {
        return { pointindex: this.parseShort() };
    } else if (format === 3) {
        // Device / Variation Index tables unsupported
        return { coordinate: this.parseShort() };
    }
}
```
</details>

### `ligGlyph(): any`

**Returns:** `any`

**Calls:**

- `this.parseList`
- `Parser.pointer`

<details><summary>Code</summary>

```typescript
function() {
    return this.parseList(Parser.pointer(caretValue));
}
```
</details>

### `ligCaretList(): { coverage: any; ligGlyphs: any; }`

**Returns:** `{ coverage: any; ligGlyphs: any; }`

**Calls:**

- `this.parsePointer`
- `this.parseList`
- `Parser.pointer`

<details><summary>Code</summary>

```typescript
function() {
    return {
        coverage: this.parsePointer(Parser.coverage),
        ligGlyphs: this.parseList(Parser.pointer(ligGlyph))
    };
}
```
</details>

### `markGlyphSets(): any`

**Returns:** `any`

**Calls:**

- `this.parseUShort`
- `this.parseList`
- `Parser.pointer`

<details><summary>Code</summary>

```typescript
function() {
    this.parseUShort(); // Version
    return this.parseList(Parser.pointer(Parser.coverage));
}
```
</details>

### `parseGDEFTable(data: any, start: any): { version: any; classDef: any; attachList: any; ligCaretList: any; markAttachClassDef: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; classDef: any; attachList: any; ligCaretList: any; markAttachClassDef: any; }`

**Calls:**

- `p.parseVersion`
- `check.argument`
- `p.parsePointer`

<details><summary>Code</summary>

```typescript
function parseGDEFTable(data, start) {
    start = start || 0;
    var p = new Parser(data, start);
    var tableVersion = p.parseVersion(1);
    check.argument(tableVersion === 1 || tableVersion === 1.2 || tableVersion === 1.3,
        'Unsupported GDEF table version.');
    var gdef = {
        version: tableVersion,
        classDef: p.parsePointer(Parser.classDef),
        attachList: p.parsePointer(attachList),
        ligCaretList: p.parsePointer(ligCaretList),
        markAttachClassDef: p.parsePointer(Parser.classDef)
    };
    if (tableVersion >= 1.2) {
        gdef.markGlyphSets = p.parsePointer(markGlyphSets);
    }
    return gdef;
}
```
</details>

### `parseGposTable(data: any, start: any): { version: any; scripts: any; features: any; lookups: any; variations?: undefined; } | { version: any; scripts: any; features: any; lookups: any; variations: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{ version: any; scripts: any; features: any; lookups: any; variations?: undefined; } | { version: any; scripts: any; features: any; lookups: any; variations: any; }`

**Calls:**

- `p.parseVersion`
- `check.argument`
- `p.parseScriptList`
- `p.parseFeatureList`
- `p.parseLookupList`
- `p.parseFeatureVariationsList`

<details><summary>Code</summary>

```typescript
function parseGposTable(data, start) {
    start = start || 0;
    var p = new Parser(data, start);
    var tableVersion = p.parseVersion(1);
    check.argument(tableVersion === 1 || tableVersion === 1.1, 'Unsupported GPOS table version ' + tableVersion);

    if (tableVersion === 1) {
        return {
            version: tableVersion,
            scripts: p.parseScriptList(),
            features: p.parseFeatureList(),
            lookups: p.parseLookupList(subtableParsers$1)
        };
    } else {
        return {
            version: tableVersion,
            scripts: p.parseScriptList(),
            features: p.parseFeatureList(),
            lookups: p.parseLookupList(subtableParsers$1),
            variations: p.parseFeatureVariationsList()
        };
    }

}
```
</details>

### `makeGposTable(gpos: any): Table`

**Parameters:**

- **`gpos`** `any`

**Returns:** `Table`

<details><summary>Code</summary>

```typescript
function makeGposTable(gpos) {
    return new table.Table('GPOS', [
        {name: 'version', type: 'ULONG', value: 0x10000},
        {name: 'scripts', type: 'TABLE', value: new table.ScriptList(gpos.scripts)},
        {name: 'features', type: 'TABLE', value: new table.FeatureList(gpos.features)},
        {name: 'lookups', type: 'TABLE', value: new table.LookupList(gpos.lookups, subtableMakers$1)}
    ]);
}
```
</details>

### `parseWindowsKernTable(p: any): {}`

**Parameters:**

- **`p`** `any`

**Returns:** `{}`

**Calls:**

- `p.skip`
- `p.parseUShort`
- `check.argument`
- `p.parseShort`

**Internal Comments:**
```
// Skip nTables. (x4)
// Skip subtableLength, subtableCoverage (x4)
// Skip searchRange, entrySelector, rangeShift. (x4)
```

<details><summary>Code</summary>

```typescript
function parseWindowsKernTable(p) {
    var pairs = {};
    // Skip nTables.
    p.skip('uShort');
    var subtableVersion = p.parseUShort();
    check.argument(subtableVersion === 0, 'Unsupported kern sub-table version.');
    // Skip subtableLength, subtableCoverage
    p.skip('uShort', 2);
    var nPairs = p.parseUShort();
    // Skip searchRange, entrySelector, rangeShift.
    p.skip('uShort', 3);
    for (var i = 0; i < nPairs; i += 1) {
        var leftIndex = p.parseUShort();
        var rightIndex = p.parseUShort();
        var value = p.parseShort();
        pairs[leftIndex + ',' + rightIndex] = value;
    }
    return pairs;
}
```
</details>

### `parseMacKernTable(p: any): {}`

**Parameters:**

- **`p`** `any`

**Returns:** `{}`

**Calls:**

- `p.skip`
- `p.parseULong`
- `console.warn`
- `p.parseUShort`
- `p.parseShort`

**Internal Comments:**
```
// The Mac kern table stores the version as a fixed (32 bits) but we only loaded the first 16 bits. (x4)
// Skip the rest. (x4)
//check.argument(nTables === 1, 'Only 1 subtable is supported (got ' + nTables + ').');
// Skip searchRange, entrySelector, rangeShift. (x4)
```

<details><summary>Code</summary>

```typescript
function parseMacKernTable(p) {
    var pairs = {};
    // The Mac kern table stores the version as a fixed (32 bits) but we only loaded the first 16 bits.
    // Skip the rest.
    p.skip('uShort');
    var nTables = p.parseULong();
    //check.argument(nTables === 1, 'Only 1 subtable is supported (got ' + nTables + ').');
    if (nTables > 1) {
        console.warn('Only the first kern subtable is supported.');
    }
    p.skip('uLong');
    var coverage = p.parseUShort();
    var subtableVersion = coverage & 0xFF;
    p.skip('uShort');
    if (subtableVersion === 0) {
        var nPairs = p.parseUShort();
        // Skip searchRange, entrySelector, rangeShift.
        p.skip('uShort', 3);
        for (var i = 0; i < nPairs; i += 1) {
            var leftIndex = p.parseUShort();
            var rightIndex = p.parseUShort();
            var value = p.parseShort();
            pairs[leftIndex + ',' + rightIndex] = value;
        }
    }
    return pairs;
}
```
</details>

### `parseKernTable(data: any, start: any): {}`

**Parameters:**

- **`data`** `any`
- **`start`** `any`

**Returns:** `{}`

**Calls:**

- `p.parseUShort`
- `parseWindowsKernTable`
- `parseMacKernTable`

<details><summary>Code</summary>

```typescript
function parseKernTable(data, start) {
    var p = new parse.Parser(data, start);
    var tableVersion = p.parseUShort();
    if (tableVersion === 0) {
        return parseWindowsKernTable(p);
    } else if (tableVersion === 1) {
        return parseMacKernTable(p);
    } else {
        throw new Error('Unsupported kern table version (' + tableVersion + ').');
    }
}
```
</details>

### `parseLocaTable(data: any, start: any, numGlyphs: any, shortVersion: any): any[]`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`numGlyphs`** `any`
- **`shortVersion`** `any`

**Returns:** `any[]`

**Calls:**

- `parseFn.call`
- `glyphOffsets.push`

**Internal Comments:**
```
// There is an extra entry after the last index element to compute the length of the last glyph. (x2)
// That's why we use numGlyphs + 1. (x2)
// The short table version stores the actual offset divided by 2. (x3)
```

<details><summary>Code</summary>

```typescript
function parseLocaTable(data, start, numGlyphs, shortVersion) {
    var p = new parse.Parser(data, start);
    var parseFn = shortVersion ? p.parseUShort : p.parseULong;
    // There is an extra entry after the last index element to compute the length of the last glyph.
    // That's why we use numGlyphs + 1.
    var glyphOffsets = [];
    for (var i = 0; i < numGlyphs + 1; i += 1) {
        var glyphOffset = parseFn.call(p);
        if (shortVersion) {
            // The short table version stores the actual offset divided by 2.
            glyphOffset *= 2;
        }

        glyphOffsets.push(glyphOffset);
    }

    return glyphOffsets;
}
```
</details>

### `loadFromUrl(url: string, callback: Function): void`

**JSDoc:**
```typescript
/**
 * Loads a font from a URL. The callback throws an error message as the first parameter if it fails
 * and the font as an ArrayBuffer in the second parameter if it succeeds.
 * @param  {string} url - The URL of the font file.
 * @param  {Function} callback - The function to call when the font load completes
 */
```

**Parameters:**

- **`url`** `string`
- **`callback`** `Function`

**Returns:** `void`

**Calls:**

- `request.open`
- `callback`
- `request.send`

<details><summary>Code</summary>

```typescript
function loadFromUrl(url, callback) {
    var request = new XMLHttpRequest();
    request.open('get', url, true);
    request.responseType = 'arraybuffer';
    request.onload = function() {
        if (request.response) {
            return callback(null, request.response);
        } else {
            return callback('Font could not be loaded: ' + request.statusText);
        }
    };

    request.onerror = function () {
        callback('Font could not be loaded');
    };

    request.send();
}
```
</details>

### `parseOpenTypeTableEntries(data: any, numTables: any): any[]`

**JSDoc:**
```typescript
/**
 * Parses OpenType table entries.
 * @param  {DataView}
 * @param  {Number}
 * @return {Object[]}
 */
```

**Parameters:**

- **`data`** `any`
- **`numTables`** `any`

**Returns:** `any[]`

**Calls:**

- `parse.getTag`
- `parse.getULong`
- `tableEntries.push`

<details><summary>Code</summary>

```typescript
function parseOpenTypeTableEntries(data, numTables) {
    var tableEntries = [];
    var p = 12;
    for (var i = 0; i < numTables; i += 1) {
        var tag = parse.getTag(data, p);
        var checksum = parse.getULong(data, p + 4);
        var offset = parse.getULong(data, p + 8);
        var length = parse.getULong(data, p + 12);
        tableEntries.push({tag: tag, checksum: checksum, offset: offset, length: length, compression: false});
        p += 16;
    }

    return tableEntries;
}
```
</details>

### `parseWOFFTableEntries(data: any, numTables: any): any[]`

**JSDoc:**
```typescript
/**
 * Parses WOFF table entries.
 * @param  {DataView}
 * @param  {Number}
 * @return {Object[]}
 */
```

**Parameters:**

- **`data`** `any`
- **`numTables`** `any`

**Returns:** `any[]`

**Calls:**

- `parse.getTag`
- `parse.getULong`
- `tableEntries.push`

<details><summary>Code</summary>

```typescript
function parseWOFFTableEntries(data, numTables) {
    var tableEntries = [];
    var p = 44; // offset to the first table directory entry.
    for (var i = 0; i < numTables; i += 1) {
        var tag = parse.getTag(data, p);
        var offset = parse.getULong(data, p + 4);
        var compLength = parse.getULong(data, p + 8);
        var origLength = parse.getULong(data, p + 12);
        var compression = (void 0);
        if (compLength < origLength) {
            compression = 'WOFF';
        } else {
            compression = false;
        }

        tableEntries.push({tag: tag, offset: offset, compression: compression,
            compressedLength: compLength, length: origLength});
        p += 20;
    }

    return tableEntries;
}
```
</details>

### `uncompressTable(data: any, tableEntry: any): TableData`

**JSDoc:**
```typescript
/**
 * @param  {DataView}
 * @param  {Object}
 * @return {TableData}
 */
```

**Parameters:**

- **`data`** `any`
- **`tableEntry`** `any`

**Returns:** `TableData`

**Calls:**

- `tinyInflate`

<details><summary>Code</summary>

```typescript
function uncompressTable(data, tableEntry) {
    if (tableEntry.compression === 'WOFF') {
        var inBuffer = new Uint8Array(data.buffer, tableEntry.offset + 2, tableEntry.compressedLength - 2);
        var outBuffer = new Uint8Array(tableEntry.length);
        tinyInflate(inBuffer, outBuffer);
        if (outBuffer.byteLength !== tableEntry.length) {
            throw new Error('Decompression error: ' + tableEntry.tag + ' decompressed length doesn\'t match recorded length');
        }

        var view = new DataView(outBuffer.buffer, 0);
        return {data: view, offset: 0};
    } else {
        return {data: data, offset: tableEntry.offset};
    }
}
```
</details>

### `parseBuffer(buffer: any, opt: any): opentype.Font`

**JSDoc:**
```typescript
/**
 * Parse the OpenType file data (as an ArrayBuffer) and return a Font object.
 * Throws an error if the font could not be parsed.
 * @param  {ArrayBuffer}
 * @param  {Object} opt - options for parsing
 * @return {opentype.Font}
 */
```

**Parameters:**

- **`buffer`** `any`
- **`opt`** `any`

**Returns:** `opentype.Font`

**Calls:**

- `parse.getTag`
- `String.fromCharCode`
- `parse.getUShort`
- `parseOpenTypeTableEntries`
- `parseWOFFTableEntries`
- `uncompressTable`
- `cmap.parse`
- `p.parseShortList`
- `p.parseByteList`
- `head.parse`
- `hhea.parse`
- `ltag.parse`
- `colr.parse`
- `cpal.parse`
- `maxp.parse`
- `os2.parse`
- `post.parse`
- `_name.parse`
- `loca.parse`
- `glyf.parse`
- `cff.parse`
- `hmtx.parse`
- `addGlyphNames`
- `kern.parse`
- `gdef.parse`
- `gpos.parse`
- `font.position.init`
- `gsub.parse`
- `fvar.parse`
- `meta.parse`

**Internal Comments:**
```
// Since the constructor can also be called to create new fonts from scratch, we indicate this (x2)
// should be an empty font that we'll fill with our own data. (x2)
// OpenType fonts use big endian byte ordering. (x2)
// We can't rely on typed array view types, because they operate with the endianness of the host computer. (x2)
// Instead we use DataViews where we can specify endianness. (x2)
```

<details><summary>Code</summary>

```typescript
function parseBuffer(buffer, opt) {
    opt = (opt === undefined || opt === null) ?  {} : opt;

    var indexToLocFormat;
    var ltagTable;

    // Since the constructor can also be called to create new fonts from scratch, we indicate this
    // should be an empty font that we'll fill with our own data.
    var font = new Font({empty: true});

    // OpenType fonts use big endian byte ordering.
    // We can't rely on typed array view types, because they operate with the endianness of the host computer.
    // Instead we use DataViews where we can specify endianness.
    var data = new DataView(buffer, 0);
    var numTables;
    var tableEntries = [];
    var signature = parse.getTag(data, 0);
    if (signature === String.fromCharCode(0, 1, 0, 0) || signature === 'true' || signature === 'typ1') {
        font.outlinesFormat = 'truetype';
        numTables = parse.getUShort(data, 4);
        tableEntries = parseOpenTypeTableEntries(data, numTables);
    } else if (signature === 'OTTO') {
        font.outlinesFormat = 'cff';
        numTables = parse.getUShort(data, 4);
        tableEntries = parseOpenTypeTableEntries(data, numTables);
    } else if (signature === 'wOFF') {
        var flavor = parse.getTag(data, 4);
        if (flavor === String.fromCharCode(0, 1, 0, 0)) {
            font.outlinesFormat = 'truetype';
        } else if (flavor === 'OTTO') {
            font.outlinesFormat = 'cff';
        } else {
            throw new Error('Unsupported OpenType flavor ' + signature);
        }

        numTables = parse.getUShort(data, 12);
        tableEntries = parseWOFFTableEntries(data, numTables);
    } else {
        throw new Error('Unsupported OpenType signature ' + signature);
    }

    var cffTableEntry;
    var fvarTableEntry;
    var glyfTableEntry;
    var gdefTableEntry;
    var gposTableEntry;
    var gsubTableEntry;
    var hmtxTableEntry;
    var kernTableEntry;
    var locaTableEntry;
    var nameTableEntry;
    var metaTableEntry;
    var p;

    for (var i = 0; i < numTables; i += 1) {
        var tableEntry = tableEntries[i];
        var table = (void 0);
        switch (tableEntry.tag) {
            case 'cmap':
                table = uncompressTable(data, tableEntry);
                font.tables.cmap = cmap.parse(table.data, table.offset);
                font.encoding = new CmapEncoding(font.tables.cmap);
                break;
            case 'cvt ' :
                table = uncompressTable(data, tableEntry);
                p = new parse.Parser(table.data, table.offset);
                font.tables.cvt = p.parseShortList(tableEntry.length / 2);
                break;
            case 'fvar':
                fvarTableEntry = tableEntry;
                break;
            case 'fpgm' :
                table = uncompressTable(data, tableEntry);
                p = new parse.Parser(table.data, table.offset);
                font.tables.fpgm = p.parseByteList(tableEntry.length);
                break;
            case 'head':
                table = uncompressTable(data, tableEntry);
                font.tables.head = head.parse(table.data, table.offset);
                font.unitsPerEm = font.tables.head.unitsPerEm;
                indexToLocFormat = font.tables.head.indexToLocFormat;
                break;
            case 'hhea':
                table = uncompressTable(data, tableEntry);
                font.tables.hhea = hhea.parse(table.data, table.offset);
                font.ascender = font.tables.hhea.ascender;
                font.descender = font.tables.hhea.descender;
                font.numberOfHMetrics = font.tables.hhea.numberOfHMetrics;
                break;
            case 'hmtx':
                hmtxTableEntry = tableEntry;
                break;
            case 'ltag':
                table = uncompressTable(data, tableEntry);
                ltagTable = ltag.parse(table.data, table.offset);
                break;
            case 'COLR':
                table = uncompressTable(data, tableEntry);
                font.tables.colr = colr.parse(table.data, table.offset);
                break;
            case 'CPAL':
                table = uncompressTable(data, tableEntry);
                font.tables.cpal = cpal.parse(table.data, table.offset);
                break;
            case 'maxp':
                table = uncompressTable(data, tableEntry);
                font.tables.maxp = maxp.parse(table.data, table.offset);
                font.numGlyphs = font.tables.maxp.numGlyphs;
                break;
            case 'name':
                nameTableEntry = tableEntry;
                break;
            case 'OS/2':
                table = uncompressTable(data, tableEntry);
                font.tables.os2 = os2.parse(table.data, table.offset);
                break;
            case 'post':
                table = uncompressTable(data, tableEntry);
                font.tables.post = post.parse(table.data, table.offset);
                font.glyphNames = new GlyphNames(font.tables.post);
                break;
            case 'prep' :
                table = uncompressTable(data, tableEntry);
                p = new parse.Parser(table.data, table.offset);
                font.tables.prep = p.parseByteList(tableEntry.length);
                break;
            case 'glyf':
                glyfTableEntry = tableEntry;
                break;
            case 'loca':
                locaTableEntry = tableEntry;
                break;
            case 'CFF ':
                cffTableEntry = tableEntry;
                break;
            case 'kern':
                kernTableEntry = tableEntry;
                break;
            case 'GDEF':
                gdefTableEntry = tableEntry;
                break;
            case 'GPOS':
                gposTableEntry = tableEntry;
                break;
            case 'GSUB':
                gsubTableEntry = tableEntry;
                break;
            case 'meta':
                metaTableEntry = tableEntry;
                break;
        }
    }

    var nameTable = uncompressTable(data, nameTableEntry);
    font.tables.name = _name.parse(nameTable.data, nameTable.offset, ltagTable);
    font.names = font.tables.name;

    if (glyfTableEntry && locaTableEntry) {
        var shortVersion = indexToLocFormat === 0;
        var locaTable = uncompressTable(data, locaTableEntry);
        var locaOffsets = loca.parse(locaTable.data, locaTable.offset, font.numGlyphs, shortVersion);
        var glyfTable = uncompressTable(data, glyfTableEntry);
        font.glyphs = glyf.parse(glyfTable.data, glyfTable.offset, locaOffsets, font, opt);
    } else if (cffTableEntry) {
        var cffTable = uncompressTable(data, cffTableEntry);
        cff.parse(cffTable.data, cffTable.offset, font, opt);
    } else {
        throw new Error('Font doesn\'t contain TrueType or CFF outlines.');
    }

    var hmtxTable = uncompressTable(data, hmtxTableEntry);
    hmtx.parse(font, hmtxTable.data, hmtxTable.offset, font.numberOfHMetrics, font.numGlyphs, font.glyphs, opt);
    addGlyphNames(font, opt);

    if (kernTableEntry) {
        var kernTable = uncompressTable(data, kernTableEntry);
        font.kerningPairs = kern.parse(kernTable.data, kernTable.offset);
    } else {
        font.kerningPairs = {};
    }

    if (gdefTableEntry) {
        var gdefTable = uncompressTable(data, gdefTableEntry);
        font.tables.gdef = gdef.parse(gdefTable.data, gdefTable.offset);
    }

    if (gposTableEntry) {
        var gposTable = uncompressTable(data, gposTableEntry);
        font.tables.gpos = gpos.parse(gposTable.data, gposTable.offset);
        font.position.init();
    }

    if (gsubTableEntry) {
        var gsubTable = uncompressTable(data, gsubTableEntry);
        font.tables.gsub = gsub.parse(gsubTable.data, gsubTable.offset);
    }

    if (fvarTableEntry) {
        var fvarTable = uncompressTable(data, fvarTableEntry);
        font.tables.fvar = fvar.parse(fvarTable.data, fvarTable.offset, font.names);
    }

    if (metaTableEntry) {
        var metaTable = uncompressTable(data, metaTableEntry);
        font.tables.meta = meta.parse(metaTable.data, metaTable.offset);
        font.metas = font.tables.meta;
    }

    return font;
}
```
</details>

### `load(url: string, callback: Function, opt: any): Promise<any>`

**JSDoc:**
```typescript
/**
 * Asynchronously load the font from a URL or a filesystem. When done, call the callback
 * with two arguments `(err, font)`. The `err` will be null on success,
 * the `font` is a Font object.
 * We use the node.js callback convention so that
 * opentype.js can integrate with frameworks like async.js.
 * @alias opentype.load
 * @param  {string} url - The URL of the font to load.
 * @param  {Function} callback - The callback.
 */
```

**Parameters:**

- **`url`** `string`
- **`callback`** `Function`
- **`opt`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `loadFromUrl`
- `callback`
- `reject`
- `parseBuffer`
- `resolve`

<details><summary>Code</summary>

```typescript
function load(url, callback, opt) {
    opt = (opt === undefined || opt === null) ?  {} : opt;

    return new Promise(function (resolve, reject) {
        loadFromUrl(url, function(err, arrayBuffer) {
            if (err) {
                if (callback) {
                    return callback(err);
                } else {
                    reject(err);
                }
            }
            var font;
            try {
                font = parseBuffer(arrayBuffer, opt);
            } catch (e) {
                if (callback) {
                    return callback(e, null);
                } else {
                    reject(e);
                }
            }
            if (callback) {
                return callback(null, font);
            } else {
                resolve(font);
            }
        });
    });
}
```
</details>


---