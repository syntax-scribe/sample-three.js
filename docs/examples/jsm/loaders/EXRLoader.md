[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `EXRLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 71 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 261 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/EXRLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTextureLoader` | `three` |
| `DataUtils` | `three` |
| `FloatType` | `three` |
| `HalfFloatType` | `three` |
| `LinearFilter` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `RedFormat` | `three` |
| `RGFormat` | `three` |
| `RGBAFormat` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `USHORT_RANGE` | `number` | let/var | `( 1 << 16 )` | ✗ |
| `BITMAP_SIZE` | `number` | let/var | `( USHORT_RANGE >> 3 )` | ✗ |
| `HUF_ENCBITS` | `16` | let/var | `16` | ✗ |
| `HUF_DECBITS` | `14` | let/var | `14` | ✗ |
| `HUF_ENCSIZE` | `number` | let/var | `( 1 << HUF_ENCBITS ) + 1` | ✗ |
| `HUF_DECSIZE` | `number` | let/var | `1 << HUF_DECBITS` | ✗ |
| `HUF_DECMASK` | `number` | let/var | `HUF_DECSIZE - 1` | ✗ |
| `NBITS` | `16` | let/var | `16` | ✗ |
| `A_OFFSET` | `number` | let/var | `1 << ( NBITS - 1 )` | ✗ |
| `MOD_MASK` | `number` | let/var | `( 1 << NBITS ) - 1` | ✗ |
| `SHORT_ZEROCODE_RUN` | `59` | let/var | `59` | ✗ |
| `LONG_ZEROCODE_RUN` | `63` | let/var | `63` | ✗ |
| `SHORTEST_LONG_RUN` | `number` | let/var | `2 + LONG_ZEROCODE_RUN - SHORT_ZEROCODE_RUN` | ✗ |
| `ULONG_SIZE` | `8` | let/var | `8` | ✗ |
| `FLOAT32_SIZE` | `4` | let/var | `4` | ✗ |
| `INT32_SIZE` | `4` | let/var | `4` | ✗ |
| `INT16_SIZE` | `2` | let/var | `2` | ✗ |
| `INT8_SIZE` | `1` | let/var | `1` | ✗ |
| `STATIC_HUFFMAN` | `0` | let/var | `0` | ✗ |
| `DEFLATE` | `1` | let/var | `1` | ✗ |
| `UNKNOWN` | `0` | let/var | `0` | ✗ |
| `LOSSY_DCT` | `1` | let/var | `1` | ✗ |
| `RLE` | `2` | let/var | `2` | ✗ |
| `k` | `number` | let/var | `0` | ✗ |
| `n` | `number` | let/var | `k - 1` | ✗ |
| `getBitsReturn` | `{ l: number; c: number; lc: number; }` | let/var | `{ l: 0, c: 0, lc: 0 }` | ✗ |
| `hufTableBuffer` | `any[]` | let/var | `new Array( 59 )` | ✗ |
| `c` | `number` | let/var | `0` | ✗ |
| `nc` | `number` | let/var | `( ( c + hufTableBuffer[ i ] ) >> 1 )` | ✗ |
| `l` | `any` | let/var | `hcode[ i ]` | ✗ |
| `p` | `any` | let/var | `inOffset` | ✗ |
| `c` | `number` | let/var | `0` | ✗ |
| `lc` | `number` | let/var | `0` | ✗ |
| `l` | `number` | let/var | `getBitsReturn.l` | ✗ |
| `zerun` | `number` | let/var | `getBitsReturn.l + SHORTEST_LONG_RUN` | ✗ |
| `zerun` | `number` | let/var | `l - SHORT_ZEROCODE_RUN + 2` | ✗ |
| `pl` | `any` | let/var | `hdecod[ ( c >> ( l - HUF_DECBITS ) ) ]` | ✗ |
| `p` | `any` | let/var | `pl.p` | ✗ |
| `plOffset` | `number` | let/var | `0` | ✗ |
| `pl` | `any` | let/var | `hdecod[ ( c << ( HUF_DECBITS - l ) ) + plOffset ]` | ✗ |
| `getCharReturn` | `{ c: number; lc: number; }` | let/var | `{ c: 0, lc: 0 }` | ✗ |
| `getCodeReturn` | `{ c: number; lc: number; }` | let/var | `{ c: 0, lc: 0 }` | ✗ |
| `cs` | `number` | let/var | `( c >> lc )` | ✗ |
| `s` | `any` | let/var | `outBuffer[ outBufferOffset.value - 1 ]` | ✗ |
| `wdec14Return` | `{ a: number; b: number; }` | let/var | `{ a: 0, b: 0 }` | ✗ |
| `hi` | `number` | let/var | `hs` | ✗ |
| `ai` | `number` | let/var | `ls + ( hi & 1 ) + ( hi >> 1 )` | ✗ |
| `as` | `number` | let/var | `ai` | ✗ |
| `bs` | `number` | let/var | `ai - hi` | ✗ |
| `bb` | `number` | let/var | `( m - ( d >> 1 ) ) & MOD_MASK` | ✗ |
| `aa` | `number` | let/var | `( d + bb - A_OFFSET ) & MOD_MASK` | ✗ |
| `w14` | `boolean` | let/var | `mx < ( 1 << 14 )` | ✗ |
| `n` | `any` | let/var | `( nx > ny ) ? ny : nx` | ✗ |
| `p` | `number` | let/var | `1` | ✗ |
| `p2` | `any` | let/var | `*not shown*` | ✗ |
| `py` | `any` | let/var | `*not shown*` | ✗ |
| `ey` | `number` | let/var | `py + oy * ( ny - p2 )` | ✗ |
| `oy1` | `number` | let/var | `oy * p` | ✗ |
| `oy2` | `number` | let/var | `oy * p2` | ✗ |
| `ox1` | `number` | let/var | `ox * p` | ✗ |
| `ox2` | `number` | let/var | `ox * p2` | ✗ |
| `i00` | `any` | let/var | `*not shown*` | ✗ |
| `i01` | `any` | let/var | `*not shown*` | ✗ |
| `i10` | `any` | let/var | `*not shown*` | ✗ |
| `i11` | `any` | let/var | `*not shown*` | ✗ |
| `px` | `number` | let/var | `py` | ✗ |
| `ex` | `number` | let/var | `py + ox * ( nx - p2 )` | ✗ |
| `p01` | `number` | let/var | `px + ox1` | ✗ |
| `p10` | `number` | let/var | `px + oy1` | ✗ |
| `p11` | `number` | let/var | `p10 + ox1` | ✗ |
| `p10` | `number` | let/var | `px + oy1` | ✗ |
| `px` | `number` | let/var | `py` | ✗ |
| `ex` | `number` | let/var | `py + ox * ( nx - p2 )` | ✗ |
| `p01` | `number` | let/var | `px + ox1` | ✗ |
| `c` | `number` | let/var | `0` | ✗ |
| `lc` | `number` | let/var | `0` | ✗ |
| `outBufferEndOffset` | `any` | let/var | `no` | ✗ |
| `index` | `number` | let/var | `( c >> ( lc - HUF_DECBITS ) ) & HUF_DECMASK` | ✗ |
| `pl` | `any` | let/var | `decodingTable[ index ]` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `( 8 - ni ) & 7` | ✗ |
| `pl` | `any` | let/var | `decodingTable[ ( c << ( HUF_DECBITS - lc ) ) & HUF_DECMASK ]` | ✗ |
| `outOffset` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `initialInOffset` | `any` | let/var | `inOffset.value` | ✗ |
| `freq` | `any[]` | let/var | `new Array( HUF_ENCSIZE )` | ✗ |
| `hdec` | `any[]` | let/var | `new Array( HUF_DECSIZE )` | ✗ |
| `ni` | `number` | let/var | `nCompressed - ( inOffset.value - initialInOffset )` | ✗ |
| `d` | `number` | let/var | `source[ t - 1 ] + source[ t ] - 128` | ✗ |
| `t1` | `number` | let/var | `0` | ✗ |
| `s` | `number` | let/var | `0` | ✗ |
| `stop` | `number` | let/var | `source.length - 1` | ✗ |
| `size` | `any` | let/var | `source.byteLength` | ✗ |
| `out` | `any[]` | let/var | `new Array()` | ✗ |
| `p` | `number` | let/var | `0` | ✗ |
| `reader` | `DataView<any>` | let/var | `new DataView( source )` | ✗ |
| `count` | `number` | let/var | `- l` | ✗ |
| `count` | `number` | let/var | `l` | ✗ |
| `dataView` | `DataView<any>` | let/var | `new DataView( outBuffer.buffer )` | ✗ |
| `width` | `any` | let/var | `channelData[ cscSet.idx[ 0 ] ].width` | ✗ |
| `height` | `any` | let/var | `channelData[ cscSet.idx[ 0 ] ].height` | ✗ |
| `numComp` | `3` | let/var | `3` | ✗ |
| `leftoverX` | `number` | let/var | `width - ( numBlocksX - 1 ) * 8` | ✗ |
| `leftoverY` | `number` | let/var | `height - ( numBlocksY - 1 ) * 8` | ✗ |
| `currAcComp` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `currDcComp` | `any[]` | let/var | `new Array( numComp )` | ✗ |
| `dctData` | `any[]` | let/var | `new Array( numComp )` | ✗ |
| `halfZigBlock` | `any[]` | let/var | `new Array( numComp )` | ✗ |
| `rowBlock` | `any[]` | let/var | `new Array( numComp )` | ✗ |
| `rowOffsets` | `any[]` | let/var | `new Array( numComp )` | ✗ |
| `maxY` | `number` | let/var | `8` | ✗ |
| `maxX` | `number` | let/var | `8` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `type` | `any` | let/var | `channelData[ cscSet.idx[ comp ] ].type` | ✗ |
| `src` | `number` | let/var | `blockx * 64 + ( ( y & 0x7 ) * 8 )` | ✗ |
| `offset` | `any` | let/var | `rowOffsets[ comp ][ y ] + 8 * numFullBlocksX * INT16_SIZE * type` | ✗ |
| `src` | `number` | let/var | `numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 )` | ✗ |
| `halfRow` | `Uint16Array<any>` | let/var | `new Uint16Array( width )` | ✗ |
| `type` | `any` | let/var | `channelData[ cscSet.idx[ comp ] ].type` | ✗ |
| `offset` | `any` | let/var | `rowOffsets[ comp ][ y ]` | ✗ |
| `dataView` | `DataView<any>` | let/var | `new DataView( outBuffer.buffer )` | ✗ |
| `cd` | `any` | let/var | `channelData[ channelIndex ]` | ✗ |
| `width` | `any` | let/var | `cd.width` | ✗ |
| `height` | `any` | let/var | `cd.height` | ✗ |
| `leftoverX` | `number` | let/var | `width - ( numBlocksX - 1 ) * 8` | ✗ |
| `leftoverY` | `number` | let/var | `height - ( numBlocksY - 1 ) * 8` | ✗ |
| `currAcComp` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `currDcComp` | `number` | let/var | `0` | ✗ |
| `dctData` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 64 )` | ✗ |
| `halfZigBlock` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array( 64 )` | ✗ |
| `rowBlock` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array( numBlocksX * 64 )` | ✗ |
| `maxY` | `number` | let/var | `8` | ✗ |
| `offset` | `any` | let/var | `rowPtrs[ channelIndex ][ y ]` | ✗ |
| `src` | `number` | let/var | `blockx * 64 + ( ( y & 0x7 ) * 8 )` | ✗ |
| `src` | `number` | let/var | `numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 )` | ✗ |
| `acValue` | `any` | let/var | `*not shown*` | ✗ |
| `dctComp` | `number` | let/var | `1` | ✗ |
| `a` | `number` | let/var | `0.5 * Math.cos( 3.14159 / 4.0 )` | ✗ |
| `b` | `number` | let/var | `0.5 * Math.cos( 3.14159 / 16.0 )` | ✗ |
| `c` | `number` | let/var | `0.5 * Math.cos( 3.14159 / 8.0 )` | ✗ |
| `d` | `number` | let/var | `0.5 * Math.cos( 3.0 * 3.14159 / 16.0 )` | ✗ |
| `e` | `number` | let/var | `0.5 * Math.cos( 5.0 * 3.14159 / 16.0 )` | ✗ |
| `f` | `number` | let/var | `0.5 * Math.cos( 3.0 * 3.14159 / 8.0 )` | ✗ |
| `g` | `number` | let/var | `0.5 * Math.cos( 7.0 * 3.14159 / 16.0 )` | ✗ |
| `alpha` | `any[]` | let/var | `new Array( 4 )` | ✗ |
| `beta` | `any[]` | let/var | `new Array( 4 )` | ✗ |
| `theta` | `any[]` | let/var | `new Array( 4 )` | ✗ |
| `gamma` | `any[]` | let/var | `new Array( 4 )` | ✗ |
| `rowPtr` | `number` | let/var | `row * 8` | ✗ |
| `y` | `any` | let/var | `data[ 0 ][ i ]` | ✗ |
| `cb` | `any` | let/var | `data[ 1 ][ i ]` | ✗ |
| `cr` | `any` | let/var | `data[ 2 ][ i ]` | ✗ |
| `rawBuffer` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( decodeRunLength( compressed ) )` | ✗ |
| `tmpBuffer` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( rawBuffer.length )` | ✗ |
| `tmpBuffer` | `Uint8Array<any>` | let/var | `new Uint8Array( rawBuffer.length )` | ✗ |
| `inDataView` | `any` | let/var | `info.viewer` | ✗ |
| `inOffset` | `{ value: any; }` | let/var | `{ value: info.offset.value }` | ✗ |
| `outBuffer` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array( info.columns * info.lines * ( info.inputChannels.length * in...` | ✗ |
| `bitmap` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( BITMAP_SIZE )` | ✗ |
| `outBufferEnd` | `number` | let/var | `0` | ✗ |
| `pizChannelData` | `any[]` | let/var | `new Array( info.inputChannels.length )` | ✗ |
| `lut` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array( USHORT_RANGE )` | ✗ |
| `cd` | `any` | let/var | `pizChannelData[ i ]` | ✗ |
| `tmpOffset` | `number` | let/var | `0` | ✗ |
| `tmpBuffer` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( outBuffer.buffer.byteLength )` | ✗ |
| `cd` | `any` | let/var | `pizChannelData[ c ]` | ✗ |
| `n` | `number` | let/var | `cd.nx * cd.size` | ✗ |
| `cp` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( outBuffer.buffer, cd.end * INT16_SIZE, n * INT16_SIZE )` | ✗ |
| `byteSize` | `number` | let/var | `info.inputChannels.length * info.lines * info.columns * info.totalBytes` | ✗ |
| `tmpBuffer` | `ArrayBuffer` | let/var | `new ArrayBuffer( byteSize )` | ✗ |
| `viewer` | `DataView<ArrayBuffer>` | let/var | `new DataView( tmpBuffer )` | ✗ |
| `tmpBufferEnd` | `number` | let/var | `0` | ✗ |
| `writePtr` | `number` | let/var | `0` | ✗ |
| `ptr` | `any[]` | let/var | `new Array( 4 )` | ✗ |
| `pixel` | `number` | let/var | `0` | ✗ |
| `type` | `any` | let/var | `info.inputChannels[ c ].pixelType` | ✗ |
| `diff` | `number` | let/var | `( rawBuffer[ ptr[ 0 ] ++ ] << 8 ) \| rawBuffer[ ptr[ 1 ] ++ ]` | ✗ |
| `diff` | `number` | let/var | `( rawBuffer[ ptr[ 0 ] ++ ] << 24 ) \| ( rawBuffer[ ptr[ 1 ] ++ ] << 16 ) \| (...` | ✗ |
| `inDataView` | `any` | let/var | `info.viewer` | ✗ |
| `inOffset` | `{ value: any; }` | let/var | `{ value: info.offset.value }` | ✗ |
| `outBuffer` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( info.columns * info.lines * ( info.inputChannels.length * inf...` | ✗ |
| `dwaHeader` | `{ version: any; unknownUncompressedSi...` | let/var | `{ version: parseInt64( inDataView, inOffset ), unknownUncompressedSize: parse...` | ✗ |
| `channelRules` | `any[]` | let/var | `new Array()` | ✗ |
| `ruleSize` | `number` | let/var | `parseUint16( inDataView, inOffset ) - INT16_SIZE` | ✗ |
| `compression` | `number` | let/var | `( value >> 2 ) & 3` | ✗ |
| `csc` | `number` | let/var | `( value >> 4 ) - 1` | ✗ |
| `index` | `number` | let/var | `new Int8Array( [ csc ] )[ 0 ]` | ✗ |
| `channels` | `any` | let/var | `EXRHeader.channels` | ✗ |
| `channelData` | `any[]` | let/var | `new Array( info.inputChannels.length )` | ✗ |
| `cd` | `{}` | let/var | `channelData[ i ] = {}` | ✗ |
| `channel` | `any` | let/var | `channels[ i ]` | ✗ |
| `cscSet` | `{ idx: any[]; }` | let/var | `{ idx: new Array( 3 ) }` | ✗ |
| `cd` | `any` | let/var | `channelData[ offset ]` | ✗ |
| `rule` | `any` | let/var | `channelRules[ i ]` | ✗ |
| `acBuffer` | `any` | let/var | `*not shown*` | ✗ |
| `dcBuffer` | `any` | let/var | `*not shown*` | ✗ |
| `rleBuffer` | `any` | let/var | `*not shown*` | ✗ |
| `zlibInfo` | `{ array: any; offset: { value: any; }...` | let/var | `{ array: info.array, offset: inOffset, size: dwaHeader.dcCompressedSize }` | ✗ |
| `outBufferEnd` | `number` | let/var | `0` | ✗ |
| `rowOffsets` | `any[]` | let/var | `new Array( channelData.length )` | ✗ |
| `cd` | `any` | let/var | `channelData[ i ]` | ✗ |
| `row` | `number` | let/var | `0` | ✗ |
| `rleOffset` | `number` | let/var | `0` | ✗ |
| `rowOffsetBytes` | `any` | let/var | `rowOffsets[ i ][ row ]` | ✗ |
| `uintBuffer` | `Uint8Array<any>` | let/var | `new Uint8Array( buffer )` | ✗ |
| `endOffset` | `number` | let/var | `0` | ✗ |
| `Uint8` | `any` | let/var | `uInt8Array[ offset.value ]` | ✗ |
| `int` | `any` | let/var | `*not shown*` | ✗ |
| `exponent` | `number` | let/var | `( binary & 0x7C00 ) >> 10` | ✗ |
| `fraction` | `number` | let/var | `binary & 0x03FF` | ✗ |
| `startOffset` | `any` | let/var | `offset.value` | ✗ |
| `channels` | `any[]` | let/var | `[]` | ✗ |
| `compressionCodes` | `string[]` | let/var | `[ 'NO_COMPRESSION', 'RLE_COMPRESSION', 'ZIPS_COMPRESSION', 'ZIP_COMPRESSION',...` | ✗ |
| `lineOrders` | `string[]` | let/var | `[ 'INCREASING_Y', 'DECREASING_Y', 'RANDOM_Y', ]` | ✗ |
| `envmaps` | `string[]` | let/var | `[ 'ENVMAP_LATLONG', 'ENVMAP_CUBE' ]` | ✗ |
| `levelModes` | `string[]` | let/var | `[ 'ONE_LEVEL', 'MIPMAP_LEVELS', 'RIPMAP_LEVELS', ]` | ✗ |
| `roundingModes` | `string[]` | let/var | `[ 'ROUND_DOWN', 'ROUND_UP', ]` | ✗ |
| `num` | `number` | let/var | `0` | ✗ |
| `tiles` | `any[]` | let/var | `new Array( count )` | ✗ |
| `b` | `number` | let/var | `( 1 << i )` | ✗ |
| `s` | `number` | let/var | `( dataSize / b ) \| 0` | ✗ |
| `EXRDecoder` | `any` | let/var | `this` | ✗ |
| `offset` | `any` | let/var | `EXRDecoder.offset` | ✗ |
| `tmpOffset` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `startX` | `number` | let/var | `tileX * EXRDecoder.blockWidth` | ✗ |
| `startY` | `number` | let/var | `tileY * EXRDecoder.blockHeight` | ✗ |
| `bytesBlockLine` | `number` | let/var | `EXRDecoder.columns * EXRDecoder.totalBytes` | ✗ |
| `isCompressed` | `boolean` | let/var | `EXRDecoder.size < EXRDecoder.lines * bytesBlockLine` | ✗ |
| `viewer` | `any` | let/var | `isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder )` | ✗ |
| `lineOffset` | `number` | let/var | `line * EXRDecoder.columns * EXRDecoder.totalBytes` | ✗ |
| `name` | `any` | let/var | `EXRHeader.channels[ channelID ].name` | ✗ |
| `lOff` | `number` | let/var | `EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns` | ✗ |
| `cOff` | `any` | let/var | `EXRDecoder.decodeChannels[ name ]` | ✗ |
| `outLineOffset` | `number` | let/var | `( EXRDecoder.height - ( 1 + startY + line ) ) * EXRDecoder.outLineWidth` | ✗ |
| `outIndex` | `any` | let/var | `outLineOffset + ( x + startX ) * EXRDecoder.outputChannels + cOff` | ✗ |
| `EXRDecoder` | `any` | let/var | `this` | ✗ |
| `offset` | `any` | let/var | `EXRDecoder.offset` | ✗ |
| `tmpOffset` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `line` | `number` | let/var | `parseInt32( EXRDecoder.viewer, offset ) - EXRHeader.dataWindow.yMin` | ✗ |
| `bytesPerLine` | `number` | let/var | `EXRDecoder.columns * EXRDecoder.totalBytes` | ✗ |
| `isCompressed` | `boolean` | let/var | `EXRDecoder.size < EXRDecoder.lines * bytesPerLine` | ✗ |
| `viewer` | `any` | let/var | `isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder )` | ✗ |
| `scan_y` | `number` | let/var | `scanlineBlockIdx * EXRDecoder.blockHeight` | ✗ |
| `true_y` | `any` | let/var | `line_y + EXRDecoder.scanOrder( scan_y )` | ✗ |
| `lineOffset` | `number` | let/var | `line_y * bytesPerLine` | ✗ |
| `outLineOffset` | `number` | let/var | `( EXRDecoder.height - 1 - true_y ) * EXRDecoder.outLineWidth` | ✗ |
| `name` | `any` | let/var | `EXRHeader.channels[ channelID ].name` | ✗ |
| `lOff` | `number` | let/var | `EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns` | ✗ |
| `cOff` | `any` | let/var | `EXRDecoder.decodeChannels[ name ]` | ✗ |
| `outIndex` | `any` | let/var | `outLineOffset + x * EXRDecoder.outputChannels + cOff` | ✗ |
| `EXRHeader` | `{ version: any; spec: { singleTile: b...` | let/var | `{}` | ✗ |
| `keepReading` | `boolean` | let/var | `true` | ✗ |
| `EXRDecoder` | `{ size: number; viewer: any; array: a...` | let/var | `{ size: 0, viewer: dataView, array: uInt8Array, offset: offset, width: EXRHea...` | ✗ |
| `channels` | `{}` | let/var | `{}` | ✗ |
| `fillAlpha` | `boolean` | let/var | `false` | ✗ |
| `invalidOutput` | `boolean` | let/var | `false` | ✗ |
| `size` | `number` | let/var | `EXRDecoder.width * EXRDecoder.height * EXRDecoder.outputChannels` | ✗ |
| `byteOffset` | `number` | let/var | `0` | ✗ |
| `offset` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `bufferDataView` | `DataView<ArrayBuffer>` | let/var | `new DataView( buffer )` | ✗ |
| `uInt8Array` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( buffer )` | ✗ |
| `byteArray` | `any` | let/var | `EXRDecoder.byteArray` | ✗ |


---

## Functions

### `EXRLoader.parse(buffer: ArrayBuffer): DataTextureLoader`

**JSDoc:**
```typescript
/**
	 * Parses the given EXR texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @return {DataTextureLoader~TexData} An object representing the parsed texture data.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`

**Returns:** `DataTextureLoader`

**Calls:**

- `Math.pow`
- `parseUint8Array`
- `getBits`
- `hufCanonicalCodeTable`
- `hufCode`
- `hufLength`
- `getChar`
- `UInt16`
- `Int16`
- `wdec14`
- `wdec16`
- `Math.trunc`
- `getCode`
- `parseUint32`
- `hufClearDecTable`
- `hufUnpackEncTable`
- `hufBuildDecTable`
- `hufDecode`
- `Math.floor`
- `reader.getInt8`
- `out.push`
- `reader.getUint8`
- `Math.ceil`
- `halfZigBlock[ comp ].fill`
- `unRleAC`
- `unZigZag`
- `dctInverse`
- `csc709Inverse`
- `convertToHalf`
- `dataView.setUint16`
- `dataView.getUint16`
- `dataView.setFloat32`
- `decodeFloat16`
- `halfZigBlock.fill`
- `Math.cos`
- `DataUtils.toHalfFloat`
- `toLinear`
- `Math.sign`
- `Math.abs`
- `info.viewer.buffer.slice`
- `decodeRunLength`
- `predictor`
- `interleaveScalar`
- `info.array.slice`
- `fflate.unzlibSync`
- `parseUint16`
- `parseUint8`
- `reverseLutFromBitmap`
- `hufUncompress`
- `wav2Decode`
- `applyLut`
- `tmpBuffer.set`
- `viewer.setUint16`
- `viewer.setUint32`
- `parseInt64`
- `parseNullTerminatedString`
- `channelRules.push`
- `uncompressZIP`
- `rowOffsets[ chan ].push`
- `lossyDctDecode`
- `lossyDctChannelDecode`
- `new TextDecoder().decode`
- `uintBuffer.slice`
- `new Uint8Array( buffer ).slice`
- `parseInt32`
- `dataView.getInt32`
- `dataView.getUint32`
- `dataView.getUint8`
- `Number`
- `dataView.getBigInt64`
- `dataView.getFloat32`
- `parseFloat32`
- `channels.push`
- `parseFixedLengthString`
- `parseChlist`
- `parseChromaticities`
- `parseCompression`
- `parseBox2i`
- `parseEnvmap`
- `parseTiledesc`
- `parseLineOrder`
- `parseV2f`
- `parseV3f`
- `parseRational`
- `parseTimecode`
- `Math.log2`
- `roundLog2`
- `Math.max`
- `EXRDecoder.uncompress`
- `uncompressRAW`
- `EXRDecoder.getter`
- `EXRDecoder.scanOrder`
- `parseValue`
- `console.warn`
- `console.error`
- `EXRDecoder.byteArray.fill`
- `calculateTileLevels`
- `calculateTiles`
- `parseTiles.bind`
- `parseScanline.bind`
- `parseHeader`
- `setupDecoder`
- `EXRDecoder.decode`

**Internal Comments:**
```
// set block DC component (x5)
// set block AC components (x3)
// UnZigZag block to float (x3)
// decode float dct (x3)
// handle partial X blocks
// convert channels back to float, if needed
// Write decoded data to output buffer
// Setup channel info (x2)
// Read range compression data (x2)
// Reverse LUT (x2)
// Huffman decoding (x3)
// Wavelet decoding
// Expand the pixel data to their original range (x3)
// Rearrange the pixel data into the format expected by the caller. (x2)
// Read compression header information (x2)
// Read channel ruleset information (x2)
// Classify channels (x2)
// Read DCT - AC component data
// Read DCT - DC component data
// Read RLE compressed data
// Prepare outbuffer data offset (x2)
// Decode lossy DCT data if we have a valid color space conversion set with the first RGB channel present
// Decode other channels
// https://stackoverflow.com/questions/5678432/decompressing-half-precision-floats-in-javascript
// start of header (x4)
// RGB images will be converted to RGBA format, preventing software emulation in select devices. (x2)
// Validate if input texture contain supported channels
// Setup output texture configuration
// half
// float
// Fill initially with 1s for the alpha value if the texture is not RGBA, RGB values will be overwritten
// const numYLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height ); (x2)
// start parsing file [START] (x2)
// get header information and validate format. (x2)
// get input compression information and prepare decoding. (x2)
// parse input data (x4)
// output texture post-processing
```

<details><summary>Code</summary>

```typescript
parse( buffer ) {

		const USHORT_RANGE = ( 1 << 16 );
		const BITMAP_SIZE = ( USHORT_RANGE >> 3 );

		const HUF_ENCBITS = 16; // literal (value) bit length
		const HUF_DECBITS = 14; // decoding bit size (>= 8)

		const HUF_ENCSIZE = ( 1 << HUF_ENCBITS ) + 1; // encoding table size
		const HUF_DECSIZE = 1 << HUF_DECBITS; // decoding table size
		const HUF_DECMASK = HUF_DECSIZE - 1;

		const NBITS = 16;
		const A_OFFSET = 1 << ( NBITS - 1 );
		const MOD_MASK = ( 1 << NBITS ) - 1;

		const SHORT_ZEROCODE_RUN = 59;
		const LONG_ZEROCODE_RUN = 63;
		const SHORTEST_LONG_RUN = 2 + LONG_ZEROCODE_RUN - SHORT_ZEROCODE_RUN;

		const ULONG_SIZE = 8;
		const FLOAT32_SIZE = 4;
		const INT32_SIZE = 4;
		const INT16_SIZE = 2;
		const INT8_SIZE = 1;

		const STATIC_HUFFMAN = 0;
		const DEFLATE = 1;

		const UNKNOWN = 0;
		const LOSSY_DCT = 1;
		const RLE = 2;

		const logBase = Math.pow( 2.7182818, 2.2 );

		function reverseLutFromBitmap( bitmap, lut ) {

			let k = 0;

			for ( let i = 0; i < USHORT_RANGE; ++ i ) {

				if ( ( i == 0 ) || ( bitmap[ i >> 3 ] & ( 1 << ( i & 7 ) ) ) ) {

					lut[ k ++ ] = i;

				}

			}

			const n = k - 1;

			while ( k < USHORT_RANGE ) lut[ k ++ ] = 0;

			return n;

		}

		function hufClearDecTable( hdec ) {

			for ( let i = 0; i < HUF_DECSIZE; i ++ ) {

				hdec[ i ] = {};
				hdec[ i ].len = 0;
				hdec[ i ].lit = 0;
				hdec[ i ].p = null;

			}

		}

		const getBitsReturn = { l: 0, c: 0, lc: 0 };

		function getBits( nBits, c, lc, uInt8Array, inOffset ) {

			while ( lc < nBits ) {

				c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
				lc += 8;

			}

			lc -= nBits;

			getBitsReturn.l = ( c >> lc ) & ( ( 1 << nBits ) - 1 );
			getBitsReturn.c = c;
			getBitsReturn.lc = lc;

		}

		const hufTableBuffer = new Array( 59 );

		function hufCanonicalCodeTable( hcode ) {

			for ( let i = 0; i <= 58; ++ i ) hufTableBuffer[ i ] = 0;
			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) hufTableBuffer[ hcode[ i ] ] += 1;

			let c = 0;

			for ( let i = 58; i > 0; -- i ) {

				const nc = ( ( c + hufTableBuffer[ i ] ) >> 1 );
				hufTableBuffer[ i ] = c;
				c = nc;

			}

			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) {

				const l = hcode[ i ];
				if ( l > 0 ) hcode[ i ] = l | ( hufTableBuffer[ l ] ++ << 6 );

			}

		}

		function hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, hcode ) {

			const p = inOffset;
			let c = 0;
			let lc = 0;

			for ( ; im <= iM; im ++ ) {

				if ( p.value - inOffset.value > ni ) return false;

				getBits( 6, c, lc, uInt8Array, p );

				const l = getBitsReturn.l;
				c = getBitsReturn.c;
				lc = getBitsReturn.lc;

				hcode[ im ] = l;

				if ( l == LONG_ZEROCODE_RUN ) {

					if ( p.value - inOffset.value > ni ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					getBits( 8, c, lc, uInt8Array, p );

					let zerun = getBitsReturn.l + SHORTEST_LONG_RUN;
					c = getBitsReturn.c;
					lc = getBitsReturn.lc;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				} else if ( l >= SHORT_ZEROCODE_RUN ) {

					let zerun = l - SHORT_ZEROCODE_RUN + 2;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				}

			}

			hufCanonicalCodeTable( hcode );

		}

		function hufLength( code ) {

			return code & 63;

		}

		function hufCode( code ) {

			return code >> 6;

		}

		function hufBuildDecTable( hcode, im, iM, hdecod ) {

			for ( ; im <= iM; im ++ ) {

				const c = hufCode( hcode[ im ] );
				const l = hufLength( hcode[ im ] );

				if ( c >> l ) {

					throw new Error( 'Invalid table entry' );

				}

				if ( l > HUF_DECBITS ) {

					const pl = hdecod[ ( c >> ( l - HUF_DECBITS ) ) ];

					if ( pl.len ) {

						throw new Error( 'Invalid table entry' );

					}

					pl.lit ++;

					if ( pl.p ) {

						const p = pl.p;
						pl.p = new Array( pl.lit );

						for ( let i = 0; i < pl.lit - 1; ++ i ) {

							pl.p[ i ] = p[ i ];

						}

					} else {

						pl.p = new Array( 1 );

					}

					pl.p[ pl.lit - 1 ] = im;

				} else if ( l ) {

					let plOffset = 0;

					for ( let i = 1 << ( HUF_DECBITS - l ); i > 0; i -- ) {

						const pl = hdecod[ ( c << ( HUF_DECBITS - l ) ) + plOffset ];

						if ( pl.len || pl.p ) {

							throw new Error( 'Invalid table entry' );

						}

						pl.len = l;
						pl.lit = im;

						plOffset ++;

					}

				}

			}

			return true;

		}

		const getCharReturn = { c: 0, lc: 0 };

		function getChar( c, lc, uInt8Array, inOffset ) {

			c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
			lc += 8;

			getCharReturn.c = c;
			getCharReturn.lc = lc;

		}

		const getCodeReturn = { c: 0, lc: 0 };

		function getCode( po, rlc, c, lc, uInt8Array, inOffset, outBuffer, outBufferOffset, outBufferEndOffset ) {

			if ( po == rlc ) {

				if ( lc < 8 ) {

					getChar( c, lc, uInt8Array, inOffset );
					c = getCharReturn.c;
					lc = getCharReturn.lc;

				}

				lc -= 8;

				let cs = ( c >> lc );
				cs = new Uint8Array( [ cs ] )[ 0 ];

				if ( outBufferOffset.value + cs > outBufferEndOffset ) {

					return false;

				}

				const s = outBuffer[ outBufferOffset.value - 1 ];

				while ( cs -- > 0 ) {

					outBuffer[ outBufferOffset.value ++ ] = s;

				}

			} else if ( outBufferOffset.value < outBufferEndOffset ) {

				outBuffer[ outBufferOffset.value ++ ] = po;

			} else {

				return false;

			}

			getCodeReturn.c = c;
			getCodeReturn.lc = lc;

		}

		function UInt16( value ) {

			return ( value & 0xFFFF );

		}

		function Int16( value ) {

			const ref = UInt16( value );
			return ( ref > 0x7FFF ) ? ref - 0x10000 : ref;

		}

		const wdec14Return = { a: 0, b: 0 };

		function wdec14( l, h ) {

			const ls = Int16( l );
			const hs = Int16( h );

			const hi = hs;
			const ai = ls + ( hi & 1 ) + ( hi >> 1 );

			const as = ai;
			const bs = ai - hi;

			wdec14Return.a = as;
			wdec14Return.b = bs;

		}

		function wdec16( l, h ) {

			const m = UInt16( l );
			const d = UInt16( h );

			const bb = ( m - ( d >> 1 ) ) & MOD_MASK;
			const aa = ( d + bb - A_OFFSET ) & MOD_MASK;

			wdec14Return.a = aa;
			wdec14Return.b = bb;

		}

		function wav2Decode( buffer, j, nx, ox, ny, oy, mx ) {

			const w14 = mx < ( 1 << 14 );
			const n = ( nx > ny ) ? ny : nx;
			let p = 1;
			let p2;
			let py;

			while ( p <= n ) p <<= 1;

			p >>= 1;
			p2 = p;
			p >>= 1;

			while ( p >= 1 ) {

				py = 0;
				const ey = py + oy * ( ny - p2 );
				const oy1 = oy * p;
				const oy2 = oy * p2;
				const ox1 = ox * p;
				const ox2 = ox * p2;
				let i00, i01, i10, i11;

				for ( ; py <= ey; py += oy2 ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;
						const p10 = px + oy1;
						const p11 = p10 + ox1;

						if ( w14 ) {

							wdec14( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec14( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec14( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec14( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;

						} else {

							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec16( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec16( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec16( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;


						}

					}

					if ( nx & p ) {

						const p10 = px + oy1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p10 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

						i00 = wdec14Return.a;
						buffer[ p10 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				if ( ny & p ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p01 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p01 + j ] );

						i00 = wdec14Return.a;
						buffer[ p01 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				p2 = p;
				p >>= 1;

			}

			return py;

		}

		function hufDecode( encodingTable, decodingTable, uInt8Array, inOffset, ni, rlc, no, outBuffer, outOffset ) {

			let c = 0;
			let lc = 0;
			const outBufferEndOffset = no;
			const inOffsetEnd = Math.trunc( inOffset.value + ( ni + 7 ) / 8 );

			while ( inOffset.value < inOffsetEnd ) {

				getChar( c, lc, uInt8Array, inOffset );

				c = getCharReturn.c;
				lc = getCharReturn.lc;

				while ( lc >= HUF_DECBITS ) {

					const index = ( c >> ( lc - HUF_DECBITS ) ) & HUF_DECMASK;
					const pl = decodingTable[ index ];

					if ( pl.len ) {

						lc -= pl.len;

						getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

						c = getCodeReturn.c;
						lc = getCodeReturn.lc;

					} else {

						if ( ! pl.p ) {

							throw new Error( 'hufDecode issues' );

						}

						let j;

						for ( j = 0; j < pl.lit; j ++ ) {

							const l = hufLength( encodingTable[ pl.p[ j ] ] );

							while ( lc < l && inOffset.value < inOffsetEnd ) {

								getChar( c, lc, uInt8Array, inOffset );

								c = getCharReturn.c;
								lc = getCharReturn.lc;

							}

							if ( lc >= l ) {

								if ( hufCode( encodingTable[ pl.p[ j ] ] ) == ( ( c >> ( lc - l ) ) & ( ( 1 << l ) - 1 ) ) ) {

									lc -= l;

									getCode( pl.p[ j ], rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

									c = getCodeReturn.c;
									lc = getCodeReturn.lc;

									break;

								}

							}

						}

						if ( j == pl.lit ) {

							throw new Error( 'hufDecode issues' );

						}

					}

				}

			}

			const i = ( 8 - ni ) & 7;

			c >>= i;
			lc -= i;

			while ( lc > 0 ) {

				const pl = decodingTable[ ( c << ( HUF_DECBITS - lc ) ) & HUF_DECMASK ];

				if ( pl.len ) {

					lc -= pl.len;

					getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

					c = getCodeReturn.c;
					lc = getCodeReturn.lc;

				} else {

					throw new Error( 'hufDecode issues' );

				}

			}

			return true;

		}

		function hufUncompress( uInt8Array, inDataView, inOffset, nCompressed, outBuffer, nRaw ) {

			const outOffset = { value: 0 };
			const initialInOffset = inOffset.value;

			const im = parseUint32( inDataView, inOffset );
			const iM = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			const nBits = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			if ( im < 0 || im >= HUF_ENCSIZE || iM < 0 || iM >= HUF_ENCSIZE ) {

				throw new Error( 'Something wrong with HUF_ENCSIZE' );

			}

			const freq = new Array( HUF_ENCSIZE );
			const hdec = new Array( HUF_DECSIZE );

			hufClearDecTable( hdec );

			const ni = nCompressed - ( inOffset.value - initialInOffset );

			hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, freq );

			if ( nBits > 8 * ( nCompressed - ( inOffset.value - initialInOffset ) ) ) {

				throw new Error( 'Something wrong with hufUncompress' );

			}

			hufBuildDecTable( freq, im, iM, hdec );

			hufDecode( freq, hdec, uInt8Array, inOffset, nBits, iM, nRaw, outBuffer, outOffset );

		}

		function applyLut( lut, data, nData ) {

			for ( let i = 0; i < nData; ++ i ) {

				data[ i ] = lut[ data[ i ] ];

			}

		}

		function predictor( source ) {

			for ( let t = 1; t < source.length; t ++ ) {

				const d = source[ t - 1 ] + source[ t ] - 128;
				source[ t ] = d;

			}

		}

		function interleaveScalar( source, out ) {

			let t1 = 0;
			let t2 = Math.floor( ( source.length + 1 ) / 2 );
			let s = 0;
			const stop = source.length - 1;

			while ( true ) {

				if ( s > stop ) break;
				out[ s ++ ] = source[ t1 ++ ];

				if ( s > stop ) break;
				out[ s ++ ] = source[ t2 ++ ];

			}

		}

		function decodeRunLength( source ) {

			let size = source.byteLength;
			const out = new Array();
			let p = 0;

			const reader = new DataView( source );

			while ( size > 0 ) {

				const l = reader.getInt8( p ++ );

				if ( l < 0 ) {

					const count = - l;
					size -= count + 1;

					for ( let i = 0; i < count; i ++ ) {

						out.push( reader.getUint8( p ++ ) );

					}


				} else {

					const count = l;
					size -= 2;

					const value = reader.getUint8( p ++ );

					for ( let i = 0; i < count + 1; i ++ ) {

						out.push( value );

					}

				}

			}

			return out;

		}

		function lossyDctDecode( cscSet, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			let dataView = new DataView( outBuffer.buffer );

			const width = channelData[ cscSet.idx[ 0 ] ].width;
			const height = channelData[ cscSet.idx[ 0 ] ].height;

			const numComp = 3;

			const numFullBlocksX = Math.floor( width / 8.0 );
			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			const currDcComp = new Array( numComp );
			const dctData = new Array( numComp );
			const halfZigBlock = new Array( numComp );
			const rowBlock = new Array( numComp );
			const rowOffsets = new Array( numComp );

			for ( let comp = 0; comp < numComp; ++ comp ) {

				rowOffsets[ comp ] = rowPtrs[ cscSet.idx[ comp ] ];
				currDcComp[ comp ] = ( comp < 1 ) ? 0 : currDcComp[ comp - 1 ] + numBlocksX * numBlocksY;
				dctData[ comp ] = new Float32Array( 64 );
				halfZigBlock[ comp ] = new Uint16Array( 64 );
				rowBlock[ comp ] = new Uint16Array( numBlocksX * 64 );

			}

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 )
					maxY = leftoverY;

				let maxX = 8;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					if ( blockx == numBlocksX - 1 )
						maxX = leftoverX;

					for ( let comp = 0; comp < numComp; ++ comp ) {

						halfZigBlock[ comp ].fill( 0 );

						// set block DC component
						halfZigBlock[ comp ][ 0 ] = dcBuffer[ currDcComp[ comp ] ++ ];
						// set block AC components
						unRleAC( currAcComp, acBuffer, halfZigBlock[ comp ] );

						// UnZigZag block to float
						unZigZag( halfZigBlock[ comp ], dctData[ comp ] );
						// decode float dct
						dctInverse( dctData[ comp ] );

					}

					if ( numComp == 3 ) {

						csc709Inverse( dctData );

					}

					for ( let comp = 0; comp < numComp; ++ comp ) {

						convertToHalf( dctData[ comp ], rowBlock[ comp ], blockx * 64 );

					}

				} // blockx

				let offset = 0;

				for ( let comp = 0; comp < numComp; ++ comp ) {

					const type = channelData[ cscSet.idx[ comp ] ].type;

					for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

						offset = rowOffsets[ comp ][ y ];

						for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

							const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

							dataView.setUint16( offset + 0 * INT16_SIZE * type, rowBlock[ comp ][ src + 0 ], true );
							dataView.setUint16( offset + 1 * INT16_SIZE * type, rowBlock[ comp ][ src + 1 ], true );
							dataView.setUint16( offset + 2 * INT16_SIZE * type, rowBlock[ comp ][ src + 2 ], true );
							dataView.setUint16( offset + 3 * INT16_SIZE * type, rowBlock[ comp ][ src + 3 ], true );

							dataView.setUint16( offset + 4 * INT16_SIZE * type, rowBlock[ comp ][ src + 4 ], true );
							dataView.setUint16( offset + 5 * INT16_SIZE * type, rowBlock[ comp ][ src + 5 ], true );
							dataView.setUint16( offset + 6 * INT16_SIZE * type, rowBlock[ comp ][ src + 6 ], true );
							dataView.setUint16( offset + 7 * INT16_SIZE * type, rowBlock[ comp ][ src + 7 ], true );

							offset += 8 * INT16_SIZE * type;

						}

					}

					// handle partial X blocks
					if ( numFullBlocksX != numBlocksX ) {

						for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

							const offset = rowOffsets[ comp ][ y ] + 8 * numFullBlocksX * INT16_SIZE * type;
							const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

							for ( let x = 0; x < maxX; ++ x ) {

								dataView.setUint16( offset + x * INT16_SIZE * type, rowBlock[ comp ][ src + x ], true );

							}

						}

					}

				} // comp

			} // blocky

			const halfRow = new Uint16Array( width );
			dataView = new DataView( outBuffer.buffer );

			// convert channels back to float, if needed
			for ( let comp = 0; comp < numComp; ++ comp ) {

				channelData[ cscSet.idx[ comp ] ].decoded = true;
				const type = channelData[ cscSet.idx[ comp ] ].type;

				if ( channelData[ comp ].type != 2 ) continue;

				for ( let y = 0; y < height; ++ y ) {

					const offset = rowOffsets[ comp ][ y ];

					for ( let x = 0; x < width; ++ x ) {

						halfRow[ x ] = dataView.getUint16( offset + x * INT16_SIZE * type, true );

					}

					for ( let x = 0; x < width; ++ x ) {

						dataView.setFloat32( offset + x * INT16_SIZE * type, decodeFloat16( halfRow[ x ] ), true );

					}

				}

			}

		}

		function lossyDctChannelDecode( channelIndex, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			const dataView = new DataView( outBuffer.buffer );
			const cd = channelData[ channelIndex ];
			const width = cd.width;
			const height = cd.height;

			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const numFullBlocksX = Math.floor( width / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			let currDcComp = 0;
			const dctData = new Float32Array( 64 );
			const halfZigBlock = new Uint16Array( 64 );
			const rowBlock = new Uint16Array( numBlocksX * 64 );

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 ) maxY = leftoverY;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					halfZigBlock.fill( 0 );
					halfZigBlock[ 0 ] = dcBuffer[ currDcComp ++ ];
					unRleAC( currAcComp, acBuffer, halfZigBlock );
					unZigZag( halfZigBlock, dctData );
					dctInverse( dctData );
					convertToHalf( dctData, rowBlock, blockx * 64 );

				}

				// Write decoded data to output buffer
				for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

					let offset = rowPtrs[ channelIndex ][ y ];

					for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

						const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < 8; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

						offset += 8 * INT16_SIZE * cd.type;

					}

					if ( numBlocksX != numFullBlocksX ) {

						const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < leftoverX; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

					}

				}

			}

			cd.decoded = true;

		}

		function unRleAC( currAcComp, acBuffer, halfZigBlock ) {

			let acValue;
			let dctComp = 1;

			while ( dctComp < 64 ) {

				acValue = acBuffer[ currAcComp.value ];

				if ( acValue == 0xff00 ) {

					dctComp = 64;

				} else if ( acValue >> 8 == 0xff ) {

					dctComp += acValue & 0xff;

				} else {

					halfZigBlock[ dctComp ] = acValue;
					dctComp ++;

				}

				currAcComp.value ++;

			}

		}

		function unZigZag( src, dst ) {

			dst[ 0 ] = decodeFloat16( src[ 0 ] );
			dst[ 1 ] = decodeFloat16( src[ 1 ] );
			dst[ 2 ] = decodeFloat16( src[ 5 ] );
			dst[ 3 ] = decodeFloat16( src[ 6 ] );
			dst[ 4 ] = decodeFloat16( src[ 14 ] );
			dst[ 5 ] = decodeFloat16( src[ 15 ] );
			dst[ 6 ] = decodeFloat16( src[ 27 ] );
			dst[ 7 ] = decodeFloat16( src[ 28 ] );
			dst[ 8 ] = decodeFloat16( src[ 2 ] );
			dst[ 9 ] = decodeFloat16( src[ 4 ] );

			dst[ 10 ] = decodeFloat16( src[ 7 ] );
			dst[ 11 ] = decodeFloat16( src[ 13 ] );
			dst[ 12 ] = decodeFloat16( src[ 16 ] );
			dst[ 13 ] = decodeFloat16( src[ 26 ] );
			dst[ 14 ] = decodeFloat16( src[ 29 ] );
			dst[ 15 ] = decodeFloat16( src[ 42 ] );
			dst[ 16 ] = decodeFloat16( src[ 3 ] );
			dst[ 17 ] = decodeFloat16( src[ 8 ] );
			dst[ 18 ] = decodeFloat16( src[ 12 ] );
			dst[ 19 ] = decodeFloat16( src[ 17 ] );

			dst[ 20 ] = decodeFloat16( src[ 25 ] );
			dst[ 21 ] = decodeFloat16( src[ 30 ] );
			dst[ 22 ] = decodeFloat16( src[ 41 ] );
			dst[ 23 ] = decodeFloat16( src[ 43 ] );
			dst[ 24 ] = decodeFloat16( src[ 9 ] );
			dst[ 25 ] = decodeFloat16( src[ 11 ] );
			dst[ 26 ] = decodeFloat16( src[ 18 ] );
			dst[ 27 ] = decodeFloat16( src[ 24 ] );
			dst[ 28 ] = decodeFloat16( src[ 31 ] );
			dst[ 29 ] = decodeFloat16( src[ 40 ] );

			dst[ 30 ] = decodeFloat16( src[ 44 ] );
			dst[ 31 ] = decodeFloat16( src[ 53 ] );
			dst[ 32 ] = decodeFloat16( src[ 10 ] );
			dst[ 33 ] = decodeFloat16( src[ 19 ] );
			dst[ 34 ] = decodeFloat16( src[ 23 ] );
			dst[ 35 ] = decodeFloat16( src[ 32 ] );
			dst[ 36 ] = decodeFloat16( src[ 39 ] );
			dst[ 37 ] = decodeFloat16( src[ 45 ] );
			dst[ 38 ] = decodeFloat16( src[ 52 ] );
			dst[ 39 ] = decodeFloat16( src[ 54 ] );

			dst[ 40 ] = decodeFloat16( src[ 20 ] );
			dst[ 41 ] = decodeFloat16( src[ 22 ] );
			dst[ 42 ] = decodeFloat16( src[ 33 ] );
			dst[ 43 ] = decodeFloat16( src[ 38 ] );
			dst[ 44 ] = decodeFloat16( src[ 46 ] );
			dst[ 45 ] = decodeFloat16( src[ 51 ] );
			dst[ 46 ] = decodeFloat16( src[ 55 ] );
			dst[ 47 ] = decodeFloat16( src[ 60 ] );
			dst[ 48 ] = decodeFloat16( src[ 21 ] );
			dst[ 49 ] = decodeFloat16( src[ 34 ] );

			dst[ 50 ] = decodeFloat16( src[ 37 ] );
			dst[ 51 ] = decodeFloat16( src[ 47 ] );
			dst[ 52 ] = decodeFloat16( src[ 50 ] );
			dst[ 53 ] = decodeFloat16( src[ 56 ] );
			dst[ 54 ] = decodeFloat16( src[ 59 ] );
			dst[ 55 ] = decodeFloat16( src[ 61 ] );
			dst[ 56 ] = decodeFloat16( src[ 35 ] );
			dst[ 57 ] = decodeFloat16( src[ 36 ] );
			dst[ 58 ] = decodeFloat16( src[ 48 ] );
			dst[ 59 ] = decodeFloat16( src[ 49 ] );

			dst[ 60 ] = decodeFloat16( src[ 57 ] );
			dst[ 61 ] = decodeFloat16( src[ 58 ] );
			dst[ 62 ] = decodeFloat16( src[ 62 ] );
			dst[ 63 ] = decodeFloat16( src[ 63 ] );

		}

		function dctInverse( data ) {

			const a = 0.5 * Math.cos( 3.14159 / 4.0 );
			const b = 0.5 * Math.cos( 3.14159 / 16.0 );
			const c = 0.5 * Math.cos( 3.14159 / 8.0 );
			const d = 0.5 * Math.cos( 3.0 * 3.14159 / 16.0 );
			const e = 0.5 * Math.cos( 5.0 * 3.14159 / 16.0 );
			const f = 0.5 * Math.cos( 3.0 * 3.14159 / 8.0 );
			const g = 0.5 * Math.cos( 7.0 * 3.14159 / 16.0 );

			const alpha = new Array( 4 );
			const beta = new Array( 4 );
			const theta = new Array( 4 );
			const gamma = new Array( 4 );

			for ( let row = 0; row < 8; ++ row ) {

				const rowPtr = row * 8;

				alpha[ 0 ] = c * data[ rowPtr + 2 ];
				alpha[ 1 ] = f * data[ rowPtr + 2 ];
				alpha[ 2 ] = c * data[ rowPtr + 6 ];
				alpha[ 3 ] = f * data[ rowPtr + 6 ];

				beta[ 0 ] = b * data[ rowPtr + 1 ] + d * data[ rowPtr + 3 ] + e * data[ rowPtr + 5 ] + g * data[ rowPtr + 7 ];
				beta[ 1 ] = d * data[ rowPtr + 1 ] - g * data[ rowPtr + 3 ] - b * data[ rowPtr + 5 ] - e * data[ rowPtr + 7 ];
				beta[ 2 ] = e * data[ rowPtr + 1 ] - b * data[ rowPtr + 3 ] + g * data[ rowPtr + 5 ] + d * data[ rowPtr + 7 ];
				beta[ 3 ] = g * data[ rowPtr + 1 ] - e * data[ rowPtr + 3 ] + d * data[ rowPtr + 5 ] - b * data[ rowPtr + 7 ];

				theta[ 0 ] = a * ( data[ rowPtr + 0 ] + data[ rowPtr + 4 ] );
				theta[ 3 ] = a * ( data[ rowPtr + 0 ] - data[ rowPtr + 4 ] );
				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ rowPtr + 0 ] = gamma[ 0 ] + beta[ 0 ];
				data[ rowPtr + 1 ] = gamma[ 1 ] + beta[ 1 ];
				data[ rowPtr + 2 ] = gamma[ 2 ] + beta[ 2 ];
				data[ rowPtr + 3 ] = gamma[ 3 ] + beta[ 3 ];

				data[ rowPtr + 4 ] = gamma[ 3 ] - beta[ 3 ];
				data[ rowPtr + 5 ] = gamma[ 2 ] - beta[ 2 ];
				data[ rowPtr + 6 ] = gamma[ 1 ] - beta[ 1 ];
				data[ rowPtr + 7 ] = gamma[ 0 ] - beta[ 0 ];

			}

			for ( let column = 0; column < 8; ++ column ) {

				alpha[ 0 ] = c * data[ 16 + column ];
				alpha[ 1 ] = f * data[ 16 + column ];
				alpha[ 2 ] = c * data[ 48 + column ];
				alpha[ 3 ] = f * data[ 48 + column ];

				beta[ 0 ] = b * data[ 8 + column ] + d * data[ 24 + column ] + e * data[ 40 + column ] + g * data[ 56 + column ];
				beta[ 1 ] = d * data[ 8 + column ] - g * data[ 24 + column ] - b * data[ 40 + column ] - e * data[ 56 + column ];
				beta[ 2 ] = e * data[ 8 + column ] - b * data[ 24 + column ] + g * data[ 40 + column ] + d * data[ 56 + column ];
				beta[ 3 ] = g * data[ 8 + column ] - e * data[ 24 + column ] + d * data[ 40 + column ] - b * data[ 56 + column ];

				theta[ 0 ] = a * ( data[ column ] + data[ 32 + column ] );
				theta[ 3 ] = a * ( data[ column ] - data[ 32 + column ] );

				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ 0 + column ] = gamma[ 0 ] + beta[ 0 ];
				data[ 8 + column ] = gamma[ 1 ] + beta[ 1 ];
				data[ 16 + column ] = gamma[ 2 ] + beta[ 2 ];
				data[ 24 + column ] = gamma[ 3 ] + beta[ 3 ];

				data[ 32 + column ] = gamma[ 3 ] - beta[ 3 ];
				data[ 40 + column ] = gamma[ 2 ] - beta[ 2 ];
				data[ 48 + column ] = gamma[ 1 ] - beta[ 1 ];
				data[ 56 + column ] = gamma[ 0 ] - beta[ 0 ];

			}

		}

		function csc709Inverse( data ) {

			for ( let i = 0; i < 64; ++ i ) {

				const y = data[ 0 ][ i ];
				const cb = data[ 1 ][ i ];
				const cr = data[ 2 ][ i ];

				data[ 0 ][ i ] = y + 1.5747 * cr;
				data[ 1 ][ i ] = y - 0.1873 * cb - 0.4682 * cr;
				data[ 2 ][ i ] = y + 1.8556 * cb;

			}

		}

		function convertToHalf( src, dst, idx ) {

			for ( let i = 0; i < 64; ++ i ) {

				dst[ idx + i ] = DataUtils.toHalfFloat( toLinear( src[ i ] ) );

			}

		}

		function toLinear( float ) {

			if ( float <= 1 ) {

				return Math.sign( float ) * Math.pow( Math.abs( float ), 2.2 );

			} else {

				return Math.sign( float ) * Math.pow( logBase, Math.abs( float ) - 1.0 );

			}

		}

		function uncompressRAW( info ) {

			return new DataView( info.array.buffer, info.offset.value, info.size );

		}

		function uncompressRLE( info ) {

			const compressed = info.viewer.buffer.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = new Uint8Array( decodeRunLength( compressed ) );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressZIP( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressPIZ( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };

			const outBuffer = new Uint16Array( info.columns * info.lines * ( info.inputChannels.length * info.type ) );
			const bitmap = new Uint8Array( BITMAP_SIZE );

			// Setup channel info
			let outBufferEnd = 0;
			const pizChannelData = new Array( info.inputChannels.length );
			for ( let i = 0, il = info.inputChannels.length; i < il; i ++ ) {

				pizChannelData[ i ] = {};
				pizChannelData[ i ][ 'start' ] = outBufferEnd;
				pizChannelData[ i ][ 'end' ] = pizChannelData[ i ][ 'start' ];
				pizChannelData[ i ][ 'nx' ] = info.columns;
				pizChannelData[ i ][ 'ny' ] = info.lines;
				pizChannelData[ i ][ 'size' ] = info.type;

				outBufferEnd += pizChannelData[ i ].nx * pizChannelData[ i ].ny * pizChannelData[ i ].size;

			}

			// Read range compression data

			const minNonZero = parseUint16( inDataView, inOffset );
			const maxNonZero = parseUint16( inDataView, inOffset );

			if ( maxNonZero >= BITMAP_SIZE ) {

				throw new Error( 'Something is wrong with PIZ_COMPRESSION BITMAP_SIZE' );

			}

			if ( minNonZero <= maxNonZero ) {

				for ( let i = 0; i < maxNonZero - minNonZero + 1; i ++ ) {

					bitmap[ i + minNonZero ] = parseUint8( inDataView, inOffset );

				}

			}

			// Reverse LUT
			const lut = new Uint16Array( USHORT_RANGE );
			const maxValue = reverseLutFromBitmap( bitmap, lut );

			const length = parseUint32( inDataView, inOffset );

			// Huffman decoding
			hufUncompress( info.array, inDataView, inOffset, length, outBuffer, outBufferEnd );

			// Wavelet decoding
			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = pizChannelData[ i ];

				for ( let j = 0; j < pizChannelData[ i ].size; ++ j ) {

					wav2Decode(
						outBuffer,
						cd.start + j,
						cd.nx,
						cd.size,
						cd.ny,
						cd.nx * cd.size,
						maxValue
					);

				}

			}

			// Expand the pixel data to their original range
			applyLut( lut, outBuffer, outBufferEnd );

			// Rearrange the pixel data into the format expected by the caller.
			let tmpOffset = 0;
			const tmpBuffer = new Uint8Array( outBuffer.buffer.byteLength );
			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					const cd = pizChannelData[ c ];

					const n = cd.nx * cd.size;
					const cp = new Uint8Array( outBuffer.buffer, cd.end * INT16_SIZE, n * INT16_SIZE );

					tmpBuffer.set( cp, tmpOffset );
					tmpOffset += n * INT16_SIZE;
					cd.end += n;

				}

			}

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressPXR( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );

			const byteSize = info.inputChannels.length * info.lines * info.columns * info.totalBytes;
			const tmpBuffer = new ArrayBuffer( byteSize );
			const viewer = new DataView( tmpBuffer );

			let tmpBufferEnd = 0;
			let writePtr = 0;
			const ptr = new Array( 4 );

			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					let pixel = 0;

					const type = info.inputChannels[ c ].pixelType;
					switch ( type ) {

						case 1:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							tmpBufferEnd = ptr[ 1 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 8 ) | rawBuffer[ ptr[ 1 ] ++ ];

								pixel += diff;

								viewer.setUint16( writePtr, pixel, true );
								writePtr += 2;

							}

							break;

						case 2:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							ptr[ 2 ] = ptr[ 1 ] + info.columns;
							tmpBufferEnd = ptr[ 2 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 24 ) | ( rawBuffer[ ptr[ 1 ] ++ ] << 16 ) | ( rawBuffer[ ptr[ 2 ] ++ ] << 8 );

								pixel += diff;

								viewer.setUint32( writePtr, pixel, true );
								writePtr += 4;

							}

							break;

					}

				}

			}

			return viewer;

		}

		function uncompressDWA( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };
			const outBuffer = new Uint8Array( info.columns * info.lines * ( info.inputChannels.length * info.type * INT16_SIZE ) );

			// Read compression header information
			const dwaHeader = {

				version: parseInt64( inDataView, inOffset ),
				unknownUncompressedSize: parseInt64( inDataView, inOffset ),
				unknownCompressedSize: parseInt64( inDataView, inOffset ),
				acCompressedSize: parseInt64( inDataView, inOffset ),
				dcCompressedSize: parseInt64( inDataView, inOffset ),
				rleCompressedSize: parseInt64( inDataView, inOffset ),
				rleUncompressedSize: parseInt64( inDataView, inOffset ),
				rleRawSize: parseInt64( inDataView, inOffset ),
				totalAcUncompressedCount: parseInt64( inDataView, inOffset ),
				totalDcUncompressedCount: parseInt64( inDataView, inOffset ),
				acCompression: parseInt64( inDataView, inOffset )

			};

			if ( dwaHeader.version < 2 )
				throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' version ' + dwaHeader.version + ' is unsupported' );

			// Read channel ruleset information
			const channelRules = new Array();
			let ruleSize = parseUint16( inDataView, inOffset ) - INT16_SIZE;

			while ( ruleSize > 0 ) {

				const name = parseNullTerminatedString( inDataView.buffer, inOffset );
				const value = parseUint8( inDataView, inOffset );
				const compression = ( value >> 2 ) & 3;
				const csc = ( value >> 4 ) - 1;
				const index = new Int8Array( [ csc ] )[ 0 ];
				const type = parseUint8( inDataView, inOffset );

				channelRules.push( {
					name: name,
					index: index,
					type: type,
					compression: compression,
				} );

				ruleSize -= name.length + 3;

			}

			// Classify channels
			const channels = EXRHeader.channels;
			const channelData = new Array( info.inputChannels.length );

			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = channelData[ i ] = {};
				const channel = channels[ i ];

				cd.name = channel.name;
				cd.compression = UNKNOWN;
				cd.decoded = false;
				cd.type = channel.pixelType;
				cd.pLinear = channel.pLinear;
				cd.width = info.columns;
				cd.height = info.lines;

			}

			const cscSet = {
				idx: new Array( 3 )
			};

			for ( let offset = 0; offset < info.inputChannels.length; ++ offset ) {

				const cd = channelData[ offset ];

				for ( let i = 0; i < channelRules.length; ++ i ) {

					const rule = channelRules[ i ];

					if ( cd.name == rule.name ) {

						cd.compression = rule.compression;

						if ( rule.index >= 0 ) {

							cscSet.idx[ rule.index ] = offset;

						}

						cd.offset = offset;

					}

				}

			}

			let acBuffer, dcBuffer, rleBuffer;

			// Read DCT - AC component data
			if ( dwaHeader.acCompressedSize > 0 ) {

				switch ( dwaHeader.acCompression ) {

					case STATIC_HUFFMAN:

						acBuffer = new Uint16Array( dwaHeader.totalAcUncompressedCount );
						hufUncompress( info.array, inDataView, inOffset, dwaHeader.acCompressedSize, acBuffer, dwaHeader.totalAcUncompressedCount );
						break;

					case DEFLATE:

						const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.totalAcUncompressedCount );
						const data = fflate.unzlibSync( compressed );
						acBuffer = new Uint16Array( data.buffer );
						inOffset.value += dwaHeader.totalAcUncompressedCount;
						break;

				}


			}

			// Read DCT - DC component data
			if ( dwaHeader.dcCompressedSize > 0 ) {

				const zlibInfo = {
					array: info.array,
					offset: inOffset,
					size: dwaHeader.dcCompressedSize
				};
				dcBuffer = new Uint16Array( uncompressZIP( zlibInfo ).buffer );
				inOffset.value += dwaHeader.dcCompressedSize;

			}

			// Read RLE compressed data
			if ( dwaHeader.rleRawSize > 0 ) {

				const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.rleCompressedSize );
				const data = fflate.unzlibSync( compressed );
				rleBuffer = decodeRunLength( data.buffer );

				inOffset.value += dwaHeader.rleCompressedSize;

			}

			// Prepare outbuffer data offset
			let outBufferEnd = 0;
			const rowOffsets = new Array( channelData.length );
			for ( let i = 0; i < rowOffsets.length; ++ i ) {

				rowOffsets[ i ] = new Array();

			}

			for ( let y = 0; y < info.lines; ++ y ) {

				for ( let chan = 0; chan < channelData.length; ++ chan ) {

					rowOffsets[ chan ].push( outBufferEnd );
					outBufferEnd += channelData[ chan ].width * info.type * INT16_SIZE;

				}

			}

			// Decode lossy DCT data if we have a valid color space conversion set with the first RGB channel present
			if ( cscSet.idx[ 0 ] !== undefined && channelData[ cscSet.idx[ 0 ] ] ) {

				lossyDctDecode( cscSet, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

			}

			// Decode other channels
			for ( let i = 0; i < channelData.length; ++ i ) {

				const cd = channelData[ i ];

				if ( cd.decoded ) continue;

				switch ( cd.compression ) {

					case RLE:

						let row = 0;
						let rleOffset = 0;

						for ( let y = 0; y < info.lines; ++ y ) {

							let rowOffsetBytes = rowOffsets[ i ][ row ];

							for ( let x = 0; x < cd.width; ++ x ) {

								for ( let byte = 0; byte < INT16_SIZE * cd.type; ++ byte ) {

									outBuffer[ rowOffsetBytes ++ ] = rleBuffer[ rleOffset + byte * cd.width * cd.height ];

								}

								rleOffset ++;

							}

							row ++;

						}

						break;

					case LOSSY_DCT:

						lossyDctChannelDecode( i, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

						break;

					default:
						throw new Error( 'EXRLoader.parse: unsupported channel compression' );

				}

			}

			return new DataView( outBuffer.buffer );

		}

		function parseNullTerminatedString( buffer, offset ) {

			const uintBuffer = new Uint8Array( buffer );
			let endOffset = 0;

			while ( uintBuffer[ offset.value + endOffset ] != 0 ) {

				endOffset += 1;

			}

			const stringValue = new TextDecoder().decode(
				uintBuffer.slice( offset.value, offset.value + endOffset )
			);

			offset.value = offset.value + endOffset + 1;

			return stringValue;

		}

		function parseFixedLengthString( buffer, offset, size ) {

			const stringValue = new TextDecoder().decode(
				new Uint8Array( buffer ).slice( offset.value, offset.value + size )
			);

			offset.value = offset.value + size;

			return stringValue;

		}

		function parseRational( dataView, offset ) {

			const x = parseInt32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}

		function parseTimecode( dataView, offset ) {

			const x = parseUint32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}

		function parseInt32( dataView, offset ) {

			const Int32 = dataView.getInt32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Int32;

		}

		function parseUint32( dataView, offset ) {

			const Uint32 = dataView.getUint32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Uint32;

		}

		function parseUint8Array( uInt8Array, offset ) {

			const Uint8 = uInt8Array[ offset.value ];

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}

		function parseUint8( dataView, offset ) {

			const Uint8 = dataView.getUint8( offset.value );

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}

		const parseInt64 = function ( dataView, offset ) {

			let int;

			if ( 'getBigInt64' in DataView.prototype ) {

				int = Number( dataView.getBigInt64( offset.value, true ) );

			} else {

				int = dataView.getUint32( offset.value + 4, true ) + Number( dataView.getUint32( offset.value, true ) << 32 );

			}

			offset.value += ULONG_SIZE;

			return int;

		};

		function parseFloat32( dataView, offset ) {

			const float = dataView.getFloat32( offset.value, true );

			offset.value += FLOAT32_SIZE;

			return float;

		}

		function decodeFloat32( dataView, offset ) {

			return DataUtils.toHalfFloat( parseFloat32( dataView, offset ) );

		}

		// https://stackoverflow.com/questions/5678432/decompressing-half-precision-floats-in-javascript
		function decodeFloat16( binary ) {

			const exponent = ( binary & 0x7C00 ) >> 10,
				fraction = binary & 0x03FF;

			return ( binary >> 15 ? - 1 : 1 ) * (
				exponent ?
					(
						exponent === 0x1F ?
							fraction ? NaN : Infinity :
							Math.pow( 2, exponent - 15 ) * ( 1 + fraction / 0x400 )
					) :
					6.103515625e-5 * ( fraction / 0x400 )
			);

		}

		function parseUint16( dataView, offset ) {

			const Uint16 = dataView.getUint16( offset.value, true );

			offset.value += INT16_SIZE;

			return Uint16;

		}

		function parseFloat16( buffer, offset ) {

			return decodeFloat16( parseUint16( buffer, offset ) );

		}

		function parseChlist( dataView, buffer, offset, size ) {

			const startOffset = offset.value;
			const channels = [];

			while ( offset.value < ( startOffset + size - 1 ) ) {

				const name = parseNullTerminatedString( buffer, offset );
				const pixelType = parseInt32( dataView, offset );
				const pLinear = parseUint8( dataView, offset );
				offset.value += 3; // reserved, three chars
				const xSampling = parseInt32( dataView, offset );
				const ySampling = parseInt32( dataView, offset );

				channels.push( {
					name: name,
					pixelType: pixelType,
					pLinear: pLinear,
					xSampling: xSampling,
					ySampling: ySampling
				} );

			}

			offset.value += 1;

			return channels;

		}

		function parseChromaticities( dataView, offset ) {

			const redX = parseFloat32( dataView, offset );
			const redY = parseFloat32( dataView, offset );
			const greenX = parseFloat32( dataView, offset );
			const greenY = parseFloat32( dataView, offset );
			const blueX = parseFloat32( dataView, offset );
			const blueY = parseFloat32( dataView, offset );
			const whiteX = parseFloat32( dataView, offset );
			const whiteY = parseFloat32( dataView, offset );

			return { redX: redX, redY: redY, greenX: greenX, greenY: greenY, blueX: blueX, blueY: blueY, whiteX: whiteX, whiteY: whiteY };

		}

		function parseCompression( dataView, offset ) {

			const compressionCodes = [
				'NO_COMPRESSION',
				'RLE_COMPRESSION',
				'ZIPS_COMPRESSION',
				'ZIP_COMPRESSION',
				'PIZ_COMPRESSION',
				'PXR24_COMPRESSION',
				'B44_COMPRESSION',
				'B44A_COMPRESSION',
				'DWAA_COMPRESSION',
				'DWAB_COMPRESSION'
			];

			const compression = parseUint8( dataView, offset );

			return compressionCodes[ compression ];

		}

		function parseBox2i( dataView, offset ) {

			const xMin = parseInt32( dataView, offset );
			const yMin = parseInt32( dataView, offset );
			const xMax = parseInt32( dataView, offset );
			const yMax = parseInt32( dataView, offset );

			return { xMin: xMin, yMin: yMin, xMax: xMax, yMax: yMax };

		}

		function parseLineOrder( dataView, offset ) {

			const lineOrders = [
				'INCREASING_Y',
				'DECREASING_Y',
				'RANDOM_Y',
			];

			const lineOrder = parseUint8( dataView, offset );

			return lineOrders[ lineOrder ];

		}

		function parseEnvmap( dataView, offset ) {

			const envmaps = [
				'ENVMAP_LATLONG',
				'ENVMAP_CUBE'
			];

			const envmap = parseUint8( dataView, offset );

			return envmaps[ envmap ];

		}

		function parseTiledesc( dataView, offset ) {

			const levelModes = [
				'ONE_LEVEL',
				'MIPMAP_LEVELS',
				'RIPMAP_LEVELS',
			];

			const roundingModes = [
				'ROUND_DOWN',
				'ROUND_UP',
			];

			const xSize = parseUint32( dataView, offset );
			const ySize = parseUint32( dataView, offset );
			const modes = parseUint8( dataView, offset );

			return {
				xSize: xSize,
				ySize: ySize,
				levelMode: levelModes[ modes & 0xf ],
				roundingMode: roundingModes[ modes >> 4 ]
			};

		}

		function parseV2f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );

			return [ x, y ];

		}

		function parseV3f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );
			const z = parseFloat32( dataView, offset );

			return [ x, y, z ];

		}

		function parseValue( dataView, buffer, offset, type, size ) {

			if ( type === 'string' || type === 'stringvector' || type === 'iccProfile' ) {

				return parseFixedLengthString( buffer, offset, size );

			} else if ( type === 'chlist' ) {

				return parseChlist( dataView, buffer, offset, size );

			} else if ( type === 'chromaticities' ) {

				return parseChromaticities( dataView, offset );

			} else if ( type === 'compression' ) {

				return parseCompression( dataView, offset );

			} else if ( type === 'box2i' ) {

				return parseBox2i( dataView, offset );

			} else if ( type === 'envmap' ) {

				return parseEnvmap( dataView, offset );

			} else if ( type === 'tiledesc' ) {

				return parseTiledesc( dataView, offset );

			} else if ( type === 'lineOrder' ) {

				return parseLineOrder( dataView, offset );

			} else if ( type === 'float' ) {

				return parseFloat32( dataView, offset );

			} else if ( type === 'v2f' ) {

				return parseV2f( dataView, offset );

			} else if ( type === 'v3f' ) {

				return parseV3f( dataView, offset );

			} else if ( type === 'int' ) {

				return parseInt32( dataView, offset );

			} else if ( type === 'rational' ) {

				return parseRational( dataView, offset );

			} else if ( type === 'timecode' ) {

				return parseTimecode( dataView, offset );

			} else if ( type === 'preview' ) {

				offset.value += size;
				return 'skipped';

			} else {

				offset.value += size;
				return undefined;

			}

		}

		function roundLog2( x, mode ) {

			const log2 = Math.log2( x );
			return mode == 'ROUND_DOWN' ? Math.floor( log2 ) : Math.ceil( log2 );

		}

		function calculateTileLevels( tiledesc, w, h ) {

			let num = 0;

			switch ( tiledesc.levelMode ) {

				case 'ONE_LEVEL':
					num = 1;
					break;

				case 'MIPMAP_LEVELS':
					num = roundLog2( Math.max( w, h ), tiledesc.roundingMode ) + 1;
					break;

				case 'RIPMAP_LEVELS':
					throw new Error( 'THREE.EXRLoader: RIPMAP_LEVELS tiles currently unsupported.' );

			}

			return num;

		}

		function calculateTiles( count, dataSize, size, roundingMode ) {

			const tiles = new Array( count );

			for ( let i = 0; i < count; i ++ ) {

				const b = ( 1 << i );
				let s = ( dataSize / b ) | 0;

				if ( roundingMode == 'ROUND_UP' && s * b < dataSize ) s += 1;

				const l = Math.max( s, 1 );

				tiles[ i ] = ( ( l + size - 1 ) / size ) | 0;

			}

			return tiles;

		}

		function parseTiles() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let tile = 0; tile < EXRDecoder.tileCount; tile ++ ) {

				const tileX = parseInt32( EXRDecoder.viewer, offset );
				const tileY = parseInt32( EXRDecoder.viewer, offset );
				offset.value += 8; // skip levels - only parsing top-level
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset );

				const startX = tileX * EXRDecoder.blockWidth;
				const startY = tileY * EXRDecoder.blockHeight;
				EXRDecoder.columns = ( startX + EXRDecoder.blockWidth > EXRDecoder.width ) ? EXRDecoder.width - startX : EXRDecoder.blockWidth;
				EXRDecoder.lines = ( startY + EXRDecoder.blockHeight > EXRDecoder.height ) ? EXRDecoder.height - startY : EXRDecoder.blockHeight;

				const bytesBlockLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesBlockLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line = 0; line < EXRDecoder.lines; line ++ ) {

					const lineOffset = line * EXRDecoder.columns * EXRDecoder.totalBytes;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;
						const outLineOffset = ( EXRDecoder.height - ( 1 + startY + line ) ) * EXRDecoder.outLineWidth;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + ( x + startX ) * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}

		function parseScanline() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let scanlineBlockIdx = 0; scanlineBlockIdx < EXRDecoder.height / EXRDecoder.blockHeight; scanlineBlockIdx ++ ) {

				const line = parseInt32( EXRDecoder.viewer, offset ) - EXRHeader.dataWindow.yMin; // line_no
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset ); // data_len
				EXRDecoder.lines = ( ( line + EXRDecoder.blockHeight > EXRDecoder.height ) ? ( EXRDecoder.height - line ) : EXRDecoder.blockHeight );

				const bytesPerLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesPerLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line_y = 0; line_y < EXRDecoder.blockHeight; line_y ++ ) {

					const scan_y = scanlineBlockIdx * EXRDecoder.blockHeight;
					const true_y = line_y + EXRDecoder.scanOrder( scan_y );
					if ( true_y >= EXRDecoder.height ) continue;

					const lineOffset = line_y * bytesPerLine;
					const outLineOffset = ( EXRDecoder.height - 1 - true_y ) * EXRDecoder.outLineWidth;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + x * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}

		function parseHeader( dataView, buffer, offset ) {

			const EXRHeader = {};

			if ( dataView.getUint32( 0, true ) != 20000630 ) { // magic

				throw new Error( 'THREE.EXRLoader: Provided file doesn\'t appear to be in OpenEXR format.' );

			}

			EXRHeader.version = dataView.getUint8( 4 );

			const spec = dataView.getUint8( 5 ); // fullMask

			EXRHeader.spec = {
				singleTile: !! ( spec & 2 ),
				longName: !! ( spec & 4 ),
				deepFormat: !! ( spec & 8 ),
				multiPart: !! ( spec & 16 ),
			};

			// start of header

			offset.value = 8; // start at 8 - after pre-amble

			let keepReading = true;

			while ( keepReading ) {

				const attributeName = parseNullTerminatedString( buffer, offset );

				if ( attributeName === '' ) {

					keepReading = false;

				} else {

					const attributeType = parseNullTerminatedString( buffer, offset );
					const attributeSize = parseUint32( dataView, offset );
					const attributeValue = parseValue( dataView, buffer, offset, attributeType, attributeSize );

					if ( attributeValue === undefined ) {

						console.warn( `THREE.EXRLoader: Skipped unknown header attribute type \'${attributeType}\'.` );

					} else {

						EXRHeader[ attributeName ] = attributeValue;

					}

				}

			}

			if ( ( spec & ~ 0x06 ) != 0 ) { // unsupported deep-image, multi-part

				console.error( 'THREE.EXRHeader:', EXRHeader );
				throw new Error( 'THREE.EXRLoader: Provided file is currently unsupported.' );

			}

			return EXRHeader;

		}

		function setupDecoder( EXRHeader, dataView, uInt8Array, offset, outputType, outputFormat ) {

			const EXRDecoder = {
				size: 0,
				viewer: dataView,
				array: uInt8Array,
				offset: offset,
				width: EXRHeader.dataWindow.xMax - EXRHeader.dataWindow.xMin + 1,
				height: EXRHeader.dataWindow.yMax - EXRHeader.dataWindow.yMin + 1,
				inputChannels: EXRHeader.channels,
				channelByteOffsets: {},
				shouldExpand: false,
				scanOrder: null,
				totalBytes: null,
				columns: null,
				lines: null,
				type: null,
				uncompress: null,
				getter: null,
				format: null,
				colorSpace: LinearSRGBColorSpace,
			};

			switch ( EXRHeader.compression ) {

				case 'NO_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRAW;
					break;

				case 'RLE_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRLE;
					break;

				case 'ZIPS_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'ZIP_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'PIZ_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressPIZ;
					break;

				case 'PXR24_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressPXR;
					break;

				case 'DWAA_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				case 'DWAB_COMPRESSION':
					EXRDecoder.blockHeight = 256;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				default:
					throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' is unsupported' );

			}

			const channels = {};
			for ( const channel of EXRHeader.channels ) {

				switch ( channel.name ) {

					case 'Y':
					case 'R':
					case 'G':
					case 'B':
					case 'A':
						channels[ channel.name ] = true;
						EXRDecoder.type = channel.pixelType;

				}

			}

			// RGB images will be converted to RGBA format, preventing software emulation in select devices.
			let fillAlpha = false;
			let invalidOutput = false;

			// Validate if input texture contain supported channels
			if ( channels.R && channels.G && channels.B ) {

				EXRDecoder.outputChannels = 4;

			} else if ( channels.Y ) {

				EXRDecoder.outputChannels = 1;

			} else {

				throw new Error( 'EXRLoader.parse: file contains unsupported data channels.' );

			}

			// Setup output texture configuration
			switch ( EXRDecoder.outputChannels ) {

				case 4:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = ! channels.A;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.decodeChannels = { R: 0, G: 1, B: 2, A: 3 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.decodeChannels = { R: 0, G: 1 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { R: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				case 1:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = true;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				default:

					invalidOutput = true;

			}

			if (invalidOutput) throw new Error( 'EXRLoader.parse: invalid output format for specified file.' );

			if ( EXRDecoder.type == 1 ) {

				// half
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat16;
						break;

					case HalfFloatType:
						EXRDecoder.getter = parseUint16;
						break;

				}

			} else if ( EXRDecoder.type == 2 ) {

				// float
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat32;
						break;

					case HalfFloatType:
						EXRDecoder.getter = decodeFloat32;

				}

			} else {

				throw new Error( 'EXRLoader.parse: unsupported pixelType ' + EXRDecoder.type + ' for ' + EXRHeader.compression + '.' );

			}

			EXRDecoder.columns = EXRDecoder.width;
			const size = EXRDecoder.width * EXRDecoder.height * EXRDecoder.outputChannels;

			switch ( outputType ) {

				case FloatType:
					EXRDecoder.byteArray = new Float32Array( size );

					// Fill initially with 1s for the alpha value if the texture is not RGBA, RGB values will be overwritten
					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 1, 0, size );

					break;

				case HalfFloatType:
					EXRDecoder.byteArray = new Uint16Array( size );

					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 0x3C00, 0, size ); // Uint16Array holds half float data, 0x3C00 is 1

					break;

				default:
					console.error( 'THREE.EXRLoader: unsupported type: ', outputType );
					break;

			}

			let byteOffset = 0;
			for ( const channel of EXRHeader.channels ) {

				if ( EXRDecoder.decodeChannels[ channel.name ] !== undefined ) {

					EXRDecoder.channelByteOffsets[ channel.name ] = byteOffset;

				}

				byteOffset += channel.pixelType * 2;

			}

			EXRDecoder.totalBytes = byteOffset;
			EXRDecoder.outLineWidth = EXRDecoder.width * EXRDecoder.outputChannels;

			if ( EXRHeader.lineOrder === 'INCREASING_Y' ) {

				EXRDecoder.scanOrder = ( y ) => y;

			} else {

				EXRDecoder.scanOrder = ( y ) => EXRDecoder.height - 1 - y;

			}

			if ( EXRHeader.spec.singleTile ) {

				EXRDecoder.blockHeight = EXRHeader.tiles.ySize;
				EXRDecoder.blockWidth = EXRHeader.tiles.xSize;

				const numXLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );
				// const numYLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );

				const numXTiles = calculateTiles( numXLevels, EXRDecoder.width, EXRHeader.tiles.xSize, EXRHeader.tiles.roundingMode );
				const numYTiles = calculateTiles( numXLevels, EXRDecoder.height, EXRHeader.tiles.ySize, EXRHeader.tiles.roundingMode );

				EXRDecoder.tileCount = numXTiles[ 0 ] * numYTiles[ 0 ];

				for ( let l = 0; l < numXLevels; l ++ )
					for ( let y = 0; y < numYTiles[ l ]; y ++ )
						for ( let x = 0; x < numXTiles[ l ]; x ++ )
							parseInt64( dataView, offset ); // tileOffset

				EXRDecoder.decode = parseTiles.bind( EXRDecoder );

			} else {

				EXRDecoder.blockWidth = EXRDecoder.width;
				const blockCount = Math.ceil( EXRDecoder.height / EXRDecoder.blockHeight );

				for ( let i = 0; i < blockCount; i ++ )
					parseInt64( dataView, offset ); // scanlineOffset

				EXRDecoder.decode = parseScanline.bind( EXRDecoder );

			}

			return EXRDecoder;

		}

		// start parsing file [START]
		const offset = { value: 0 };
		const bufferDataView = new DataView( buffer );
		const uInt8Array = new Uint8Array( buffer );

		// get header information and validate format.
		const EXRHeader = parseHeader( bufferDataView, buffer, offset );

		// get input compression information and prepare decoding.
		const EXRDecoder = setupDecoder( EXRHeader, bufferDataView, uInt8Array, offset, this.type, this.outputFormat );

		// parse input data
		EXRDecoder.decode();

		// output texture post-processing
		if ( EXRDecoder.shouldExpand ) {

			const byteArray = EXRDecoder.byteArray;

			if ( this.outputFormat == RGBAFormat ) {

				for ( let i = 0; i < byteArray.length; i += 4 )
					byteArray [i + 2 ] = ( byteArray [ i + 1 ] = byteArray[ i ] );

			} else if ( this.outputFormat == RGFormat ) {

				for ( let i = 0; i < byteArray.length; i += 2 )
					byteArray [ i + 1 ] = byteArray[ i ] ;

			}

		}

		return {
			header: EXRHeader,
			width: EXRDecoder.width,
			height: EXRDecoder.height,
			data: EXRDecoder.byteArray,
			format: EXRDecoder.format,
			colorSpace: EXRDecoder.colorSpace,
			type: this.type,
		};

	}
```
</details>

### `EXRLoader.setDataType(value: any): EXRLoader`

**JSDoc:**
```typescript
/**
	 * Sets the texture type.
	 *
	 * @param {(HalfFloatType|FloatType)} value - The texture type to set.
	 * @return {EXRLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `EXRLoader`

<details><summary>Code</summary>

```typescript
setDataType( value ) {

		this.type = value;
		return this;

	}
```
</details>

### `EXRLoader.setOutputFormat(value: any): EXRLoader`

**JSDoc:**
```typescript
/**
	 * Sets texture output format. Defaults to `RGBAFormat`.
	 *
	 * @param {(RGBAFormat|RGFormat|RedFormat)} value - Texture output format.
	 * @return {EXRLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `EXRLoader`

<details><summary>Code</summary>

```typescript
setOutputFormat( value ) {

		this.outputFormat = value;
		return this;

	}
```
</details>

### `EXRLoader.load(url: any, onLoad: any, onProgress: any, onError: any): any`

**Parameters:**

- **`url`** `any`
- **`onLoad`** `any`
- **`onProgress`** `any`
- **`onError`** `any`

**Returns:** `any`

**Calls:**

- `onLoad`
- `super.load`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		function onLoadCallback( texture, texData ) {

			texture.colorSpace = texData.colorSpace;
			texture.minFilter = LinearFilter;
			texture.magFilter = LinearFilter;
			texture.generateMipmaps = false;
			texture.flipY = false;

			if ( onLoad ) onLoad( texture, texData );

		}

		return super.load( url, onLoadCallback, onProgress, onError );

	}
```
</details>

### `reverseLutFromBitmap(bitmap: any, lut: any): number`

**Parameters:**

- **`bitmap`** `any`
- **`lut`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function reverseLutFromBitmap( bitmap, lut ) {

			let k = 0;

			for ( let i = 0; i < USHORT_RANGE; ++ i ) {

				if ( ( i == 0 ) || ( bitmap[ i >> 3 ] & ( 1 << ( i & 7 ) ) ) ) {

					lut[ k ++ ] = i;

				}

			}

			const n = k - 1;

			while ( k < USHORT_RANGE ) lut[ k ++ ] = 0;

			return n;

		}
```
</details>

### `hufClearDecTable(hdec: any): void`

**Parameters:**

- **`hdec`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function hufClearDecTable( hdec ) {

			for ( let i = 0; i < HUF_DECSIZE; i ++ ) {

				hdec[ i ] = {};
				hdec[ i ].len = 0;
				hdec[ i ].lit = 0;
				hdec[ i ].p = null;

			}

		}
```
</details>

### `getBits(nBits: any, c: any, lc: any, uInt8Array: any, inOffset: any): void`

**Parameters:**

- **`nBits`** `any`
- **`c`** `any`
- **`lc`** `any`
- **`uInt8Array`** `any`
- **`inOffset`** `any`

**Returns:** `void`

**Calls:**

- `parseUint8Array`

<details><summary>Code</summary>

```typescript
function getBits( nBits, c, lc, uInt8Array, inOffset ) {

			while ( lc < nBits ) {

				c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
				lc += 8;

			}

			lc -= nBits;

			getBitsReturn.l = ( c >> lc ) & ( ( 1 << nBits ) - 1 );
			getBitsReturn.c = c;
			getBitsReturn.lc = lc;

		}
```
</details>

### `hufCanonicalCodeTable(hcode: any): void`

**Parameters:**

- **`hcode`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function hufCanonicalCodeTable( hcode ) {

			for ( let i = 0; i <= 58; ++ i ) hufTableBuffer[ i ] = 0;
			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) hufTableBuffer[ hcode[ i ] ] += 1;

			let c = 0;

			for ( let i = 58; i > 0; -- i ) {

				const nc = ( ( c + hufTableBuffer[ i ] ) >> 1 );
				hufTableBuffer[ i ] = c;
				c = nc;

			}

			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) {

				const l = hcode[ i ];
				if ( l > 0 ) hcode[ i ] = l | ( hufTableBuffer[ l ] ++ << 6 );

			}

		}
```
</details>

### `hufUnpackEncTable(uInt8Array: any, inOffset: any, ni: any, im: any, iM: any, hcode: any): boolean`

**Parameters:**

- **`uInt8Array`** `any`
- **`inOffset`** `any`
- **`ni`** `any`
- **`im`** `any`
- **`iM`** `any`
- **`hcode`** `any`

**Returns:** `boolean`

**Calls:**

- `getBits`
- `hufCanonicalCodeTable`

<details><summary>Code</summary>

```typescript
function hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, hcode ) {

			const p = inOffset;
			let c = 0;
			let lc = 0;

			for ( ; im <= iM; im ++ ) {

				if ( p.value - inOffset.value > ni ) return false;

				getBits( 6, c, lc, uInt8Array, p );

				const l = getBitsReturn.l;
				c = getBitsReturn.c;
				lc = getBitsReturn.lc;

				hcode[ im ] = l;

				if ( l == LONG_ZEROCODE_RUN ) {

					if ( p.value - inOffset.value > ni ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					getBits( 8, c, lc, uInt8Array, p );

					let zerun = getBitsReturn.l + SHORTEST_LONG_RUN;
					c = getBitsReturn.c;
					lc = getBitsReturn.lc;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				} else if ( l >= SHORT_ZEROCODE_RUN ) {

					let zerun = l - SHORT_ZEROCODE_RUN + 2;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				}

			}

			hufCanonicalCodeTable( hcode );

		}
```
</details>

### `hufLength(code: any): number`

**Parameters:**

- **`code`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function hufLength( code ) {

			return code & 63;

		}
```
</details>

### `hufCode(code: any): number`

**Parameters:**

- **`code`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function hufCode( code ) {

			return code >> 6;

		}
```
</details>

### `hufBuildDecTable(hcode: any, im: any, iM: any, hdecod: any): boolean`

**Parameters:**

- **`hcode`** `any`
- **`im`** `any`
- **`iM`** `any`
- **`hdecod`** `any`

**Returns:** `boolean`

**Calls:**

- `hufCode`
- `hufLength`

<details><summary>Code</summary>

```typescript
function hufBuildDecTable( hcode, im, iM, hdecod ) {

			for ( ; im <= iM; im ++ ) {

				const c = hufCode( hcode[ im ] );
				const l = hufLength( hcode[ im ] );

				if ( c >> l ) {

					throw new Error( 'Invalid table entry' );

				}

				if ( l > HUF_DECBITS ) {

					const pl = hdecod[ ( c >> ( l - HUF_DECBITS ) ) ];

					if ( pl.len ) {

						throw new Error( 'Invalid table entry' );

					}

					pl.lit ++;

					if ( pl.p ) {

						const p = pl.p;
						pl.p = new Array( pl.lit );

						for ( let i = 0; i < pl.lit - 1; ++ i ) {

							pl.p[ i ] = p[ i ];

						}

					} else {

						pl.p = new Array( 1 );

					}

					pl.p[ pl.lit - 1 ] = im;

				} else if ( l ) {

					let plOffset = 0;

					for ( let i = 1 << ( HUF_DECBITS - l ); i > 0; i -- ) {

						const pl = hdecod[ ( c << ( HUF_DECBITS - l ) ) + plOffset ];

						if ( pl.len || pl.p ) {

							throw new Error( 'Invalid table entry' );

						}

						pl.len = l;
						pl.lit = im;

						plOffset ++;

					}

				}

			}

			return true;

		}
```
</details>

### `getChar(c: any, lc: any, uInt8Array: any, inOffset: any): void`

**Parameters:**

- **`c`** `any`
- **`lc`** `any`
- **`uInt8Array`** `any`
- **`inOffset`** `any`

**Returns:** `void`

**Calls:**

- `parseUint8Array`

<details><summary>Code</summary>

```typescript
function getChar( c, lc, uInt8Array, inOffset ) {

			c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
			lc += 8;

			getCharReturn.c = c;
			getCharReturn.lc = lc;

		}
```
</details>

### `getCode(po: any, rlc: any, c: any, lc: any, uInt8Array: any, inOffset: any, outBuffer: any, outBufferOffset: any, outBufferEndOffset: any): boolean`

**Parameters:**

- **`po`** `any`
- **`rlc`** `any`
- **`c`** `any`
- **`lc`** `any`
- **`uInt8Array`** `any`
- **`inOffset`** `any`
- **`outBuffer`** `any`
- **`outBufferOffset`** `any`
- **`outBufferEndOffset`** `any`

**Returns:** `boolean`

**Calls:**

- `getChar`

<details><summary>Code</summary>

```typescript
function getCode( po, rlc, c, lc, uInt8Array, inOffset, outBuffer, outBufferOffset, outBufferEndOffset ) {

			if ( po == rlc ) {

				if ( lc < 8 ) {

					getChar( c, lc, uInt8Array, inOffset );
					c = getCharReturn.c;
					lc = getCharReturn.lc;

				}

				lc -= 8;

				let cs = ( c >> lc );
				cs = new Uint8Array( [ cs ] )[ 0 ];

				if ( outBufferOffset.value + cs > outBufferEndOffset ) {

					return false;

				}

				const s = outBuffer[ outBufferOffset.value - 1 ];

				while ( cs -- > 0 ) {

					outBuffer[ outBufferOffset.value ++ ] = s;

				}

			} else if ( outBufferOffset.value < outBufferEndOffset ) {

				outBuffer[ outBufferOffset.value ++ ] = po;

			} else {

				return false;

			}

			getCodeReturn.c = c;
			getCodeReturn.lc = lc;

		}
```
</details>

### `UInt16(value: any): number`

**Parameters:**

- **`value`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function UInt16( value ) {

			return ( value & 0xFFFF );

		}
```
</details>

### `Int16(value: any): number`

**Parameters:**

- **`value`** `any`

**Returns:** `number`

**Calls:**

- `UInt16`

<details><summary>Code</summary>

```typescript
function Int16( value ) {

			const ref = UInt16( value );
			return ( ref > 0x7FFF ) ? ref - 0x10000 : ref;

		}
```
</details>

### `wdec14(l: any, h: any): void`

**Parameters:**

- **`l`** `any`
- **`h`** `any`

**Returns:** `void`

**Calls:**

- `Int16`

<details><summary>Code</summary>

```typescript
function wdec14( l, h ) {

			const ls = Int16( l );
			const hs = Int16( h );

			const hi = hs;
			const ai = ls + ( hi & 1 ) + ( hi >> 1 );

			const as = ai;
			const bs = ai - hi;

			wdec14Return.a = as;
			wdec14Return.b = bs;

		}
```
</details>

### `wdec16(l: any, h: any): void`

**Parameters:**

- **`l`** `any`
- **`h`** `any`

**Returns:** `void`

**Calls:**

- `UInt16`

<details><summary>Code</summary>

```typescript
function wdec16( l, h ) {

			const m = UInt16( l );
			const d = UInt16( h );

			const bb = ( m - ( d >> 1 ) ) & MOD_MASK;
			const aa = ( d + bb - A_OFFSET ) & MOD_MASK;

			wdec14Return.a = aa;
			wdec14Return.b = bb;

		}
```
</details>

### `wav2Decode(buffer: any, j: any, nx: any, ox: any, ny: any, oy: any, mx: any): number`

**Parameters:**

- **`buffer`** `any`
- **`j`** `any`
- **`nx`** `any`
- **`ox`** `any`
- **`ny`** `any`
- **`oy`** `any`
- **`mx`** `any`

**Returns:** `number`

**Calls:**

- `wdec14`
- `wdec16`

<details><summary>Code</summary>

```typescript
function wav2Decode( buffer, j, nx, ox, ny, oy, mx ) {

			const w14 = mx < ( 1 << 14 );
			const n = ( nx > ny ) ? ny : nx;
			let p = 1;
			let p2;
			let py;

			while ( p <= n ) p <<= 1;

			p >>= 1;
			p2 = p;
			p >>= 1;

			while ( p >= 1 ) {

				py = 0;
				const ey = py + oy * ( ny - p2 );
				const oy1 = oy * p;
				const oy2 = oy * p2;
				const ox1 = ox * p;
				const ox2 = ox * p2;
				let i00, i01, i10, i11;

				for ( ; py <= ey; py += oy2 ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;
						const p10 = px + oy1;
						const p11 = p10 + ox1;

						if ( w14 ) {

							wdec14( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec14( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec14( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec14( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;

						} else {

							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec16( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec16( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec16( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;


						}

					}

					if ( nx & p ) {

						const p10 = px + oy1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p10 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

						i00 = wdec14Return.a;
						buffer[ p10 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				if ( ny & p ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p01 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p01 + j ] );

						i00 = wdec14Return.a;
						buffer[ p01 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				p2 = p;
				p >>= 1;

			}

			return py;

		}
```
</details>

### `hufDecode(encodingTable: any, decodingTable: any, uInt8Array: any, inOffset: any, ni: any, rlc: any, no: any, outBuffer: any, outOffset: any): boolean`

**Parameters:**

- **`encodingTable`** `any`
- **`decodingTable`** `any`
- **`uInt8Array`** `any`
- **`inOffset`** `any`
- **`ni`** `any`
- **`rlc`** `any`
- **`no`** `any`
- **`outBuffer`** `any`
- **`outOffset`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.trunc`
- `getChar`
- `getCode`
- `hufLength`
- `hufCode`

<details><summary>Code</summary>

```typescript
function hufDecode( encodingTable, decodingTable, uInt8Array, inOffset, ni, rlc, no, outBuffer, outOffset ) {

			let c = 0;
			let lc = 0;
			const outBufferEndOffset = no;
			const inOffsetEnd = Math.trunc( inOffset.value + ( ni + 7 ) / 8 );

			while ( inOffset.value < inOffsetEnd ) {

				getChar( c, lc, uInt8Array, inOffset );

				c = getCharReturn.c;
				lc = getCharReturn.lc;

				while ( lc >= HUF_DECBITS ) {

					const index = ( c >> ( lc - HUF_DECBITS ) ) & HUF_DECMASK;
					const pl = decodingTable[ index ];

					if ( pl.len ) {

						lc -= pl.len;

						getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

						c = getCodeReturn.c;
						lc = getCodeReturn.lc;

					} else {

						if ( ! pl.p ) {

							throw new Error( 'hufDecode issues' );

						}

						let j;

						for ( j = 0; j < pl.lit; j ++ ) {

							const l = hufLength( encodingTable[ pl.p[ j ] ] );

							while ( lc < l && inOffset.value < inOffsetEnd ) {

								getChar( c, lc, uInt8Array, inOffset );

								c = getCharReturn.c;
								lc = getCharReturn.lc;

							}

							if ( lc >= l ) {

								if ( hufCode( encodingTable[ pl.p[ j ] ] ) == ( ( c >> ( lc - l ) ) & ( ( 1 << l ) - 1 ) ) ) {

									lc -= l;

									getCode( pl.p[ j ], rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

									c = getCodeReturn.c;
									lc = getCodeReturn.lc;

									break;

								}

							}

						}

						if ( j == pl.lit ) {

							throw new Error( 'hufDecode issues' );

						}

					}

				}

			}

			const i = ( 8 - ni ) & 7;

			c >>= i;
			lc -= i;

			while ( lc > 0 ) {

				const pl = decodingTable[ ( c << ( HUF_DECBITS - lc ) ) & HUF_DECMASK ];

				if ( pl.len ) {

					lc -= pl.len;

					getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

					c = getCodeReturn.c;
					lc = getCodeReturn.lc;

				} else {

					throw new Error( 'hufDecode issues' );

				}

			}

			return true;

		}
```
</details>

### `hufUncompress(uInt8Array: any, inDataView: any, inOffset: any, nCompressed: any, outBuffer: any, nRaw: any): void`

**Parameters:**

- **`uInt8Array`** `any`
- **`inDataView`** `any`
- **`inOffset`** `any`
- **`nCompressed`** `any`
- **`outBuffer`** `any`
- **`nRaw`** `any`

**Returns:** `void`

**Calls:**

- `parseUint32`
- `hufClearDecTable`
- `hufUnpackEncTable`
- `hufBuildDecTable`
- `hufDecode`

<details><summary>Code</summary>

```typescript
function hufUncompress( uInt8Array, inDataView, inOffset, nCompressed, outBuffer, nRaw ) {

			const outOffset = { value: 0 };
			const initialInOffset = inOffset.value;

			const im = parseUint32( inDataView, inOffset );
			const iM = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			const nBits = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			if ( im < 0 || im >= HUF_ENCSIZE || iM < 0 || iM >= HUF_ENCSIZE ) {

				throw new Error( 'Something wrong with HUF_ENCSIZE' );

			}

			const freq = new Array( HUF_ENCSIZE );
			const hdec = new Array( HUF_DECSIZE );

			hufClearDecTable( hdec );

			const ni = nCompressed - ( inOffset.value - initialInOffset );

			hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, freq );

			if ( nBits > 8 * ( nCompressed - ( inOffset.value - initialInOffset ) ) ) {

				throw new Error( 'Something wrong with hufUncompress' );

			}

			hufBuildDecTable( freq, im, iM, hdec );

			hufDecode( freq, hdec, uInt8Array, inOffset, nBits, iM, nRaw, outBuffer, outOffset );

		}
```
</details>

### `applyLut(lut: any, data: any, nData: any): void`

**Parameters:**

- **`lut`** `any`
- **`data`** `any`
- **`nData`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function applyLut( lut, data, nData ) {

			for ( let i = 0; i < nData; ++ i ) {

				data[ i ] = lut[ data[ i ] ];

			}

		}
```
</details>

### `predictor(source: any): void`

**Parameters:**

- **`source`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function predictor( source ) {

			for ( let t = 1; t < source.length; t ++ ) {

				const d = source[ t - 1 ] + source[ t ] - 128;
				source[ t ] = d;

			}

		}
```
</details>

### `interleaveScalar(source: any, out: any): void`

**Parameters:**

- **`source`** `any`
- **`out`** `any`

**Returns:** `void`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
function interleaveScalar( source, out ) {

			let t1 = 0;
			let t2 = Math.floor( ( source.length + 1 ) / 2 );
			let s = 0;
			const stop = source.length - 1;

			while ( true ) {

				if ( s > stop ) break;
				out[ s ++ ] = source[ t1 ++ ];

				if ( s > stop ) break;
				out[ s ++ ] = source[ t2 ++ ];

			}

		}
```
</details>

### `decodeRunLength(source: any): any[]`

**Parameters:**

- **`source`** `any`

**Returns:** `any[]`

**Calls:**

- `reader.getInt8`
- `out.push`
- `reader.getUint8`

<details><summary>Code</summary>

```typescript
function decodeRunLength( source ) {

			let size = source.byteLength;
			const out = new Array();
			let p = 0;

			const reader = new DataView( source );

			while ( size > 0 ) {

				const l = reader.getInt8( p ++ );

				if ( l < 0 ) {

					const count = - l;
					size -= count + 1;

					for ( let i = 0; i < count; i ++ ) {

						out.push( reader.getUint8( p ++ ) );

					}


				} else {

					const count = l;
					size -= 2;

					const value = reader.getUint8( p ++ );

					for ( let i = 0; i < count + 1; i ++ ) {

						out.push( value );

					}

				}

			}

			return out;

		}
```
</details>

### `lossyDctDecode(cscSet: any, rowPtrs: any, channelData: any, acBuffer: any, dcBuffer: any, outBuffer: any): void`

**Parameters:**

- **`cscSet`** `any`
- **`rowPtrs`** `any`
- **`channelData`** `any`
- **`acBuffer`** `any`
- **`dcBuffer`** `any`
- **`outBuffer`** `any`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.ceil`
- `halfZigBlock[ comp ].fill`
- `unRleAC`
- `unZigZag`
- `dctInverse`
- `csc709Inverse`
- `convertToHalf`
- `dataView.setUint16`
- `dataView.getUint16`
- `dataView.setFloat32`
- `decodeFloat16`

**Internal Comments:**
```
// set block DC component (x5)
// set block AC components (x3)
// UnZigZag block to float (x3)
// decode float dct (x3)
// handle partial X blocks
// convert channels back to float, if needed
```

<details><summary>Code</summary>

```typescript
function lossyDctDecode( cscSet, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			let dataView = new DataView( outBuffer.buffer );

			const width = channelData[ cscSet.idx[ 0 ] ].width;
			const height = channelData[ cscSet.idx[ 0 ] ].height;

			const numComp = 3;

			const numFullBlocksX = Math.floor( width / 8.0 );
			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			const currDcComp = new Array( numComp );
			const dctData = new Array( numComp );
			const halfZigBlock = new Array( numComp );
			const rowBlock = new Array( numComp );
			const rowOffsets = new Array( numComp );

			for ( let comp = 0; comp < numComp; ++ comp ) {

				rowOffsets[ comp ] = rowPtrs[ cscSet.idx[ comp ] ];
				currDcComp[ comp ] = ( comp < 1 ) ? 0 : currDcComp[ comp - 1 ] + numBlocksX * numBlocksY;
				dctData[ comp ] = new Float32Array( 64 );
				halfZigBlock[ comp ] = new Uint16Array( 64 );
				rowBlock[ comp ] = new Uint16Array( numBlocksX * 64 );

			}

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 )
					maxY = leftoverY;

				let maxX = 8;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					if ( blockx == numBlocksX - 1 )
						maxX = leftoverX;

					for ( let comp = 0; comp < numComp; ++ comp ) {

						halfZigBlock[ comp ].fill( 0 );

						// set block DC component
						halfZigBlock[ comp ][ 0 ] = dcBuffer[ currDcComp[ comp ] ++ ];
						// set block AC components
						unRleAC( currAcComp, acBuffer, halfZigBlock[ comp ] );

						// UnZigZag block to float
						unZigZag( halfZigBlock[ comp ], dctData[ comp ] );
						// decode float dct
						dctInverse( dctData[ comp ] );

					}

					if ( numComp == 3 ) {

						csc709Inverse( dctData );

					}

					for ( let comp = 0; comp < numComp; ++ comp ) {

						convertToHalf( dctData[ comp ], rowBlock[ comp ], blockx * 64 );

					}

				} // blockx

				let offset = 0;

				for ( let comp = 0; comp < numComp; ++ comp ) {

					const type = channelData[ cscSet.idx[ comp ] ].type;

					for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

						offset = rowOffsets[ comp ][ y ];

						for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

							const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

							dataView.setUint16( offset + 0 * INT16_SIZE * type, rowBlock[ comp ][ src + 0 ], true );
							dataView.setUint16( offset + 1 * INT16_SIZE * type, rowBlock[ comp ][ src + 1 ], true );
							dataView.setUint16( offset + 2 * INT16_SIZE * type, rowBlock[ comp ][ src + 2 ], true );
							dataView.setUint16( offset + 3 * INT16_SIZE * type, rowBlock[ comp ][ src + 3 ], true );

							dataView.setUint16( offset + 4 * INT16_SIZE * type, rowBlock[ comp ][ src + 4 ], true );
							dataView.setUint16( offset + 5 * INT16_SIZE * type, rowBlock[ comp ][ src + 5 ], true );
							dataView.setUint16( offset + 6 * INT16_SIZE * type, rowBlock[ comp ][ src + 6 ], true );
							dataView.setUint16( offset + 7 * INT16_SIZE * type, rowBlock[ comp ][ src + 7 ], true );

							offset += 8 * INT16_SIZE * type;

						}

					}

					// handle partial X blocks
					if ( numFullBlocksX != numBlocksX ) {

						for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

							const offset = rowOffsets[ comp ][ y ] + 8 * numFullBlocksX * INT16_SIZE * type;
							const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

							for ( let x = 0; x < maxX; ++ x ) {

								dataView.setUint16( offset + x * INT16_SIZE * type, rowBlock[ comp ][ src + x ], true );

							}

						}

					}

				} // comp

			} // blocky

			const halfRow = new Uint16Array( width );
			dataView = new DataView( outBuffer.buffer );

			// convert channels back to float, if needed
			for ( let comp = 0; comp < numComp; ++ comp ) {

				channelData[ cscSet.idx[ comp ] ].decoded = true;
				const type = channelData[ cscSet.idx[ comp ] ].type;

				if ( channelData[ comp ].type != 2 ) continue;

				for ( let y = 0; y < height; ++ y ) {

					const offset = rowOffsets[ comp ][ y ];

					for ( let x = 0; x < width; ++ x ) {

						halfRow[ x ] = dataView.getUint16( offset + x * INT16_SIZE * type, true );

					}

					for ( let x = 0; x < width; ++ x ) {

						dataView.setFloat32( offset + x * INT16_SIZE * type, decodeFloat16( halfRow[ x ] ), true );

					}

				}

			}

		}
```
</details>

### `lossyDctChannelDecode(channelIndex: any, rowPtrs: any, channelData: any, acBuffer: any, dcBuffer: any, outBuffer: any): void`

**Parameters:**

- **`channelIndex`** `any`
- **`rowPtrs`** `any`
- **`channelData`** `any`
- **`acBuffer`** `any`
- **`dcBuffer`** `any`
- **`outBuffer`** `any`

**Returns:** `void`

**Calls:**

- `Math.ceil`
- `Math.floor`
- `halfZigBlock.fill`
- `unRleAC`
- `unZigZag`
- `dctInverse`
- `convertToHalf`
- `dataView.setUint16`

**Internal Comments:**
```
// Write decoded data to output buffer
```

<details><summary>Code</summary>

```typescript
function lossyDctChannelDecode( channelIndex, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			const dataView = new DataView( outBuffer.buffer );
			const cd = channelData[ channelIndex ];
			const width = cd.width;
			const height = cd.height;

			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const numFullBlocksX = Math.floor( width / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			let currDcComp = 0;
			const dctData = new Float32Array( 64 );
			const halfZigBlock = new Uint16Array( 64 );
			const rowBlock = new Uint16Array( numBlocksX * 64 );

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 ) maxY = leftoverY;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					halfZigBlock.fill( 0 );
					halfZigBlock[ 0 ] = dcBuffer[ currDcComp ++ ];
					unRleAC( currAcComp, acBuffer, halfZigBlock );
					unZigZag( halfZigBlock, dctData );
					dctInverse( dctData );
					convertToHalf( dctData, rowBlock, blockx * 64 );

				}

				// Write decoded data to output buffer
				for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

					let offset = rowPtrs[ channelIndex ][ y ];

					for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

						const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < 8; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

						offset += 8 * INT16_SIZE * cd.type;

					}

					if ( numBlocksX != numFullBlocksX ) {

						const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < leftoverX; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

					}

				}

			}

			cd.decoded = true;

		}
```
</details>

### `unRleAC(currAcComp: any, acBuffer: any, halfZigBlock: any): void`

**Parameters:**

- **`currAcComp`** `any`
- **`acBuffer`** `any`
- **`halfZigBlock`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function unRleAC( currAcComp, acBuffer, halfZigBlock ) {

			let acValue;
			let dctComp = 1;

			while ( dctComp < 64 ) {

				acValue = acBuffer[ currAcComp.value ];

				if ( acValue == 0xff00 ) {

					dctComp = 64;

				} else if ( acValue >> 8 == 0xff ) {

					dctComp += acValue & 0xff;

				} else {

					halfZigBlock[ dctComp ] = acValue;
					dctComp ++;

				}

				currAcComp.value ++;

			}

		}
```
</details>

### `unZigZag(src: any, dst: any): void`

**Parameters:**

- **`src`** `any`
- **`dst`** `any`

**Returns:** `void`

**Calls:**

- `decodeFloat16`

<details><summary>Code</summary>

```typescript
function unZigZag( src, dst ) {

			dst[ 0 ] = decodeFloat16( src[ 0 ] );
			dst[ 1 ] = decodeFloat16( src[ 1 ] );
			dst[ 2 ] = decodeFloat16( src[ 5 ] );
			dst[ 3 ] = decodeFloat16( src[ 6 ] );
			dst[ 4 ] = decodeFloat16( src[ 14 ] );
			dst[ 5 ] = decodeFloat16( src[ 15 ] );
			dst[ 6 ] = decodeFloat16( src[ 27 ] );
			dst[ 7 ] = decodeFloat16( src[ 28 ] );
			dst[ 8 ] = decodeFloat16( src[ 2 ] );
			dst[ 9 ] = decodeFloat16( src[ 4 ] );

			dst[ 10 ] = decodeFloat16( src[ 7 ] );
			dst[ 11 ] = decodeFloat16( src[ 13 ] );
			dst[ 12 ] = decodeFloat16( src[ 16 ] );
			dst[ 13 ] = decodeFloat16( src[ 26 ] );
			dst[ 14 ] = decodeFloat16( src[ 29 ] );
			dst[ 15 ] = decodeFloat16( src[ 42 ] );
			dst[ 16 ] = decodeFloat16( src[ 3 ] );
			dst[ 17 ] = decodeFloat16( src[ 8 ] );
			dst[ 18 ] = decodeFloat16( src[ 12 ] );
			dst[ 19 ] = decodeFloat16( src[ 17 ] );

			dst[ 20 ] = decodeFloat16( src[ 25 ] );
			dst[ 21 ] = decodeFloat16( src[ 30 ] );
			dst[ 22 ] = decodeFloat16( src[ 41 ] );
			dst[ 23 ] = decodeFloat16( src[ 43 ] );
			dst[ 24 ] = decodeFloat16( src[ 9 ] );
			dst[ 25 ] = decodeFloat16( src[ 11 ] );
			dst[ 26 ] = decodeFloat16( src[ 18 ] );
			dst[ 27 ] = decodeFloat16( src[ 24 ] );
			dst[ 28 ] = decodeFloat16( src[ 31 ] );
			dst[ 29 ] = decodeFloat16( src[ 40 ] );

			dst[ 30 ] = decodeFloat16( src[ 44 ] );
			dst[ 31 ] = decodeFloat16( src[ 53 ] );
			dst[ 32 ] = decodeFloat16( src[ 10 ] );
			dst[ 33 ] = decodeFloat16( src[ 19 ] );
			dst[ 34 ] = decodeFloat16( src[ 23 ] );
			dst[ 35 ] = decodeFloat16( src[ 32 ] );
			dst[ 36 ] = decodeFloat16( src[ 39 ] );
			dst[ 37 ] = decodeFloat16( src[ 45 ] );
			dst[ 38 ] = decodeFloat16( src[ 52 ] );
			dst[ 39 ] = decodeFloat16( src[ 54 ] );

			dst[ 40 ] = decodeFloat16( src[ 20 ] );
			dst[ 41 ] = decodeFloat16( src[ 22 ] );
			dst[ 42 ] = decodeFloat16( src[ 33 ] );
			dst[ 43 ] = decodeFloat16( src[ 38 ] );
			dst[ 44 ] = decodeFloat16( src[ 46 ] );
			dst[ 45 ] = decodeFloat16( src[ 51 ] );
			dst[ 46 ] = decodeFloat16( src[ 55 ] );
			dst[ 47 ] = decodeFloat16( src[ 60 ] );
			dst[ 48 ] = decodeFloat16( src[ 21 ] );
			dst[ 49 ] = decodeFloat16( src[ 34 ] );

			dst[ 50 ] = decodeFloat16( src[ 37 ] );
			dst[ 51 ] = decodeFloat16( src[ 47 ] );
			dst[ 52 ] = decodeFloat16( src[ 50 ] );
			dst[ 53 ] = decodeFloat16( src[ 56 ] );
			dst[ 54 ] = decodeFloat16( src[ 59 ] );
			dst[ 55 ] = decodeFloat16( src[ 61 ] );
			dst[ 56 ] = decodeFloat16( src[ 35 ] );
			dst[ 57 ] = decodeFloat16( src[ 36 ] );
			dst[ 58 ] = decodeFloat16( src[ 48 ] );
			dst[ 59 ] = decodeFloat16( src[ 49 ] );

			dst[ 60 ] = decodeFloat16( src[ 57 ] );
			dst[ 61 ] = decodeFloat16( src[ 58 ] );
			dst[ 62 ] = decodeFloat16( src[ 62 ] );
			dst[ 63 ] = decodeFloat16( src[ 63 ] );

		}
```
</details>

### `dctInverse(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `Math.cos`

<details><summary>Code</summary>

```typescript
function dctInverse( data ) {

			const a = 0.5 * Math.cos( 3.14159 / 4.0 );
			const b = 0.5 * Math.cos( 3.14159 / 16.0 );
			const c = 0.5 * Math.cos( 3.14159 / 8.0 );
			const d = 0.5 * Math.cos( 3.0 * 3.14159 / 16.0 );
			const e = 0.5 * Math.cos( 5.0 * 3.14159 / 16.0 );
			const f = 0.5 * Math.cos( 3.0 * 3.14159 / 8.0 );
			const g = 0.5 * Math.cos( 7.0 * 3.14159 / 16.0 );

			const alpha = new Array( 4 );
			const beta = new Array( 4 );
			const theta = new Array( 4 );
			const gamma = new Array( 4 );

			for ( let row = 0; row < 8; ++ row ) {

				const rowPtr = row * 8;

				alpha[ 0 ] = c * data[ rowPtr + 2 ];
				alpha[ 1 ] = f * data[ rowPtr + 2 ];
				alpha[ 2 ] = c * data[ rowPtr + 6 ];
				alpha[ 3 ] = f * data[ rowPtr + 6 ];

				beta[ 0 ] = b * data[ rowPtr + 1 ] + d * data[ rowPtr + 3 ] + e * data[ rowPtr + 5 ] + g * data[ rowPtr + 7 ];
				beta[ 1 ] = d * data[ rowPtr + 1 ] - g * data[ rowPtr + 3 ] - b * data[ rowPtr + 5 ] - e * data[ rowPtr + 7 ];
				beta[ 2 ] = e * data[ rowPtr + 1 ] - b * data[ rowPtr + 3 ] + g * data[ rowPtr + 5 ] + d * data[ rowPtr + 7 ];
				beta[ 3 ] = g * data[ rowPtr + 1 ] - e * data[ rowPtr + 3 ] + d * data[ rowPtr + 5 ] - b * data[ rowPtr + 7 ];

				theta[ 0 ] = a * ( data[ rowPtr + 0 ] + data[ rowPtr + 4 ] );
				theta[ 3 ] = a * ( data[ rowPtr + 0 ] - data[ rowPtr + 4 ] );
				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ rowPtr + 0 ] = gamma[ 0 ] + beta[ 0 ];
				data[ rowPtr + 1 ] = gamma[ 1 ] + beta[ 1 ];
				data[ rowPtr + 2 ] = gamma[ 2 ] + beta[ 2 ];
				data[ rowPtr + 3 ] = gamma[ 3 ] + beta[ 3 ];

				data[ rowPtr + 4 ] = gamma[ 3 ] - beta[ 3 ];
				data[ rowPtr + 5 ] = gamma[ 2 ] - beta[ 2 ];
				data[ rowPtr + 6 ] = gamma[ 1 ] - beta[ 1 ];
				data[ rowPtr + 7 ] = gamma[ 0 ] - beta[ 0 ];

			}

			for ( let column = 0; column < 8; ++ column ) {

				alpha[ 0 ] = c * data[ 16 + column ];
				alpha[ 1 ] = f * data[ 16 + column ];
				alpha[ 2 ] = c * data[ 48 + column ];
				alpha[ 3 ] = f * data[ 48 + column ];

				beta[ 0 ] = b * data[ 8 + column ] + d * data[ 24 + column ] + e * data[ 40 + column ] + g * data[ 56 + column ];
				beta[ 1 ] = d * data[ 8 + column ] - g * data[ 24 + column ] - b * data[ 40 + column ] - e * data[ 56 + column ];
				beta[ 2 ] = e * data[ 8 + column ] - b * data[ 24 + column ] + g * data[ 40 + column ] + d * data[ 56 + column ];
				beta[ 3 ] = g * data[ 8 + column ] - e * data[ 24 + column ] + d * data[ 40 + column ] - b * data[ 56 + column ];

				theta[ 0 ] = a * ( data[ column ] + data[ 32 + column ] );
				theta[ 3 ] = a * ( data[ column ] - data[ 32 + column ] );

				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ 0 + column ] = gamma[ 0 ] + beta[ 0 ];
				data[ 8 + column ] = gamma[ 1 ] + beta[ 1 ];
				data[ 16 + column ] = gamma[ 2 ] + beta[ 2 ];
				data[ 24 + column ] = gamma[ 3 ] + beta[ 3 ];

				data[ 32 + column ] = gamma[ 3 ] - beta[ 3 ];
				data[ 40 + column ] = gamma[ 2 ] - beta[ 2 ];
				data[ 48 + column ] = gamma[ 1 ] - beta[ 1 ];
				data[ 56 + column ] = gamma[ 0 ] - beta[ 0 ];

			}

		}
```
</details>

### `csc709Inverse(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function csc709Inverse( data ) {

			for ( let i = 0; i < 64; ++ i ) {

				const y = data[ 0 ][ i ];
				const cb = data[ 1 ][ i ];
				const cr = data[ 2 ][ i ];

				data[ 0 ][ i ] = y + 1.5747 * cr;
				data[ 1 ][ i ] = y - 0.1873 * cb - 0.4682 * cr;
				data[ 2 ][ i ] = y + 1.8556 * cb;

			}

		}
```
</details>

### `convertToHalf(src: any, dst: any, idx: any): void`

**Parameters:**

- **`src`** `any`
- **`dst`** `any`
- **`idx`** `any`

**Returns:** `void`

**Calls:**

- `DataUtils.toHalfFloat`
- `toLinear`

<details><summary>Code</summary>

```typescript
function convertToHalf( src, dst, idx ) {

			for ( let i = 0; i < 64; ++ i ) {

				dst[ idx + i ] = DataUtils.toHalfFloat( toLinear( src[ i ] ) );

			}

		}
```
</details>

### `toLinear(float: any): number`

**Parameters:**

- **`float`** `any`

**Returns:** `number`

**Calls:**

- `Math.sign`
- `Math.pow`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function toLinear( float ) {

			if ( float <= 1 ) {

				return Math.sign( float ) * Math.pow( Math.abs( float ), 2.2 );

			} else {

				return Math.sign( float ) * Math.pow( logBase, Math.abs( float ) - 1.0 );

			}

		}
```
</details>

### `uncompressRAW(info: any): DataView<any>`

**Parameters:**

- **`info`** `any`

**Returns:** `DataView<any>`

<details><summary>Code</summary>

```typescript
function uncompressRAW( info ) {

			return new DataView( info.array.buffer, info.offset.value, info.size );

		}
```
</details>

### `uncompressRLE(info: any): DataView<ArrayBuffer>`

**Parameters:**

- **`info`** `any`

**Returns:** `DataView<ArrayBuffer>`

**Calls:**

- `info.viewer.buffer.slice`
- `decodeRunLength`
- `predictor`
- `interleaveScalar`

<details><summary>Code</summary>

```typescript
function uncompressRLE( info ) {

			const compressed = info.viewer.buffer.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = new Uint8Array( decodeRunLength( compressed ) );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}
```
</details>

### `uncompressZIP(info: any): DataView<any>`

**Parameters:**

- **`info`** `any`

**Returns:** `DataView<any>`

**Calls:**

- `info.array.slice`
- `fflate.unzlibSync`
- `predictor`
- `interleaveScalar`

<details><summary>Code</summary>

```typescript
function uncompressZIP( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}
```
</details>

### `uncompressPIZ(info: any): DataView<ArrayBuffer>`

**Parameters:**

- **`info`** `any`

**Returns:** `DataView<ArrayBuffer>`

**Calls:**

- `parseUint16`
- `parseUint8`
- `reverseLutFromBitmap`
- `parseUint32`
- `hufUncompress`
- `wav2Decode`
- `applyLut`
- `tmpBuffer.set`

**Internal Comments:**
```
// Setup channel info (x2)
// Read range compression data (x2)
// Reverse LUT (x2)
// Huffman decoding (x3)
// Wavelet decoding
// Expand the pixel data to their original range (x3)
// Rearrange the pixel data into the format expected by the caller. (x2)
```

<details><summary>Code</summary>

```typescript
function uncompressPIZ( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };

			const outBuffer = new Uint16Array( info.columns * info.lines * ( info.inputChannels.length * info.type ) );
			const bitmap = new Uint8Array( BITMAP_SIZE );

			// Setup channel info
			let outBufferEnd = 0;
			const pizChannelData = new Array( info.inputChannels.length );
			for ( let i = 0, il = info.inputChannels.length; i < il; i ++ ) {

				pizChannelData[ i ] = {};
				pizChannelData[ i ][ 'start' ] = outBufferEnd;
				pizChannelData[ i ][ 'end' ] = pizChannelData[ i ][ 'start' ];
				pizChannelData[ i ][ 'nx' ] = info.columns;
				pizChannelData[ i ][ 'ny' ] = info.lines;
				pizChannelData[ i ][ 'size' ] = info.type;

				outBufferEnd += pizChannelData[ i ].nx * pizChannelData[ i ].ny * pizChannelData[ i ].size;

			}

			// Read range compression data

			const minNonZero = parseUint16( inDataView, inOffset );
			const maxNonZero = parseUint16( inDataView, inOffset );

			if ( maxNonZero >= BITMAP_SIZE ) {

				throw new Error( 'Something is wrong with PIZ_COMPRESSION BITMAP_SIZE' );

			}

			if ( minNonZero <= maxNonZero ) {

				for ( let i = 0; i < maxNonZero - minNonZero + 1; i ++ ) {

					bitmap[ i + minNonZero ] = parseUint8( inDataView, inOffset );

				}

			}

			// Reverse LUT
			const lut = new Uint16Array( USHORT_RANGE );
			const maxValue = reverseLutFromBitmap( bitmap, lut );

			const length = parseUint32( inDataView, inOffset );

			// Huffman decoding
			hufUncompress( info.array, inDataView, inOffset, length, outBuffer, outBufferEnd );

			// Wavelet decoding
			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = pizChannelData[ i ];

				for ( let j = 0; j < pizChannelData[ i ].size; ++ j ) {

					wav2Decode(
						outBuffer,
						cd.start + j,
						cd.nx,
						cd.size,
						cd.ny,
						cd.nx * cd.size,
						maxValue
					);

				}

			}

			// Expand the pixel data to their original range
			applyLut( lut, outBuffer, outBufferEnd );

			// Rearrange the pixel data into the format expected by the caller.
			let tmpOffset = 0;
			const tmpBuffer = new Uint8Array( outBuffer.buffer.byteLength );
			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					const cd = pizChannelData[ c ];

					const n = cd.nx * cd.size;
					const cp = new Uint8Array( outBuffer.buffer, cd.end * INT16_SIZE, n * INT16_SIZE );

					tmpBuffer.set( cp, tmpOffset );
					tmpOffset += n * INT16_SIZE;
					cd.end += n;

				}

			}

			return new DataView( tmpBuffer.buffer );

		}
```
</details>

### `uncompressPXR(info: any): DataView<ArrayBuffer>`

**Parameters:**

- **`info`** `any`

**Returns:** `DataView<ArrayBuffer>`

**Calls:**

- `info.array.slice`
- `fflate.unzlibSync`
- `viewer.setUint16`
- `viewer.setUint32`

<details><summary>Code</summary>

```typescript
function uncompressPXR( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );

			const byteSize = info.inputChannels.length * info.lines * info.columns * info.totalBytes;
			const tmpBuffer = new ArrayBuffer( byteSize );
			const viewer = new DataView( tmpBuffer );

			let tmpBufferEnd = 0;
			let writePtr = 0;
			const ptr = new Array( 4 );

			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					let pixel = 0;

					const type = info.inputChannels[ c ].pixelType;
					switch ( type ) {

						case 1:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							tmpBufferEnd = ptr[ 1 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 8 ) | rawBuffer[ ptr[ 1 ] ++ ];

								pixel += diff;

								viewer.setUint16( writePtr, pixel, true );
								writePtr += 2;

							}

							break;

						case 2:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							ptr[ 2 ] = ptr[ 1 ] + info.columns;
							tmpBufferEnd = ptr[ 2 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 24 ) | ( rawBuffer[ ptr[ 1 ] ++ ] << 16 ) | ( rawBuffer[ ptr[ 2 ] ++ ] << 8 );

								pixel += diff;

								viewer.setUint32( writePtr, pixel, true );
								writePtr += 4;

							}

							break;

					}

				}

			}

			return viewer;

		}
```
</details>

### `uncompressDWA(info: any): DataView<ArrayBuffer>`

**Parameters:**

- **`info`** `any`

**Returns:** `DataView<ArrayBuffer>`

**Calls:**

- `parseInt64`
- `parseUint16`
- `parseNullTerminatedString`
- `parseUint8`
- `channelRules.push`
- `hufUncompress`
- `info.array.slice`
- `fflate.unzlibSync`
- `uncompressZIP`
- `decodeRunLength`
- `rowOffsets[ chan ].push`
- `lossyDctDecode`
- `lossyDctChannelDecode`

**Internal Comments:**
```
// Read compression header information (x2)
// Read channel ruleset information (x2)
// Classify channels (x2)
// Read DCT - AC component data
// Read DCT - DC component data
// Read RLE compressed data
// Prepare outbuffer data offset (x2)
// Decode lossy DCT data if we have a valid color space conversion set with the first RGB channel present
// Decode other channels
```

<details><summary>Code</summary>

```typescript
function uncompressDWA( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };
			const outBuffer = new Uint8Array( info.columns * info.lines * ( info.inputChannels.length * info.type * INT16_SIZE ) );

			// Read compression header information
			const dwaHeader = {

				version: parseInt64( inDataView, inOffset ),
				unknownUncompressedSize: parseInt64( inDataView, inOffset ),
				unknownCompressedSize: parseInt64( inDataView, inOffset ),
				acCompressedSize: parseInt64( inDataView, inOffset ),
				dcCompressedSize: parseInt64( inDataView, inOffset ),
				rleCompressedSize: parseInt64( inDataView, inOffset ),
				rleUncompressedSize: parseInt64( inDataView, inOffset ),
				rleRawSize: parseInt64( inDataView, inOffset ),
				totalAcUncompressedCount: parseInt64( inDataView, inOffset ),
				totalDcUncompressedCount: parseInt64( inDataView, inOffset ),
				acCompression: parseInt64( inDataView, inOffset )

			};

			if ( dwaHeader.version < 2 )
				throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' version ' + dwaHeader.version + ' is unsupported' );

			// Read channel ruleset information
			const channelRules = new Array();
			let ruleSize = parseUint16( inDataView, inOffset ) - INT16_SIZE;

			while ( ruleSize > 0 ) {

				const name = parseNullTerminatedString( inDataView.buffer, inOffset );
				const value = parseUint8( inDataView, inOffset );
				const compression = ( value >> 2 ) & 3;
				const csc = ( value >> 4 ) - 1;
				const index = new Int8Array( [ csc ] )[ 0 ];
				const type = parseUint8( inDataView, inOffset );

				channelRules.push( {
					name: name,
					index: index,
					type: type,
					compression: compression,
				} );

				ruleSize -= name.length + 3;

			}

			// Classify channels
			const channels = EXRHeader.channels;
			const channelData = new Array( info.inputChannels.length );

			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = channelData[ i ] = {};
				const channel = channels[ i ];

				cd.name = channel.name;
				cd.compression = UNKNOWN;
				cd.decoded = false;
				cd.type = channel.pixelType;
				cd.pLinear = channel.pLinear;
				cd.width = info.columns;
				cd.height = info.lines;

			}

			const cscSet = {
				idx: new Array( 3 )
			};

			for ( let offset = 0; offset < info.inputChannels.length; ++ offset ) {

				const cd = channelData[ offset ];

				for ( let i = 0; i < channelRules.length; ++ i ) {

					const rule = channelRules[ i ];

					if ( cd.name == rule.name ) {

						cd.compression = rule.compression;

						if ( rule.index >= 0 ) {

							cscSet.idx[ rule.index ] = offset;

						}

						cd.offset = offset;

					}

				}

			}

			let acBuffer, dcBuffer, rleBuffer;

			// Read DCT - AC component data
			if ( dwaHeader.acCompressedSize > 0 ) {

				switch ( dwaHeader.acCompression ) {

					case STATIC_HUFFMAN:

						acBuffer = new Uint16Array( dwaHeader.totalAcUncompressedCount );
						hufUncompress( info.array, inDataView, inOffset, dwaHeader.acCompressedSize, acBuffer, dwaHeader.totalAcUncompressedCount );
						break;

					case DEFLATE:

						const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.totalAcUncompressedCount );
						const data = fflate.unzlibSync( compressed );
						acBuffer = new Uint16Array( data.buffer );
						inOffset.value += dwaHeader.totalAcUncompressedCount;
						break;

				}


			}

			// Read DCT - DC component data
			if ( dwaHeader.dcCompressedSize > 0 ) {

				const zlibInfo = {
					array: info.array,
					offset: inOffset,
					size: dwaHeader.dcCompressedSize
				};
				dcBuffer = new Uint16Array( uncompressZIP( zlibInfo ).buffer );
				inOffset.value += dwaHeader.dcCompressedSize;

			}

			// Read RLE compressed data
			if ( dwaHeader.rleRawSize > 0 ) {

				const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.rleCompressedSize );
				const data = fflate.unzlibSync( compressed );
				rleBuffer = decodeRunLength( data.buffer );

				inOffset.value += dwaHeader.rleCompressedSize;

			}

			// Prepare outbuffer data offset
			let outBufferEnd = 0;
			const rowOffsets = new Array( channelData.length );
			for ( let i = 0; i < rowOffsets.length; ++ i ) {

				rowOffsets[ i ] = new Array();

			}

			for ( let y = 0; y < info.lines; ++ y ) {

				for ( let chan = 0; chan < channelData.length; ++ chan ) {

					rowOffsets[ chan ].push( outBufferEnd );
					outBufferEnd += channelData[ chan ].width * info.type * INT16_SIZE;

				}

			}

			// Decode lossy DCT data if we have a valid color space conversion set with the first RGB channel present
			if ( cscSet.idx[ 0 ] !== undefined && channelData[ cscSet.idx[ 0 ] ] ) {

				lossyDctDecode( cscSet, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

			}

			// Decode other channels
			for ( let i = 0; i < channelData.length; ++ i ) {

				const cd = channelData[ i ];

				if ( cd.decoded ) continue;

				switch ( cd.compression ) {

					case RLE:

						let row = 0;
						let rleOffset = 0;

						for ( let y = 0; y < info.lines; ++ y ) {

							let rowOffsetBytes = rowOffsets[ i ][ row ];

							for ( let x = 0; x < cd.width; ++ x ) {

								for ( let byte = 0; byte < INT16_SIZE * cd.type; ++ byte ) {

									outBuffer[ rowOffsetBytes ++ ] = rleBuffer[ rleOffset + byte * cd.width * cd.height ];

								}

								rleOffset ++;

							}

							row ++;

						}

						break;

					case LOSSY_DCT:

						lossyDctChannelDecode( i, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

						break;

					default:
						throw new Error( 'EXRLoader.parse: unsupported channel compression' );

				}

			}

			return new DataView( outBuffer.buffer );

		}
```
</details>

### `parseNullTerminatedString(buffer: any, offset: any): string`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `string`

**Calls:**

- `new TextDecoder().decode`
- `uintBuffer.slice`

<details><summary>Code</summary>

```typescript
function parseNullTerminatedString( buffer, offset ) {

			const uintBuffer = new Uint8Array( buffer );
			let endOffset = 0;

			while ( uintBuffer[ offset.value + endOffset ] != 0 ) {

				endOffset += 1;

			}

			const stringValue = new TextDecoder().decode(
				uintBuffer.slice( offset.value, offset.value + endOffset )
			);

			offset.value = offset.value + endOffset + 1;

			return stringValue;

		}
```
</details>

### `parseFixedLengthString(buffer: any, offset: any, size: any): string`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`
- **`size`** `any`

**Returns:** `string`

**Calls:**

- `new TextDecoder().decode`
- `new Uint8Array( buffer ).slice`

<details><summary>Code</summary>

```typescript
function parseFixedLengthString( buffer, offset, size ) {

			const stringValue = new TextDecoder().decode(
				new Uint8Array( buffer ).slice( offset.value, offset.value + size )
			);

			offset.value = offset.value + size;

			return stringValue;

		}
```
</details>

### `parseRational(dataView: any, offset: any): any[]`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any[]`

**Calls:**

- `parseInt32`
- `parseUint32`

<details><summary>Code</summary>

```typescript
function parseRational( dataView, offset ) {

			const x = parseInt32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}
```
</details>

### `parseTimecode(dataView: any, offset: any): any[]`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any[]`

**Calls:**

- `parseUint32`

<details><summary>Code</summary>

```typescript
function parseTimecode( dataView, offset ) {

			const x = parseUint32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}
```
</details>

### `parseInt32(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getInt32`

<details><summary>Code</summary>

```typescript
function parseInt32( dataView, offset ) {

			const Int32 = dataView.getInt32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Int32;

		}
```
</details>

### `parseUint32(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getUint32`

<details><summary>Code</summary>

```typescript
function parseUint32( dataView, offset ) {

			const Uint32 = dataView.getUint32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Uint32;

		}
```
</details>

### `parseUint8Array(uInt8Array: any, offset: any): any`

**Parameters:**

- **`uInt8Array`** `any`
- **`offset`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function parseUint8Array( uInt8Array, offset ) {

			const Uint8 = uInt8Array[ offset.value ];

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}
```
</details>

### `parseUint8(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getUint8`

<details><summary>Code</summary>

```typescript
function parseUint8( dataView, offset ) {

			const Uint8 = dataView.getUint8( offset.value );

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}
```
</details>

### `parseInt64(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `Number`
- `dataView.getBigInt64`
- `dataView.getUint32`

<details><summary>Code</summary>

```typescript
function ( dataView, offset ) {

			let int;

			if ( 'getBigInt64' in DataView.prototype ) {

				int = Number( dataView.getBigInt64( offset.value, true ) );

			} else {

				int = dataView.getUint32( offset.value + 4, true ) + Number( dataView.getUint32( offset.value, true ) << 32 );

			}

			offset.value += ULONG_SIZE;

			return int;

		}
```
</details>

### `parseFloat32(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getFloat32`

<details><summary>Code</summary>

```typescript
function parseFloat32( dataView, offset ) {

			const float = dataView.getFloat32( offset.value, true );

			offset.value += FLOAT32_SIZE;

			return float;

		}
```
</details>

### `decodeFloat32(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `DataUtils.toHalfFloat`
- `parseFloat32`

<details><summary>Code</summary>

```typescript
function decodeFloat32( dataView, offset ) {

			return DataUtils.toHalfFloat( parseFloat32( dataView, offset ) );

		}
```
</details>

### `decodeFloat16(binary: any): number`

**Parameters:**

- **`binary`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function decodeFloat16( binary ) {

			const exponent = ( binary & 0x7C00 ) >> 10,
				fraction = binary & 0x03FF;

			return ( binary >> 15 ? - 1 : 1 ) * (
				exponent ?
					(
						exponent === 0x1F ?
							fraction ? NaN : Infinity :
							Math.pow( 2, exponent - 15 ) * ( 1 + fraction / 0x400 )
					) :
					6.103515625e-5 * ( fraction / 0x400 )
			);

		}
```
</details>

### `parseUint16(dataView: any, offset: any): any`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `dataView.getUint16`

<details><summary>Code</summary>

```typescript
function parseUint16( dataView, offset ) {

			const Uint16 = dataView.getUint16( offset.value, true );

			offset.value += INT16_SIZE;

			return Uint16;

		}
```
</details>

### `parseFloat16(buffer: any, offset: any): number`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `number`

**Calls:**

- `decodeFloat16`
- `parseUint16`

<details><summary>Code</summary>

```typescript
function parseFloat16( buffer, offset ) {

			return decodeFloat16( parseUint16( buffer, offset ) );

		}
```
</details>

### `parseChlist(dataView: any, buffer: any, offset: any, size: any): { name: string; pixelType: any; pLinear: any; xSampling: any; ySampling: any; }[]`

**Parameters:**

- **`dataView`** `any`
- **`buffer`** `any`
- **`offset`** `any`
- **`size`** `any`

**Returns:** `{ name: string; pixelType: any; pLinear: any; xSampling: any; ySampling: any; }[]`

**Calls:**

- `parseNullTerminatedString`
- `parseInt32`
- `parseUint8`
- `channels.push`

<details><summary>Code</summary>

```typescript
function parseChlist( dataView, buffer, offset, size ) {

			const startOffset = offset.value;
			const channels = [];

			while ( offset.value < ( startOffset + size - 1 ) ) {

				const name = parseNullTerminatedString( buffer, offset );
				const pixelType = parseInt32( dataView, offset );
				const pLinear = parseUint8( dataView, offset );
				offset.value += 3; // reserved, three chars
				const xSampling = parseInt32( dataView, offset );
				const ySampling = parseInt32( dataView, offset );

				channels.push( {
					name: name,
					pixelType: pixelType,
					pLinear: pLinear,
					xSampling: xSampling,
					ySampling: ySampling
				} );

			}

			offset.value += 1;

			return channels;

		}
```
</details>

### `parseChromaticities(dataView: any, offset: any): { redX: any; redY: any; greenX: any; greenY: any; blueX: any; blueY: any; whiteX: any; whiteY: any; }`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `{ redX: any; redY: any; greenX: any; greenY: any; blueX: any; blueY: any; whiteX: any; whiteY: any; }`

**Calls:**

- `parseFloat32`

<details><summary>Code</summary>

```typescript
function parseChromaticities( dataView, offset ) {

			const redX = parseFloat32( dataView, offset );
			const redY = parseFloat32( dataView, offset );
			const greenX = parseFloat32( dataView, offset );
			const greenY = parseFloat32( dataView, offset );
			const blueX = parseFloat32( dataView, offset );
			const blueY = parseFloat32( dataView, offset );
			const whiteX = parseFloat32( dataView, offset );
			const whiteY = parseFloat32( dataView, offset );

			return { redX: redX, redY: redY, greenX: greenX, greenY: greenY, blueX: blueX, blueY: blueY, whiteX: whiteX, whiteY: whiteY };

		}
```
</details>

### `parseCompression(dataView: any, offset: any): string`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `string`

**Calls:**

- `parseUint8`

<details><summary>Code</summary>

```typescript
function parseCompression( dataView, offset ) {

			const compressionCodes = [
				'NO_COMPRESSION',
				'RLE_COMPRESSION',
				'ZIPS_COMPRESSION',
				'ZIP_COMPRESSION',
				'PIZ_COMPRESSION',
				'PXR24_COMPRESSION',
				'B44_COMPRESSION',
				'B44A_COMPRESSION',
				'DWAA_COMPRESSION',
				'DWAB_COMPRESSION'
			];

			const compression = parseUint8( dataView, offset );

			return compressionCodes[ compression ];

		}
```
</details>

### `parseBox2i(dataView: any, offset: any): { xMin: any; yMin: any; xMax: any; yMax: any; }`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `{ xMin: any; yMin: any; xMax: any; yMax: any; }`

**Calls:**

- `parseInt32`

<details><summary>Code</summary>

```typescript
function parseBox2i( dataView, offset ) {

			const xMin = parseInt32( dataView, offset );
			const yMin = parseInt32( dataView, offset );
			const xMax = parseInt32( dataView, offset );
			const yMax = parseInt32( dataView, offset );

			return { xMin: xMin, yMin: yMin, xMax: xMax, yMax: yMax };

		}
```
</details>

### `parseLineOrder(dataView: any, offset: any): string`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `string`

**Calls:**

- `parseUint8`

<details><summary>Code</summary>

```typescript
function parseLineOrder( dataView, offset ) {

			const lineOrders = [
				'INCREASING_Y',
				'DECREASING_Y',
				'RANDOM_Y',
			];

			const lineOrder = parseUint8( dataView, offset );

			return lineOrders[ lineOrder ];

		}
```
</details>

### `parseEnvmap(dataView: any, offset: any): string`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `string`

**Calls:**

- `parseUint8`

<details><summary>Code</summary>

```typescript
function parseEnvmap( dataView, offset ) {

			const envmaps = [
				'ENVMAP_LATLONG',
				'ENVMAP_CUBE'
			];

			const envmap = parseUint8( dataView, offset );

			return envmaps[ envmap ];

		}
```
</details>

### `parseTiledesc(dataView: any, offset: any): { xSize: any; ySize: any; levelMode: string; roundingMode: string; }`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `{ xSize: any; ySize: any; levelMode: string; roundingMode: string; }`

**Calls:**

- `parseUint32`
- `parseUint8`

<details><summary>Code</summary>

```typescript
function parseTiledesc( dataView, offset ) {

			const levelModes = [
				'ONE_LEVEL',
				'MIPMAP_LEVELS',
				'RIPMAP_LEVELS',
			];

			const roundingModes = [
				'ROUND_DOWN',
				'ROUND_UP',
			];

			const xSize = parseUint32( dataView, offset );
			const ySize = parseUint32( dataView, offset );
			const modes = parseUint8( dataView, offset );

			return {
				xSize: xSize,
				ySize: ySize,
				levelMode: levelModes[ modes & 0xf ],
				roundingMode: roundingModes[ modes >> 4 ]
			};

		}
```
</details>

### `parseV2f(dataView: any, offset: any): any[]`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any[]`

**Calls:**

- `parseFloat32`

<details><summary>Code</summary>

```typescript
function parseV2f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );

			return [ x, y ];

		}
```
</details>

### `parseV3f(dataView: any, offset: any): any[]`

**Parameters:**

- **`dataView`** `any`
- **`offset`** `any`

**Returns:** `any[]`

**Calls:**

- `parseFloat32`

<details><summary>Code</summary>

```typescript
function parseV3f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );
			const z = parseFloat32( dataView, offset );

			return [ x, y, z ];

		}
```
</details>

### `parseValue(dataView: any, buffer: any, offset: any, type: any, size: any): any`

**Parameters:**

- **`dataView`** `any`
- **`buffer`** `any`
- **`offset`** `any`
- **`type`** `any`
- **`size`** `any`

**Returns:** `any`

**Calls:**

- `parseFixedLengthString`
- `parseChlist`
- `parseChromaticities`
- `parseCompression`
- `parseBox2i`
- `parseEnvmap`
- `parseTiledesc`
- `parseLineOrder`
- `parseFloat32`
- `parseV2f`
- `parseV3f`
- `parseInt32`
- `parseRational`
- `parseTimecode`

<details><summary>Code</summary>

```typescript
function parseValue( dataView, buffer, offset, type, size ) {

			if ( type === 'string' || type === 'stringvector' || type === 'iccProfile' ) {

				return parseFixedLengthString( buffer, offset, size );

			} else if ( type === 'chlist' ) {

				return parseChlist( dataView, buffer, offset, size );

			} else if ( type === 'chromaticities' ) {

				return parseChromaticities( dataView, offset );

			} else if ( type === 'compression' ) {

				return parseCompression( dataView, offset );

			} else if ( type === 'box2i' ) {

				return parseBox2i( dataView, offset );

			} else if ( type === 'envmap' ) {

				return parseEnvmap( dataView, offset );

			} else if ( type === 'tiledesc' ) {

				return parseTiledesc( dataView, offset );

			} else if ( type === 'lineOrder' ) {

				return parseLineOrder( dataView, offset );

			} else if ( type === 'float' ) {

				return parseFloat32( dataView, offset );

			} else if ( type === 'v2f' ) {

				return parseV2f( dataView, offset );

			} else if ( type === 'v3f' ) {

				return parseV3f( dataView, offset );

			} else if ( type === 'int' ) {

				return parseInt32( dataView, offset );

			} else if ( type === 'rational' ) {

				return parseRational( dataView, offset );

			} else if ( type === 'timecode' ) {

				return parseTimecode( dataView, offset );

			} else if ( type === 'preview' ) {

				offset.value += size;
				return 'skipped';

			} else {

				offset.value += size;
				return undefined;

			}

		}
```
</details>

### `roundLog2(x: any, mode: any): number`

**Parameters:**

- **`x`** `any`
- **`mode`** `any`

**Returns:** `number`

**Calls:**

- `Math.log2`
- `Math.floor`
- `Math.ceil`

<details><summary>Code</summary>

```typescript
function roundLog2( x, mode ) {

			const log2 = Math.log2( x );
			return mode == 'ROUND_DOWN' ? Math.floor( log2 ) : Math.ceil( log2 );

		}
```
</details>

### `calculateTileLevels(tiledesc: any, w: any, h: any): number`

**Parameters:**

- **`tiledesc`** `any`
- **`w`** `any`
- **`h`** `any`

**Returns:** `number`

**Calls:**

- `roundLog2`
- `Math.max`

<details><summary>Code</summary>

```typescript
function calculateTileLevels( tiledesc, w, h ) {

			let num = 0;

			switch ( tiledesc.levelMode ) {

				case 'ONE_LEVEL':
					num = 1;
					break;

				case 'MIPMAP_LEVELS':
					num = roundLog2( Math.max( w, h ), tiledesc.roundingMode ) + 1;
					break;

				case 'RIPMAP_LEVELS':
					throw new Error( 'THREE.EXRLoader: RIPMAP_LEVELS tiles currently unsupported.' );

			}

			return num;

		}
```
</details>

### `calculateTiles(count: any, dataSize: any, size: any, roundingMode: any): any[]`

**Parameters:**

- **`count`** `any`
- **`dataSize`** `any`
- **`size`** `any`
- **`roundingMode`** `any`

**Returns:** `any[]`

**Calls:**

- `Math.max`

<details><summary>Code</summary>

```typescript
function calculateTiles( count, dataSize, size, roundingMode ) {

			const tiles = new Array( count );

			for ( let i = 0; i < count; i ++ ) {

				const b = ( 1 << i );
				let s = ( dataSize / b ) | 0;

				if ( roundingMode == 'ROUND_UP' && s * b < dataSize ) s += 1;

				const l = Math.max( s, 1 );

				tiles[ i ] = ( ( l + size - 1 ) / size ) | 0;

			}

			return tiles;

		}
```
</details>

### `parseTiles(): void`

**Returns:** `void`

**Calls:**

- `parseInt32`
- `parseUint32`
- `EXRDecoder.uncompress`
- `uncompressRAW`
- `EXRDecoder.getter`

<details><summary>Code</summary>

```typescript
function parseTiles() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let tile = 0; tile < EXRDecoder.tileCount; tile ++ ) {

				const tileX = parseInt32( EXRDecoder.viewer, offset );
				const tileY = parseInt32( EXRDecoder.viewer, offset );
				offset.value += 8; // skip levels - only parsing top-level
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset );

				const startX = tileX * EXRDecoder.blockWidth;
				const startY = tileY * EXRDecoder.blockHeight;
				EXRDecoder.columns = ( startX + EXRDecoder.blockWidth > EXRDecoder.width ) ? EXRDecoder.width - startX : EXRDecoder.blockWidth;
				EXRDecoder.lines = ( startY + EXRDecoder.blockHeight > EXRDecoder.height ) ? EXRDecoder.height - startY : EXRDecoder.blockHeight;

				const bytesBlockLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesBlockLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line = 0; line < EXRDecoder.lines; line ++ ) {

					const lineOffset = line * EXRDecoder.columns * EXRDecoder.totalBytes;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;
						const outLineOffset = ( EXRDecoder.height - ( 1 + startY + line ) ) * EXRDecoder.outLineWidth;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + ( x + startX ) * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}
```
</details>

### `parseScanline(): void`

**Returns:** `void`

**Calls:**

- `parseInt32`
- `parseUint32`
- `EXRDecoder.uncompress`
- `uncompressRAW`
- `EXRDecoder.scanOrder`
- `EXRDecoder.getter`

<details><summary>Code</summary>

```typescript
function parseScanline() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let scanlineBlockIdx = 0; scanlineBlockIdx < EXRDecoder.height / EXRDecoder.blockHeight; scanlineBlockIdx ++ ) {

				const line = parseInt32( EXRDecoder.viewer, offset ) - EXRHeader.dataWindow.yMin; // line_no
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset ); // data_len
				EXRDecoder.lines = ( ( line + EXRDecoder.blockHeight > EXRDecoder.height ) ? ( EXRDecoder.height - line ) : EXRDecoder.blockHeight );

				const bytesPerLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesPerLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line_y = 0; line_y < EXRDecoder.blockHeight; line_y ++ ) {

					const scan_y = scanlineBlockIdx * EXRDecoder.blockHeight;
					const true_y = line_y + EXRDecoder.scanOrder( scan_y );
					if ( true_y >= EXRDecoder.height ) continue;

					const lineOffset = line_y * bytesPerLine;
					const outLineOffset = ( EXRDecoder.height - 1 - true_y ) * EXRDecoder.outLineWidth;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + x * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}
```
</details>

### `parseHeader(dataView: any, buffer: any, offset: any): { version: any; spec: { singleTile: boolean; longName: boolean; deepFormat: boolean; multiPart: boolean; }; }`

**Parameters:**

- **`dataView`** `any`
- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `{ version: any; spec: { singleTile: boolean; longName: boolean; deepFormat: boolean; multiPart: boolean; }; }`

**Calls:**

- `dataView.getUint32`
- `dataView.getUint8`
- `parseNullTerminatedString`
- `parseUint32`
- `parseValue`
- `console.warn`
- `console.error`

**Internal Comments:**
```
// start of header (x4)
```

<details><summary>Code</summary>

```typescript
function parseHeader( dataView, buffer, offset ) {

			const EXRHeader = {};

			if ( dataView.getUint32( 0, true ) != 20000630 ) { // magic

				throw new Error( 'THREE.EXRLoader: Provided file doesn\'t appear to be in OpenEXR format.' );

			}

			EXRHeader.version = dataView.getUint8( 4 );

			const spec = dataView.getUint8( 5 ); // fullMask

			EXRHeader.spec = {
				singleTile: !! ( spec & 2 ),
				longName: !! ( spec & 4 ),
				deepFormat: !! ( spec & 8 ),
				multiPart: !! ( spec & 16 ),
			};

			// start of header

			offset.value = 8; // start at 8 - after pre-amble

			let keepReading = true;

			while ( keepReading ) {

				const attributeName = parseNullTerminatedString( buffer, offset );

				if ( attributeName === '' ) {

					keepReading = false;

				} else {

					const attributeType = parseNullTerminatedString( buffer, offset );
					const attributeSize = parseUint32( dataView, offset );
					const attributeValue = parseValue( dataView, buffer, offset, attributeType, attributeSize );

					if ( attributeValue === undefined ) {

						console.warn( `THREE.EXRLoader: Skipped unknown header attribute type \'${attributeType}\'.` );

					} else {

						EXRHeader[ attributeName ] = attributeValue;

					}

				}

			}

			if ( ( spec & ~ 0x06 ) != 0 ) { // unsupported deep-image, multi-part

				console.error( 'THREE.EXRHeader:', EXRHeader );
				throw new Error( 'THREE.EXRLoader: Provided file is currently unsupported.' );

			}

			return EXRHeader;

		}
```
</details>

### `setupDecoder(EXRHeader: any, dataView: any, uInt8Array: any, offset: any, outputType: any, outputFormat: any): { size: number; viewer: any; array: any; offset: any; width: number; height: number; inputChannels: any; channelByteOffsets: {}; shouldExpand: boolean; scanOrder: any; totalBytes: any; columns: any; ... 5 more ...; colorSpace: any; }`

**Parameters:**

- **`EXRHeader`** `any`
- **`dataView`** `any`
- **`uInt8Array`** `any`
- **`offset`** `any`
- **`outputType`** `any`
- **`outputFormat`** `any`

**Returns:** `{ size: number; viewer: any; array: any; offset: any; width: number; height: number; inputChannels: any; channelByteOffsets: {}; shouldExpand: boolean; scanOrder: any; totalBytes: any; columns: any; ... 5 more ...; colorSpace: any; }`

**Calls:**

- `EXRDecoder.byteArray.fill`
- `console.error`
- `calculateTileLevels`
- `calculateTiles`
- `parseInt64`
- `parseTiles.bind`
- `Math.ceil`
- `parseScanline.bind`

**Internal Comments:**
```
// RGB images will be converted to RGBA format, preventing software emulation in select devices. (x2)
// Validate if input texture contain supported channels
// Setup output texture configuration
// half
// float
// Fill initially with 1s for the alpha value if the texture is not RGBA, RGB values will be overwritten
// const numYLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height ); (x2)
```

<details><summary>Code</summary>

```typescript
function setupDecoder( EXRHeader, dataView, uInt8Array, offset, outputType, outputFormat ) {

			const EXRDecoder = {
				size: 0,
				viewer: dataView,
				array: uInt8Array,
				offset: offset,
				width: EXRHeader.dataWindow.xMax - EXRHeader.dataWindow.xMin + 1,
				height: EXRHeader.dataWindow.yMax - EXRHeader.dataWindow.yMin + 1,
				inputChannels: EXRHeader.channels,
				channelByteOffsets: {},
				shouldExpand: false,
				scanOrder: null,
				totalBytes: null,
				columns: null,
				lines: null,
				type: null,
				uncompress: null,
				getter: null,
				format: null,
				colorSpace: LinearSRGBColorSpace,
			};

			switch ( EXRHeader.compression ) {

				case 'NO_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRAW;
					break;

				case 'RLE_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRLE;
					break;

				case 'ZIPS_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'ZIP_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'PIZ_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressPIZ;
					break;

				case 'PXR24_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressPXR;
					break;

				case 'DWAA_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				case 'DWAB_COMPRESSION':
					EXRDecoder.blockHeight = 256;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				default:
					throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' is unsupported' );

			}

			const channels = {};
			for ( const channel of EXRHeader.channels ) {

				switch ( channel.name ) {

					case 'Y':
					case 'R':
					case 'G':
					case 'B':
					case 'A':
						channels[ channel.name ] = true;
						EXRDecoder.type = channel.pixelType;

				}

			}

			// RGB images will be converted to RGBA format, preventing software emulation in select devices.
			let fillAlpha = false;
			let invalidOutput = false;

			// Validate if input texture contain supported channels
			if ( channels.R && channels.G && channels.B ) {

				EXRDecoder.outputChannels = 4;

			} else if ( channels.Y ) {

				EXRDecoder.outputChannels = 1;

			} else {

				throw new Error( 'EXRLoader.parse: file contains unsupported data channels.' );

			}

			// Setup output texture configuration
			switch ( EXRDecoder.outputChannels ) {

				case 4:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = ! channels.A;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.decodeChannels = { R: 0, G: 1, B: 2, A: 3 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.decodeChannels = { R: 0, G: 1 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { R: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				case 1:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = true;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				default:

					invalidOutput = true;

			}

			if (invalidOutput) throw new Error( 'EXRLoader.parse: invalid output format for specified file.' );

			if ( EXRDecoder.type == 1 ) {

				// half
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat16;
						break;

					case HalfFloatType:
						EXRDecoder.getter = parseUint16;
						break;

				}

			} else if ( EXRDecoder.type == 2 ) {

				// float
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat32;
						break;

					case HalfFloatType:
						EXRDecoder.getter = decodeFloat32;

				}

			} else {

				throw new Error( 'EXRLoader.parse: unsupported pixelType ' + EXRDecoder.type + ' for ' + EXRHeader.compression + '.' );

			}

			EXRDecoder.columns = EXRDecoder.width;
			const size = EXRDecoder.width * EXRDecoder.height * EXRDecoder.outputChannels;

			switch ( outputType ) {

				case FloatType:
					EXRDecoder.byteArray = new Float32Array( size );

					// Fill initially with 1s for the alpha value if the texture is not RGBA, RGB values will be overwritten
					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 1, 0, size );

					break;

				case HalfFloatType:
					EXRDecoder.byteArray = new Uint16Array( size );

					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 0x3C00, 0, size ); // Uint16Array holds half float data, 0x3C00 is 1

					break;

				default:
					console.error( 'THREE.EXRLoader: unsupported type: ', outputType );
					break;

			}

			let byteOffset = 0;
			for ( const channel of EXRHeader.channels ) {

				if ( EXRDecoder.decodeChannels[ channel.name ] !== undefined ) {

					EXRDecoder.channelByteOffsets[ channel.name ] = byteOffset;

				}

				byteOffset += channel.pixelType * 2;

			}

			EXRDecoder.totalBytes = byteOffset;
			EXRDecoder.outLineWidth = EXRDecoder.width * EXRDecoder.outputChannels;

			if ( EXRHeader.lineOrder === 'INCREASING_Y' ) {

				EXRDecoder.scanOrder = ( y ) => y;

			} else {

				EXRDecoder.scanOrder = ( y ) => EXRDecoder.height - 1 - y;

			}

			if ( EXRHeader.spec.singleTile ) {

				EXRDecoder.blockHeight = EXRHeader.tiles.ySize;
				EXRDecoder.blockWidth = EXRHeader.tiles.xSize;

				const numXLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );
				// const numYLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );

				const numXTiles = calculateTiles( numXLevels, EXRDecoder.width, EXRHeader.tiles.xSize, EXRHeader.tiles.roundingMode );
				const numYTiles = calculateTiles( numXLevels, EXRDecoder.height, EXRHeader.tiles.ySize, EXRHeader.tiles.roundingMode );

				EXRDecoder.tileCount = numXTiles[ 0 ] * numYTiles[ 0 ];

				for ( let l = 0; l < numXLevels; l ++ )
					for ( let y = 0; y < numYTiles[ l ]; y ++ )
						for ( let x = 0; x < numXTiles[ l ]; x ++ )
							parseInt64( dataView, offset ); // tileOffset

				EXRDecoder.decode = parseTiles.bind( EXRDecoder );

			} else {

				EXRDecoder.blockWidth = EXRDecoder.width;
				const blockCount = Math.ceil( EXRDecoder.height / EXRDecoder.blockHeight );

				for ( let i = 0; i < blockCount; i ++ )
					parseInt64( dataView, offset ); // scanlineOffset

				EXRDecoder.decode = parseScanline.bind( EXRDecoder );

			}

			return EXRDecoder;

		}
```
</details>

### `onLoadCallback(texture: any, texData: any): void`

**Parameters:**

- **`texture`** `any`
- **`texData`** `any`

**Returns:** `void`

**Calls:**

- `onLoad`

<details><summary>Code</summary>

```typescript
function onLoadCallback( texture, texData ) {

			texture.colorSpace = texData.colorSpace;
			texture.minFilter = LinearFilter;
			texture.magFilter = LinearFilter;
			texture.generateMipmaps = false;
			texture.flipY = false;

			if ( onLoad ) onLoad( texture, texData );

		}
```
</details>


---

## Classes

### `EXRLoader`

<details><summary>Class Code</summary>

```ts
class EXRLoader extends DataTextureLoader {

	/**
	 * Constructs a new EXR loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * The texture type.
		 *
		 * @type {(HalfFloatType|FloatType)}
		 * @default HalfFloatType
		 */
		this.type = HalfFloatType;

		/**
		 * Texture output format.
		 *
		 * @type {(RGBAFormat|RGFormat|RedFormat)}
		 * @default RGBAFormat
		 */
		this.outputFormat = RGBAFormat;

	}

	/**
	 * Parses the given EXR texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @return {DataTextureLoader~TexData} An object representing the parsed texture data.
	 */
	parse( buffer ) {

		const USHORT_RANGE = ( 1 << 16 );
		const BITMAP_SIZE = ( USHORT_RANGE >> 3 );

		const HUF_ENCBITS = 16; // literal (value) bit length
		const HUF_DECBITS = 14; // decoding bit size (>= 8)

		const HUF_ENCSIZE = ( 1 << HUF_ENCBITS ) + 1; // encoding table size
		const HUF_DECSIZE = 1 << HUF_DECBITS; // decoding table size
		const HUF_DECMASK = HUF_DECSIZE - 1;

		const NBITS = 16;
		const A_OFFSET = 1 << ( NBITS - 1 );
		const MOD_MASK = ( 1 << NBITS ) - 1;

		const SHORT_ZEROCODE_RUN = 59;
		const LONG_ZEROCODE_RUN = 63;
		const SHORTEST_LONG_RUN = 2 + LONG_ZEROCODE_RUN - SHORT_ZEROCODE_RUN;

		const ULONG_SIZE = 8;
		const FLOAT32_SIZE = 4;
		const INT32_SIZE = 4;
		const INT16_SIZE = 2;
		const INT8_SIZE = 1;

		const STATIC_HUFFMAN = 0;
		const DEFLATE = 1;

		const UNKNOWN = 0;
		const LOSSY_DCT = 1;
		const RLE = 2;

		const logBase = Math.pow( 2.7182818, 2.2 );

		function reverseLutFromBitmap( bitmap, lut ) {

			let k = 0;

			for ( let i = 0; i < USHORT_RANGE; ++ i ) {

				if ( ( i == 0 ) || ( bitmap[ i >> 3 ] & ( 1 << ( i & 7 ) ) ) ) {

					lut[ k ++ ] = i;

				}

			}

			const n = k - 1;

			while ( k < USHORT_RANGE ) lut[ k ++ ] = 0;

			return n;

		}

		function hufClearDecTable( hdec ) {

			for ( let i = 0; i < HUF_DECSIZE; i ++ ) {

				hdec[ i ] = {};
				hdec[ i ].len = 0;
				hdec[ i ].lit = 0;
				hdec[ i ].p = null;

			}

		}

		const getBitsReturn = { l: 0, c: 0, lc: 0 };

		function getBits( nBits, c, lc, uInt8Array, inOffset ) {

			while ( lc < nBits ) {

				c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
				lc += 8;

			}

			lc -= nBits;

			getBitsReturn.l = ( c >> lc ) & ( ( 1 << nBits ) - 1 );
			getBitsReturn.c = c;
			getBitsReturn.lc = lc;

		}

		const hufTableBuffer = new Array( 59 );

		function hufCanonicalCodeTable( hcode ) {

			for ( let i = 0; i <= 58; ++ i ) hufTableBuffer[ i ] = 0;
			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) hufTableBuffer[ hcode[ i ] ] += 1;

			let c = 0;

			for ( let i = 58; i > 0; -- i ) {

				const nc = ( ( c + hufTableBuffer[ i ] ) >> 1 );
				hufTableBuffer[ i ] = c;
				c = nc;

			}

			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) {

				const l = hcode[ i ];
				if ( l > 0 ) hcode[ i ] = l | ( hufTableBuffer[ l ] ++ << 6 );

			}

		}

		function hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, hcode ) {

			const p = inOffset;
			let c = 0;
			let lc = 0;

			for ( ; im <= iM; im ++ ) {

				if ( p.value - inOffset.value > ni ) return false;

				getBits( 6, c, lc, uInt8Array, p );

				const l = getBitsReturn.l;
				c = getBitsReturn.c;
				lc = getBitsReturn.lc;

				hcode[ im ] = l;

				if ( l == LONG_ZEROCODE_RUN ) {

					if ( p.value - inOffset.value > ni ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					getBits( 8, c, lc, uInt8Array, p );

					let zerun = getBitsReturn.l + SHORTEST_LONG_RUN;
					c = getBitsReturn.c;
					lc = getBitsReturn.lc;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				} else if ( l >= SHORT_ZEROCODE_RUN ) {

					let zerun = l - SHORT_ZEROCODE_RUN + 2;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				}

			}

			hufCanonicalCodeTable( hcode );

		}

		function hufLength( code ) {

			return code & 63;

		}

		function hufCode( code ) {

			return code >> 6;

		}

		function hufBuildDecTable( hcode, im, iM, hdecod ) {

			for ( ; im <= iM; im ++ ) {

				const c = hufCode( hcode[ im ] );
				const l = hufLength( hcode[ im ] );

				if ( c >> l ) {

					throw new Error( 'Invalid table entry' );

				}

				if ( l > HUF_DECBITS ) {

					const pl = hdecod[ ( c >> ( l - HUF_DECBITS ) ) ];

					if ( pl.len ) {

						throw new Error( 'Invalid table entry' );

					}

					pl.lit ++;

					if ( pl.p ) {

						const p = pl.p;
						pl.p = new Array( pl.lit );

						for ( let i = 0; i < pl.lit - 1; ++ i ) {

							pl.p[ i ] = p[ i ];

						}

					} else {

						pl.p = new Array( 1 );

					}

					pl.p[ pl.lit - 1 ] = im;

				} else if ( l ) {

					let plOffset = 0;

					for ( let i = 1 << ( HUF_DECBITS - l ); i > 0; i -- ) {

						const pl = hdecod[ ( c << ( HUF_DECBITS - l ) ) + plOffset ];

						if ( pl.len || pl.p ) {

							throw new Error( 'Invalid table entry' );

						}

						pl.len = l;
						pl.lit = im;

						plOffset ++;

					}

				}

			}

			return true;

		}

		const getCharReturn = { c: 0, lc: 0 };

		function getChar( c, lc, uInt8Array, inOffset ) {

			c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
			lc += 8;

			getCharReturn.c = c;
			getCharReturn.lc = lc;

		}

		const getCodeReturn = { c: 0, lc: 0 };

		function getCode( po, rlc, c, lc, uInt8Array, inOffset, outBuffer, outBufferOffset, outBufferEndOffset ) {

			if ( po == rlc ) {

				if ( lc < 8 ) {

					getChar( c, lc, uInt8Array, inOffset );
					c = getCharReturn.c;
					lc = getCharReturn.lc;

				}

				lc -= 8;

				let cs = ( c >> lc );
				cs = new Uint8Array( [ cs ] )[ 0 ];

				if ( outBufferOffset.value + cs > outBufferEndOffset ) {

					return false;

				}

				const s = outBuffer[ outBufferOffset.value - 1 ];

				while ( cs -- > 0 ) {

					outBuffer[ outBufferOffset.value ++ ] = s;

				}

			} else if ( outBufferOffset.value < outBufferEndOffset ) {

				outBuffer[ outBufferOffset.value ++ ] = po;

			} else {

				return false;

			}

			getCodeReturn.c = c;
			getCodeReturn.lc = lc;

		}

		function UInt16( value ) {

			return ( value & 0xFFFF );

		}

		function Int16( value ) {

			const ref = UInt16( value );
			return ( ref > 0x7FFF ) ? ref - 0x10000 : ref;

		}

		const wdec14Return = { a: 0, b: 0 };

		function wdec14( l, h ) {

			const ls = Int16( l );
			const hs = Int16( h );

			const hi = hs;
			const ai = ls + ( hi & 1 ) + ( hi >> 1 );

			const as = ai;
			const bs = ai - hi;

			wdec14Return.a = as;
			wdec14Return.b = bs;

		}

		function wdec16( l, h ) {

			const m = UInt16( l );
			const d = UInt16( h );

			const bb = ( m - ( d >> 1 ) ) & MOD_MASK;
			const aa = ( d + bb - A_OFFSET ) & MOD_MASK;

			wdec14Return.a = aa;
			wdec14Return.b = bb;

		}

		function wav2Decode( buffer, j, nx, ox, ny, oy, mx ) {

			const w14 = mx < ( 1 << 14 );
			const n = ( nx > ny ) ? ny : nx;
			let p = 1;
			let p2;
			let py;

			while ( p <= n ) p <<= 1;

			p >>= 1;
			p2 = p;
			p >>= 1;

			while ( p >= 1 ) {

				py = 0;
				const ey = py + oy * ( ny - p2 );
				const oy1 = oy * p;
				const oy2 = oy * p2;
				const ox1 = ox * p;
				const ox2 = ox * p2;
				let i00, i01, i10, i11;

				for ( ; py <= ey; py += oy2 ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;
						const p10 = px + oy1;
						const p11 = p10 + ox1;

						if ( w14 ) {

							wdec14( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec14( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec14( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec14( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;

						} else {

							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec16( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec16( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec16( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;


						}

					}

					if ( nx & p ) {

						const p10 = px + oy1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p10 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

						i00 = wdec14Return.a;
						buffer[ p10 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				if ( ny & p ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p01 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p01 + j ] );

						i00 = wdec14Return.a;
						buffer[ p01 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				p2 = p;
				p >>= 1;

			}

			return py;

		}

		function hufDecode( encodingTable, decodingTable, uInt8Array, inOffset, ni, rlc, no, outBuffer, outOffset ) {

			let c = 0;
			let lc = 0;
			const outBufferEndOffset = no;
			const inOffsetEnd = Math.trunc( inOffset.value + ( ni + 7 ) / 8 );

			while ( inOffset.value < inOffsetEnd ) {

				getChar( c, lc, uInt8Array, inOffset );

				c = getCharReturn.c;
				lc = getCharReturn.lc;

				while ( lc >= HUF_DECBITS ) {

					const index = ( c >> ( lc - HUF_DECBITS ) ) & HUF_DECMASK;
					const pl = decodingTable[ index ];

					if ( pl.len ) {

						lc -= pl.len;

						getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

						c = getCodeReturn.c;
						lc = getCodeReturn.lc;

					} else {

						if ( ! pl.p ) {

							throw new Error( 'hufDecode issues' );

						}

						let j;

						for ( j = 0; j < pl.lit; j ++ ) {

							const l = hufLength( encodingTable[ pl.p[ j ] ] );

							while ( lc < l && inOffset.value < inOffsetEnd ) {

								getChar( c, lc, uInt8Array, inOffset );

								c = getCharReturn.c;
								lc = getCharReturn.lc;

							}

							if ( lc >= l ) {

								if ( hufCode( encodingTable[ pl.p[ j ] ] ) == ( ( c >> ( lc - l ) ) & ( ( 1 << l ) - 1 ) ) ) {

									lc -= l;

									getCode( pl.p[ j ], rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

									c = getCodeReturn.c;
									lc = getCodeReturn.lc;

									break;

								}

							}

						}

						if ( j == pl.lit ) {

							throw new Error( 'hufDecode issues' );

						}

					}

				}

			}

			const i = ( 8 - ni ) & 7;

			c >>= i;
			lc -= i;

			while ( lc > 0 ) {

				const pl = decodingTable[ ( c << ( HUF_DECBITS - lc ) ) & HUF_DECMASK ];

				if ( pl.len ) {

					lc -= pl.len;

					getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

					c = getCodeReturn.c;
					lc = getCodeReturn.lc;

				} else {

					throw new Error( 'hufDecode issues' );

				}

			}

			return true;

		}

		function hufUncompress( uInt8Array, inDataView, inOffset, nCompressed, outBuffer, nRaw ) {

			const outOffset = { value: 0 };
			const initialInOffset = inOffset.value;

			const im = parseUint32( inDataView, inOffset );
			const iM = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			const nBits = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			if ( im < 0 || im >= HUF_ENCSIZE || iM < 0 || iM >= HUF_ENCSIZE ) {

				throw new Error( 'Something wrong with HUF_ENCSIZE' );

			}

			const freq = new Array( HUF_ENCSIZE );
			const hdec = new Array( HUF_DECSIZE );

			hufClearDecTable( hdec );

			const ni = nCompressed - ( inOffset.value - initialInOffset );

			hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, freq );

			if ( nBits > 8 * ( nCompressed - ( inOffset.value - initialInOffset ) ) ) {

				throw new Error( 'Something wrong with hufUncompress' );

			}

			hufBuildDecTable( freq, im, iM, hdec );

			hufDecode( freq, hdec, uInt8Array, inOffset, nBits, iM, nRaw, outBuffer, outOffset );

		}

		function applyLut( lut, data, nData ) {

			for ( let i = 0; i < nData; ++ i ) {

				data[ i ] = lut[ data[ i ] ];

			}

		}

		function predictor( source ) {

			for ( let t = 1; t < source.length; t ++ ) {

				const d = source[ t - 1 ] + source[ t ] - 128;
				source[ t ] = d;

			}

		}

		function interleaveScalar( source, out ) {

			let t1 = 0;
			let t2 = Math.floor( ( source.length + 1 ) / 2 );
			let s = 0;
			const stop = source.length - 1;

			while ( true ) {

				if ( s > stop ) break;
				out[ s ++ ] = source[ t1 ++ ];

				if ( s > stop ) break;
				out[ s ++ ] = source[ t2 ++ ];

			}

		}

		function decodeRunLength( source ) {

			let size = source.byteLength;
			const out = new Array();
			let p = 0;

			const reader = new DataView( source );

			while ( size > 0 ) {

				const l = reader.getInt8( p ++ );

				if ( l < 0 ) {

					const count = - l;
					size -= count + 1;

					for ( let i = 0; i < count; i ++ ) {

						out.push( reader.getUint8( p ++ ) );

					}


				} else {

					const count = l;
					size -= 2;

					const value = reader.getUint8( p ++ );

					for ( let i = 0; i < count + 1; i ++ ) {

						out.push( value );

					}

				}

			}

			return out;

		}

		function lossyDctDecode( cscSet, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			let dataView = new DataView( outBuffer.buffer );

			const width = channelData[ cscSet.idx[ 0 ] ].width;
			const height = channelData[ cscSet.idx[ 0 ] ].height;

			const numComp = 3;

			const numFullBlocksX = Math.floor( width / 8.0 );
			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			const currDcComp = new Array( numComp );
			const dctData = new Array( numComp );
			const halfZigBlock = new Array( numComp );
			const rowBlock = new Array( numComp );
			const rowOffsets = new Array( numComp );

			for ( let comp = 0; comp < numComp; ++ comp ) {

				rowOffsets[ comp ] = rowPtrs[ cscSet.idx[ comp ] ];
				currDcComp[ comp ] = ( comp < 1 ) ? 0 : currDcComp[ comp - 1 ] + numBlocksX * numBlocksY;
				dctData[ comp ] = new Float32Array( 64 );
				halfZigBlock[ comp ] = new Uint16Array( 64 );
				rowBlock[ comp ] = new Uint16Array( numBlocksX * 64 );

			}

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 )
					maxY = leftoverY;

				let maxX = 8;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					if ( blockx == numBlocksX - 1 )
						maxX = leftoverX;

					for ( let comp = 0; comp < numComp; ++ comp ) {

						halfZigBlock[ comp ].fill( 0 );

						// set block DC component
						halfZigBlock[ comp ][ 0 ] = dcBuffer[ currDcComp[ comp ] ++ ];
						// set block AC components
						unRleAC( currAcComp, acBuffer, halfZigBlock[ comp ] );

						// UnZigZag block to float
						unZigZag( halfZigBlock[ comp ], dctData[ comp ] );
						// decode float dct
						dctInverse( dctData[ comp ] );

					}

					if ( numComp == 3 ) {

						csc709Inverse( dctData );

					}

					for ( let comp = 0; comp < numComp; ++ comp ) {

						convertToHalf( dctData[ comp ], rowBlock[ comp ], blockx * 64 );

					}

				} // blockx

				let offset = 0;

				for ( let comp = 0; comp < numComp; ++ comp ) {

					const type = channelData[ cscSet.idx[ comp ] ].type;

					for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

						offset = rowOffsets[ comp ][ y ];

						for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

							const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

							dataView.setUint16( offset + 0 * INT16_SIZE * type, rowBlock[ comp ][ src + 0 ], true );
							dataView.setUint16( offset + 1 * INT16_SIZE * type, rowBlock[ comp ][ src + 1 ], true );
							dataView.setUint16( offset + 2 * INT16_SIZE * type, rowBlock[ comp ][ src + 2 ], true );
							dataView.setUint16( offset + 3 * INT16_SIZE * type, rowBlock[ comp ][ src + 3 ], true );

							dataView.setUint16( offset + 4 * INT16_SIZE * type, rowBlock[ comp ][ src + 4 ], true );
							dataView.setUint16( offset + 5 * INT16_SIZE * type, rowBlock[ comp ][ src + 5 ], true );
							dataView.setUint16( offset + 6 * INT16_SIZE * type, rowBlock[ comp ][ src + 6 ], true );
							dataView.setUint16( offset + 7 * INT16_SIZE * type, rowBlock[ comp ][ src + 7 ], true );

							offset += 8 * INT16_SIZE * type;

						}

					}

					// handle partial X blocks
					if ( numFullBlocksX != numBlocksX ) {

						for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

							const offset = rowOffsets[ comp ][ y ] + 8 * numFullBlocksX * INT16_SIZE * type;
							const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

							for ( let x = 0; x < maxX; ++ x ) {

								dataView.setUint16( offset + x * INT16_SIZE * type, rowBlock[ comp ][ src + x ], true );

							}

						}

					}

				} // comp

			} // blocky

			const halfRow = new Uint16Array( width );
			dataView = new DataView( outBuffer.buffer );

			// convert channels back to float, if needed
			for ( let comp = 0; comp < numComp; ++ comp ) {

				channelData[ cscSet.idx[ comp ] ].decoded = true;
				const type = channelData[ cscSet.idx[ comp ] ].type;

				if ( channelData[ comp ].type != 2 ) continue;

				for ( let y = 0; y < height; ++ y ) {

					const offset = rowOffsets[ comp ][ y ];

					for ( let x = 0; x < width; ++ x ) {

						halfRow[ x ] = dataView.getUint16( offset + x * INT16_SIZE * type, true );

					}

					for ( let x = 0; x < width; ++ x ) {

						dataView.setFloat32( offset + x * INT16_SIZE * type, decodeFloat16( halfRow[ x ] ), true );

					}

				}

			}

		}

		function lossyDctChannelDecode( channelIndex, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			const dataView = new DataView( outBuffer.buffer );
			const cd = channelData[ channelIndex ];
			const width = cd.width;
			const height = cd.height;

			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const numFullBlocksX = Math.floor( width / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			let currDcComp = 0;
			const dctData = new Float32Array( 64 );
			const halfZigBlock = new Uint16Array( 64 );
			const rowBlock = new Uint16Array( numBlocksX * 64 );

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 ) maxY = leftoverY;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					halfZigBlock.fill( 0 );
					halfZigBlock[ 0 ] = dcBuffer[ currDcComp ++ ];
					unRleAC( currAcComp, acBuffer, halfZigBlock );
					unZigZag( halfZigBlock, dctData );
					dctInverse( dctData );
					convertToHalf( dctData, rowBlock, blockx * 64 );

				}

				// Write decoded data to output buffer
				for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

					let offset = rowPtrs[ channelIndex ][ y ];

					for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

						const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < 8; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

						offset += 8 * INT16_SIZE * cd.type;

					}

					if ( numBlocksX != numFullBlocksX ) {

						const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < leftoverX; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

					}

				}

			}

			cd.decoded = true;

		}

		function unRleAC( currAcComp, acBuffer, halfZigBlock ) {

			let acValue;
			let dctComp = 1;

			while ( dctComp < 64 ) {

				acValue = acBuffer[ currAcComp.value ];

				if ( acValue == 0xff00 ) {

					dctComp = 64;

				} else if ( acValue >> 8 == 0xff ) {

					dctComp += acValue & 0xff;

				} else {

					halfZigBlock[ dctComp ] = acValue;
					dctComp ++;

				}

				currAcComp.value ++;

			}

		}

		function unZigZag( src, dst ) {

			dst[ 0 ] = decodeFloat16( src[ 0 ] );
			dst[ 1 ] = decodeFloat16( src[ 1 ] );
			dst[ 2 ] = decodeFloat16( src[ 5 ] );
			dst[ 3 ] = decodeFloat16( src[ 6 ] );
			dst[ 4 ] = decodeFloat16( src[ 14 ] );
			dst[ 5 ] = decodeFloat16( src[ 15 ] );
			dst[ 6 ] = decodeFloat16( src[ 27 ] );
			dst[ 7 ] = decodeFloat16( src[ 28 ] );
			dst[ 8 ] = decodeFloat16( src[ 2 ] );
			dst[ 9 ] = decodeFloat16( src[ 4 ] );

			dst[ 10 ] = decodeFloat16( src[ 7 ] );
			dst[ 11 ] = decodeFloat16( src[ 13 ] );
			dst[ 12 ] = decodeFloat16( src[ 16 ] );
			dst[ 13 ] = decodeFloat16( src[ 26 ] );
			dst[ 14 ] = decodeFloat16( src[ 29 ] );
			dst[ 15 ] = decodeFloat16( src[ 42 ] );
			dst[ 16 ] = decodeFloat16( src[ 3 ] );
			dst[ 17 ] = decodeFloat16( src[ 8 ] );
			dst[ 18 ] = decodeFloat16( src[ 12 ] );
			dst[ 19 ] = decodeFloat16( src[ 17 ] );

			dst[ 20 ] = decodeFloat16( src[ 25 ] );
			dst[ 21 ] = decodeFloat16( src[ 30 ] );
			dst[ 22 ] = decodeFloat16( src[ 41 ] );
			dst[ 23 ] = decodeFloat16( src[ 43 ] );
			dst[ 24 ] = decodeFloat16( src[ 9 ] );
			dst[ 25 ] = decodeFloat16( src[ 11 ] );
			dst[ 26 ] = decodeFloat16( src[ 18 ] );
			dst[ 27 ] = decodeFloat16( src[ 24 ] );
			dst[ 28 ] = decodeFloat16( src[ 31 ] );
			dst[ 29 ] = decodeFloat16( src[ 40 ] );

			dst[ 30 ] = decodeFloat16( src[ 44 ] );
			dst[ 31 ] = decodeFloat16( src[ 53 ] );
			dst[ 32 ] = decodeFloat16( src[ 10 ] );
			dst[ 33 ] = decodeFloat16( src[ 19 ] );
			dst[ 34 ] = decodeFloat16( src[ 23 ] );
			dst[ 35 ] = decodeFloat16( src[ 32 ] );
			dst[ 36 ] = decodeFloat16( src[ 39 ] );
			dst[ 37 ] = decodeFloat16( src[ 45 ] );
			dst[ 38 ] = decodeFloat16( src[ 52 ] );
			dst[ 39 ] = decodeFloat16( src[ 54 ] );

			dst[ 40 ] = decodeFloat16( src[ 20 ] );
			dst[ 41 ] = decodeFloat16( src[ 22 ] );
			dst[ 42 ] = decodeFloat16( src[ 33 ] );
			dst[ 43 ] = decodeFloat16( src[ 38 ] );
			dst[ 44 ] = decodeFloat16( src[ 46 ] );
			dst[ 45 ] = decodeFloat16( src[ 51 ] );
			dst[ 46 ] = decodeFloat16( src[ 55 ] );
			dst[ 47 ] = decodeFloat16( src[ 60 ] );
			dst[ 48 ] = decodeFloat16( src[ 21 ] );
			dst[ 49 ] = decodeFloat16( src[ 34 ] );

			dst[ 50 ] = decodeFloat16( src[ 37 ] );
			dst[ 51 ] = decodeFloat16( src[ 47 ] );
			dst[ 52 ] = decodeFloat16( src[ 50 ] );
			dst[ 53 ] = decodeFloat16( src[ 56 ] );
			dst[ 54 ] = decodeFloat16( src[ 59 ] );
			dst[ 55 ] = decodeFloat16( src[ 61 ] );
			dst[ 56 ] = decodeFloat16( src[ 35 ] );
			dst[ 57 ] = decodeFloat16( src[ 36 ] );
			dst[ 58 ] = decodeFloat16( src[ 48 ] );
			dst[ 59 ] = decodeFloat16( src[ 49 ] );

			dst[ 60 ] = decodeFloat16( src[ 57 ] );
			dst[ 61 ] = decodeFloat16( src[ 58 ] );
			dst[ 62 ] = decodeFloat16( src[ 62 ] );
			dst[ 63 ] = decodeFloat16( src[ 63 ] );

		}

		function dctInverse( data ) {

			const a = 0.5 * Math.cos( 3.14159 / 4.0 );
			const b = 0.5 * Math.cos( 3.14159 / 16.0 );
			const c = 0.5 * Math.cos( 3.14159 / 8.0 );
			const d = 0.5 * Math.cos( 3.0 * 3.14159 / 16.0 );
			const e = 0.5 * Math.cos( 5.0 * 3.14159 / 16.0 );
			const f = 0.5 * Math.cos( 3.0 * 3.14159 / 8.0 );
			const g = 0.5 * Math.cos( 7.0 * 3.14159 / 16.0 );

			const alpha = new Array( 4 );
			const beta = new Array( 4 );
			const theta = new Array( 4 );
			const gamma = new Array( 4 );

			for ( let row = 0; row < 8; ++ row ) {

				const rowPtr = row * 8;

				alpha[ 0 ] = c * data[ rowPtr + 2 ];
				alpha[ 1 ] = f * data[ rowPtr + 2 ];
				alpha[ 2 ] = c * data[ rowPtr + 6 ];
				alpha[ 3 ] = f * data[ rowPtr + 6 ];

				beta[ 0 ] = b * data[ rowPtr + 1 ] + d * data[ rowPtr + 3 ] + e * data[ rowPtr + 5 ] + g * data[ rowPtr + 7 ];
				beta[ 1 ] = d * data[ rowPtr + 1 ] - g * data[ rowPtr + 3 ] - b * data[ rowPtr + 5 ] - e * data[ rowPtr + 7 ];
				beta[ 2 ] = e * data[ rowPtr + 1 ] - b * data[ rowPtr + 3 ] + g * data[ rowPtr + 5 ] + d * data[ rowPtr + 7 ];
				beta[ 3 ] = g * data[ rowPtr + 1 ] - e * data[ rowPtr + 3 ] + d * data[ rowPtr + 5 ] - b * data[ rowPtr + 7 ];

				theta[ 0 ] = a * ( data[ rowPtr + 0 ] + data[ rowPtr + 4 ] );
				theta[ 3 ] = a * ( data[ rowPtr + 0 ] - data[ rowPtr + 4 ] );
				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ rowPtr + 0 ] = gamma[ 0 ] + beta[ 0 ];
				data[ rowPtr + 1 ] = gamma[ 1 ] + beta[ 1 ];
				data[ rowPtr + 2 ] = gamma[ 2 ] + beta[ 2 ];
				data[ rowPtr + 3 ] = gamma[ 3 ] + beta[ 3 ];

				data[ rowPtr + 4 ] = gamma[ 3 ] - beta[ 3 ];
				data[ rowPtr + 5 ] = gamma[ 2 ] - beta[ 2 ];
				data[ rowPtr + 6 ] = gamma[ 1 ] - beta[ 1 ];
				data[ rowPtr + 7 ] = gamma[ 0 ] - beta[ 0 ];

			}

			for ( let column = 0; column < 8; ++ column ) {

				alpha[ 0 ] = c * data[ 16 + column ];
				alpha[ 1 ] = f * data[ 16 + column ];
				alpha[ 2 ] = c * data[ 48 + column ];
				alpha[ 3 ] = f * data[ 48 + column ];

				beta[ 0 ] = b * data[ 8 + column ] + d * data[ 24 + column ] + e * data[ 40 + column ] + g * data[ 56 + column ];
				beta[ 1 ] = d * data[ 8 + column ] - g * data[ 24 + column ] - b * data[ 40 + column ] - e * data[ 56 + column ];
				beta[ 2 ] = e * data[ 8 + column ] - b * data[ 24 + column ] + g * data[ 40 + column ] + d * data[ 56 + column ];
				beta[ 3 ] = g * data[ 8 + column ] - e * data[ 24 + column ] + d * data[ 40 + column ] - b * data[ 56 + column ];

				theta[ 0 ] = a * ( data[ column ] + data[ 32 + column ] );
				theta[ 3 ] = a * ( data[ column ] - data[ 32 + column ] );

				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ 0 + column ] = gamma[ 0 ] + beta[ 0 ];
				data[ 8 + column ] = gamma[ 1 ] + beta[ 1 ];
				data[ 16 + column ] = gamma[ 2 ] + beta[ 2 ];
				data[ 24 + column ] = gamma[ 3 ] + beta[ 3 ];

				data[ 32 + column ] = gamma[ 3 ] - beta[ 3 ];
				data[ 40 + column ] = gamma[ 2 ] - beta[ 2 ];
				data[ 48 + column ] = gamma[ 1 ] - beta[ 1 ];
				data[ 56 + column ] = gamma[ 0 ] - beta[ 0 ];

			}

		}

		function csc709Inverse( data ) {

			for ( let i = 0; i < 64; ++ i ) {

				const y = data[ 0 ][ i ];
				const cb = data[ 1 ][ i ];
				const cr = data[ 2 ][ i ];

				data[ 0 ][ i ] = y + 1.5747 * cr;
				data[ 1 ][ i ] = y - 0.1873 * cb - 0.4682 * cr;
				data[ 2 ][ i ] = y + 1.8556 * cb;

			}

		}

		function convertToHalf( src, dst, idx ) {

			for ( let i = 0; i < 64; ++ i ) {

				dst[ idx + i ] = DataUtils.toHalfFloat( toLinear( src[ i ] ) );

			}

		}

		function toLinear( float ) {

			if ( float <= 1 ) {

				return Math.sign( float ) * Math.pow( Math.abs( float ), 2.2 );

			} else {

				return Math.sign( float ) * Math.pow( logBase, Math.abs( float ) - 1.0 );

			}

		}

		function uncompressRAW( info ) {

			return new DataView( info.array.buffer, info.offset.value, info.size );

		}

		function uncompressRLE( info ) {

			const compressed = info.viewer.buffer.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = new Uint8Array( decodeRunLength( compressed ) );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressZIP( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressPIZ( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };

			const outBuffer = new Uint16Array( info.columns * info.lines * ( info.inputChannels.length * info.type ) );
			const bitmap = new Uint8Array( BITMAP_SIZE );

			// Setup channel info
			let outBufferEnd = 0;
			const pizChannelData = new Array( info.inputChannels.length );
			for ( let i = 0, il = info.inputChannels.length; i < il; i ++ ) {

				pizChannelData[ i ] = {};
				pizChannelData[ i ][ 'start' ] = outBufferEnd;
				pizChannelData[ i ][ 'end' ] = pizChannelData[ i ][ 'start' ];
				pizChannelData[ i ][ 'nx' ] = info.columns;
				pizChannelData[ i ][ 'ny' ] = info.lines;
				pizChannelData[ i ][ 'size' ] = info.type;

				outBufferEnd += pizChannelData[ i ].nx * pizChannelData[ i ].ny * pizChannelData[ i ].size;

			}

			// Read range compression data

			const minNonZero = parseUint16( inDataView, inOffset );
			const maxNonZero = parseUint16( inDataView, inOffset );

			if ( maxNonZero >= BITMAP_SIZE ) {

				throw new Error( 'Something is wrong with PIZ_COMPRESSION BITMAP_SIZE' );

			}

			if ( minNonZero <= maxNonZero ) {

				for ( let i = 0; i < maxNonZero - minNonZero + 1; i ++ ) {

					bitmap[ i + minNonZero ] = parseUint8( inDataView, inOffset );

				}

			}

			// Reverse LUT
			const lut = new Uint16Array( USHORT_RANGE );
			const maxValue = reverseLutFromBitmap( bitmap, lut );

			const length = parseUint32( inDataView, inOffset );

			// Huffman decoding
			hufUncompress( info.array, inDataView, inOffset, length, outBuffer, outBufferEnd );

			// Wavelet decoding
			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = pizChannelData[ i ];

				for ( let j = 0; j < pizChannelData[ i ].size; ++ j ) {

					wav2Decode(
						outBuffer,
						cd.start + j,
						cd.nx,
						cd.size,
						cd.ny,
						cd.nx * cd.size,
						maxValue
					);

				}

			}

			// Expand the pixel data to their original range
			applyLut( lut, outBuffer, outBufferEnd );

			// Rearrange the pixel data into the format expected by the caller.
			let tmpOffset = 0;
			const tmpBuffer = new Uint8Array( outBuffer.buffer.byteLength );
			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					const cd = pizChannelData[ c ];

					const n = cd.nx * cd.size;
					const cp = new Uint8Array( outBuffer.buffer, cd.end * INT16_SIZE, n * INT16_SIZE );

					tmpBuffer.set( cp, tmpOffset );
					tmpOffset += n * INT16_SIZE;
					cd.end += n;

				}

			}

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressPXR( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );

			const byteSize = info.inputChannels.length * info.lines * info.columns * info.totalBytes;
			const tmpBuffer = new ArrayBuffer( byteSize );
			const viewer = new DataView( tmpBuffer );

			let tmpBufferEnd = 0;
			let writePtr = 0;
			const ptr = new Array( 4 );

			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					let pixel = 0;

					const type = info.inputChannels[ c ].pixelType;
					switch ( type ) {

						case 1:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							tmpBufferEnd = ptr[ 1 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 8 ) | rawBuffer[ ptr[ 1 ] ++ ];

								pixel += diff;

								viewer.setUint16( writePtr, pixel, true );
								writePtr += 2;

							}

							break;

						case 2:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							ptr[ 2 ] = ptr[ 1 ] + info.columns;
							tmpBufferEnd = ptr[ 2 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 24 ) | ( rawBuffer[ ptr[ 1 ] ++ ] << 16 ) | ( rawBuffer[ ptr[ 2 ] ++ ] << 8 );

								pixel += diff;

								viewer.setUint32( writePtr, pixel, true );
								writePtr += 4;

							}

							break;

					}

				}

			}

			return viewer;

		}

		function uncompressDWA( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };
			const outBuffer = new Uint8Array( info.columns * info.lines * ( info.inputChannels.length * info.type * INT16_SIZE ) );

			// Read compression header information
			const dwaHeader = {

				version: parseInt64( inDataView, inOffset ),
				unknownUncompressedSize: parseInt64( inDataView, inOffset ),
				unknownCompressedSize: parseInt64( inDataView, inOffset ),
				acCompressedSize: parseInt64( inDataView, inOffset ),
				dcCompressedSize: parseInt64( inDataView, inOffset ),
				rleCompressedSize: parseInt64( inDataView, inOffset ),
				rleUncompressedSize: parseInt64( inDataView, inOffset ),
				rleRawSize: parseInt64( inDataView, inOffset ),
				totalAcUncompressedCount: parseInt64( inDataView, inOffset ),
				totalDcUncompressedCount: parseInt64( inDataView, inOffset ),
				acCompression: parseInt64( inDataView, inOffset )

			};

			if ( dwaHeader.version < 2 )
				throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' version ' + dwaHeader.version + ' is unsupported' );

			// Read channel ruleset information
			const channelRules = new Array();
			let ruleSize = parseUint16( inDataView, inOffset ) - INT16_SIZE;

			while ( ruleSize > 0 ) {

				const name = parseNullTerminatedString( inDataView.buffer, inOffset );
				const value = parseUint8( inDataView, inOffset );
				const compression = ( value >> 2 ) & 3;
				const csc = ( value >> 4 ) - 1;
				const index = new Int8Array( [ csc ] )[ 0 ];
				const type = parseUint8( inDataView, inOffset );

				channelRules.push( {
					name: name,
					index: index,
					type: type,
					compression: compression,
				} );

				ruleSize -= name.length + 3;

			}

			// Classify channels
			const channels = EXRHeader.channels;
			const channelData = new Array( info.inputChannels.length );

			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = channelData[ i ] = {};
				const channel = channels[ i ];

				cd.name = channel.name;
				cd.compression = UNKNOWN;
				cd.decoded = false;
				cd.type = channel.pixelType;
				cd.pLinear = channel.pLinear;
				cd.width = info.columns;
				cd.height = info.lines;

			}

			const cscSet = {
				idx: new Array( 3 )
			};

			for ( let offset = 0; offset < info.inputChannels.length; ++ offset ) {

				const cd = channelData[ offset ];

				for ( let i = 0; i < channelRules.length; ++ i ) {

					const rule = channelRules[ i ];

					if ( cd.name == rule.name ) {

						cd.compression = rule.compression;

						if ( rule.index >= 0 ) {

							cscSet.idx[ rule.index ] = offset;

						}

						cd.offset = offset;

					}

				}

			}

			let acBuffer, dcBuffer, rleBuffer;

			// Read DCT - AC component data
			if ( dwaHeader.acCompressedSize > 0 ) {

				switch ( dwaHeader.acCompression ) {

					case STATIC_HUFFMAN:

						acBuffer = new Uint16Array( dwaHeader.totalAcUncompressedCount );
						hufUncompress( info.array, inDataView, inOffset, dwaHeader.acCompressedSize, acBuffer, dwaHeader.totalAcUncompressedCount );
						break;

					case DEFLATE:

						const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.totalAcUncompressedCount );
						const data = fflate.unzlibSync( compressed );
						acBuffer = new Uint16Array( data.buffer );
						inOffset.value += dwaHeader.totalAcUncompressedCount;
						break;

				}


			}

			// Read DCT - DC component data
			if ( dwaHeader.dcCompressedSize > 0 ) {

				const zlibInfo = {
					array: info.array,
					offset: inOffset,
					size: dwaHeader.dcCompressedSize
				};
				dcBuffer = new Uint16Array( uncompressZIP( zlibInfo ).buffer );
				inOffset.value += dwaHeader.dcCompressedSize;

			}

			// Read RLE compressed data
			if ( dwaHeader.rleRawSize > 0 ) {

				const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.rleCompressedSize );
				const data = fflate.unzlibSync( compressed );
				rleBuffer = decodeRunLength( data.buffer );

				inOffset.value += dwaHeader.rleCompressedSize;

			}

			// Prepare outbuffer data offset
			let outBufferEnd = 0;
			const rowOffsets = new Array( channelData.length );
			for ( let i = 0; i < rowOffsets.length; ++ i ) {

				rowOffsets[ i ] = new Array();

			}

			for ( let y = 0; y < info.lines; ++ y ) {

				for ( let chan = 0; chan < channelData.length; ++ chan ) {

					rowOffsets[ chan ].push( outBufferEnd );
					outBufferEnd += channelData[ chan ].width * info.type * INT16_SIZE;

				}

			}

			// Decode lossy DCT data if we have a valid color space conversion set with the first RGB channel present
			if ( cscSet.idx[ 0 ] !== undefined && channelData[ cscSet.idx[ 0 ] ] ) {

				lossyDctDecode( cscSet, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

			}

			// Decode other channels
			for ( let i = 0; i < channelData.length; ++ i ) {

				const cd = channelData[ i ];

				if ( cd.decoded ) continue;

				switch ( cd.compression ) {

					case RLE:

						let row = 0;
						let rleOffset = 0;

						for ( let y = 0; y < info.lines; ++ y ) {

							let rowOffsetBytes = rowOffsets[ i ][ row ];

							for ( let x = 0; x < cd.width; ++ x ) {

								for ( let byte = 0; byte < INT16_SIZE * cd.type; ++ byte ) {

									outBuffer[ rowOffsetBytes ++ ] = rleBuffer[ rleOffset + byte * cd.width * cd.height ];

								}

								rleOffset ++;

							}

							row ++;

						}

						break;

					case LOSSY_DCT:

						lossyDctChannelDecode( i, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

						break;

					default:
						throw new Error( 'EXRLoader.parse: unsupported channel compression' );

				}

			}

			return new DataView( outBuffer.buffer );

		}

		function parseNullTerminatedString( buffer, offset ) {

			const uintBuffer = new Uint8Array( buffer );
			let endOffset = 0;

			while ( uintBuffer[ offset.value + endOffset ] != 0 ) {

				endOffset += 1;

			}

			const stringValue = new TextDecoder().decode(
				uintBuffer.slice( offset.value, offset.value + endOffset )
			);

			offset.value = offset.value + endOffset + 1;

			return stringValue;

		}

		function parseFixedLengthString( buffer, offset, size ) {

			const stringValue = new TextDecoder().decode(
				new Uint8Array( buffer ).slice( offset.value, offset.value + size )
			);

			offset.value = offset.value + size;

			return stringValue;

		}

		function parseRational( dataView, offset ) {

			const x = parseInt32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}

		function parseTimecode( dataView, offset ) {

			const x = parseUint32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}

		function parseInt32( dataView, offset ) {

			const Int32 = dataView.getInt32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Int32;

		}

		function parseUint32( dataView, offset ) {

			const Uint32 = dataView.getUint32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Uint32;

		}

		function parseUint8Array( uInt8Array, offset ) {

			const Uint8 = uInt8Array[ offset.value ];

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}

		function parseUint8( dataView, offset ) {

			const Uint8 = dataView.getUint8( offset.value );

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}

		const parseInt64 = function ( dataView, offset ) {

			let int;

			if ( 'getBigInt64' in DataView.prototype ) {

				int = Number( dataView.getBigInt64( offset.value, true ) );

			} else {

				int = dataView.getUint32( offset.value + 4, true ) + Number( dataView.getUint32( offset.value, true ) << 32 );

			}

			offset.value += ULONG_SIZE;

			return int;

		};

		function parseFloat32( dataView, offset ) {

			const float = dataView.getFloat32( offset.value, true );

			offset.value += FLOAT32_SIZE;

			return float;

		}

		function decodeFloat32( dataView, offset ) {

			return DataUtils.toHalfFloat( parseFloat32( dataView, offset ) );

		}

		// https://stackoverflow.com/questions/5678432/decompressing-half-precision-floats-in-javascript
		function decodeFloat16( binary ) {

			const exponent = ( binary & 0x7C00 ) >> 10,
				fraction = binary & 0x03FF;

			return ( binary >> 15 ? - 1 : 1 ) * (
				exponent ?
					(
						exponent === 0x1F ?
							fraction ? NaN : Infinity :
							Math.pow( 2, exponent - 15 ) * ( 1 + fraction / 0x400 )
					) :
					6.103515625e-5 * ( fraction / 0x400 )
			);

		}

		function parseUint16( dataView, offset ) {

			const Uint16 = dataView.getUint16( offset.value, true );

			offset.value += INT16_SIZE;

			return Uint16;

		}

		function parseFloat16( buffer, offset ) {

			return decodeFloat16( parseUint16( buffer, offset ) );

		}

		function parseChlist( dataView, buffer, offset, size ) {

			const startOffset = offset.value;
			const channels = [];

			while ( offset.value < ( startOffset + size - 1 ) ) {

				const name = parseNullTerminatedString( buffer, offset );
				const pixelType = parseInt32( dataView, offset );
				const pLinear = parseUint8( dataView, offset );
				offset.value += 3; // reserved, three chars
				const xSampling = parseInt32( dataView, offset );
				const ySampling = parseInt32( dataView, offset );

				channels.push( {
					name: name,
					pixelType: pixelType,
					pLinear: pLinear,
					xSampling: xSampling,
					ySampling: ySampling
				} );

			}

			offset.value += 1;

			return channels;

		}

		function parseChromaticities( dataView, offset ) {

			const redX = parseFloat32( dataView, offset );
			const redY = parseFloat32( dataView, offset );
			const greenX = parseFloat32( dataView, offset );
			const greenY = parseFloat32( dataView, offset );
			const blueX = parseFloat32( dataView, offset );
			const blueY = parseFloat32( dataView, offset );
			const whiteX = parseFloat32( dataView, offset );
			const whiteY = parseFloat32( dataView, offset );

			return { redX: redX, redY: redY, greenX: greenX, greenY: greenY, blueX: blueX, blueY: blueY, whiteX: whiteX, whiteY: whiteY };

		}

		function parseCompression( dataView, offset ) {

			const compressionCodes = [
				'NO_COMPRESSION',
				'RLE_COMPRESSION',
				'ZIPS_COMPRESSION',
				'ZIP_COMPRESSION',
				'PIZ_COMPRESSION',
				'PXR24_COMPRESSION',
				'B44_COMPRESSION',
				'B44A_COMPRESSION',
				'DWAA_COMPRESSION',
				'DWAB_COMPRESSION'
			];

			const compression = parseUint8( dataView, offset );

			return compressionCodes[ compression ];

		}

		function parseBox2i( dataView, offset ) {

			const xMin = parseInt32( dataView, offset );
			const yMin = parseInt32( dataView, offset );
			const xMax = parseInt32( dataView, offset );
			const yMax = parseInt32( dataView, offset );

			return { xMin: xMin, yMin: yMin, xMax: xMax, yMax: yMax };

		}

		function parseLineOrder( dataView, offset ) {

			const lineOrders = [
				'INCREASING_Y',
				'DECREASING_Y',
				'RANDOM_Y',
			];

			const lineOrder = parseUint8( dataView, offset );

			return lineOrders[ lineOrder ];

		}

		function parseEnvmap( dataView, offset ) {

			const envmaps = [
				'ENVMAP_LATLONG',
				'ENVMAP_CUBE'
			];

			const envmap = parseUint8( dataView, offset );

			return envmaps[ envmap ];

		}

		function parseTiledesc( dataView, offset ) {

			const levelModes = [
				'ONE_LEVEL',
				'MIPMAP_LEVELS',
				'RIPMAP_LEVELS',
			];

			const roundingModes = [
				'ROUND_DOWN',
				'ROUND_UP',
			];

			const xSize = parseUint32( dataView, offset );
			const ySize = parseUint32( dataView, offset );
			const modes = parseUint8( dataView, offset );

			return {
				xSize: xSize,
				ySize: ySize,
				levelMode: levelModes[ modes & 0xf ],
				roundingMode: roundingModes[ modes >> 4 ]
			};

		}

		function parseV2f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );

			return [ x, y ];

		}

		function parseV3f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );
			const z = parseFloat32( dataView, offset );

			return [ x, y, z ];

		}

		function parseValue( dataView, buffer, offset, type, size ) {

			if ( type === 'string' || type === 'stringvector' || type === 'iccProfile' ) {

				return parseFixedLengthString( buffer, offset, size );

			} else if ( type === 'chlist' ) {

				return parseChlist( dataView, buffer, offset, size );

			} else if ( type === 'chromaticities' ) {

				return parseChromaticities( dataView, offset );

			} else if ( type === 'compression' ) {

				return parseCompression( dataView, offset );

			} else if ( type === 'box2i' ) {

				return parseBox2i( dataView, offset );

			} else if ( type === 'envmap' ) {

				return parseEnvmap( dataView, offset );

			} else if ( type === 'tiledesc' ) {

				return parseTiledesc( dataView, offset );

			} else if ( type === 'lineOrder' ) {

				return parseLineOrder( dataView, offset );

			} else if ( type === 'float' ) {

				return parseFloat32( dataView, offset );

			} else if ( type === 'v2f' ) {

				return parseV2f( dataView, offset );

			} else if ( type === 'v3f' ) {

				return parseV3f( dataView, offset );

			} else if ( type === 'int' ) {

				return parseInt32( dataView, offset );

			} else if ( type === 'rational' ) {

				return parseRational( dataView, offset );

			} else if ( type === 'timecode' ) {

				return parseTimecode( dataView, offset );

			} else if ( type === 'preview' ) {

				offset.value += size;
				return 'skipped';

			} else {

				offset.value += size;
				return undefined;

			}

		}

		function roundLog2( x, mode ) {

			const log2 = Math.log2( x );
			return mode == 'ROUND_DOWN' ? Math.floor( log2 ) : Math.ceil( log2 );

		}

		function calculateTileLevels( tiledesc, w, h ) {

			let num = 0;

			switch ( tiledesc.levelMode ) {

				case 'ONE_LEVEL':
					num = 1;
					break;

				case 'MIPMAP_LEVELS':
					num = roundLog2( Math.max( w, h ), tiledesc.roundingMode ) + 1;
					break;

				case 'RIPMAP_LEVELS':
					throw new Error( 'THREE.EXRLoader: RIPMAP_LEVELS tiles currently unsupported.' );

			}

			return num;

		}

		function calculateTiles( count, dataSize, size, roundingMode ) {

			const tiles = new Array( count );

			for ( let i = 0; i < count; i ++ ) {

				const b = ( 1 << i );
				let s = ( dataSize / b ) | 0;

				if ( roundingMode == 'ROUND_UP' && s * b < dataSize ) s += 1;

				const l = Math.max( s, 1 );

				tiles[ i ] = ( ( l + size - 1 ) / size ) | 0;

			}

			return tiles;

		}

		function parseTiles() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let tile = 0; tile < EXRDecoder.tileCount; tile ++ ) {

				const tileX = parseInt32( EXRDecoder.viewer, offset );
				const tileY = parseInt32( EXRDecoder.viewer, offset );
				offset.value += 8; // skip levels - only parsing top-level
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset );

				const startX = tileX * EXRDecoder.blockWidth;
				const startY = tileY * EXRDecoder.blockHeight;
				EXRDecoder.columns = ( startX + EXRDecoder.blockWidth > EXRDecoder.width ) ? EXRDecoder.width - startX : EXRDecoder.blockWidth;
				EXRDecoder.lines = ( startY + EXRDecoder.blockHeight > EXRDecoder.height ) ? EXRDecoder.height - startY : EXRDecoder.blockHeight;

				const bytesBlockLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesBlockLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line = 0; line < EXRDecoder.lines; line ++ ) {

					const lineOffset = line * EXRDecoder.columns * EXRDecoder.totalBytes;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;
						const outLineOffset = ( EXRDecoder.height - ( 1 + startY + line ) ) * EXRDecoder.outLineWidth;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + ( x + startX ) * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}

		function parseScanline() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let scanlineBlockIdx = 0; scanlineBlockIdx < EXRDecoder.height / EXRDecoder.blockHeight; scanlineBlockIdx ++ ) {

				const line = parseInt32( EXRDecoder.viewer, offset ) - EXRHeader.dataWindow.yMin; // line_no
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset ); // data_len
				EXRDecoder.lines = ( ( line + EXRDecoder.blockHeight > EXRDecoder.height ) ? ( EXRDecoder.height - line ) : EXRDecoder.blockHeight );

				const bytesPerLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesPerLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line_y = 0; line_y < EXRDecoder.blockHeight; line_y ++ ) {

					const scan_y = scanlineBlockIdx * EXRDecoder.blockHeight;
					const true_y = line_y + EXRDecoder.scanOrder( scan_y );
					if ( true_y >= EXRDecoder.height ) continue;

					const lineOffset = line_y * bytesPerLine;
					const outLineOffset = ( EXRDecoder.height - 1 - true_y ) * EXRDecoder.outLineWidth;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + x * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}

		function parseHeader( dataView, buffer, offset ) {

			const EXRHeader = {};

			if ( dataView.getUint32( 0, true ) != 20000630 ) { // magic

				throw new Error( 'THREE.EXRLoader: Provided file doesn\'t appear to be in OpenEXR format.' );

			}

			EXRHeader.version = dataView.getUint8( 4 );

			const spec = dataView.getUint8( 5 ); // fullMask

			EXRHeader.spec = {
				singleTile: !! ( spec & 2 ),
				longName: !! ( spec & 4 ),
				deepFormat: !! ( spec & 8 ),
				multiPart: !! ( spec & 16 ),
			};

			// start of header

			offset.value = 8; // start at 8 - after pre-amble

			let keepReading = true;

			while ( keepReading ) {

				const attributeName = parseNullTerminatedString( buffer, offset );

				if ( attributeName === '' ) {

					keepReading = false;

				} else {

					const attributeType = parseNullTerminatedString( buffer, offset );
					const attributeSize = parseUint32( dataView, offset );
					const attributeValue = parseValue( dataView, buffer, offset, attributeType, attributeSize );

					if ( attributeValue === undefined ) {

						console.warn( `THREE.EXRLoader: Skipped unknown header attribute type \'${attributeType}\'.` );

					} else {

						EXRHeader[ attributeName ] = attributeValue;

					}

				}

			}

			if ( ( spec & ~ 0x06 ) != 0 ) { // unsupported deep-image, multi-part

				console.error( 'THREE.EXRHeader:', EXRHeader );
				throw new Error( 'THREE.EXRLoader: Provided file is currently unsupported.' );

			}

			return EXRHeader;

		}

		function setupDecoder( EXRHeader, dataView, uInt8Array, offset, outputType, outputFormat ) {

			const EXRDecoder = {
				size: 0,
				viewer: dataView,
				array: uInt8Array,
				offset: offset,
				width: EXRHeader.dataWindow.xMax - EXRHeader.dataWindow.xMin + 1,
				height: EXRHeader.dataWindow.yMax - EXRHeader.dataWindow.yMin + 1,
				inputChannels: EXRHeader.channels,
				channelByteOffsets: {},
				shouldExpand: false,
				scanOrder: null,
				totalBytes: null,
				columns: null,
				lines: null,
				type: null,
				uncompress: null,
				getter: null,
				format: null,
				colorSpace: LinearSRGBColorSpace,
			};

			switch ( EXRHeader.compression ) {

				case 'NO_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRAW;
					break;

				case 'RLE_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRLE;
					break;

				case 'ZIPS_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'ZIP_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'PIZ_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressPIZ;
					break;

				case 'PXR24_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressPXR;
					break;

				case 'DWAA_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				case 'DWAB_COMPRESSION':
					EXRDecoder.blockHeight = 256;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				default:
					throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' is unsupported' );

			}

			const channels = {};
			for ( const channel of EXRHeader.channels ) {

				switch ( channel.name ) {

					case 'Y':
					case 'R':
					case 'G':
					case 'B':
					case 'A':
						channels[ channel.name ] = true;
						EXRDecoder.type = channel.pixelType;

				}

			}

			// RGB images will be converted to RGBA format, preventing software emulation in select devices.
			let fillAlpha = false;
			let invalidOutput = false;

			// Validate if input texture contain supported channels
			if ( channels.R && channels.G && channels.B ) {

				EXRDecoder.outputChannels = 4;

			} else if ( channels.Y ) {

				EXRDecoder.outputChannels = 1;

			} else {

				throw new Error( 'EXRLoader.parse: file contains unsupported data channels.' );

			}

			// Setup output texture configuration
			switch ( EXRDecoder.outputChannels ) {

				case 4:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = ! channels.A;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.decodeChannels = { R: 0, G: 1, B: 2, A: 3 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.decodeChannels = { R: 0, G: 1 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { R: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				case 1:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = true;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				default:

					invalidOutput = true;

			}

			if (invalidOutput) throw new Error( 'EXRLoader.parse: invalid output format for specified file.' );

			if ( EXRDecoder.type == 1 ) {

				// half
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat16;
						break;

					case HalfFloatType:
						EXRDecoder.getter = parseUint16;
						break;

				}

			} else if ( EXRDecoder.type == 2 ) {

				// float
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat32;
						break;

					case HalfFloatType:
						EXRDecoder.getter = decodeFloat32;

				}

			} else {

				throw new Error( 'EXRLoader.parse: unsupported pixelType ' + EXRDecoder.type + ' for ' + EXRHeader.compression + '.' );

			}

			EXRDecoder.columns = EXRDecoder.width;
			const size = EXRDecoder.width * EXRDecoder.height * EXRDecoder.outputChannels;

			switch ( outputType ) {

				case FloatType:
					EXRDecoder.byteArray = new Float32Array( size );

					// Fill initially with 1s for the alpha value if the texture is not RGBA, RGB values will be overwritten
					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 1, 0, size );

					break;

				case HalfFloatType:
					EXRDecoder.byteArray = new Uint16Array( size );

					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 0x3C00, 0, size ); // Uint16Array holds half float data, 0x3C00 is 1

					break;

				default:
					console.error( 'THREE.EXRLoader: unsupported type: ', outputType );
					break;

			}

			let byteOffset = 0;
			for ( const channel of EXRHeader.channels ) {

				if ( EXRDecoder.decodeChannels[ channel.name ] !== undefined ) {

					EXRDecoder.channelByteOffsets[ channel.name ] = byteOffset;

				}

				byteOffset += channel.pixelType * 2;

			}

			EXRDecoder.totalBytes = byteOffset;
			EXRDecoder.outLineWidth = EXRDecoder.width * EXRDecoder.outputChannels;

			if ( EXRHeader.lineOrder === 'INCREASING_Y' ) {

				EXRDecoder.scanOrder = ( y ) => y;

			} else {

				EXRDecoder.scanOrder = ( y ) => EXRDecoder.height - 1 - y;

			}

			if ( EXRHeader.spec.singleTile ) {

				EXRDecoder.blockHeight = EXRHeader.tiles.ySize;
				EXRDecoder.blockWidth = EXRHeader.tiles.xSize;

				const numXLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );
				// const numYLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );

				const numXTiles = calculateTiles( numXLevels, EXRDecoder.width, EXRHeader.tiles.xSize, EXRHeader.tiles.roundingMode );
				const numYTiles = calculateTiles( numXLevels, EXRDecoder.height, EXRHeader.tiles.ySize, EXRHeader.tiles.roundingMode );

				EXRDecoder.tileCount = numXTiles[ 0 ] * numYTiles[ 0 ];

				for ( let l = 0; l < numXLevels; l ++ )
					for ( let y = 0; y < numYTiles[ l ]; y ++ )
						for ( let x = 0; x < numXTiles[ l ]; x ++ )
							parseInt64( dataView, offset ); // tileOffset

				EXRDecoder.decode = parseTiles.bind( EXRDecoder );

			} else {

				EXRDecoder.blockWidth = EXRDecoder.width;
				const blockCount = Math.ceil( EXRDecoder.height / EXRDecoder.blockHeight );

				for ( let i = 0; i < blockCount; i ++ )
					parseInt64( dataView, offset ); // scanlineOffset

				EXRDecoder.decode = parseScanline.bind( EXRDecoder );

			}

			return EXRDecoder;

		}

		// start parsing file [START]
		const offset = { value: 0 };
		const bufferDataView = new DataView( buffer );
		const uInt8Array = new Uint8Array( buffer );

		// get header information and validate format.
		const EXRHeader = parseHeader( bufferDataView, buffer, offset );

		// get input compression information and prepare decoding.
		const EXRDecoder = setupDecoder( EXRHeader, bufferDataView, uInt8Array, offset, this.type, this.outputFormat );

		// parse input data
		EXRDecoder.decode();

		// output texture post-processing
		if ( EXRDecoder.shouldExpand ) {

			const byteArray = EXRDecoder.byteArray;

			if ( this.outputFormat == RGBAFormat ) {

				for ( let i = 0; i < byteArray.length; i += 4 )
					byteArray [i + 2 ] = ( byteArray [ i + 1 ] = byteArray[ i ] );

			} else if ( this.outputFormat == RGFormat ) {

				for ( let i = 0; i < byteArray.length; i += 2 )
					byteArray [ i + 1 ] = byteArray[ i ] ;

			}

		}

		return {
			header: EXRHeader,
			width: EXRDecoder.width,
			height: EXRDecoder.height,
			data: EXRDecoder.byteArray,
			format: EXRDecoder.format,
			colorSpace: EXRDecoder.colorSpace,
			type: this.type,
		};

	}

	/**
	 * Sets the texture type.
	 *
	 * @param {(HalfFloatType|FloatType)} value - The texture type to set.
	 * @return {EXRLoader} A reference to this loader.
	 */
	setDataType( value ) {

		this.type = value;
		return this;

	}

	/**
	 * Sets texture output format. Defaults to `RGBAFormat`.
	 *
	 * @param {(RGBAFormat|RGFormat|RedFormat)} value - Texture output format.
	 * @return {EXRLoader} A reference to this loader.
	 */
	setOutputFormat( value ) {

		this.outputFormat = value;
		return this;

	}

	load( url, onLoad, onProgress, onError ) {

		function onLoadCallback( texture, texData ) {

			texture.colorSpace = texData.colorSpace;
			texture.minFilter = LinearFilter;
			texture.magFilter = LinearFilter;
			texture.generateMipmaps = false;
			texture.flipY = false;

			if ( onLoad ) onLoad( texture, texData );

		}

		return super.load( url, onLoadCallback, onProgress, onError );

	}

}
```
</details>

#### Methods

##### `parse(buffer: ArrayBuffer): DataTextureLoader`

<details><summary>Code</summary>

```ts
parse( buffer ) {

		const USHORT_RANGE = ( 1 << 16 );
		const BITMAP_SIZE = ( USHORT_RANGE >> 3 );

		const HUF_ENCBITS = 16; // literal (value) bit length
		const HUF_DECBITS = 14; // decoding bit size (>= 8)

		const HUF_ENCSIZE = ( 1 << HUF_ENCBITS ) + 1; // encoding table size
		const HUF_DECSIZE = 1 << HUF_DECBITS; // decoding table size
		const HUF_DECMASK = HUF_DECSIZE - 1;

		const NBITS = 16;
		const A_OFFSET = 1 << ( NBITS - 1 );
		const MOD_MASK = ( 1 << NBITS ) - 1;

		const SHORT_ZEROCODE_RUN = 59;
		const LONG_ZEROCODE_RUN = 63;
		const SHORTEST_LONG_RUN = 2 + LONG_ZEROCODE_RUN - SHORT_ZEROCODE_RUN;

		const ULONG_SIZE = 8;
		const FLOAT32_SIZE = 4;
		const INT32_SIZE = 4;
		const INT16_SIZE = 2;
		const INT8_SIZE = 1;

		const STATIC_HUFFMAN = 0;
		const DEFLATE = 1;

		const UNKNOWN = 0;
		const LOSSY_DCT = 1;
		const RLE = 2;

		const logBase = Math.pow( 2.7182818, 2.2 );

		function reverseLutFromBitmap( bitmap, lut ) {

			let k = 0;

			for ( let i = 0; i < USHORT_RANGE; ++ i ) {

				if ( ( i == 0 ) || ( bitmap[ i >> 3 ] & ( 1 << ( i & 7 ) ) ) ) {

					lut[ k ++ ] = i;

				}

			}

			const n = k - 1;

			while ( k < USHORT_RANGE ) lut[ k ++ ] = 0;

			return n;

		}

		function hufClearDecTable( hdec ) {

			for ( let i = 0; i < HUF_DECSIZE; i ++ ) {

				hdec[ i ] = {};
				hdec[ i ].len = 0;
				hdec[ i ].lit = 0;
				hdec[ i ].p = null;

			}

		}

		const getBitsReturn = { l: 0, c: 0, lc: 0 };

		function getBits( nBits, c, lc, uInt8Array, inOffset ) {

			while ( lc < nBits ) {

				c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
				lc += 8;

			}

			lc -= nBits;

			getBitsReturn.l = ( c >> lc ) & ( ( 1 << nBits ) - 1 );
			getBitsReturn.c = c;
			getBitsReturn.lc = lc;

		}

		const hufTableBuffer = new Array( 59 );

		function hufCanonicalCodeTable( hcode ) {

			for ( let i = 0; i <= 58; ++ i ) hufTableBuffer[ i ] = 0;
			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) hufTableBuffer[ hcode[ i ] ] += 1;

			let c = 0;

			for ( let i = 58; i > 0; -- i ) {

				const nc = ( ( c + hufTableBuffer[ i ] ) >> 1 );
				hufTableBuffer[ i ] = c;
				c = nc;

			}

			for ( let i = 0; i < HUF_ENCSIZE; ++ i ) {

				const l = hcode[ i ];
				if ( l > 0 ) hcode[ i ] = l | ( hufTableBuffer[ l ] ++ << 6 );

			}

		}

		function hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, hcode ) {

			const p = inOffset;
			let c = 0;
			let lc = 0;

			for ( ; im <= iM; im ++ ) {

				if ( p.value - inOffset.value > ni ) return false;

				getBits( 6, c, lc, uInt8Array, p );

				const l = getBitsReturn.l;
				c = getBitsReturn.c;
				lc = getBitsReturn.lc;

				hcode[ im ] = l;

				if ( l == LONG_ZEROCODE_RUN ) {

					if ( p.value - inOffset.value > ni ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					getBits( 8, c, lc, uInt8Array, p );

					let zerun = getBitsReturn.l + SHORTEST_LONG_RUN;
					c = getBitsReturn.c;
					lc = getBitsReturn.lc;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				} else if ( l >= SHORT_ZEROCODE_RUN ) {

					let zerun = l - SHORT_ZEROCODE_RUN + 2;

					if ( im + zerun > iM + 1 ) {

						throw new Error( 'Something wrong with hufUnpackEncTable' );

					}

					while ( zerun -- ) hcode[ im ++ ] = 0;

					im --;

				}

			}

			hufCanonicalCodeTable( hcode );

		}

		function hufLength( code ) {

			return code & 63;

		}

		function hufCode( code ) {

			return code >> 6;

		}

		function hufBuildDecTable( hcode, im, iM, hdecod ) {

			for ( ; im <= iM; im ++ ) {

				const c = hufCode( hcode[ im ] );
				const l = hufLength( hcode[ im ] );

				if ( c >> l ) {

					throw new Error( 'Invalid table entry' );

				}

				if ( l > HUF_DECBITS ) {

					const pl = hdecod[ ( c >> ( l - HUF_DECBITS ) ) ];

					if ( pl.len ) {

						throw new Error( 'Invalid table entry' );

					}

					pl.lit ++;

					if ( pl.p ) {

						const p = pl.p;
						pl.p = new Array( pl.lit );

						for ( let i = 0; i < pl.lit - 1; ++ i ) {

							pl.p[ i ] = p[ i ];

						}

					} else {

						pl.p = new Array( 1 );

					}

					pl.p[ pl.lit - 1 ] = im;

				} else if ( l ) {

					let plOffset = 0;

					for ( let i = 1 << ( HUF_DECBITS - l ); i > 0; i -- ) {

						const pl = hdecod[ ( c << ( HUF_DECBITS - l ) ) + plOffset ];

						if ( pl.len || pl.p ) {

							throw new Error( 'Invalid table entry' );

						}

						pl.len = l;
						pl.lit = im;

						plOffset ++;

					}

				}

			}

			return true;

		}

		const getCharReturn = { c: 0, lc: 0 };

		function getChar( c, lc, uInt8Array, inOffset ) {

			c = ( c << 8 ) | parseUint8Array( uInt8Array, inOffset );
			lc += 8;

			getCharReturn.c = c;
			getCharReturn.lc = lc;

		}

		const getCodeReturn = { c: 0, lc: 0 };

		function getCode( po, rlc, c, lc, uInt8Array, inOffset, outBuffer, outBufferOffset, outBufferEndOffset ) {

			if ( po == rlc ) {

				if ( lc < 8 ) {

					getChar( c, lc, uInt8Array, inOffset );
					c = getCharReturn.c;
					lc = getCharReturn.lc;

				}

				lc -= 8;

				let cs = ( c >> lc );
				cs = new Uint8Array( [ cs ] )[ 0 ];

				if ( outBufferOffset.value + cs > outBufferEndOffset ) {

					return false;

				}

				const s = outBuffer[ outBufferOffset.value - 1 ];

				while ( cs -- > 0 ) {

					outBuffer[ outBufferOffset.value ++ ] = s;

				}

			} else if ( outBufferOffset.value < outBufferEndOffset ) {

				outBuffer[ outBufferOffset.value ++ ] = po;

			} else {

				return false;

			}

			getCodeReturn.c = c;
			getCodeReturn.lc = lc;

		}

		function UInt16( value ) {

			return ( value & 0xFFFF );

		}

		function Int16( value ) {

			const ref = UInt16( value );
			return ( ref > 0x7FFF ) ? ref - 0x10000 : ref;

		}

		const wdec14Return = { a: 0, b: 0 };

		function wdec14( l, h ) {

			const ls = Int16( l );
			const hs = Int16( h );

			const hi = hs;
			const ai = ls + ( hi & 1 ) + ( hi >> 1 );

			const as = ai;
			const bs = ai - hi;

			wdec14Return.a = as;
			wdec14Return.b = bs;

		}

		function wdec16( l, h ) {

			const m = UInt16( l );
			const d = UInt16( h );

			const bb = ( m - ( d >> 1 ) ) & MOD_MASK;
			const aa = ( d + bb - A_OFFSET ) & MOD_MASK;

			wdec14Return.a = aa;
			wdec14Return.b = bb;

		}

		function wav2Decode( buffer, j, nx, ox, ny, oy, mx ) {

			const w14 = mx < ( 1 << 14 );
			const n = ( nx > ny ) ? ny : nx;
			let p = 1;
			let p2;
			let py;

			while ( p <= n ) p <<= 1;

			p >>= 1;
			p2 = p;
			p >>= 1;

			while ( p >= 1 ) {

				py = 0;
				const ey = py + oy * ( ny - p2 );
				const oy1 = oy * p;
				const oy2 = oy * p2;
				const ox1 = ox * p;
				const ox2 = ox * p2;
				let i00, i01, i10, i11;

				for ( ; py <= ey; py += oy2 ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;
						const p10 = px + oy1;
						const p11 = p10 + ox1;

						if ( w14 ) {

							wdec14( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec14( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec14( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec14( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;

						} else {

							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

							i00 = wdec14Return.a;
							i10 = wdec14Return.b;

							wdec16( buffer[ p01 + j ], buffer[ p11 + j ] );

							i01 = wdec14Return.a;
							i11 = wdec14Return.b;

							wdec16( i00, i01 );

							buffer[ px + j ] = wdec14Return.a;
							buffer[ p01 + j ] = wdec14Return.b;

							wdec16( i10, i11 );

							buffer[ p10 + j ] = wdec14Return.a;
							buffer[ p11 + j ] = wdec14Return.b;


						}

					}

					if ( nx & p ) {

						const p10 = px + oy1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p10 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p10 + j ] );

						i00 = wdec14Return.a;
						buffer[ p10 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				if ( ny & p ) {

					let px = py;
					const ex = py + ox * ( nx - p2 );

					for ( ; px <= ex; px += ox2 ) {

						const p01 = px + ox1;

						if ( w14 )
							wdec14( buffer[ px + j ], buffer[ p01 + j ] );
						else
							wdec16( buffer[ px + j ], buffer[ p01 + j ] );

						i00 = wdec14Return.a;
						buffer[ p01 + j ] = wdec14Return.b;

						buffer[ px + j ] = i00;

					}

				}

				p2 = p;
				p >>= 1;

			}

			return py;

		}

		function hufDecode( encodingTable, decodingTable, uInt8Array, inOffset, ni, rlc, no, outBuffer, outOffset ) {

			let c = 0;
			let lc = 0;
			const outBufferEndOffset = no;
			const inOffsetEnd = Math.trunc( inOffset.value + ( ni + 7 ) / 8 );

			while ( inOffset.value < inOffsetEnd ) {

				getChar( c, lc, uInt8Array, inOffset );

				c = getCharReturn.c;
				lc = getCharReturn.lc;

				while ( lc >= HUF_DECBITS ) {

					const index = ( c >> ( lc - HUF_DECBITS ) ) & HUF_DECMASK;
					const pl = decodingTable[ index ];

					if ( pl.len ) {

						lc -= pl.len;

						getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

						c = getCodeReturn.c;
						lc = getCodeReturn.lc;

					} else {

						if ( ! pl.p ) {

							throw new Error( 'hufDecode issues' );

						}

						let j;

						for ( j = 0; j < pl.lit; j ++ ) {

							const l = hufLength( encodingTable[ pl.p[ j ] ] );

							while ( lc < l && inOffset.value < inOffsetEnd ) {

								getChar( c, lc, uInt8Array, inOffset );

								c = getCharReturn.c;
								lc = getCharReturn.lc;

							}

							if ( lc >= l ) {

								if ( hufCode( encodingTable[ pl.p[ j ] ] ) == ( ( c >> ( lc - l ) ) & ( ( 1 << l ) - 1 ) ) ) {

									lc -= l;

									getCode( pl.p[ j ], rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

									c = getCodeReturn.c;
									lc = getCodeReturn.lc;

									break;

								}

							}

						}

						if ( j == pl.lit ) {

							throw new Error( 'hufDecode issues' );

						}

					}

				}

			}

			const i = ( 8 - ni ) & 7;

			c >>= i;
			lc -= i;

			while ( lc > 0 ) {

				const pl = decodingTable[ ( c << ( HUF_DECBITS - lc ) ) & HUF_DECMASK ];

				if ( pl.len ) {

					lc -= pl.len;

					getCode( pl.lit, rlc, c, lc, uInt8Array, inOffset, outBuffer, outOffset, outBufferEndOffset );

					c = getCodeReturn.c;
					lc = getCodeReturn.lc;

				} else {

					throw new Error( 'hufDecode issues' );

				}

			}

			return true;

		}

		function hufUncompress( uInt8Array, inDataView, inOffset, nCompressed, outBuffer, nRaw ) {

			const outOffset = { value: 0 };
			const initialInOffset = inOffset.value;

			const im = parseUint32( inDataView, inOffset );
			const iM = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			const nBits = parseUint32( inDataView, inOffset );

			inOffset.value += 4;

			if ( im < 0 || im >= HUF_ENCSIZE || iM < 0 || iM >= HUF_ENCSIZE ) {

				throw new Error( 'Something wrong with HUF_ENCSIZE' );

			}

			const freq = new Array( HUF_ENCSIZE );
			const hdec = new Array( HUF_DECSIZE );

			hufClearDecTable( hdec );

			const ni = nCompressed - ( inOffset.value - initialInOffset );

			hufUnpackEncTable( uInt8Array, inOffset, ni, im, iM, freq );

			if ( nBits > 8 * ( nCompressed - ( inOffset.value - initialInOffset ) ) ) {

				throw new Error( 'Something wrong with hufUncompress' );

			}

			hufBuildDecTable( freq, im, iM, hdec );

			hufDecode( freq, hdec, uInt8Array, inOffset, nBits, iM, nRaw, outBuffer, outOffset );

		}

		function applyLut( lut, data, nData ) {

			for ( let i = 0; i < nData; ++ i ) {

				data[ i ] = lut[ data[ i ] ];

			}

		}

		function predictor( source ) {

			for ( let t = 1; t < source.length; t ++ ) {

				const d = source[ t - 1 ] + source[ t ] - 128;
				source[ t ] = d;

			}

		}

		function interleaveScalar( source, out ) {

			let t1 = 0;
			let t2 = Math.floor( ( source.length + 1 ) / 2 );
			let s = 0;
			const stop = source.length - 1;

			while ( true ) {

				if ( s > stop ) break;
				out[ s ++ ] = source[ t1 ++ ];

				if ( s > stop ) break;
				out[ s ++ ] = source[ t2 ++ ];

			}

		}

		function decodeRunLength( source ) {

			let size = source.byteLength;
			const out = new Array();
			let p = 0;

			const reader = new DataView( source );

			while ( size > 0 ) {

				const l = reader.getInt8( p ++ );

				if ( l < 0 ) {

					const count = - l;
					size -= count + 1;

					for ( let i = 0; i < count; i ++ ) {

						out.push( reader.getUint8( p ++ ) );

					}


				} else {

					const count = l;
					size -= 2;

					const value = reader.getUint8( p ++ );

					for ( let i = 0; i < count + 1; i ++ ) {

						out.push( value );

					}

				}

			}

			return out;

		}

		function lossyDctDecode( cscSet, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			let dataView = new DataView( outBuffer.buffer );

			const width = channelData[ cscSet.idx[ 0 ] ].width;
			const height = channelData[ cscSet.idx[ 0 ] ].height;

			const numComp = 3;

			const numFullBlocksX = Math.floor( width / 8.0 );
			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			const currDcComp = new Array( numComp );
			const dctData = new Array( numComp );
			const halfZigBlock = new Array( numComp );
			const rowBlock = new Array( numComp );
			const rowOffsets = new Array( numComp );

			for ( let comp = 0; comp < numComp; ++ comp ) {

				rowOffsets[ comp ] = rowPtrs[ cscSet.idx[ comp ] ];
				currDcComp[ comp ] = ( comp < 1 ) ? 0 : currDcComp[ comp - 1 ] + numBlocksX * numBlocksY;
				dctData[ comp ] = new Float32Array( 64 );
				halfZigBlock[ comp ] = new Uint16Array( 64 );
				rowBlock[ comp ] = new Uint16Array( numBlocksX * 64 );

			}

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 )
					maxY = leftoverY;

				let maxX = 8;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					if ( blockx == numBlocksX - 1 )
						maxX = leftoverX;

					for ( let comp = 0; comp < numComp; ++ comp ) {

						halfZigBlock[ comp ].fill( 0 );

						// set block DC component
						halfZigBlock[ comp ][ 0 ] = dcBuffer[ currDcComp[ comp ] ++ ];
						// set block AC components
						unRleAC( currAcComp, acBuffer, halfZigBlock[ comp ] );

						// UnZigZag block to float
						unZigZag( halfZigBlock[ comp ], dctData[ comp ] );
						// decode float dct
						dctInverse( dctData[ comp ] );

					}

					if ( numComp == 3 ) {

						csc709Inverse( dctData );

					}

					for ( let comp = 0; comp < numComp; ++ comp ) {

						convertToHalf( dctData[ comp ], rowBlock[ comp ], blockx * 64 );

					}

				} // blockx

				let offset = 0;

				for ( let comp = 0; comp < numComp; ++ comp ) {

					const type = channelData[ cscSet.idx[ comp ] ].type;

					for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

						offset = rowOffsets[ comp ][ y ];

						for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

							const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

							dataView.setUint16( offset + 0 * INT16_SIZE * type, rowBlock[ comp ][ src + 0 ], true );
							dataView.setUint16( offset + 1 * INT16_SIZE * type, rowBlock[ comp ][ src + 1 ], true );
							dataView.setUint16( offset + 2 * INT16_SIZE * type, rowBlock[ comp ][ src + 2 ], true );
							dataView.setUint16( offset + 3 * INT16_SIZE * type, rowBlock[ comp ][ src + 3 ], true );

							dataView.setUint16( offset + 4 * INT16_SIZE * type, rowBlock[ comp ][ src + 4 ], true );
							dataView.setUint16( offset + 5 * INT16_SIZE * type, rowBlock[ comp ][ src + 5 ], true );
							dataView.setUint16( offset + 6 * INT16_SIZE * type, rowBlock[ comp ][ src + 6 ], true );
							dataView.setUint16( offset + 7 * INT16_SIZE * type, rowBlock[ comp ][ src + 7 ], true );

							offset += 8 * INT16_SIZE * type;

						}

					}

					// handle partial X blocks
					if ( numFullBlocksX != numBlocksX ) {

						for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

							const offset = rowOffsets[ comp ][ y ] + 8 * numFullBlocksX * INT16_SIZE * type;
							const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

							for ( let x = 0; x < maxX; ++ x ) {

								dataView.setUint16( offset + x * INT16_SIZE * type, rowBlock[ comp ][ src + x ], true );

							}

						}

					}

				} // comp

			} // blocky

			const halfRow = new Uint16Array( width );
			dataView = new DataView( outBuffer.buffer );

			// convert channels back to float, if needed
			for ( let comp = 0; comp < numComp; ++ comp ) {

				channelData[ cscSet.idx[ comp ] ].decoded = true;
				const type = channelData[ cscSet.idx[ comp ] ].type;

				if ( channelData[ comp ].type != 2 ) continue;

				for ( let y = 0; y < height; ++ y ) {

					const offset = rowOffsets[ comp ][ y ];

					for ( let x = 0; x < width; ++ x ) {

						halfRow[ x ] = dataView.getUint16( offset + x * INT16_SIZE * type, true );

					}

					for ( let x = 0; x < width; ++ x ) {

						dataView.setFloat32( offset + x * INT16_SIZE * type, decodeFloat16( halfRow[ x ] ), true );

					}

				}

			}

		}

		function lossyDctChannelDecode( channelIndex, rowPtrs, channelData, acBuffer, dcBuffer, outBuffer ) {

			const dataView = new DataView( outBuffer.buffer );
			const cd = channelData[ channelIndex ];
			const width = cd.width;
			const height = cd.height;

			const numBlocksX = Math.ceil( width / 8.0 );
			const numBlocksY = Math.ceil( height / 8.0 );
			const numFullBlocksX = Math.floor( width / 8.0 );
			const leftoverX = width - ( numBlocksX - 1 ) * 8;
			const leftoverY = height - ( numBlocksY - 1 ) * 8;

			const currAcComp = { value: 0 };
			let currDcComp = 0;
			const dctData = new Float32Array( 64 );
			const halfZigBlock = new Uint16Array( 64 );
			const rowBlock = new Uint16Array( numBlocksX * 64 );

			for ( let blocky = 0; blocky < numBlocksY; ++ blocky ) {

				let maxY = 8;

				if ( blocky == numBlocksY - 1 ) maxY = leftoverY;

				for ( let blockx = 0; blockx < numBlocksX; ++ blockx ) {

					halfZigBlock.fill( 0 );
					halfZigBlock[ 0 ] = dcBuffer[ currDcComp ++ ];
					unRleAC( currAcComp, acBuffer, halfZigBlock );
					unZigZag( halfZigBlock, dctData );
					dctInverse( dctData );
					convertToHalf( dctData, rowBlock, blockx * 64 );

				}

				// Write decoded data to output buffer
				for ( let y = 8 * blocky; y < 8 * blocky + maxY; ++ y ) {

					let offset = rowPtrs[ channelIndex ][ y ];

					for ( let blockx = 0; blockx < numFullBlocksX; ++ blockx ) {

						const src = blockx * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < 8; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

						offset += 8 * INT16_SIZE * cd.type;

					}

					if ( numBlocksX != numFullBlocksX ) {

						const src = numFullBlocksX * 64 + ( ( y & 0x7 ) * 8 );

						for ( let x = 0; x < leftoverX; ++ x ) {

							dataView.setUint16( offset + x * INT16_SIZE * cd.type, rowBlock[ src + x ], true );

						}

					}

				}

			}

			cd.decoded = true;

		}

		function unRleAC( currAcComp, acBuffer, halfZigBlock ) {

			let acValue;
			let dctComp = 1;

			while ( dctComp < 64 ) {

				acValue = acBuffer[ currAcComp.value ];

				if ( acValue == 0xff00 ) {

					dctComp = 64;

				} else if ( acValue >> 8 == 0xff ) {

					dctComp += acValue & 0xff;

				} else {

					halfZigBlock[ dctComp ] = acValue;
					dctComp ++;

				}

				currAcComp.value ++;

			}

		}

		function unZigZag( src, dst ) {

			dst[ 0 ] = decodeFloat16( src[ 0 ] );
			dst[ 1 ] = decodeFloat16( src[ 1 ] );
			dst[ 2 ] = decodeFloat16( src[ 5 ] );
			dst[ 3 ] = decodeFloat16( src[ 6 ] );
			dst[ 4 ] = decodeFloat16( src[ 14 ] );
			dst[ 5 ] = decodeFloat16( src[ 15 ] );
			dst[ 6 ] = decodeFloat16( src[ 27 ] );
			dst[ 7 ] = decodeFloat16( src[ 28 ] );
			dst[ 8 ] = decodeFloat16( src[ 2 ] );
			dst[ 9 ] = decodeFloat16( src[ 4 ] );

			dst[ 10 ] = decodeFloat16( src[ 7 ] );
			dst[ 11 ] = decodeFloat16( src[ 13 ] );
			dst[ 12 ] = decodeFloat16( src[ 16 ] );
			dst[ 13 ] = decodeFloat16( src[ 26 ] );
			dst[ 14 ] = decodeFloat16( src[ 29 ] );
			dst[ 15 ] = decodeFloat16( src[ 42 ] );
			dst[ 16 ] = decodeFloat16( src[ 3 ] );
			dst[ 17 ] = decodeFloat16( src[ 8 ] );
			dst[ 18 ] = decodeFloat16( src[ 12 ] );
			dst[ 19 ] = decodeFloat16( src[ 17 ] );

			dst[ 20 ] = decodeFloat16( src[ 25 ] );
			dst[ 21 ] = decodeFloat16( src[ 30 ] );
			dst[ 22 ] = decodeFloat16( src[ 41 ] );
			dst[ 23 ] = decodeFloat16( src[ 43 ] );
			dst[ 24 ] = decodeFloat16( src[ 9 ] );
			dst[ 25 ] = decodeFloat16( src[ 11 ] );
			dst[ 26 ] = decodeFloat16( src[ 18 ] );
			dst[ 27 ] = decodeFloat16( src[ 24 ] );
			dst[ 28 ] = decodeFloat16( src[ 31 ] );
			dst[ 29 ] = decodeFloat16( src[ 40 ] );

			dst[ 30 ] = decodeFloat16( src[ 44 ] );
			dst[ 31 ] = decodeFloat16( src[ 53 ] );
			dst[ 32 ] = decodeFloat16( src[ 10 ] );
			dst[ 33 ] = decodeFloat16( src[ 19 ] );
			dst[ 34 ] = decodeFloat16( src[ 23 ] );
			dst[ 35 ] = decodeFloat16( src[ 32 ] );
			dst[ 36 ] = decodeFloat16( src[ 39 ] );
			dst[ 37 ] = decodeFloat16( src[ 45 ] );
			dst[ 38 ] = decodeFloat16( src[ 52 ] );
			dst[ 39 ] = decodeFloat16( src[ 54 ] );

			dst[ 40 ] = decodeFloat16( src[ 20 ] );
			dst[ 41 ] = decodeFloat16( src[ 22 ] );
			dst[ 42 ] = decodeFloat16( src[ 33 ] );
			dst[ 43 ] = decodeFloat16( src[ 38 ] );
			dst[ 44 ] = decodeFloat16( src[ 46 ] );
			dst[ 45 ] = decodeFloat16( src[ 51 ] );
			dst[ 46 ] = decodeFloat16( src[ 55 ] );
			dst[ 47 ] = decodeFloat16( src[ 60 ] );
			dst[ 48 ] = decodeFloat16( src[ 21 ] );
			dst[ 49 ] = decodeFloat16( src[ 34 ] );

			dst[ 50 ] = decodeFloat16( src[ 37 ] );
			dst[ 51 ] = decodeFloat16( src[ 47 ] );
			dst[ 52 ] = decodeFloat16( src[ 50 ] );
			dst[ 53 ] = decodeFloat16( src[ 56 ] );
			dst[ 54 ] = decodeFloat16( src[ 59 ] );
			dst[ 55 ] = decodeFloat16( src[ 61 ] );
			dst[ 56 ] = decodeFloat16( src[ 35 ] );
			dst[ 57 ] = decodeFloat16( src[ 36 ] );
			dst[ 58 ] = decodeFloat16( src[ 48 ] );
			dst[ 59 ] = decodeFloat16( src[ 49 ] );

			dst[ 60 ] = decodeFloat16( src[ 57 ] );
			dst[ 61 ] = decodeFloat16( src[ 58 ] );
			dst[ 62 ] = decodeFloat16( src[ 62 ] );
			dst[ 63 ] = decodeFloat16( src[ 63 ] );

		}

		function dctInverse( data ) {

			const a = 0.5 * Math.cos( 3.14159 / 4.0 );
			const b = 0.5 * Math.cos( 3.14159 / 16.0 );
			const c = 0.5 * Math.cos( 3.14159 / 8.0 );
			const d = 0.5 * Math.cos( 3.0 * 3.14159 / 16.0 );
			const e = 0.5 * Math.cos( 5.0 * 3.14159 / 16.0 );
			const f = 0.5 * Math.cos( 3.0 * 3.14159 / 8.0 );
			const g = 0.5 * Math.cos( 7.0 * 3.14159 / 16.0 );

			const alpha = new Array( 4 );
			const beta = new Array( 4 );
			const theta = new Array( 4 );
			const gamma = new Array( 4 );

			for ( let row = 0; row < 8; ++ row ) {

				const rowPtr = row * 8;

				alpha[ 0 ] = c * data[ rowPtr + 2 ];
				alpha[ 1 ] = f * data[ rowPtr + 2 ];
				alpha[ 2 ] = c * data[ rowPtr + 6 ];
				alpha[ 3 ] = f * data[ rowPtr + 6 ];

				beta[ 0 ] = b * data[ rowPtr + 1 ] + d * data[ rowPtr + 3 ] + e * data[ rowPtr + 5 ] + g * data[ rowPtr + 7 ];
				beta[ 1 ] = d * data[ rowPtr + 1 ] - g * data[ rowPtr + 3 ] - b * data[ rowPtr + 5 ] - e * data[ rowPtr + 7 ];
				beta[ 2 ] = e * data[ rowPtr + 1 ] - b * data[ rowPtr + 3 ] + g * data[ rowPtr + 5 ] + d * data[ rowPtr + 7 ];
				beta[ 3 ] = g * data[ rowPtr + 1 ] - e * data[ rowPtr + 3 ] + d * data[ rowPtr + 5 ] - b * data[ rowPtr + 7 ];

				theta[ 0 ] = a * ( data[ rowPtr + 0 ] + data[ rowPtr + 4 ] );
				theta[ 3 ] = a * ( data[ rowPtr + 0 ] - data[ rowPtr + 4 ] );
				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ rowPtr + 0 ] = gamma[ 0 ] + beta[ 0 ];
				data[ rowPtr + 1 ] = gamma[ 1 ] + beta[ 1 ];
				data[ rowPtr + 2 ] = gamma[ 2 ] + beta[ 2 ];
				data[ rowPtr + 3 ] = gamma[ 3 ] + beta[ 3 ];

				data[ rowPtr + 4 ] = gamma[ 3 ] - beta[ 3 ];
				data[ rowPtr + 5 ] = gamma[ 2 ] - beta[ 2 ];
				data[ rowPtr + 6 ] = gamma[ 1 ] - beta[ 1 ];
				data[ rowPtr + 7 ] = gamma[ 0 ] - beta[ 0 ];

			}

			for ( let column = 0; column < 8; ++ column ) {

				alpha[ 0 ] = c * data[ 16 + column ];
				alpha[ 1 ] = f * data[ 16 + column ];
				alpha[ 2 ] = c * data[ 48 + column ];
				alpha[ 3 ] = f * data[ 48 + column ];

				beta[ 0 ] = b * data[ 8 + column ] + d * data[ 24 + column ] + e * data[ 40 + column ] + g * data[ 56 + column ];
				beta[ 1 ] = d * data[ 8 + column ] - g * data[ 24 + column ] - b * data[ 40 + column ] - e * data[ 56 + column ];
				beta[ 2 ] = e * data[ 8 + column ] - b * data[ 24 + column ] + g * data[ 40 + column ] + d * data[ 56 + column ];
				beta[ 3 ] = g * data[ 8 + column ] - e * data[ 24 + column ] + d * data[ 40 + column ] - b * data[ 56 + column ];

				theta[ 0 ] = a * ( data[ column ] + data[ 32 + column ] );
				theta[ 3 ] = a * ( data[ column ] - data[ 32 + column ] );

				theta[ 1 ] = alpha[ 0 ] + alpha[ 3 ];
				theta[ 2 ] = alpha[ 1 ] - alpha[ 2 ];

				gamma[ 0 ] = theta[ 0 ] + theta[ 1 ];
				gamma[ 1 ] = theta[ 3 ] + theta[ 2 ];
				gamma[ 2 ] = theta[ 3 ] - theta[ 2 ];
				gamma[ 3 ] = theta[ 0 ] - theta[ 1 ];

				data[ 0 + column ] = gamma[ 0 ] + beta[ 0 ];
				data[ 8 + column ] = gamma[ 1 ] + beta[ 1 ];
				data[ 16 + column ] = gamma[ 2 ] + beta[ 2 ];
				data[ 24 + column ] = gamma[ 3 ] + beta[ 3 ];

				data[ 32 + column ] = gamma[ 3 ] - beta[ 3 ];
				data[ 40 + column ] = gamma[ 2 ] - beta[ 2 ];
				data[ 48 + column ] = gamma[ 1 ] - beta[ 1 ];
				data[ 56 + column ] = gamma[ 0 ] - beta[ 0 ];

			}

		}

		function csc709Inverse( data ) {

			for ( let i = 0; i < 64; ++ i ) {

				const y = data[ 0 ][ i ];
				const cb = data[ 1 ][ i ];
				const cr = data[ 2 ][ i ];

				data[ 0 ][ i ] = y + 1.5747 * cr;
				data[ 1 ][ i ] = y - 0.1873 * cb - 0.4682 * cr;
				data[ 2 ][ i ] = y + 1.8556 * cb;

			}

		}

		function convertToHalf( src, dst, idx ) {

			for ( let i = 0; i < 64; ++ i ) {

				dst[ idx + i ] = DataUtils.toHalfFloat( toLinear( src[ i ] ) );

			}

		}

		function toLinear( float ) {

			if ( float <= 1 ) {

				return Math.sign( float ) * Math.pow( Math.abs( float ), 2.2 );

			} else {

				return Math.sign( float ) * Math.pow( logBase, Math.abs( float ) - 1.0 );

			}

		}

		function uncompressRAW( info ) {

			return new DataView( info.array.buffer, info.offset.value, info.size );

		}

		function uncompressRLE( info ) {

			const compressed = info.viewer.buffer.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = new Uint8Array( decodeRunLength( compressed ) );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressZIP( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );
			const tmpBuffer = new Uint8Array( rawBuffer.length );

			predictor( rawBuffer ); // revert predictor

			interleaveScalar( rawBuffer, tmpBuffer ); // interleave pixels

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressPIZ( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };

			const outBuffer = new Uint16Array( info.columns * info.lines * ( info.inputChannels.length * info.type ) );
			const bitmap = new Uint8Array( BITMAP_SIZE );

			// Setup channel info
			let outBufferEnd = 0;
			const pizChannelData = new Array( info.inputChannels.length );
			for ( let i = 0, il = info.inputChannels.length; i < il; i ++ ) {

				pizChannelData[ i ] = {};
				pizChannelData[ i ][ 'start' ] = outBufferEnd;
				pizChannelData[ i ][ 'end' ] = pizChannelData[ i ][ 'start' ];
				pizChannelData[ i ][ 'nx' ] = info.columns;
				pizChannelData[ i ][ 'ny' ] = info.lines;
				pizChannelData[ i ][ 'size' ] = info.type;

				outBufferEnd += pizChannelData[ i ].nx * pizChannelData[ i ].ny * pizChannelData[ i ].size;

			}

			// Read range compression data

			const minNonZero = parseUint16( inDataView, inOffset );
			const maxNonZero = parseUint16( inDataView, inOffset );

			if ( maxNonZero >= BITMAP_SIZE ) {

				throw new Error( 'Something is wrong with PIZ_COMPRESSION BITMAP_SIZE' );

			}

			if ( minNonZero <= maxNonZero ) {

				for ( let i = 0; i < maxNonZero - minNonZero + 1; i ++ ) {

					bitmap[ i + minNonZero ] = parseUint8( inDataView, inOffset );

				}

			}

			// Reverse LUT
			const lut = new Uint16Array( USHORT_RANGE );
			const maxValue = reverseLutFromBitmap( bitmap, lut );

			const length = parseUint32( inDataView, inOffset );

			// Huffman decoding
			hufUncompress( info.array, inDataView, inOffset, length, outBuffer, outBufferEnd );

			// Wavelet decoding
			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = pizChannelData[ i ];

				for ( let j = 0; j < pizChannelData[ i ].size; ++ j ) {

					wav2Decode(
						outBuffer,
						cd.start + j,
						cd.nx,
						cd.size,
						cd.ny,
						cd.nx * cd.size,
						maxValue
					);

				}

			}

			// Expand the pixel data to their original range
			applyLut( lut, outBuffer, outBufferEnd );

			// Rearrange the pixel data into the format expected by the caller.
			let tmpOffset = 0;
			const tmpBuffer = new Uint8Array( outBuffer.buffer.byteLength );
			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					const cd = pizChannelData[ c ];

					const n = cd.nx * cd.size;
					const cp = new Uint8Array( outBuffer.buffer, cd.end * INT16_SIZE, n * INT16_SIZE );

					tmpBuffer.set( cp, tmpOffset );
					tmpOffset += n * INT16_SIZE;
					cd.end += n;

				}

			}

			return new DataView( tmpBuffer.buffer );

		}

		function uncompressPXR( info ) {

			const compressed = info.array.slice( info.offset.value, info.offset.value + info.size );

			const rawBuffer = fflate.unzlibSync( compressed );

			const byteSize = info.inputChannels.length * info.lines * info.columns * info.totalBytes;
			const tmpBuffer = new ArrayBuffer( byteSize );
			const viewer = new DataView( tmpBuffer );

			let tmpBufferEnd = 0;
			let writePtr = 0;
			const ptr = new Array( 4 );

			for ( let y = 0; y < info.lines; y ++ ) {

				for ( let c = 0; c < info.inputChannels.length; c ++ ) {

					let pixel = 0;

					const type = info.inputChannels[ c ].pixelType;
					switch ( type ) {

						case 1:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							tmpBufferEnd = ptr[ 1 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 8 ) | rawBuffer[ ptr[ 1 ] ++ ];

								pixel += diff;

								viewer.setUint16( writePtr, pixel, true );
								writePtr += 2;

							}

							break;

						case 2:

							ptr[ 0 ] = tmpBufferEnd;
							ptr[ 1 ] = ptr[ 0 ] + info.columns;
							ptr[ 2 ] = ptr[ 1 ] + info.columns;
							tmpBufferEnd = ptr[ 2 ] + info.columns;

							for ( let j = 0; j < info.columns; ++ j ) {

								const diff = ( rawBuffer[ ptr[ 0 ] ++ ] << 24 ) | ( rawBuffer[ ptr[ 1 ] ++ ] << 16 ) | ( rawBuffer[ ptr[ 2 ] ++ ] << 8 );

								pixel += diff;

								viewer.setUint32( writePtr, pixel, true );
								writePtr += 4;

							}

							break;

					}

				}

			}

			return viewer;

		}

		function uncompressDWA( info ) {

			const inDataView = info.viewer;
			const inOffset = { value: info.offset.value };
			const outBuffer = new Uint8Array( info.columns * info.lines * ( info.inputChannels.length * info.type * INT16_SIZE ) );

			// Read compression header information
			const dwaHeader = {

				version: parseInt64( inDataView, inOffset ),
				unknownUncompressedSize: parseInt64( inDataView, inOffset ),
				unknownCompressedSize: parseInt64( inDataView, inOffset ),
				acCompressedSize: parseInt64( inDataView, inOffset ),
				dcCompressedSize: parseInt64( inDataView, inOffset ),
				rleCompressedSize: parseInt64( inDataView, inOffset ),
				rleUncompressedSize: parseInt64( inDataView, inOffset ),
				rleRawSize: parseInt64( inDataView, inOffset ),
				totalAcUncompressedCount: parseInt64( inDataView, inOffset ),
				totalDcUncompressedCount: parseInt64( inDataView, inOffset ),
				acCompression: parseInt64( inDataView, inOffset )

			};

			if ( dwaHeader.version < 2 )
				throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' version ' + dwaHeader.version + ' is unsupported' );

			// Read channel ruleset information
			const channelRules = new Array();
			let ruleSize = parseUint16( inDataView, inOffset ) - INT16_SIZE;

			while ( ruleSize > 0 ) {

				const name = parseNullTerminatedString( inDataView.buffer, inOffset );
				const value = parseUint8( inDataView, inOffset );
				const compression = ( value >> 2 ) & 3;
				const csc = ( value >> 4 ) - 1;
				const index = new Int8Array( [ csc ] )[ 0 ];
				const type = parseUint8( inDataView, inOffset );

				channelRules.push( {
					name: name,
					index: index,
					type: type,
					compression: compression,
				} );

				ruleSize -= name.length + 3;

			}

			// Classify channels
			const channels = EXRHeader.channels;
			const channelData = new Array( info.inputChannels.length );

			for ( let i = 0; i < info.inputChannels.length; ++ i ) {

				const cd = channelData[ i ] = {};
				const channel = channels[ i ];

				cd.name = channel.name;
				cd.compression = UNKNOWN;
				cd.decoded = false;
				cd.type = channel.pixelType;
				cd.pLinear = channel.pLinear;
				cd.width = info.columns;
				cd.height = info.lines;

			}

			const cscSet = {
				idx: new Array( 3 )
			};

			for ( let offset = 0; offset < info.inputChannels.length; ++ offset ) {

				const cd = channelData[ offset ];

				for ( let i = 0; i < channelRules.length; ++ i ) {

					const rule = channelRules[ i ];

					if ( cd.name == rule.name ) {

						cd.compression = rule.compression;

						if ( rule.index >= 0 ) {

							cscSet.idx[ rule.index ] = offset;

						}

						cd.offset = offset;

					}

				}

			}

			let acBuffer, dcBuffer, rleBuffer;

			// Read DCT - AC component data
			if ( dwaHeader.acCompressedSize > 0 ) {

				switch ( dwaHeader.acCompression ) {

					case STATIC_HUFFMAN:

						acBuffer = new Uint16Array( dwaHeader.totalAcUncompressedCount );
						hufUncompress( info.array, inDataView, inOffset, dwaHeader.acCompressedSize, acBuffer, dwaHeader.totalAcUncompressedCount );
						break;

					case DEFLATE:

						const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.totalAcUncompressedCount );
						const data = fflate.unzlibSync( compressed );
						acBuffer = new Uint16Array( data.buffer );
						inOffset.value += dwaHeader.totalAcUncompressedCount;
						break;

				}


			}

			// Read DCT - DC component data
			if ( dwaHeader.dcCompressedSize > 0 ) {

				const zlibInfo = {
					array: info.array,
					offset: inOffset,
					size: dwaHeader.dcCompressedSize
				};
				dcBuffer = new Uint16Array( uncompressZIP( zlibInfo ).buffer );
				inOffset.value += dwaHeader.dcCompressedSize;

			}

			// Read RLE compressed data
			if ( dwaHeader.rleRawSize > 0 ) {

				const compressed = info.array.slice( inOffset.value, inOffset.value + dwaHeader.rleCompressedSize );
				const data = fflate.unzlibSync( compressed );
				rleBuffer = decodeRunLength( data.buffer );

				inOffset.value += dwaHeader.rleCompressedSize;

			}

			// Prepare outbuffer data offset
			let outBufferEnd = 0;
			const rowOffsets = new Array( channelData.length );
			for ( let i = 0; i < rowOffsets.length; ++ i ) {

				rowOffsets[ i ] = new Array();

			}

			for ( let y = 0; y < info.lines; ++ y ) {

				for ( let chan = 0; chan < channelData.length; ++ chan ) {

					rowOffsets[ chan ].push( outBufferEnd );
					outBufferEnd += channelData[ chan ].width * info.type * INT16_SIZE;

				}

			}

			// Decode lossy DCT data if we have a valid color space conversion set with the first RGB channel present
			if ( cscSet.idx[ 0 ] !== undefined && channelData[ cscSet.idx[ 0 ] ] ) {

				lossyDctDecode( cscSet, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

			}

			// Decode other channels
			for ( let i = 0; i < channelData.length; ++ i ) {

				const cd = channelData[ i ];

				if ( cd.decoded ) continue;

				switch ( cd.compression ) {

					case RLE:

						let row = 0;
						let rleOffset = 0;

						for ( let y = 0; y < info.lines; ++ y ) {

							let rowOffsetBytes = rowOffsets[ i ][ row ];

							for ( let x = 0; x < cd.width; ++ x ) {

								for ( let byte = 0; byte < INT16_SIZE * cd.type; ++ byte ) {

									outBuffer[ rowOffsetBytes ++ ] = rleBuffer[ rleOffset + byte * cd.width * cd.height ];

								}

								rleOffset ++;

							}

							row ++;

						}

						break;

					case LOSSY_DCT:

						lossyDctChannelDecode( i, rowOffsets, channelData, acBuffer, dcBuffer, outBuffer );

						break;

					default:
						throw new Error( 'EXRLoader.parse: unsupported channel compression' );

				}

			}

			return new DataView( outBuffer.buffer );

		}

		function parseNullTerminatedString( buffer, offset ) {

			const uintBuffer = new Uint8Array( buffer );
			let endOffset = 0;

			while ( uintBuffer[ offset.value + endOffset ] != 0 ) {

				endOffset += 1;

			}

			const stringValue = new TextDecoder().decode(
				uintBuffer.slice( offset.value, offset.value + endOffset )
			);

			offset.value = offset.value + endOffset + 1;

			return stringValue;

		}

		function parseFixedLengthString( buffer, offset, size ) {

			const stringValue = new TextDecoder().decode(
				new Uint8Array( buffer ).slice( offset.value, offset.value + size )
			);

			offset.value = offset.value + size;

			return stringValue;

		}

		function parseRational( dataView, offset ) {

			const x = parseInt32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}

		function parseTimecode( dataView, offset ) {

			const x = parseUint32( dataView, offset );
			const y = parseUint32( dataView, offset );

			return [ x, y ];

		}

		function parseInt32( dataView, offset ) {

			const Int32 = dataView.getInt32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Int32;

		}

		function parseUint32( dataView, offset ) {

			const Uint32 = dataView.getUint32( offset.value, true );

			offset.value = offset.value + INT32_SIZE;

			return Uint32;

		}

		function parseUint8Array( uInt8Array, offset ) {

			const Uint8 = uInt8Array[ offset.value ];

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}

		function parseUint8( dataView, offset ) {

			const Uint8 = dataView.getUint8( offset.value );

			offset.value = offset.value + INT8_SIZE;

			return Uint8;

		}

		const parseInt64 = function ( dataView, offset ) {

			let int;

			if ( 'getBigInt64' in DataView.prototype ) {

				int = Number( dataView.getBigInt64( offset.value, true ) );

			} else {

				int = dataView.getUint32( offset.value + 4, true ) + Number( dataView.getUint32( offset.value, true ) << 32 );

			}

			offset.value += ULONG_SIZE;

			return int;

		};

		function parseFloat32( dataView, offset ) {

			const float = dataView.getFloat32( offset.value, true );

			offset.value += FLOAT32_SIZE;

			return float;

		}

		function decodeFloat32( dataView, offset ) {

			return DataUtils.toHalfFloat( parseFloat32( dataView, offset ) );

		}

		// https://stackoverflow.com/questions/5678432/decompressing-half-precision-floats-in-javascript
		function decodeFloat16( binary ) {

			const exponent = ( binary & 0x7C00 ) >> 10,
				fraction = binary & 0x03FF;

			return ( binary >> 15 ? - 1 : 1 ) * (
				exponent ?
					(
						exponent === 0x1F ?
							fraction ? NaN : Infinity :
							Math.pow( 2, exponent - 15 ) * ( 1 + fraction / 0x400 )
					) :
					6.103515625e-5 * ( fraction / 0x400 )
			);

		}

		function parseUint16( dataView, offset ) {

			const Uint16 = dataView.getUint16( offset.value, true );

			offset.value += INT16_SIZE;

			return Uint16;

		}

		function parseFloat16( buffer, offset ) {

			return decodeFloat16( parseUint16( buffer, offset ) );

		}

		function parseChlist( dataView, buffer, offset, size ) {

			const startOffset = offset.value;
			const channels = [];

			while ( offset.value < ( startOffset + size - 1 ) ) {

				const name = parseNullTerminatedString( buffer, offset );
				const pixelType = parseInt32( dataView, offset );
				const pLinear = parseUint8( dataView, offset );
				offset.value += 3; // reserved, three chars
				const xSampling = parseInt32( dataView, offset );
				const ySampling = parseInt32( dataView, offset );

				channels.push( {
					name: name,
					pixelType: pixelType,
					pLinear: pLinear,
					xSampling: xSampling,
					ySampling: ySampling
				} );

			}

			offset.value += 1;

			return channels;

		}

		function parseChromaticities( dataView, offset ) {

			const redX = parseFloat32( dataView, offset );
			const redY = parseFloat32( dataView, offset );
			const greenX = parseFloat32( dataView, offset );
			const greenY = parseFloat32( dataView, offset );
			const blueX = parseFloat32( dataView, offset );
			const blueY = parseFloat32( dataView, offset );
			const whiteX = parseFloat32( dataView, offset );
			const whiteY = parseFloat32( dataView, offset );

			return { redX: redX, redY: redY, greenX: greenX, greenY: greenY, blueX: blueX, blueY: blueY, whiteX: whiteX, whiteY: whiteY };

		}

		function parseCompression( dataView, offset ) {

			const compressionCodes = [
				'NO_COMPRESSION',
				'RLE_COMPRESSION',
				'ZIPS_COMPRESSION',
				'ZIP_COMPRESSION',
				'PIZ_COMPRESSION',
				'PXR24_COMPRESSION',
				'B44_COMPRESSION',
				'B44A_COMPRESSION',
				'DWAA_COMPRESSION',
				'DWAB_COMPRESSION'
			];

			const compression = parseUint8( dataView, offset );

			return compressionCodes[ compression ];

		}

		function parseBox2i( dataView, offset ) {

			const xMin = parseInt32( dataView, offset );
			const yMin = parseInt32( dataView, offset );
			const xMax = parseInt32( dataView, offset );
			const yMax = parseInt32( dataView, offset );

			return { xMin: xMin, yMin: yMin, xMax: xMax, yMax: yMax };

		}

		function parseLineOrder( dataView, offset ) {

			const lineOrders = [
				'INCREASING_Y',
				'DECREASING_Y',
				'RANDOM_Y',
			];

			const lineOrder = parseUint8( dataView, offset );

			return lineOrders[ lineOrder ];

		}

		function parseEnvmap( dataView, offset ) {

			const envmaps = [
				'ENVMAP_LATLONG',
				'ENVMAP_CUBE'
			];

			const envmap = parseUint8( dataView, offset );

			return envmaps[ envmap ];

		}

		function parseTiledesc( dataView, offset ) {

			const levelModes = [
				'ONE_LEVEL',
				'MIPMAP_LEVELS',
				'RIPMAP_LEVELS',
			];

			const roundingModes = [
				'ROUND_DOWN',
				'ROUND_UP',
			];

			const xSize = parseUint32( dataView, offset );
			const ySize = parseUint32( dataView, offset );
			const modes = parseUint8( dataView, offset );

			return {
				xSize: xSize,
				ySize: ySize,
				levelMode: levelModes[ modes & 0xf ],
				roundingMode: roundingModes[ modes >> 4 ]
			};

		}

		function parseV2f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );

			return [ x, y ];

		}

		function parseV3f( dataView, offset ) {

			const x = parseFloat32( dataView, offset );
			const y = parseFloat32( dataView, offset );
			const z = parseFloat32( dataView, offset );

			return [ x, y, z ];

		}

		function parseValue( dataView, buffer, offset, type, size ) {

			if ( type === 'string' || type === 'stringvector' || type === 'iccProfile' ) {

				return parseFixedLengthString( buffer, offset, size );

			} else if ( type === 'chlist' ) {

				return parseChlist( dataView, buffer, offset, size );

			} else if ( type === 'chromaticities' ) {

				return parseChromaticities( dataView, offset );

			} else if ( type === 'compression' ) {

				return parseCompression( dataView, offset );

			} else if ( type === 'box2i' ) {

				return parseBox2i( dataView, offset );

			} else if ( type === 'envmap' ) {

				return parseEnvmap( dataView, offset );

			} else if ( type === 'tiledesc' ) {

				return parseTiledesc( dataView, offset );

			} else if ( type === 'lineOrder' ) {

				return parseLineOrder( dataView, offset );

			} else if ( type === 'float' ) {

				return parseFloat32( dataView, offset );

			} else if ( type === 'v2f' ) {

				return parseV2f( dataView, offset );

			} else if ( type === 'v3f' ) {

				return parseV3f( dataView, offset );

			} else if ( type === 'int' ) {

				return parseInt32( dataView, offset );

			} else if ( type === 'rational' ) {

				return parseRational( dataView, offset );

			} else if ( type === 'timecode' ) {

				return parseTimecode( dataView, offset );

			} else if ( type === 'preview' ) {

				offset.value += size;
				return 'skipped';

			} else {

				offset.value += size;
				return undefined;

			}

		}

		function roundLog2( x, mode ) {

			const log2 = Math.log2( x );
			return mode == 'ROUND_DOWN' ? Math.floor( log2 ) : Math.ceil( log2 );

		}

		function calculateTileLevels( tiledesc, w, h ) {

			let num = 0;

			switch ( tiledesc.levelMode ) {

				case 'ONE_LEVEL':
					num = 1;
					break;

				case 'MIPMAP_LEVELS':
					num = roundLog2( Math.max( w, h ), tiledesc.roundingMode ) + 1;
					break;

				case 'RIPMAP_LEVELS':
					throw new Error( 'THREE.EXRLoader: RIPMAP_LEVELS tiles currently unsupported.' );

			}

			return num;

		}

		function calculateTiles( count, dataSize, size, roundingMode ) {

			const tiles = new Array( count );

			for ( let i = 0; i < count; i ++ ) {

				const b = ( 1 << i );
				let s = ( dataSize / b ) | 0;

				if ( roundingMode == 'ROUND_UP' && s * b < dataSize ) s += 1;

				const l = Math.max( s, 1 );

				tiles[ i ] = ( ( l + size - 1 ) / size ) | 0;

			}

			return tiles;

		}

		function parseTiles() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let tile = 0; tile < EXRDecoder.tileCount; tile ++ ) {

				const tileX = parseInt32( EXRDecoder.viewer, offset );
				const tileY = parseInt32( EXRDecoder.viewer, offset );
				offset.value += 8; // skip levels - only parsing top-level
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset );

				const startX = tileX * EXRDecoder.blockWidth;
				const startY = tileY * EXRDecoder.blockHeight;
				EXRDecoder.columns = ( startX + EXRDecoder.blockWidth > EXRDecoder.width ) ? EXRDecoder.width - startX : EXRDecoder.blockWidth;
				EXRDecoder.lines = ( startY + EXRDecoder.blockHeight > EXRDecoder.height ) ? EXRDecoder.height - startY : EXRDecoder.blockHeight;

				const bytesBlockLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesBlockLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line = 0; line < EXRDecoder.lines; line ++ ) {

					const lineOffset = line * EXRDecoder.columns * EXRDecoder.totalBytes;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;
						const outLineOffset = ( EXRDecoder.height - ( 1 + startY + line ) ) * EXRDecoder.outLineWidth;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + ( x + startX ) * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}

		function parseScanline() {

			const EXRDecoder = this;
			const offset = EXRDecoder.offset;
			const tmpOffset = { value: 0 };

			for ( let scanlineBlockIdx = 0; scanlineBlockIdx < EXRDecoder.height / EXRDecoder.blockHeight; scanlineBlockIdx ++ ) {

				const line = parseInt32( EXRDecoder.viewer, offset ) - EXRHeader.dataWindow.yMin; // line_no
				EXRDecoder.size = parseUint32( EXRDecoder.viewer, offset ); // data_len
				EXRDecoder.lines = ( ( line + EXRDecoder.blockHeight > EXRDecoder.height ) ? ( EXRDecoder.height - line ) : EXRDecoder.blockHeight );

				const bytesPerLine = EXRDecoder.columns * EXRDecoder.totalBytes;
				const isCompressed = EXRDecoder.size < EXRDecoder.lines * bytesPerLine;
				const viewer = isCompressed ? EXRDecoder.uncompress( EXRDecoder ) : uncompressRAW( EXRDecoder );

				offset.value += EXRDecoder.size;

				for ( let line_y = 0; line_y < EXRDecoder.blockHeight; line_y ++ ) {

					const scan_y = scanlineBlockIdx * EXRDecoder.blockHeight;
					const true_y = line_y + EXRDecoder.scanOrder( scan_y );
					if ( true_y >= EXRDecoder.height ) continue;

					const lineOffset = line_y * bytesPerLine;
					const outLineOffset = ( EXRDecoder.height - 1 - true_y ) * EXRDecoder.outLineWidth;

					for ( let channelID = 0; channelID < EXRDecoder.inputChannels.length; channelID ++ ) {

						const name = EXRHeader.channels[ channelID ].name;
						const lOff = EXRDecoder.channelByteOffsets[ name ] * EXRDecoder.columns;
						const cOff = EXRDecoder.decodeChannels[ name ];

						if ( cOff === undefined ) continue;

						tmpOffset.value = lineOffset + lOff;

						for ( let x = 0; x < EXRDecoder.columns; x ++ ) {

							const outIndex = outLineOffset + x * EXRDecoder.outputChannels + cOff;
							EXRDecoder.byteArray[ outIndex ] = EXRDecoder.getter( viewer, tmpOffset );

						}

					}

				}

			}

		}

		function parseHeader( dataView, buffer, offset ) {

			const EXRHeader = {};

			if ( dataView.getUint32( 0, true ) != 20000630 ) { // magic

				throw new Error( 'THREE.EXRLoader: Provided file doesn\'t appear to be in OpenEXR format.' );

			}

			EXRHeader.version = dataView.getUint8( 4 );

			const spec = dataView.getUint8( 5 ); // fullMask

			EXRHeader.spec = {
				singleTile: !! ( spec & 2 ),
				longName: !! ( spec & 4 ),
				deepFormat: !! ( spec & 8 ),
				multiPart: !! ( spec & 16 ),
			};

			// start of header

			offset.value = 8; // start at 8 - after pre-amble

			let keepReading = true;

			while ( keepReading ) {

				const attributeName = parseNullTerminatedString( buffer, offset );

				if ( attributeName === '' ) {

					keepReading = false;

				} else {

					const attributeType = parseNullTerminatedString( buffer, offset );
					const attributeSize = parseUint32( dataView, offset );
					const attributeValue = parseValue( dataView, buffer, offset, attributeType, attributeSize );

					if ( attributeValue === undefined ) {

						console.warn( `THREE.EXRLoader: Skipped unknown header attribute type \'${attributeType}\'.` );

					} else {

						EXRHeader[ attributeName ] = attributeValue;

					}

				}

			}

			if ( ( spec & ~ 0x06 ) != 0 ) { // unsupported deep-image, multi-part

				console.error( 'THREE.EXRHeader:', EXRHeader );
				throw new Error( 'THREE.EXRLoader: Provided file is currently unsupported.' );

			}

			return EXRHeader;

		}

		function setupDecoder( EXRHeader, dataView, uInt8Array, offset, outputType, outputFormat ) {

			const EXRDecoder = {
				size: 0,
				viewer: dataView,
				array: uInt8Array,
				offset: offset,
				width: EXRHeader.dataWindow.xMax - EXRHeader.dataWindow.xMin + 1,
				height: EXRHeader.dataWindow.yMax - EXRHeader.dataWindow.yMin + 1,
				inputChannels: EXRHeader.channels,
				channelByteOffsets: {},
				shouldExpand: false,
				scanOrder: null,
				totalBytes: null,
				columns: null,
				lines: null,
				type: null,
				uncompress: null,
				getter: null,
				format: null,
				colorSpace: LinearSRGBColorSpace,
			};

			switch ( EXRHeader.compression ) {

				case 'NO_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRAW;
					break;

				case 'RLE_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressRLE;
					break;

				case 'ZIPS_COMPRESSION':
					EXRDecoder.blockHeight = 1;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'ZIP_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressZIP;
					break;

				case 'PIZ_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressPIZ;
					break;

				case 'PXR24_COMPRESSION':
					EXRDecoder.blockHeight = 16;
					EXRDecoder.uncompress = uncompressPXR;
					break;

				case 'DWAA_COMPRESSION':
					EXRDecoder.blockHeight = 32;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				case 'DWAB_COMPRESSION':
					EXRDecoder.blockHeight = 256;
					EXRDecoder.uncompress = uncompressDWA;
					break;

				default:
					throw new Error( 'EXRLoader.parse: ' + EXRHeader.compression + ' is unsupported' );

			}

			const channels = {};
			for ( const channel of EXRHeader.channels ) {

				switch ( channel.name ) {

					case 'Y':
					case 'R':
					case 'G':
					case 'B':
					case 'A':
						channels[ channel.name ] = true;
						EXRDecoder.type = channel.pixelType;

				}

			}

			// RGB images will be converted to RGBA format, preventing software emulation in select devices.
			let fillAlpha = false;
			let invalidOutput = false;

			// Validate if input texture contain supported channels
			if ( channels.R && channels.G && channels.B ) {

				EXRDecoder.outputChannels = 4;

			} else if ( channels.Y ) {

				EXRDecoder.outputChannels = 1;

			} else {

				throw new Error( 'EXRLoader.parse: file contains unsupported data channels.' );

			}

			// Setup output texture configuration
			switch ( EXRDecoder.outputChannels ) {

				case 4:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = ! channels.A;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.decodeChannels = { R: 0, G: 1, B: 2, A: 3 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.decodeChannels = { R: 0, G: 1 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { R: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				case 1:

					if ( outputFormat == RGBAFormat ) {

						fillAlpha = true;
						EXRDecoder.format = RGBAFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 4;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RGFormat ) {

						EXRDecoder.format = RGFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 2;
						EXRDecoder.shouldExpand = true;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else if ( outputFormat == RedFormat ) {

						EXRDecoder.format = RedFormat;
						EXRDecoder.colorSpace = LinearSRGBColorSpace;
						EXRDecoder.outputChannels = 1;
						EXRDecoder.decodeChannels = { Y: 0 };

					} else  {

						invalidOutput = true;

					}

					break;

				default:

					invalidOutput = true;

			}

			if (invalidOutput) throw new Error( 'EXRLoader.parse: invalid output format for specified file.' );

			if ( EXRDecoder.type == 1 ) {

				// half
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat16;
						break;

					case HalfFloatType:
						EXRDecoder.getter = parseUint16;
						break;

				}

			} else if ( EXRDecoder.type == 2 ) {

				// float
				switch ( outputType ) {

					case FloatType:
						EXRDecoder.getter = parseFloat32;
						break;

					case HalfFloatType:
						EXRDecoder.getter = decodeFloat32;

				}

			} else {

				throw new Error( 'EXRLoader.parse: unsupported pixelType ' + EXRDecoder.type + ' for ' + EXRHeader.compression + '.' );

			}

			EXRDecoder.columns = EXRDecoder.width;
			const size = EXRDecoder.width * EXRDecoder.height * EXRDecoder.outputChannels;

			switch ( outputType ) {

				case FloatType:
					EXRDecoder.byteArray = new Float32Array( size );

					// Fill initially with 1s for the alpha value if the texture is not RGBA, RGB values will be overwritten
					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 1, 0, size );

					break;

				case HalfFloatType:
					EXRDecoder.byteArray = new Uint16Array( size );

					if ( fillAlpha )
						EXRDecoder.byteArray.fill( 0x3C00, 0, size ); // Uint16Array holds half float data, 0x3C00 is 1

					break;

				default:
					console.error( 'THREE.EXRLoader: unsupported type: ', outputType );
					break;

			}

			let byteOffset = 0;
			for ( const channel of EXRHeader.channels ) {

				if ( EXRDecoder.decodeChannels[ channel.name ] !== undefined ) {

					EXRDecoder.channelByteOffsets[ channel.name ] = byteOffset;

				}

				byteOffset += channel.pixelType * 2;

			}

			EXRDecoder.totalBytes = byteOffset;
			EXRDecoder.outLineWidth = EXRDecoder.width * EXRDecoder.outputChannels;

			if ( EXRHeader.lineOrder === 'INCREASING_Y' ) {

				EXRDecoder.scanOrder = ( y ) => y;

			} else {

				EXRDecoder.scanOrder = ( y ) => EXRDecoder.height - 1 - y;

			}

			if ( EXRHeader.spec.singleTile ) {

				EXRDecoder.blockHeight = EXRHeader.tiles.ySize;
				EXRDecoder.blockWidth = EXRHeader.tiles.xSize;

				const numXLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );
				// const numYLevels = calculateTileLevels( EXRHeader.tiles, EXRDecoder.width, EXRDecoder.height );

				const numXTiles = calculateTiles( numXLevels, EXRDecoder.width, EXRHeader.tiles.xSize, EXRHeader.tiles.roundingMode );
				const numYTiles = calculateTiles( numXLevels, EXRDecoder.height, EXRHeader.tiles.ySize, EXRHeader.tiles.roundingMode );

				EXRDecoder.tileCount = numXTiles[ 0 ] * numYTiles[ 0 ];

				for ( let l = 0; l < numXLevels; l ++ )
					for ( let y = 0; y < numYTiles[ l ]; y ++ )
						for ( let x = 0; x < numXTiles[ l ]; x ++ )
							parseInt64( dataView, offset ); // tileOffset

				EXRDecoder.decode = parseTiles.bind( EXRDecoder );

			} else {

				EXRDecoder.blockWidth = EXRDecoder.width;
				const blockCount = Math.ceil( EXRDecoder.height / EXRDecoder.blockHeight );

				for ( let i = 0; i < blockCount; i ++ )
					parseInt64( dataView, offset ); // scanlineOffset

				EXRDecoder.decode = parseScanline.bind( EXRDecoder );

			}

			return EXRDecoder;

		}

		// start parsing file [START]
		const offset = { value: 0 };
		const bufferDataView = new DataView( buffer );
		const uInt8Array = new Uint8Array( buffer );

		// get header information and validate format.
		const EXRHeader = parseHeader( bufferDataView, buffer, offset );

		// get input compression information and prepare decoding.
		const EXRDecoder = setupDecoder( EXRHeader, bufferDataView, uInt8Array, offset, this.type, this.outputFormat );

		// parse input data
		EXRDecoder.decode();

		// output texture post-processing
		if ( EXRDecoder.shouldExpand ) {

			const byteArray = EXRDecoder.byteArray;

			if ( this.outputFormat == RGBAFormat ) {

				for ( let i = 0; i < byteArray.length; i += 4 )
					byteArray [i + 2 ] = ( byteArray [ i + 1 ] = byteArray[ i ] );

			} else if ( this.outputFormat == RGFormat ) {

				for ( let i = 0; i < byteArray.length; i += 2 )
					byteArray [ i + 1 ] = byteArray[ i ] ;

			}

		}

		return {
			header: EXRHeader,
			width: EXRDecoder.width,
			height: EXRDecoder.height,
			data: EXRDecoder.byteArray,
			format: EXRDecoder.format,
			colorSpace: EXRDecoder.colorSpace,
			type: this.type,
		};

	}
```
</details>

##### `setDataType(value: any): EXRLoader`

<details><summary>Code</summary>

```ts
setDataType( value ) {

		this.type = value;
		return this;

	}
```
</details>

##### `setOutputFormat(value: any): EXRLoader`

<details><summary>Code</summary>

```ts
setOutputFormat( value ) {

		this.outputFormat = value;
		return this;

	}
```
</details>

##### `load(url: any, onLoad: any, onProgress: any, onError: any): any`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		function onLoadCallback( texture, texData ) {

			texture.colorSpace = texData.colorSpace;
			texture.minFilter = LinearFilter;
			texture.magFilter = LinearFilter;
			texture.generateMipmaps = false;
			texture.flipY = false;

			if ( onLoad ) onLoad( texture, texData );

		}

		return super.load( url, onLoadCallback, onProgress, onError );

	}
```
</details>


---