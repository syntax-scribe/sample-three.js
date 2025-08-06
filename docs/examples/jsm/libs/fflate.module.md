[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `fflate.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 202 |
| 📊 Variables & Constants | 375 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/fflate.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ch2` | `{}` | let/var | `{}` | ✗ |
| `w` | `Worker` | let/var | `new Worker(ch2[id] \|\| (ch2[id] = URL.createObjectURL(new Blob([ c + ';addEv...` | ✗ |
| `d` | `any` | let/var | `e.data` | ✗ |
| `ed` | `any` | let/var | `d.$e$` | ✗ |
| `err` | `Error` | let/var | `new Error(ed[0])` | ✗ |
| `wk` | `(c: any, id: any, msg: any, transfer:...` | let/var | `(function (c, id, msg, transfer, cb) { var w = new Worker(ch2[id] \|\| (ch2[i...` | ✗ |
| `u8` | `Uint8ArrayConstructor` | let/var | `Uint8Array` | ✗ |
| `u16` | `Uint16ArrayConstructor` | let/var | `Uint16Array` | ✗ |
| `i32` | `Int32ArrayConstructor` | let/var | `Int32Array` | ✗ |
| `fleb` | `Uint8Array<ArrayBuffer>` | let/var | `new u8([0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 4, 4, 4, ...` | ✗ |
| `fdeb` | `Uint8Array<ArrayBuffer>` | let/var | `new u8([0, 0, 0, 0, 1, 1, 2, 2, 3, 3, 4, 4, 5, 5, 6, 6, 7, 7, 8, 8, 9, 9, 10,...` | ✗ |
| `clim` | `Uint8Array<ArrayBuffer>` | let/var | `new u8([16, 17, 18, 0, 8, 7, 9, 6, 10, 5, 11, 4, 12, 3, 13, 2, 14, 1, 15])` | ✗ |
| `b` | `Uint16Array<ArrayBuffer>` | let/var | `new u16(31)` | ✗ |
| `r` | `Int32Array<ArrayBuffer>` | let/var | `new i32(b[30])` | ✗ |
| `fl` | `Uint16Array<ArrayBuffer>` | let/var | `_a.b` | ✗ |
| `revfl` | `Int32Array<ArrayBuffer>` | let/var | `_a.r` | ✗ |
| `fd` | `Uint16Array<ArrayBuffer>` | let/var | `_b.b` | ✗ |
| `revfd` | `Int32Array<ArrayBuffer>` | let/var | `_b.r` | ✗ |
| `rev` | `Uint16Array<ArrayBuffer>` | let/var | `new u16(32768)` | ✗ |
| `x` | `number` | let/var | `((i & 0xAAAA) >> 1) \| ((i & 0x5555) << 1)` | ✗ |
| `s` | `any` | let/var | `cd.length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `l` | `Uint16Array<any>` | let/var | `new u16(mb)` | ✗ |
| `le` | `Uint16Array<any>` | let/var | `new u16(mb)` | ✗ |
| `co` | `any` | let/var | `*not shown*` | ✗ |
| `rvb` | `number` | let/var | `15 - mb` | ✗ |
| `sv` | `number` | let/var | `(i << 4) \| cd[i]` | ✗ |
| `r_1` | `number` | let/var | `mb - cd[i]` | ✗ |
| `v` | `number` | let/var | `le[cd[i] - 1]++ << r_1` | ✗ |
| `hMap` | `(cd: any, mb: any, r: any) => Uint16A...` | let/var | `(function (cd, mb, r) { var s = cd.length; // index var i = 0; // u16 "map": ...` | ✗ |
| `flt` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(288)` | ✗ |
| `fdt` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(32)` | ✗ |
| `m` | `any` | let/var | `a[0]` | ✗ |
| `o` | `number` | let/var | `(p / 8) \| 0` | ✗ |
| `o` | `number` | let/var | `(p / 8) \| 0` | ✗ |
| `FlateErrorCode` | `{ UnexpectedEOF: number; InvalidBlock...` | let/var | `{ UnexpectedEOF: 0, InvalidBlockType: 1, InvalidLengthLiteral: 2, InvalidDist...` | ✓ |
| `ec` | `string[]` | let/var | `[ 'unexpected EOF', 'invalid block type', 'invalid length/literal', 'invalid ...` | ✗ |
| `e` | `Error` | let/var | `new Error(msg \|\| ec[ind])` | ✗ |
| `sl` | `any` | let/var | `dat.length` | ✗ |
| `dl` | `any` | let/var | `dict ? dict.length : 0` | ✗ |
| `noBuf` | `boolean` | let/var | `!buf` | ✗ |
| `resize` | `boolean` | let/var | `noBuf \|\| st.i != 2` | ✗ |
| `noSt` | `any` | let/var | `st.i` | ✗ |
| `bl` | `any` | let/var | `buf.length` | ✗ |
| `nbuf` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(Math.max(bl * 2, l))` | ✗ |
| `final` | `any` | let/var | `st.f \|\| 0` | ✗ |
| `pos` | `any` | let/var | `st.p \|\| 0` | ✗ |
| `bt` | `any` | let/var | `st.b \|\| 0` | ✗ |
| `lm` | `any` | let/var | `st.l` | ✗ |
| `dm` | `any` | let/var | `st.d` | ✗ |
| `lbt` | `any` | let/var | `st.m` | ✗ |
| `dbt` | `any` | let/var | `st.n` | ✗ |
| `tbts` | `number` | let/var | `sl * 8` | ✗ |
| `s` | `number` | let/var | `shft(pos) + 4` | ✗ |
| `l` | `number` | let/var | `dat[s - 4] \| (dat[s - 3] << 8)` | ✗ |
| `t` | `number` | let/var | `s + l` | ✗ |
| `hLit` | `number` | let/var | `bits(dat, pos, 31) + 257` | ✗ |
| `hcLen` | `number` | let/var | `bits(dat, pos + 10, 15) + 4` | ✗ |
| `tl` | `number` | let/var | `hLit + bits(dat, pos + 5, 31) + 1` | ✗ |
| `ldt` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(tl)` | ✗ |
| `clt` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(19)` | ✗ |
| `clbmsk` | `number` | let/var | `(1 << clb) - 1` | ✗ |
| `r` | `number` | let/var | `clm[bits(dat, pos, clbmsk)]` | ✗ |
| `c` | `number` | let/var | `0` | ✗ |
| `n` | `number` | let/var | `0` | ✗ |
| `lms` | `number` | let/var | `(1 << lbt) - 1` | ✗ |
| `dms` | `number` | let/var | `(1 << dbt) - 1` | ✗ |
| `lpos` | `any` | let/var | `pos` | ✗ |
| `sym` | `number` | let/var | `c >> 4` | ✗ |
| `add` | `number` | let/var | `sym - 254` | ✗ |
| `i` | `number` | let/var | `sym - 257` | ✗ |
| `b` | `number` | let/var | `fleb[i]` | ✗ |
| `d` | `any` | let/var | `dm[bits16(dat, pos) & dms]` | ✗ |
| `dsym` | `number` | let/var | `d >> 4` | ✗ |
| `end` | `any` | let/var | `bt + add` | ✗ |
| `shift` | `number` | let/var | `dl - dt` | ✗ |
| `o` | `number` | let/var | `(p / 8) \| 0` | ✗ |
| `o` | `number` | let/var | `(p / 8) \| 0` | ✗ |
| `t` | `any[]` | let/var | `[]` | ✗ |
| `s` | `number` | let/var | `t.length` | ✗ |
| `v` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(t[0].s + 1)` | ✗ |
| `l` | `{ s: number; f: any; }` | let/var | `t[0]` | ✗ |
| `r` | `{ s: number; f: any; }` | let/var | `t[1]` | ✗ |
| `i0` | `number` | let/var | `0` | ✗ |
| `i1` | `number` | let/var | `1` | ✗ |
| `i2` | `number` | let/var | `2` | ✗ |
| `maxSym` | `number` | let/var | `t2[0].s` | ✗ |
| `tr` | `Uint16Array<ArrayBuffer>` | let/var | `new u16(maxSym + 1)` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `dt` | `number` | let/var | `0` | ✗ |
| `lft` | `number` | let/var | `mbt - mb` | ✗ |
| `cst` | `number` | let/var | `1 << lft` | ✗ |
| `i2_1` | `number` | let/var | `t2[i].s` | ✗ |
| `i2_2` | `number` | let/var | `t2[i].s` | ✗ |
| `i2_3` | `number` | let/var | `t2[i].s` | ✗ |
| `s` | `any` | let/var | `c.length` | ✗ |
| `cl` | `Uint16Array<ArrayBuffer>` | let/var | `new u16(++s)` | ✗ |
| `cli` | `number` | let/var | `0` | ✗ |
| `cln` | `any` | let/var | `c[0]` | ✗ |
| `cls` | `number` | let/var | `1` | ✗ |
| `l` | `number` | let/var | `0` | ✗ |
| `s` | `any` | let/var | `dat.length` | ✗ |
| `dlt` | `Uint8Array<ArrayBuffer>` | let/var | `_a.t` | ✗ |
| `mlb` | `any` | let/var | `_a.l` | ✗ |
| `ddt` | `Uint8Array<ArrayBuffer>` | let/var | `_b.t` | ✗ |
| `mdb` | `any` | let/var | `_b.l` | ✗ |
| `lclt` | `Uint16Array<ArrayBuffer>` | let/var | `_c.c` | ✗ |
| `nlc` | `any` | let/var | `_c.n` | ✗ |
| `lcdt` | `Uint16Array<ArrayBuffer>` | let/var | `_d.c` | ✗ |
| `ndc` | `any` | let/var | `_d.n` | ✗ |
| `lcfreq` | `Uint16Array<ArrayBuffer>` | let/var | `new u16(19)` | ✗ |
| `lct` | `Uint8Array<ArrayBuffer>` | let/var | `_e.t` | ✗ |
| `mlcb` | `any` | let/var | `_e.l` | ✗ |
| `nlcc` | `number` | let/var | `19` | ✗ |
| `flen` | `number` | let/var | `(bl + 5) << 3` | ✗ |
| `ftlen` | `any` | let/var | `clen(lf, flt) + clen(df, fdt) + eb` | ✗ |
| `dtlen` | `any` | let/var | `clen(lf, dlt) + clen(df, ddt) + eb + 14 + 3 * nlcc + clen(lcfreq, lct) + 2 * ...` | ✗ |
| `lm` | `any` | let/var | `*not shown*` | ✗ |
| `ll` | `any` | let/var | `*not shown*` | ✗ |
| `dm` | `any` | let/var | `*not shown*` | ✗ |
| `dl` | `any` | let/var | `*not shown*` | ✗ |
| `lcts` | `Uint16Array<ArrayBuffer>[]` | let/var | `[lclt, lcdt]` | ✗ |
| `clct` | `Uint16Array<ArrayBuffer>` | let/var | `lcts[it]` | ✗ |
| `len` | `number` | let/var | `clct[i] & 31` | ✗ |
| `sym` | `any` | let/var | `syms[i]` | ✗ |
| `dst` | `number` | let/var | `sym & 31` | ✗ |
| `deo` | `Int32Array<ArrayBuffer>` | let/var | `new i32([65540, 131080, 131088, 131104, 262176, 1048704, 1048832, 2114560, 21...` | ✗ |
| `et` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(0)` | ✗ |
| `s` | `any` | let/var | `st.z \|\| dat.length` | ✗ |
| `o` | `Uint8Array<any>` | let/var | `new u8(pre + s + 5 * (1 + Math.ceil(s / 7000)) + post)` | ✗ |
| `lst` | `any` | let/var | `st.l` | ✗ |
| `pos` | `number` | let/var | `(st.r \|\| 0) & 7` | ✗ |
| `opt` | `number` | let/var | `deo[lvl - 1]` | ✗ |
| `n` | `number` | let/var | `opt >> 13` | ✗ |
| `c` | `number` | let/var | `opt & 8191` | ✗ |
| `msk_1` | `number` | let/var | `(1 << plvl) - 1` | ✗ |
| `prev` | `any` | let/var | `st.p \|\| new u16(32768)` | ✗ |
| `head` | `any` | let/var | `st.h \|\| new u16(msk_1 + 1)` | ✗ |
| `bs2_1` | `number` | let/var | `2 * bs1_1` | ✗ |
| `syms` | `Int32Array<ArrayBuffer>` | let/var | `new i32(25000)` | ✗ |
| `lf` | `Uint16Array<ArrayBuffer>` | let/var | `new u16(288)` | ✗ |
| `df` | `Uint16Array<ArrayBuffer>` | let/var | `new u16(32)` | ✗ |
| `lc_1` | `number` | let/var | `0` | ✗ |
| `eb` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `st.i \|\| 0` | ✗ |
| `li` | `number` | let/var | `0` | ✗ |
| `wi` | `any` | let/var | `st.w \|\| 0` | ✗ |
| `bs` | `number` | let/var | `0` | ✗ |
| `imod` | `number` | let/var | `i & 32767` | ✗ |
| `pimod` | `any` | let/var | `head[hv]` | ✗ |
| `rem` | `number` | let/var | `s - i` | ✗ |
| `l` | `number` | let/var | `2` | ✗ |
| `d` | `number` | let/var | `0` | ✗ |
| `ch_1` | `number` | let/var | `c` | ✗ |
| `dif` | `number` | let/var | `imod - pimod & 32767` | ✗ |
| `maxn` | `number` | let/var | `Math.min(n, rem) - 1` | ✗ |
| `nl` | `number` | let/var | `0` | ✗ |
| `md` | `number` | let/var | `0` | ✗ |
| `ti` | `number` | let/var | `i - dif + j & 32767` | ✗ |
| `pti` | `any` | let/var | `prev[ti]` | ✗ |
| `cd` | `number` | let/var | `ti - pti & 32767` | ✗ |
| `lin` | `number` | let/var | `revfl[l] & 31` | ✗ |
| `din` | `number` | let/var | `revfd[d] & 31` | ✗ |
| `e` | `any` | let/var | `i + 65535` | ✗ |
| `t` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array(256)` | ✗ |
| `c` | `number` | let/var | `i` | ✗ |
| `k` | `number` | let/var | `9` | ✗ |
| `c` | `number` | let/var | `-1` | ✗ |
| `cr` | `number` | let/var | `c` | ✗ |
| `a` | `number` | let/var | `1` | ✗ |
| `b` | `number` | let/var | `0` | ✗ |
| `n` | `number` | let/var | `a` | ✗ |
| `m` | `number` | let/var | `b` | ✗ |
| `l` | `number` | let/var | `d.length \| 0` | ✗ |
| `newDat` | `Uint8Array<any>` | let/var | `new u8(dict.length + dat.length)` | ✗ |
| `o` | `{}` | let/var | `{}` | ✗ |
| `v` | `any` | let/var | `dt[i]` | ✗ |
| `k` | `any` | let/var | `ks[i]` | ✗ |
| `spInd` | `any` | let/var | `st_1.indexOf(' ', 8) + 1` | ✗ |
| `ch` | `any[]` | let/var | `[]` | ✗ |
| `tl` | `any[]` | let/var | `[]` | ✗ |
| `fnStr` | `string` | let/var | `''` | ✗ |
| `td_1` | `{}` | let/var | `{}` | ✗ |
| `m` | `number` | let/var | `fns.length - 1` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `fn` | `any` | let/var | `o.filename` | ✗ |
| `flg` | `any` | let/var | `d[3]` | ✗ |
| `st` | `number` | let/var | `10` | ✗ |
| `l` | `any` | let/var | `d.length` | ✗ |
| `lv` | `any` | let/var | `o.level` | ✗ |
| `fl` | `number` | let/var | `lv == 0 ? 0 : lv < 6 ? 1 : lv == 9 ? 3 : 2` | ✗ |
| `endLen` | `any` | let/var | `chunk.length + this.s.z` | ✗ |
| `newBuf` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(endLen & -32768)` | ✗ |
| `split` | `number` | let/var | `this.b.length - this.s.z` | ✗ |
| `Deflate` | `typeof Deflate` | let/var | `(function () { function Deflate(opts, cb) { if (typeof opts == 'function') cb...` | ✗ |
| `strm` | `Deflate` | let/var | `new Deflate(ev.data)` | ✗ |
| `AsyncDeflate` | `(opts: any, cb: any) => void` | let/var | `(function () { function AsyncDeflate(opts, cb) { astrmify([ bDflt, function (...` | ✗ |
| `dict` | `any` | let/var | `opts && opts.dictionary && opts.dictionary.subarray(-32768)` | ✗ |
| `n` | `Uint8Array<any>` | let/var | `new u8(this.p.length + c.length)` | ✗ |
| `bts` | `any` | let/var | `this.s.b` | ✗ |
| `Inflate` | `typeof Inflate` | let/var | `(function () { function Inflate(opts, cb) { // no StrmOpt here to avoid addin...` | ✗ |
| `strm` | `Inflate` | let/var | `new Inflate(ev.data)` | ✗ |
| `AsyncInflate` | `(opts: any, cb: any) => void` | let/var | `(function () { function AsyncInflate(opts, cb) { astrmify([ bInflt, function ...` | ✗ |
| `Gzip` | `typeof Gzip` | let/var | `(function () { function Gzip(opts, cb) { this.c = crc(); this.l = 0; this.v =...` | ✗ |
| `strm` | `Gzip` | let/var | `new Gzip(ev.data)` | ✗ |
| `AsyncGzip` | `(opts: any, cb: any) => void` | let/var | `(function () { function AsyncGzip(opts, cb) { astrmify([ bDflt, gze, function...` | ✗ |
| `l` | `any` | let/var | `data.length` | ✗ |
| `s` | `number` | let/var | `d.length` | ✗ |
| `s` | `number` | let/var | `p.length > 3 ? gzs(p) : 4` | ✗ |
| `Gunzip` | `typeof Gunzip` | let/var | `(function () { function Gunzip(opts, cb) { this.v = 1; this.r = 0; Inflate.ca...` | ✗ |
| `_this` | `any` | let/var | `this` | ✗ |
| `strm` | `Gunzip` | let/var | `new Gunzip(ev.data)` | ✗ |
| `AsyncGunzip` | `(opts: any, cb: any) => void` | let/var | `(function () { function AsyncGunzip(opts, cb) { var _this = this; astrmify([ ...` | ✗ |
| `Zlib` | `typeof Zlib` | let/var | `(function () { function Zlib(opts, cb) { this.c = adler(); this.v = 1; Deflat...` | ✗ |
| `strm` | `Zlib` | let/var | `new Zlib(ev.data)` | ✗ |
| `AsyncZlib` | `(opts: any, cb: any) => void` | let/var | `(function () { function AsyncZlib(opts, cb) { astrmify([ bDflt, zle, function...` | ✗ |
| `Unzlib` | `typeof Unzlib` | let/var | `(function () { function Unzlib(opts, cb) { Inflate.call(this, opts, cb); this...` | ✗ |
| `strm` | `Unzlib` | let/var | `new Unzlib(ev.data)` | ✗ |
| `AsyncUnzlib` | `(opts: any, cb: any) => void` | let/var | `(function () { function AsyncUnzlib(opts, cb) { astrmify([ bInflt, zule, func...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `n` | `Uint8Array<any>` | let/var | `new u8(this.p.length + chunk.length)` | ✗ |
| `Decompress` | `typeof Decompress` | let/var | `(function () { function Decompress(opts, cb) { this.o = StrmOpt.call(this, op...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `AsyncDecompress` | `typeof AsyncDecompress` | let/var | `(function () { function AsyncDecompress(opts, cb) { Decompress.call(this, opt...` | ✗ |
| `val` | `any` | let/var | `d[k]` | ✗ |
| `n` | `string` | let/var | `p + k` | ✗ |
| `op` | `any` | let/var | `o` | ✗ |
| `te` | `TextEncoder` | let/var | `typeof TextEncoder != 'undefined' && /*#__PURE__*/ new TextEncoder()` | ✗ |
| `td` | `TextDecoder` | let/var | `typeof TextDecoder != 'undefined' && /*#__PURE__*/ new TextDecoder()` | ✗ |
| `tds` | `number` | let/var | `0` | ✗ |
| `c` | `any` | let/var | `d[i++]` | ✗ |
| `eb` | `any` | let/var | `(c > 127) + (c > 223) + (c > 239)` | ✗ |
| `dat` | `Uint8Array<any>` | let/var | `new u8(this.p.length + chunk.length)` | ✗ |
| `s` | `string` | let/var | `_a.s` | ✗ |
| `r` | `Uint8Array<any>` | let/var | `_a.r` | ✗ |
| `DecodeUTF8` | `typeof DecodeUTF8` | let/var | `(function () { /** * Creates a UTF-8 decoding stream * @param cb The callback...` | ✗ |
| `EncodeUTF8` | `typeof EncodeUTF8` | let/var | `(function () { /** * Creates a UTF-8 decoding stream * @param cb The callback...` | ✗ |
| `ar_1` | `Uint8Array<any>` | let/var | `new u8(str.length)` | ✗ |
| `l` | `any` | let/var | `str.length` | ✗ |
| `ar` | `Uint8Array<any>` | let/var | `new u8(str.length + (str.length >> 1))` | ✗ |
| `ai` | `number` | let/var | `0` | ✗ |
| `n` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(ai + 8 + ((l - i) << 1))` | ✗ |
| `r` | `string` | let/var | `''` | ✗ |
| `s` | `string` | let/var | `_a.s` | ✗ |
| `es` | `any` | let/var | `b + 46 + fnl` | ✗ |
| `_a` | `number[]` | let/var | `z && bs == 4294967295 ? z64e(d, es) : [bs, b4(d, b + 24), b4(d, b + 42)]` | ✗ |
| `sc` | `number` | let/var | `_a[0]` | ✗ |
| `su` | `number` | let/var | `_a[1]` | ✗ |
| `off` | `number` | let/var | `_a[2]` | ✗ |
| `le` | `number` | let/var | `0` | ✗ |
| `l` | `any` | let/var | `ex[k].length` | ✗ |
| `fl` | `any` | let/var | `fn.length` | ✗ |
| `ex` | `any` | let/var | `f.extra` | ✗ |
| `col` | `any` | let/var | `co && co.length` | ✗ |
| `dt` | `Date` | let/var | `new Date(f.mtime == null ? Date.now() : f.mtime)` | ✗ |
| `y` | `number` | let/var | `dt.getFullYear() - 1980` | ✗ |
| `exf` | `any` | let/var | `ex[k]` | ✗ |
| `l` | `any` | let/var | `exf.length` | ✗ |
| `ZipPassThrough` | `typeof ZipPassThrough` | let/var | `(function () { /** * Creates a pass-through stream that can be added to ZIP a...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `ZipDeflate` | `typeof ZipDeflate` | let/var | `(function () { /** * Creates a DEFLATE stream that can be added to ZIP archiv...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `AsyncZipDeflate` | `typeof AsyncZipDeflate` | let/var | `(function () { /** * Creates an asynchronous DEFLATE stream that can be added...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `fl_1` | `number` | let/var | `f.length` | ✗ |
| `com` | `any` | let/var | `file.comment` | ✗ |
| `o` | `Uint8Array<any>` | let/var | `com && strToU8(com)` | ✗ |
| `u` | `boolean` | let/var | `fl_1 != file.filename.length \|\| (o && (com.length != o.length))` | ✗ |
| `hl_1` | `number` | let/var | `fl_1 + exfl(file.extra) + 30` | ✗ |
| `header` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(hl_1)` | ✗ |
| `chks_1` | `Uint8Array<ArrayBuffer>[]` | let/var | `[header]` | ✗ |
| `chk` | `Uint8Array<ArrayBuffer>` | let/var | `chks_2[_i]` | ✗ |
| `tr_1` | `number` | let/var | `this.d` | ✗ |
| `ind_1` | `number` | let/var | `this.u.length` | ✗ |
| `nxt` | `any` | let/var | `_this.u[ind_1 + 1]` | ✗ |
| `cl_1` | `number` | let/var | `0` | ✗ |
| `dd` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(16)` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `bt` | `number` | let/var | `0` | ✗ |
| `l` | `number` | let/var | `0` | ✗ |
| `tl` | `number` | let/var | `0` | ✗ |
| `f` | `any` | let/var | `_a[_i]` | ✗ |
| `out` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(tl + 22)` | ✗ |
| `f` | `any` | let/var | `_a[_i]` | ✗ |
| `Zip` | `typeof Zip` | let/var | `(function () { /** * Creates an empty ZIP archive to which files can be added...` | ✗ |
| `r` | `{}` | let/var | `{}` | ✗ |
| `lft` | `number` | let/var | `k.length` | ✗ |
| `o` | `number` | let/var | `0` | ✗ |
| `tot` | `number` | let/var | `0` | ✗ |
| `slft` | `number` | let/var | `lft` | ✗ |
| `files` | `any[]` | let/var | `new Array(lft)` | ✗ |
| `term` | `any[]` | let/var | `[]` | ✗ |
| `out` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(tot + 22)` | ✗ |
| `oe` | `number` | let/var | `o` | ✗ |
| `cdl` | `number` | let/var | `tot - o` | ✗ |
| `f` | `any` | let/var | `files[i]` | ✗ |
| `l` | `any` | let/var | `f.c.length` | ✗ |
| `badd` | `any` | let/var | `30 + f.f.length + exfl(f.extra)` | ✗ |
| `loc` | `any` | let/var | `tot + badd` | ✗ |
| `fn` | `string` | let/var | `k[i]` | ✗ |
| `_a` | `any` | let/var | `r[fn]` | ✗ |
| `file` | `any` | let/var | `_a[0]` | ✗ |
| `p` | `any` | let/var | `_a[1]` | ✗ |
| `size` | `any` | let/var | `file.length` | ✗ |
| `s` | `number` | let/var | `f.length` | ✗ |
| `com` | `any` | let/var | `p.comment` | ✗ |
| `m` | `Uint8Array<any>` | let/var | `com && strToU8(com)` | ✗ |
| `ms` | `number` | let/var | `m && m.length` | ✗ |
| `compression` | `number` | let/var | `p.level == 0 ? 0 : 8` | ✗ |
| `l` | `any` | let/var | `d.length` | ✗ |
| `r` | `{}` | let/var | `{}` | ✗ |
| `files` | `any[]` | let/var | `[]` | ✗ |
| `o` | `number` | let/var | `0` | ✗ |
| `tot` | `number` | let/var | `0` | ✗ |
| `_a` | `any` | let/var | `r[fn]` | ✗ |
| `file` | `any` | let/var | `_a[0]` | ✗ |
| `p` | `any` | let/var | `_a[1]` | ✗ |
| `compression` | `number` | let/var | `p.level == 0 ? 0 : 8` | ✗ |
| `s` | `number` | let/var | `f.length` | ✗ |
| `com` | `any` | let/var | `p.comment` | ✗ |
| `m` | `Uint8Array<any>` | let/var | `com && strToU8(com)` | ✗ |
| `ms` | `number` | let/var | `m && m.length` | ✗ |
| `d` | `any` | let/var | `compression ? deflateSync(file, p) : file` | ✗ |
| `l` | `any` | let/var | `d.length` | ✗ |
| `out` | `Uint8Array<ArrayBuffer>` | let/var | `new u8(tot + 22)` | ✗ |
| `oe` | `number` | let/var | `o` | ✗ |
| `cdl` | `number` | let/var | `tot - o` | ✗ |
| `badd` | `any` | let/var | `30 + f.f.length + exfl(f.extra)` | ✗ |
| `UnzipPassThrough` | `typeof UnzipPassThrough` | let/var | `(function () { function UnzipPassThrough() { } UnzipPassThrough.prototype.pus...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `UnzipInflate` | `typeof UnzipInflate` | let/var | `(function () { /** * Creates a DEFLATE decompression that can be used in ZIP ...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `AsyncUnzipInflate` | `typeof AsyncUnzipInflate` | let/var | `(function () { /** * Creates a DEFLATE decompression that can be used in ZIP ...` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `f` | `number` | let/var | `0` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `is` | `any` | let/var | `void 0` | ✗ |
| `buf` | `any` | let/var | `void 0` | ✗ |
| `l` | `any` | let/var | `buf.length` | ✗ |
| `oc` | `any` | let/var | `this.c` | ✗ |
| `add` | `any` | let/var | `oc && this.d` | ✗ |
| `_a` | `any` | let/var | `*not shown*` | ✗ |
| `u` | `number` | let/var | `bf & 2048` | ✗ |
| `dd` | `number` | let/var | `bf & 8` | ✗ |
| `chks_3` | `any[]` | let/var | `[]` | ✗ |
| `d_1` | `any` | let/var | `*not shown*` | ✗ |
| `ctr` | `any` | let/var | `_this.o[cmp_1]` | ✗ |
| `dat` | `any` | let/var | `chks_4[_i]` | ✗ |
| `file_1` | `{ name: string; compression: number; ...` | let/var | `{ name: fn_1, compression: cmp_1, start: function () { if (!file_1.ondata) er...` | ✗ |
| `this_1` | `this` | let/var | `this` | ✗ |
| `dat` | `any` | let/var | `f ? buf.subarray(0, is - 12 - (oc == -2 && 8) - (b4(buf, is - 16) == 0x8074B5...` | ✗ |
| `Unzip` | `typeof Unzip` | let/var | `(function () { /** * Creates a ZIP decompression stream * @param cb The callb...` | ✗ |
| `mt` | `typeof setTimeout \| { (callback: Voi...` | let/var | `typeof queueMicrotask == 'function' ? queueMicrotask : typeof setTimeout == '...` | ✗ |
| `term` | `any[]` | let/var | `[]` | ✗ |
| `files` | `{}` | let/var | `{}` | ✗ |
| `e` | `number` | let/var | `data.length - 22` | ✗ |
| `c` | `number` | let/var | `lft` | ✗ |
| `z` | `boolean` | let/var | `o == 4294967295 \|\| c == 65535` | ✗ |
| `fltr` | `any` | let/var | `opts && opts.filter` | ✗ |
| `c_1` | `any` | let/var | `_a[0]` | ✗ |
| `sc` | `any` | let/var | `_a[1]` | ✗ |
| `su` | `any` | let/var | `_a[2]` | ✗ |
| `fn` | `any` | let/var | `_a[3]` | ✗ |
| `no` | `any` | let/var | `_a[4]` | ✗ |
| `off` | `any` | let/var | `_a[5]` | ✗ |
| `files` | `{}` | let/var | `{}` | ✗ |
| `e` | `number` | let/var | `data.length - 22` | ✗ |
| `z` | `boolean` | let/var | `o == 4294967295 \|\| c == 65535` | ✗ |
| `fltr` | `any` | let/var | `opts && opts.filter` | ✗ |
| `c_2` | `any` | let/var | `_a[0]` | ✗ |
| `sc` | `any` | let/var | `_a[1]` | ✗ |
| `su` | `any` | let/var | `_a[2]` | ✗ |
| `fn` | `any` | let/var | `_a[3]` | ✗ |
| `no` | `any` | let/var | `_a[4]` | ✗ |
| `off` | `any` | let/var | `_a[5]` | ✗ |


---

## Functions

### `freb(eb: any, start: any): { b: Uint16Array<ArrayBuffer>; r: Int32Array<ArrayBuffer>; }`

**Parameters:**

- **`eb`** `any`
- **`start`** `any`

**Returns:** `{ b: Uint16Array<ArrayBuffer>; r: Int32Array<ArrayBuffer>; }`

**Internal Comments:**
```
// numbers here are at max 18 bits (x2)
```

<details><summary>Code</summary>

```typescript
function (eb, start) {
    var b = new u16(31);
    for (var i = 0; i < 31; ++i) {
        b[i] = start += 1 << eb[i - 1];
    }
    // numbers here are at max 18 bits
    var r = new i32(b[30]);
    for (var i = 1; i < 30; ++i) {
        for (var j = b[i]; j < b[i + 1]; ++j) {
            r[j] = ((j - b[i]) << 5) | i;
        }
    }
    return { b: b, r: r };
}
```
</details>

### `max(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (a) {
    var m = a[0];
    for (var i = 1; i < a.length; ++i) {
        if (a[i] > m)
            m = a[i];
    }
    return m;
}
```
</details>

### `bits(d: any, p: any, m: any): number`

**Parameters:**

- **`d`** `any`
- **`p`** `any`
- **`m`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (d, p, m) {
    var o = (p / 8) | 0;
    return ((d[o] | (d[o + 1] << 8)) >> (p & 7)) & m;
}
```
</details>

### `bits16(d: any, p: any): number`

**Parameters:**

- **`d`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (d, p) {
    var o = (p / 8) | 0;
    return ((d[o] | (d[o + 1] << 8) | (d[o + 2] << 16)) >> (p & 7));
}
```
</details>

### `shft(p: any): number`

**Parameters:**

- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (p) { return ((p + 7) / 8) | 0; }
```
</details>

### `slc(v: any, s: any, e: any): Uint8Array<any>`

**Parameters:**

- **`v`** `any`
- **`s`** `any`
- **`e`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `v.subarray`

**Internal Comments:**
```
// can't use .constructor in case user-supplied
```

<details><summary>Code</summary>

```typescript
function (v, s, e) {
    if (s == null || s < 0)
        s = 0;
    if (e == null || e > v.length)
        e = v.length;
    // can't use .constructor in case user-supplied
    return new u8(v.subarray(s, e));
}
```
</details>

### `err(ind: any, msg: any, nt: any): Error`

**Parameters:**

- **`ind`** `any`
- **`msg`** `any`
- **`nt`** `any`

**Returns:** `Error`

**Calls:**

- `Error.captureStackTrace`

<details><summary>Code</summary>

```typescript
function (ind, msg, nt) {
    var e = new Error(msg || ec[ind]);
    e.code = ind;
    if (Error.captureStackTrace)
        Error.captureStackTrace(e, err);
    if (!nt)
        throw e;
    return e;
}
```
</details>

### `inflt(dat: any, st: any, buf: any, dict: any): any`

**Parameters:**

- **`dat`** `any`
- **`st`** `any`
- **`buf`** `any`
- **`dict`** `any`

**Returns:** `any`

**Calls:**

- `Math.max`
- `nbuf.set`
- `bits`
- `shft`
- `err`
- `cbuf`
- `buf.set`
- `dat.subarray`
- `max`
- `hMap`
- `ldt.subarray`
- `bits16`
- `Math.min`
- `slc`
- `buf.subarray`

**Internal Comments:**
```
// source length       dict length (x2)
// have to estimate size (x2)
// no state (x2)
// Assumes roughly 33% compression ratio average
// ensure buffer can fit at least l elements (x2)
// need to increase size to fit
// Double or set to necessary, whichever is greater (x2)
//  last chunk         bitpos           bytes (x2)
// total bits (x2)
// BFINAL - this is only 1 when last chunk is next (x3)
// type: 0 = no compression, 1 = fixed huffman, 2 = dynamic huffman (x2)
// go to end of byte boundary (x2)
// ensure size
// Copy over uncompressed data (x4)
// Get new bitpos, update byte count (x6)
//  literal                            lengths (x2)
// length+distance tree (x2)
// code length tree (x2)
// use index map to get real code (x4)
// code lengths bits (x2)
// code lengths map (x2)
// bits read (x3)
// symbol (x2)
// code length to copy
//  copy   count (x2)
//    length tree                 distance tree (x2)
// max length bits (x3)
// max dist bits (x3)
// Make sure the buffer can hold this + the largest possible addition
// Maximum chunk size (practically, theoretically infinite) is 2^17
// bits read, code (x2)
// no extra bits needed if less
// index (x2)
// dist (x2)
// don't reallocate for streams or user buffers
```

<details><summary>Code</summary>

```typescript
function (dat, st, buf, dict) {
    // source length       dict length
    var sl = dat.length, dl = dict ? dict.length : 0;
    if (!sl || st.f && !st.l)
        return buf || new u8(0);
    var noBuf = !buf;
    // have to estimate size
    var resize = noBuf || st.i != 2;
    // no state
    var noSt = st.i;
    // Assumes roughly 33% compression ratio average
    if (noBuf)
        buf = new u8(sl * 3);
    // ensure buffer can fit at least l elements
    var cbuf = function (l) {
        var bl = buf.length;
        // need to increase size to fit
        if (l > bl) {
            // Double or set to necessary, whichever is greater
            var nbuf = new u8(Math.max(bl * 2, l));
            nbuf.set(buf);
            buf = nbuf;
        }
    };
    //  last chunk         bitpos           bytes
    var final = st.f || 0, pos = st.p || 0, bt = st.b || 0, lm = st.l, dm = st.d, lbt = st.m, dbt = st.n;
    // total bits
    var tbts = sl * 8;
    do {
        if (!lm) {
            // BFINAL - this is only 1 when last chunk is next
            final = bits(dat, pos, 1);
            // type: 0 = no compression, 1 = fixed huffman, 2 = dynamic huffman
            var type = bits(dat, pos + 1, 3);
            pos += 3;
            if (!type) {
                // go to end of byte boundary
                var s = shft(pos) + 4, l = dat[s - 4] | (dat[s - 3] << 8), t = s + l;
                if (t > sl) {
                    if (noSt)
                        err(0);
                    break;
                }
                // ensure size
                if (resize)
                    cbuf(bt + l);
                // Copy over uncompressed data
                buf.set(dat.subarray(s, t), bt);
                // Get new bitpos, update byte count
                st.b = bt += l, st.p = pos = t * 8, st.f = final;
                continue;
            }
            else if (type == 1)
                lm = flrm, dm = fdrm, lbt = 9, dbt = 5;
            else if (type == 2) {
                //  literal                            lengths
                var hLit = bits(dat, pos, 31) + 257, hcLen = bits(dat, pos + 10, 15) + 4;
                var tl = hLit + bits(dat, pos + 5, 31) + 1;
                pos += 14;
                // length+distance tree
                var ldt = new u8(tl);
                // code length tree
                var clt = new u8(19);
                for (var i = 0; i < hcLen; ++i) {
                    // use index map to get real code
                    clt[clim[i]] = bits(dat, pos + i * 3, 7);
                }
                pos += hcLen * 3;
                // code lengths bits
                var clb = max(clt), clbmsk = (1 << clb) - 1;
                // code lengths map
                var clm = hMap(clt, clb, 1);
                for (var i = 0; i < tl;) {
                    var r = clm[bits(dat, pos, clbmsk)];
                    // bits read
                    pos += r & 15;
                    // symbol
                    var s = r >> 4;
                    // code length to copy
                    if (s < 16) {
                        ldt[i++] = s;
                    }
                    else {
                        //  copy   count
                        var c = 0, n = 0;
                        if (s == 16)
                            n = 3 + bits(dat, pos, 3), pos += 2, c = ldt[i - 1];
                        else if (s == 17)
                            n = 3 + bits(dat, pos, 7), pos += 3;
                        else if (s == 18)
                            n = 11 + bits(dat, pos, 127), pos += 7;
                        while (n--)
                            ldt[i++] = c;
                    }
                }
                //    length tree                 distance tree
                var lt = ldt.subarray(0, hLit), dt = ldt.subarray(hLit);
                // max length bits
                lbt = max(lt);
                // max dist bits
                dbt = max(dt);
                lm = hMap(lt, lbt, 1);
                dm = hMap(dt, dbt, 1);
            }
            else
                err(1);
            if (pos > tbts) {
                if (noSt)
                    err(0);
                break;
            }
        }
        // Make sure the buffer can hold this + the largest possible addition
        // Maximum chunk size (practically, theoretically infinite) is 2^17
        if (resize)
            cbuf(bt + 131072);
        var lms = (1 << lbt) - 1, dms = (1 << dbt) - 1;
        var lpos = pos;
        for (;; lpos = pos) {
            // bits read, code
            var c = lm[bits16(dat, pos) & lms], sym = c >> 4;
            pos += c & 15;
            if (pos > tbts) {
                if (noSt)
                    err(0);
                break;
            }
            if (!c)
                err(2);
            if (sym < 256)
                buf[bt++] = sym;
            else if (sym == 256) {
                lpos = pos, lm = null;
                break;
            }
            else {
                var add = sym - 254;
                // no extra bits needed if less
                if (sym > 264) {
                    // index
                    var i = sym - 257, b = fleb[i];
                    add = bits(dat, pos, (1 << b) - 1) + fl[i];
                    pos += b;
                }
                // dist
                var d = dm[bits16(dat, pos) & dms], dsym = d >> 4;
                if (!d)
                    err(3);
                pos += d & 15;
                var dt = fd[dsym];
                if (dsym > 3) {
                    var b = fdeb[dsym];
                    dt += bits16(dat, pos) & (1 << b) - 1, pos += b;
                }
                if (pos > tbts) {
                    if (noSt)
                        err(0);
                    break;
                }
                if (resize)
                    cbuf(bt + 131072);
                var end = bt + add;
                if (bt < dt) {
                    var shift = dl - dt, dend = Math.min(dt, end);
                    if (shift + bt < 0)
                        err(3);
                    for (; bt < dend; ++bt)
                        buf[bt] = dict[shift + bt];
                }
                for (; bt < end; ++bt)
                    buf[bt] = buf[bt - dt];
            }
        }
        st.l = lm, st.p = lpos, st.b = bt, st.f = final;
        if (lm)
            final = 1, st.m = lbt, st.d = dm, st.n = dbt;
    } while (!final);
    // don't reallocate for streams or user buffers
    return bt != buf.length && noBuf ? slc(buf, 0, bt) : buf.subarray(0, bt);
}
```
</details>

### `cbuf(l: any): void`

**Parameters:**

- **`l`** `any`

**Returns:** `void`

**Calls:**

- `Math.max`
- `nbuf.set`

**Internal Comments:**
```
// need to increase size to fit
// Double or set to necessary, whichever is greater (x2)
```

<details><summary>Code</summary>

```typescript
function (l) {
        var bl = buf.length;
        // need to increase size to fit
        if (l > bl) {
            // Double or set to necessary, whichever is greater
            var nbuf = new u8(Math.max(bl * 2, l));
            nbuf.set(buf);
            buf = nbuf;
        }
    }
```
</details>

### `wbits(d: any, p: any, v: any): void`

**Parameters:**

- **`d`** `any`
- **`p`** `any`
- **`v`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (d, p, v) {
    v <<= p & 7;
    var o = (p / 8) | 0;
    d[o] |= v;
    d[o + 1] |= v >> 8;
}
```
</details>

### `wbits16(d: any, p: any, v: any): void`

**Parameters:**

- **`d`** `any`
- **`p`** `any`
- **`v`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (d, p, v) {
    v <<= p & 7;
    var o = (p / 8) | 0;
    d[o] |= v;
    d[o + 1] |= v >> 8;
    d[o + 2] |= v >> 16;
}
```
</details>

### `hTree(d: any, mb: any): { t: Uint8Array<ArrayBuffer>; l: any; }`

**Parameters:**

- **`d`** `any`
- **`mb`** `any`

**Returns:** `{ t: Uint8Array<ArrayBuffer>; l: any; }`

**Calls:**

- `t.push`
- `t.slice`
- `t.sort`
- `ln`
- `t2.sort`

**Internal Comments:**
```
// Need extra info to make a tree (x2)
// after i2 reaches last ind, will be stopped (x4)
// freq must be greater than largest possible number of symbols (x4)
// efficient algorithm from UZIP.js
// i0 is lookbehind, i2 is lookahead - after processing two low-freq
// symbols that combined have high freq, will start processing i2 (high-freq,
// non-composite) symbols instead
// see https://reddit.com/r/photopea/comments/ikekht/uzipjs_questions/
// code lengths (x2)
// max bits in tree (x2)
// more algorithms from UZIP.js (x2)
// TODO: find out how this code works (debt) (x2)
//  ind    debt (x2)
//    left            cost (x2)
```

<details><summary>Code</summary>

```typescript
function (d, mb) {
    // Need extra info to make a tree
    var t = [];
    for (var i = 0; i < d.length; ++i) {
        if (d[i])
            t.push({ s: i, f: d[i] });
    }
    var s = t.length;
    var t2 = t.slice();
    if (!s)
        return { t: et, l: 0 };
    if (s == 1) {
        var v = new u8(t[0].s + 1);
        v[t[0].s] = 1;
        return { t: v, l: 1 };
    }
    t.sort(function (a, b) { return a.f - b.f; });
    // after i2 reaches last ind, will be stopped
    // freq must be greater than largest possible number of symbols
    t.push({ s: -1, f: 25001 });
    var l = t[0], r = t[1], i0 = 0, i1 = 1, i2 = 2;
    t[0] = { s: -1, f: l.f + r.f, l: l, r: r };
    // efficient algorithm from UZIP.js
    // i0 is lookbehind, i2 is lookahead - after processing two low-freq
    // symbols that combined have high freq, will start processing i2 (high-freq,
    // non-composite) symbols instead
    // see https://reddit.com/r/photopea/comments/ikekht/uzipjs_questions/
    while (i1 != s - 1) {
        l = t[t[i0].f < t[i2].f ? i0++ : i2++];
        r = t[i0 != i1 && t[i0].f < t[i2].f ? i0++ : i2++];
        t[i1++] = { s: -1, f: l.f + r.f, l: l, r: r };
    }
    var maxSym = t2[0].s;
    for (var i = 1; i < s; ++i) {
        if (t2[i].s > maxSym)
            maxSym = t2[i].s;
    }
    // code lengths
    var tr = new u16(maxSym + 1);
    // max bits in tree
    var mbt = ln(t[i1 - 1], tr, 0);
    if (mbt > mb) {
        // more algorithms from UZIP.js
        // TODO: find out how this code works (debt)
        //  ind    debt
        var i = 0, dt = 0;
        //    left            cost
        var lft = mbt - mb, cst = 1 << lft;
        t2.sort(function (a, b) { return tr[b.s] - tr[a.s] || a.f - b.f; });
        for (; i < s; ++i) {
            var i2_1 = t2[i].s;
            if (tr[i2_1] > mb) {
                dt += cst - (1 << (mbt - tr[i2_1]));
                tr[i2_1] = mb;
            }
            else
                break;
        }
        dt >>= lft;
        while (dt > 0) {
            var i2_2 = t2[i].s;
            if (tr[i2_2] < mb)
                dt -= 1 << (mb - tr[i2_2]++ - 1);
            else
                ++i;
        }
        for (; i >= 0 && dt; --i) {
            var i2_3 = t2[i].s;
            if (tr[i2_3] == mb) {
                --tr[i2_3];
                ++dt;
            }
        }
        mbt = mb;
    }
    return { t: new u8(tr), l: mbt };
}
```
</details>

### `ln(n: any, l: any, d: any): any`

**Parameters:**

- **`n`** `any`
- **`l`** `any`
- **`d`** `any`

**Returns:** `any`

**Calls:**

- `Math.max`
- `ln`

<details><summary>Code</summary>

```typescript
function (n, l, d) {
    return n.s == -1
        ? Math.max(ln(n.l, l, d + 1), ln(n.r, l, d + 1))
        : (l[n.s] = d);
}
```
</details>

### `lc(c: any): { c: Uint16Array<ArrayBuffer>; n: any; }`

**Parameters:**

- **`c`** `any`

**Returns:** `{ c: Uint16Array<ArrayBuffer>; n: any; }`

**Calls:**

- `w`
- `cl.subarray`

**Internal Comments:**
```
// Note that the semicolon was intentional
//  ind      num         streak (x2)
```

<details><summary>Code</summary>

```typescript
function (c) {
    var s = c.length;
    // Note that the semicolon was intentional
    while (s && !c[--s])
        ;
    var cl = new u16(++s);
    //  ind      num         streak
    var cli = 0, cln = c[0], cls = 1;
    var w = function (v) { cl[cli++] = v; };
    for (var i = 1; i <= s; ++i) {
        if (c[i] == cln && i != s)
            ++cls;
        else {
            if (!cln && cls > 2) {
                for (; cls > 138; cls -= 138)
                    w(32754);
                if (cls > 2) {
                    w(cls > 10 ? ((cls - 11) << 5) | 28690 : ((cls - 3) << 5) | 12305);
                    cls = 0;
                }
            }
            else if (cls > 3) {
                w(cln), --cls;
                for (; cls > 6; cls -= 6)
                    w(8304);
                if (cls > 2)
                    w(((cls - 3) << 5) | 8208), cls = 0;
            }
            while (cls--)
                w(cln);
            cls = 1;
            cln = c[i];
        }
    }
    return { c: cl.subarray(0, cli), n: s };
}
```
</details>

### `w(v: any): void`

**Parameters:**

- **`v`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (v) { cl[cli++] = v; }
```
</details>

### `clen(cf: any, cl: any): number`

**Parameters:**

- **`cf`** `any`
- **`cl`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (cf, cl) {
    var l = 0;
    for (var i = 0; i < cl.length; ++i)
        l += cf[i] * cl[i];
    return l;
}
```
</details>

### `wfblk(out: any, pos: any, dat: any): number`

**Parameters:**

- **`out`** `any`
- **`pos`** `any`
- **`dat`** `any`

**Returns:** `number`

**Calls:**

- `shft`

**Internal Comments:**
```
// no need to write 00 as type: TypedArray defaults to 0 (x2)
```

<details><summary>Code</summary>

```typescript
function (out, pos, dat) {
    // no need to write 00 as type: TypedArray defaults to 0
    var s = dat.length;
    var o = shft(pos + 2);
    out[o] = s & 255;
    out[o + 1] = s >> 8;
    out[o + 2] = out[o] ^ 255;
    out[o + 3] = out[o + 1] ^ 255;
    for (var i = 0; i < s; ++i)
        out[o + i + 4] = dat[i];
    return (o + 4 + s) * 8;
}
```
</details>

### `wblk(dat: any, out: any, final: any, syms: any, lf: any, df: any, eb: any, li: any, bs: any, bl: any, p: any): any`

**Parameters:**

- **`dat`** `any`
- **`out`** `any`
- **`final`** `any`
- **`syms`** `any`
- **`lf`** `any`
- **`df`** `any`
- **`eb`** `any`
- **`li`** `any`
- **`bs`** `any`
- **`bl`** `any`
- **`p`** `any`

**Returns:** `any`

**Calls:**

- `wbits`
- `hTree`
- `lc`
- `clen`
- `wfblk`
- `dat.subarray`
- `hMap`
- `wbits16`

<details><summary>Code</summary>

```typescript
function (dat, out, final, syms, lf, df, eb, li, bs, bl, p) {
    wbits(out, p++, final);
    ++lf[256];
    var _a = hTree(lf, 15), dlt = _a.t, mlb = _a.l;
    var _b = hTree(df, 15), ddt = _b.t, mdb = _b.l;
    var _c = lc(dlt), lclt = _c.c, nlc = _c.n;
    var _d = lc(ddt), lcdt = _d.c, ndc = _d.n;
    var lcfreq = new u16(19);
    for (var i = 0; i < lclt.length; ++i)
        ++lcfreq[lclt[i] & 31];
    for (var i = 0; i < lcdt.length; ++i)
        ++lcfreq[lcdt[i] & 31];
    var _e = hTree(lcfreq, 7), lct = _e.t, mlcb = _e.l;
    var nlcc = 19;
    for (; nlcc > 4 && !lct[clim[nlcc - 1]]; --nlcc)
        ;
    var flen = (bl + 5) << 3;
    var ftlen = clen(lf, flt) + clen(df, fdt) + eb;
    var dtlen = clen(lf, dlt) + clen(df, ddt) + eb + 14 + 3 * nlcc + clen(lcfreq, lct) + 2 * lcfreq[16] + 3 * lcfreq[17] + 7 * lcfreq[18];
    if (bs >= 0 && flen <= ftlen && flen <= dtlen)
        return wfblk(out, p, dat.subarray(bs, bs + bl));
    var lm, ll, dm, dl;
    wbits(out, p, 1 + (dtlen < ftlen)), p += 2;
    if (dtlen < ftlen) {
        lm = hMap(dlt, mlb, 0), ll = dlt, dm = hMap(ddt, mdb, 0), dl = ddt;
        var llm = hMap(lct, mlcb, 0);
        wbits(out, p, nlc - 257);
        wbits(out, p + 5, ndc - 1);
        wbits(out, p + 10, nlcc - 4);
        p += 14;
        for (var i = 0; i < nlcc; ++i)
            wbits(out, p + 3 * i, lct[clim[i]]);
        p += 3 * nlcc;
        var lcts = [lclt, lcdt];
        for (var it = 0; it < 2; ++it) {
            var clct = lcts[it];
            for (var i = 0; i < clct.length; ++i) {
                var len = clct[i] & 31;
                wbits(out, p, llm[len]), p += lct[len];
                if (len > 15)
                    wbits(out, p, (clct[i] >> 5) & 127), p += clct[i] >> 12;
            }
        }
    }
    else {
        lm = flm, ll = flt, dm = fdm, dl = fdt;
    }
    for (var i = 0; i < li; ++i) {
        var sym = syms[i];
        if (sym > 255) {
            var len = (sym >> 18) & 31;
            wbits16(out, p, lm[len + 257]), p += ll[len + 257];
            if (len > 7)
                wbits(out, p, (sym >> 23) & 31), p += fleb[len];
            var dst = sym & 31;
            wbits16(out, p, dm[dst]), p += dl[dst];
            if (dst > 3)
                wbits16(out, p, (sym >> 5) & 8191), p += fdeb[dst];
        }
        else {
            wbits16(out, p, lm[sym]), p += ll[sym];
        }
    }
    wbits16(out, p, lm[256]);
    return p + ll[256];
}
```
</details>

### `dflt(dat: any, lvl: any, plvl: any, pre: any, post: any, st: any): Uint8Array<any>`

**Parameters:**

- **`dat`** `any`
- **`lvl`** `any`
- **`plvl`** `any`
- **`pre`** `any`
- **`post`** `any`
- **`st`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `Math.ceil`
- `o.subarray`
- `hsh`
- `wblk`
- `Math.min`
- `Math.max`
- `wfblk`
- `dat.subarray`
- `slc`
- `shft`

**Internal Comments:**
```
// writing to this writes to the output buffer (x2)
//    prev 2-byte val map    curr 2-byte val map (x2)
// 24576 is an arbitrary number of maximum symbols per block (x2)
// 424 buffer for last block (x2)
// length/literal freq   distance freq (x2)
//  l/lcnt  exbits  index          l/lind  waitdx          blkpos (x2)
// hash value (x2)
// index mod 32768    previous index mod (x2)
// We always should modify head and prev, but only add symbols if
// this data is not yet processed ("wait" for wait index)
// bytes remaining (x2)
//  len    dist   chain (x2)
// max possible length (x2)
// not capped at dif because decompressors implement "rolling" index population (x2)
// break out early when we reach "nice" (we are satisfied enough)
// now, find the rarest 2-byte sequence within this (x2)
// length of literals and search for that instead. (x2)
// Much faster than just using the start (x2)
// check the previous match (x4)
// d will be nonzero only when a match was found
// store both dist and len data in one int32 (x4)
// Make sure this is recognized as a len/dist with 28th bit (2^28) (x4)
// shft(pos) now 1 less if pos & 7 != 0 (x3)
// end (x2)
// write final block (x4)
```

<details><summary>Code</summary>

```typescript
function (dat, lvl, plvl, pre, post, st) {
    var s = st.z || dat.length;
    var o = new u8(pre + s + 5 * (1 + Math.ceil(s / 7000)) + post);
    // writing to this writes to the output buffer
    var w = o.subarray(pre, o.length - post);
    var lst = st.l;
    var pos = (st.r || 0) & 7;
    if (lvl) {
        if (pos)
            w[0] = st.r >> 3;
        var opt = deo[lvl - 1];
        var n = opt >> 13, c = opt & 8191;
        var msk_1 = (1 << plvl) - 1;
        //    prev 2-byte val map    curr 2-byte val map
        var prev = st.p || new u16(32768), head = st.h || new u16(msk_1 + 1);
        var bs1_1 = Math.ceil(plvl / 3), bs2_1 = 2 * bs1_1;
        var hsh = function (i) { return (dat[i] ^ (dat[i + 1] << bs1_1) ^ (dat[i + 2] << bs2_1)) & msk_1; };
        // 24576 is an arbitrary number of maximum symbols per block
        // 424 buffer for last block
        var syms = new i32(25000);
        // length/literal freq   distance freq
        var lf = new u16(288), df = new u16(32);
        //  l/lcnt  exbits  index          l/lind  waitdx          blkpos
        var lc_1 = 0, eb = 0, i = st.i || 0, li = 0, wi = st.w || 0, bs = 0;
        for (; i + 2 < s; ++i) {
            // hash value
            var hv = hsh(i);
            // index mod 32768    previous index mod
            var imod = i & 32767, pimod = head[hv];
            prev[imod] = pimod;
            head[hv] = imod;
            // We always should modify head and prev, but only add symbols if
            // this data is not yet processed ("wait" for wait index)
            if (wi <= i) {
                // bytes remaining
                var rem = s - i;
                if ((lc_1 > 7000 || li > 24576) && (rem > 423 || !lst)) {
                    pos = wblk(dat, w, 0, syms, lf, df, eb, li, bs, i - bs, pos);
                    li = lc_1 = eb = 0, bs = i;
                    for (var j = 0; j < 286; ++j)
                        lf[j] = 0;
                    for (var j = 0; j < 30; ++j)
                        df[j] = 0;
                }
                //  len    dist   chain
                var l = 2, d = 0, ch_1 = c, dif = imod - pimod & 32767;
                if (rem > 2 && hv == hsh(i - dif)) {
                    var maxn = Math.min(n, rem) - 1;
                    var maxd = Math.min(32767, i);
                    // max possible length
                    // not capped at dif because decompressors implement "rolling" index population
                    var ml = Math.min(258, rem);
                    while (dif <= maxd && --ch_1 && imod != pimod) {
                        if (dat[i + l] == dat[i + l - dif]) {
                            var nl = 0;
                            for (; nl < ml && dat[i + nl] == dat[i + nl - dif]; ++nl)
                                ;
                            if (nl > l) {
                                l = nl, d = dif;
                                // break out early when we reach "nice" (we are satisfied enough)
                                if (nl > maxn)
                                    break;
                                // now, find the rarest 2-byte sequence within this
                                // length of literals and search for that instead.
                                // Much faster than just using the start
                                var mmd = Math.min(dif, nl - 2);
                                var md = 0;
                                for (var j = 0; j < mmd; ++j) {
                                    var ti = i - dif + j & 32767;
                                    var pti = prev[ti];
                                    var cd = ti - pti & 32767;
                                    if (cd > md)
                                        md = cd, pimod = ti;
                                }
                            }
                        }
                        // check the previous match
                        imod = pimod, pimod = prev[imod];
                        dif += imod - pimod & 32767;
                    }
                }
                // d will be nonzero only when a match was found
                if (d) {
                    // store both dist and len data in one int32
                    // Make sure this is recognized as a len/dist with 28th bit (2^28)
                    syms[li++] = 268435456 | (revfl[l] << 18) | revfd[d];
                    var lin = revfl[l] & 31, din = revfd[d] & 31;
                    eb += fleb[lin] + fdeb[din];
                    ++lf[257 + lin];
                    ++df[din];
                    wi = i + l;
                    ++lc_1;
                }
                else {
                    syms[li++] = dat[i];
                    ++lf[dat[i]];
                }
            }
        }
        for (i = Math.max(i, wi); i < s; ++i) {
            syms[li++] = dat[i];
            ++lf[dat[i]];
        }
        pos = wblk(dat, w, lst, syms, lf, df, eb, li, bs, i - bs, pos);
        if (!lst) {
            st.r = (pos & 7) | w[(pos / 8) | 0] << 3;
            // shft(pos) now 1 less if pos & 7 != 0
            pos -= 7;
            st.h = head, st.p = prev, st.i = i, st.w = wi;
        }
    }
    else {
        for (var i = st.w || 0; i < s + lst; i += 65535) {
            // end
            var e = i + 65535;
            if (e >= s) {
                // write final block
                w[(pos / 8) | 0] = lst;
                e = s;
            }
            pos = wfblk(w, pos + 1, dat.subarray(i, e));
        }
        st.i = s;
    }
    return slc(o, 0, pre + shft(pos) + post);
}
```
</details>

### `hsh(i: any): number`

**Parameters:**

- **`i`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (i) { return (dat[i] ^ (dat[i + 1] << bs1_1) ^ (dat[i + 2] << bs2_1)) & msk_1; }
```
</details>

### `crc(): { p: (d: any) => void; d: () => number; }`

**Returns:** `{ p: (d: any) => void; d: () => number; }`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function () {
    var c = -1;
    return {
        p: function (d) {
            // closures have awful performance
            var cr = c;
            for (var i = 0; i < d.length; ++i)
                cr = crct[(cr & 255) ^ d[i]] ^ (cr >>> 8);
            c = cr;
        },
        d: function () { return ~c; }
    };
}
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var cr = c;
            for (var i = 0; i < d.length; ++i)
                cr = crct[(cr & 255) ^ d[i]] ^ (cr >>> 8);
            c = cr;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () { return ~c; }
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var cr = c;
            for (var i = 0; i < d.length; ++i)
                cr = crct[(cr & 255) ^ d[i]] ^ (cr >>> 8);
            c = cr;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () { return ~c; }
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var cr = c;
            for (var i = 0; i < d.length; ++i)
                cr = crct[(cr & 255) ^ d[i]] ^ (cr >>> 8);
            c = cr;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () { return ~c; }
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var cr = c;
            for (var i = 0; i < d.length; ++i)
                cr = crct[(cr & 255) ^ d[i]] ^ (cr >>> 8);
            c = cr;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () { return ~c; }
```
</details>

### `adler(): { p: (d: any) => void; d: () => number; }`

**Returns:** `{ p: (d: any) => void; d: () => number; }`

**Calls:**

- `Math.min`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function () {
    var a = 1, b = 0;
    return {
        p: function (d) {
            // closures have awful performance
            var n = a, m = b;
            var l = d.length | 0;
            for (var i = 0; i != l;) {
                var e = Math.min(i + 2655, l);
                for (; i < e; ++i)
                    m += n += d[i];
                n = (n & 65535) + 15 * (n >> 16), m = (m & 65535) + 15 * (m >> 16);
            }
            a = n, b = m;
        },
        d: function () {
            a %= 65521, b %= 65521;
            return (a & 255) << 24 | (a & 0xFF00) << 8 | (b & 255) << 8 | (b >> 8);
        }
    };
}
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var n = a, m = b;
            var l = d.length | 0;
            for (var i = 0; i != l;) {
                var e = Math.min(i + 2655, l);
                for (; i < e; ++i)
                    m += n += d[i];
                n = (n & 65535) + 15 * (n >> 16), m = (m & 65535) + 15 * (m >> 16);
            }
            a = n, b = m;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
            a %= 65521, b %= 65521;
            return (a & 255) << 24 | (a & 0xFF00) << 8 | (b & 255) << 8 | (b >> 8);
        }
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var n = a, m = b;
            var l = d.length | 0;
            for (var i = 0; i != l;) {
                var e = Math.min(i + 2655, l);
                for (; i < e; ++i)
                    m += n += d[i];
                n = (n & 65535) + 15 * (n >> 16), m = (m & 65535) + 15 * (m >> 16);
            }
            a = n, b = m;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
            a %= 65521, b %= 65521;
            return (a & 255) << 24 | (a & 0xFF00) << 8 | (b & 255) << 8 | (b >> 8);
        }
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var n = a, m = b;
            var l = d.length | 0;
            for (var i = 0; i != l;) {
                var e = Math.min(i + 2655, l);
                for (; i < e; ++i)
                    m += n += d[i];
                n = (n & 65535) + 15 * (n >> 16), m = (m & 65535) + 15 * (m >> 16);
            }
            a = n, b = m;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
            a %= 65521, b %= 65521;
            return (a & 255) << 24 | (a & 0xFF00) << 8 | (b & 255) << 8 | (b >> 8);
        }
```
</details>

### `p(d: any): void`

**Parameters:**

- **`d`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`

**Internal Comments:**
```
// closures have awful performance (x2)
```

<details><summary>Code</summary>

```typescript
function (d) {
            // closures have awful performance
            var n = a, m = b;
            var l = d.length | 0;
            for (var i = 0; i != l;) {
                var e = Math.min(i + 2655, l);
                for (; i < e; ++i)
                    m += n += d[i];
                n = (n & 65535) + 15 * (n >> 16), m = (m & 65535) + 15 * (m >> 16);
            }
            a = n, b = m;
        }
```
</details>

### `d(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {
            a %= 65521, b %= 65521;
            return (a & 255) << 24 | (a & 0xFF00) << 8 | (b & 255) << 8 | (b >> 8);
        }
```
</details>

### `dopt(dat: any, opt: any, pre: any, post: any, st: any): Uint8Array<any>`

**Parameters:**

- **`dat`** `any`
- **`opt`** `any`
- **`pre`** `any`
- **`post`** `any`
- **`st`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `opt.dictionary.subarray`
- `newDat.set`
- `dflt`
- `Math.ceil`
- `Math.max`
- `Math.min`
- `Math.log`

<details><summary>Code</summary>

```typescript
function (dat, opt, pre, post, st) {
    if (!st) {
        st = { l: 1 };
        if (opt.dictionary) {
            var dict = opt.dictionary.subarray(-32768);
            var newDat = new u8(dict.length + dat.length);
            newDat.set(dict);
            newDat.set(dat, dict.length);
            dat = newDat;
            st.w = dict.length;
        }
    }
    return dflt(dat, opt.level == null ? 6 : opt.level, opt.mem == null ? (st.l ? Math.ceil(Math.max(8, Math.min(13, Math.log(dat.length))) * 1.5) : 20) : (12 + opt.mem), pre, post, st);
}
```
</details>

### `mrg(a: any, b: any): {}`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function (a, b) {
    var o = {};
    for (var k in a)
        o[k] = a[k];
    for (var k in b)
        o[k] = b[k];
    return o;
}
```
</details>

### `wcln(fn: any, fnStr: any, td: any): any`

**Parameters:**

- **`fn`** `any`
- **`fnStr`** `any`
- **`td`** `any`

**Returns:** `any`

**Calls:**

- `fn`
- `fn.toString`
- `st.slice(st.indexOf('[') + 1, st.lastIndexOf(']')).replace(/\s+/g, '').split`
- `v.toString`
- `st_1.indexOf`
- `st_1.slice`
- `v.prototype[t].toString`

**Internal Comments:**
```
// for global objects
```

<details><summary>Code</summary>

```typescript
function (fn, fnStr, td) {
    var dt = fn();
    var st = fn.toString();
    var ks = st.slice(st.indexOf('[') + 1, st.lastIndexOf(']')).replace(/\s+/g, '').split(',');
    for (var i = 0; i < dt.length; ++i) {
        var v = dt[i], k = ks[i];
        if (typeof v == 'function') {
            fnStr += ';' + k + '=';
            var st_1 = v.toString();
            if (v.prototype) {
                // for global objects
                if (st_1.indexOf('[native code]') != -1) {
                    var spInd = st_1.indexOf(' ', 8) + 1;
                    fnStr += st_1.slice(spInd, st_1.indexOf('(', spInd));
                }
                else {
                    fnStr += st_1;
                    for (var t in v.prototype)
                        fnStr += ';' + k + '.prototype.' + t + '=' + v.prototype[t].toString();
                }
            }
            else
                fnStr += st_1;
        }
        else
            td[k] = v;
    }
    return fnStr;
}
```
</details>

### `cbfs(v: any): any[]`

**Parameters:**

- **`v`** `any`

**Returns:** `any[]`

**Calls:**

- `tl.push`

<details><summary>Code</summary>

```typescript
function (v) {
    var tl = [];
    for (var k in v) {
        if (v[k].buffer) {
            tl.push((v[k] = new v[k].constructor(v[k])).buffer);
        }
    }
    return tl;
}
```
</details>

### `wrkr(fns: any, init: any, id: any, cb: any): Worker`

**Parameters:**

- **`fns`** `any`
- **`init`** `any`
- **`id`** `any`
- **`cb`** `any`

**Returns:** `Worker`

**Calls:**

- `wcln`
- `mrg`
- `wk`
- `init.toString`
- `cbfs`

<details><summary>Code</summary>

```typescript
function (fns, init, id, cb) {
    if (!ch[id]) {
        var fnStr = '', td_1 = {}, m = fns.length - 1;
        for (var i = 0; i < m; ++i)
            fnStr = wcln(fns[i], fnStr, td_1);
        ch[id] = { c: wcln(fns[m], fnStr, td_1), e: td_1 };
    }
    var td = mrg({}, ch[id].e);
    return wk(ch[id].c + ';onmessage=function(e){for(var k in e.data)self[k]=e.data[k];onmessage=' + init.toString() + '}', id, td, cbfs(td), cb);
}
```
</details>

### `bInflt(): (Uint8ArrayConstructor | Uint16ArrayConstructor | Int32ArrayConstructor | string[] | Uint8Array<ArrayBuffer> | ((dat: any, st: any, buf: any, dict: any) => any) | Uint16Array<...>)[]`

**Returns:** `(Uint8ArrayConstructor | Uint16ArrayConstructor | Int32ArrayConstructor | string[] | Uint8Array<ArrayBuffer> | ((dat: any, st: any, buf: any, dict: any) => any) | Uint16Array<...>)[]`

<details><summary>Code</summary>

```typescript
function () { return [u8, u16, i32, fleb, fdeb, clim, fl, fd, flrm, fdrm, rev, ec, hMap, max, bits, bits16, shft, slc, err, inflt, inflateSync, pbf, gopt]; }
```
</details>

### `bDflt(): (Uint8ArrayConstructor | Uint16ArrayConstructor | Int32ArrayConstructor | Int32Array<ArrayBuffer> | Uint8Array<...> | Uint16Array<...> | ((dat: any, out: any, final: any, syms: any, lf: any, df: any, eb: any, li: any, bs: any, bl: any, p: any) => any))[]`

**Returns:** `(Uint8ArrayConstructor | Uint16ArrayConstructor | Int32ArrayConstructor | Int32Array<ArrayBuffer> | Uint8Array<...> | Uint16Array<...> | ((dat: any, out: any, final: any, syms: any, lf: any, df: any, eb: any, li: any, bs: any, bl: any, p: any) => any))[]`

<details><summary>Code</summary>

```typescript
function () { return [u8, u16, i32, fleb, fdeb, clim, revfl, revfd, flm, flt, fdm, fdt, rev, deo, et, hMap, wbits, wbits16, hTree, ln, lc, clen, wfblk, wblk, shft, slc, dflt, dopt, deflateSync, pbf]; }
```
</details>

### `gze(): (Int32Array<ArrayBuffer> | ((d: any, b: any, v: any) => void))[]`

**Returns:** `(Int32Array<ArrayBuffer> | ((d: any, b: any, v: any) => void))[]`

<details><summary>Code</summary>

```typescript
function () { return [gzh, gzhl, wbytes, crc, crct]; }
```
</details>

### `guze(): ((d: any) => number)[]`

**Returns:** `((d: any) => number)[]`

<details><summary>Code</summary>

```typescript
function () { return [gzs, gzl]; }
```
</details>

### `zle(): ((d: any, b: any, v: any) => void)[]`

**Returns:** `((d: any, b: any, v: any) => void)[]`

<details><summary>Code</summary>

```typescript
function () { return [zlh, wbytes, adler]; }
```
</details>

### `zule(): ((d: any, dict: any) => number)[]`

**Returns:** `((d: any, dict: any) => number)[]`

<details><summary>Code</summary>

```typescript
function () { return [zls]; }
```
</details>

### `pbf(msg: any): void`

**Parameters:**

- **`msg`** `any`

**Returns:** `void`

**Calls:**

- `postMessage`

<details><summary>Code</summary>

```typescript
function (msg) { return postMessage(msg, [msg.buffer]); }
```
</details>

### `gopt(o: any): { out: Uint8Array<any>; dictionary: any; }`

**Parameters:**

- **`o`** `any`

**Returns:** `{ out: Uint8Array<any>; dictionary: any; }`

<details><summary>Code</summary>

```typescript
function (o) { return o && {
    out: o.size && new u8(o.size),
    dictionary: o.dictionary
}; }
```
</details>

### `cbify(dat: any, opts: any, fns: any, init: any, id: any, cb: any): () => void`

**Parameters:**

- **`dat`** `any`
- **`opts`** `any`
- **`fns`** `any`
- **`init`** `any`
- **`id`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `wrkr`
- `w.terminate`
- `cb`
- `w.postMessage`

<details><summary>Code</summary>

```typescript
function (dat, opts, fns, init, id, cb) {
    var w = wrkr(fns, init, id, function (err, dat) {
        w.terminate();
        cb(err, dat);
    });
    w.postMessage([dat, opts], opts.consume ? [dat.buffer] : []);
    return function () { w.terminate(); };
}
```
</details>

### `astrm(strm: any): (ev: any) => void`

**Parameters:**

- **`strm`** `any`

**Returns:** `(ev: any) => void`

**Calls:**

- `postMessage`
- `strm.push`
- `strm.flush`

<details><summary>Code</summary>

```typescript
function (strm) {
    strm.ondata = function (dat, final) { return postMessage([dat, final], [dat.buffer]); };
    return function (ev) {
        if (ev.data.length) {
            strm.push(ev.data[0], ev.data[1]);
            postMessage([ev.data[0].length]);
        }
        else
            strm.flush();
    };
}
```
</details>

### `astrmify(fns: any, strm: any, opts: any, init: any, id: any, flush: any, ext: any): void`

**Parameters:**

- **`fns`** `any`
- **`strm`** `any`
- **`opts`** `any`
- **`init`** `any`
- **`id`** `any`
- **`flush`** `any`
- **`ext`** `any`

**Returns:** `void`

**Calls:**

- `wrkr`
- `w.terminate`
- `strm.ondata.call`
- `Array.isArray`
- `ext`
- `strm.ondrain`
- `w.postMessage`
- `err`
- `strm.ondata`

<details><summary>Code</summary>

```typescript
function (fns, strm, opts, init, id, flush, ext) {
    var t;
    var w = wrkr(fns, init, id, function (err, dat) {
        if (err)
            w.terminate(), strm.ondata.call(strm, err);
        else if (!Array.isArray(dat))
            ext(dat);
        else if (dat.length == 1) {
            strm.queuedSize -= dat[0];
            if (strm.ondrain)
                strm.ondrain(dat[0]);
        }
        else {
            if (dat[1])
                w.terminate();
            strm.ondata.call(strm, err, dat[0], dat[1]);
        }
    });
    w.postMessage(opts);
    strm.queuedSize = 0;
    strm.push = function (d, f) {
        if (!strm.ondata)
            err(5);
        if (t)
            strm.ondata(err(4, 0, 1), null, !!f);
        strm.queuedSize += d.length;
        w.postMessage([d, t = f], [d.buffer]);
    };
    strm.terminate = function () { w.terminate(); };
    if (flush) {
        strm.flush = function () { w.postMessage([]); };
    }
}
```
</details>

### `b2(d: any, b: any): number`

**Parameters:**

- **`d`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (d, b) { return d[b] | (d[b + 1] << 8); }
```
</details>

### `b4(d: any, b: any): number`

**Parameters:**

- **`d`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (d, b) { return (d[b] | (d[b + 1] << 8) | (d[b + 2] << 16) | (d[b + 3] << 24)) >>> 0; }
```
</details>

### `b8(d: any, b: any): number`

**Parameters:**

- **`d`** `any`
- **`b`** `any`

**Returns:** `number`

**Calls:**

- `b4`

<details><summary>Code</summary>

```typescript
function (d, b) { return b4(d, b) + (b4(d, b + 4) * 4294967296); }
```
</details>

### `wbytes(d: any, b: any, v: any): void`

**Parameters:**

- **`d`** `any`
- **`b`** `any`
- **`v`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (d, b, v) {
    for (; v; ++b)
        d[b] = v, v >>>= 8;
}
```
</details>

### `gzh(c: any, o: any): void`

**Parameters:**

- **`c`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `wbytes`
- `Math.floor`
- `Date.now`
- `fn.charCodeAt`

<details><summary>Code</summary>

```typescript
function (c, o) {
    var fn = o.filename;
    c[0] = 31, c[1] = 139, c[2] = 8, c[8] = o.level < 2 ? 4 : o.level == 9 ? 2 : 0, c[9] = 3; // assume Unix
    if (o.mtime != 0)
        wbytes(c, 4, Math.floor(new Date(o.mtime || Date.now()) / 1000));
    if (fn) {
        c[3] = 8;
        for (var i = 0; i <= fn.length; ++i)
            c[i + 10] = fn.charCodeAt(i);
    }
}
```
</details>

### `gzs(d: any): number`

**Parameters:**

- **`d`** `any`

**Returns:** `number`

**Calls:**

- `err`

<details><summary>Code</summary>

```typescript
function (d) {
    if (d[0] != 31 || d[1] != 139 || d[2] != 8)
        err(6, 'invalid gzip data');
    var flg = d[3];
    var st = 10;
    if (flg & 4)
        st += (d[10] | d[11] << 8) + 2;
    for (var zs = (flg >> 3 & 1) + (flg >> 4 & 1); zs > 0; zs -= !d[st++])
        ;
    return st + (flg & 2);
}
```
</details>

### `gzl(d: any): number`

**Parameters:**

- **`d`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (d) {
    var l = d.length;
    return (d[l - 4] | d[l - 3] << 8 | d[l - 2] << 16 | d[l - 1] << 24) >>> 0;
}
```
</details>

### `gzhl(o: any): any`

**Parameters:**

- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (o) { return 10 + (o.filename ? o.filename.length + 1 : 0); }
```
</details>

### `zlh(c: any, o: any): void`

**Parameters:**

- **`c`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `adler`
- `h.p`
- `wbytes`
- `h.d`

<details><summary>Code</summary>

```typescript
function (c, o) {
    var lv = o.level, fl = lv == 0 ? 0 : lv < 6 ? 1 : lv == 9 ? 3 : 2;
    c[0] = 120, c[1] = (fl << 6) | (o.dictionary && 32);
    c[1] |= 31 - ((c[0] << 8) | c[1]) % 31;
    if (o.dictionary) {
        var h = adler();
        h.p(o.dictionary);
        wbytes(c, 2, h.d());
    }
}
```
</details>

### `zls(d: any, dict: any): number`

**Parameters:**

- **`d`** `any`
- **`dict`** `any`

**Returns:** `number`

**Calls:**

- `err`

<details><summary>Code</summary>

```typescript
function (d, dict) {
    if ((d[0] & 15) != 8 || (d[0] >> 4) > 7 || ((d[0] << 8 | d[1]) % 31))
        err(6, 'invalid zlib data');
    if ((d[1] >> 5 & 1) == +!dict)
        err(6, 'invalid zlib data: ' + (d[1] & 32 ? 'need' : 'unexpected') + ' dictionary');
    return (d[1] >> 3 & 4) + 2;
}
```
</details>

### `StrmOpt(opts: any, cb: any): any`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function StrmOpt(opts, cb) {
    if (typeof opts == 'function')
        cb = opts, opts = {};
    this.ondata = cb;
    return opts;
}
```
</details>

### `Deflate(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `this.o.dictionary.subarray`
- `this.b.set`

**Internal Comments:**
```
// Buffer length must always be 0 mod 32768 for index calculations to be correct when modifying head and prev (x4)
// 98304 = 32768 (lookback) + 65536 (common chunk size) (x4)
```

<details><summary>Code</summary>

```typescript
function Deflate(opts, cb) {
        if (typeof opts == 'function')
            cb = opts, opts = {};
        this.ondata = cb;
        this.o = opts || {};
        this.s = { l: 0, i: 32768, w: 32768, z: 32768 };
        // Buffer length must always be 0 mod 32768 for index calculations to be correct when modifying head and prev
        // 98304 = 32768 (lookback) + 65536 (common chunk size)
        this.b = new u8(98304);
        if (this.o.dictionary) {
            var dict = this.o.dictionary.subarray(-32768);
            this.b.set(dict, 32768 - dict.length);
            this.s.i = 32768 - dict.length;
        }
    }
```
</details>

### `AsyncDeflate(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `astrmify`
- `StrmOpt.call`
- `astrm`

<details><summary>Code</summary>

```typescript
function AsyncDeflate(opts, cb) {
        astrmify([
            bDflt,
            function () { return [astrm, Deflate]; }
        ], this, StrmOpt.call(this, opts, cb), function (ev) {
            var strm = new Deflate(ev.data);
            onmessage = astrm(strm);
        }, 6, 1);
    }
```
</details>

### `deflate(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `cbify`
- `pbf`
- `deflateSync`

<details><summary>Code</summary>

```typescript
export function deflate(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    return cbify(data, opts, [
        bDflt,
    ], function (ev) { return pbf(deflateSync(ev.data[0], ev.data[1])); }, 0, cb);
}
```
</details>

### `deflateSync(data: any, opts: any): Uint8Array<any>`

**JSDoc:**
```typescript
/**
 * Compresses data with DEFLATE without any wrapper
 * @param data The data to compress
 * @param opts The compression options
 * @returns The deflated version of the data
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `dopt`

<details><summary>Code</summary>

```typescript
export function deflateSync(data, opts) {
    return dopt(data, opts || {}, 0, 0);
}
```
</details>

### `Inflate(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `opts.dictionary.subarray`
- `this.o.set`

**Internal Comments:**
```
// no StrmOpt here to avoid adding to workerizer
```

<details><summary>Code</summary>

```typescript
function Inflate(opts, cb) {
        // no StrmOpt here to avoid adding to workerizer
        if (typeof opts == 'function')
            cb = opts, opts = {};
        this.ondata = cb;
        var dict = opts && opts.dictionary && opts.dictionary.subarray(-32768);
        this.s = { i: 0, b: dict ? dict.length : 0 };
        this.o = new u8(32768);
        this.p = new u8(0);
        if (dict)
            this.o.set(dict);
    }
```
</details>

### `AsyncInflate(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `astrmify`
- `StrmOpt.call`
- `astrm`

<details><summary>Code</summary>

```typescript
function AsyncInflate(opts, cb) {
        astrmify([
            bInflt,
            function () { return [astrm, Inflate]; }
        ], this, StrmOpt.call(this, opts, cb), function (ev) {
            var strm = new Inflate(ev.data);
            onmessage = astrm(strm);
        }, 7, 0);
    }
```
</details>

### `inflate(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `cbify`
- `pbf`
- `inflateSync`
- `gopt`

<details><summary>Code</summary>

```typescript
export function inflate(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    return cbify(data, opts, [
        bInflt
    ], function (ev) { return pbf(inflateSync(ev.data[0], gopt(ev.data[1]))); }, 1, cb);
}
```
</details>

### `inflateSync(data: any, opts: any): any`

**JSDoc:**
```typescript
/**
 * Expands DEFLATE data with no wrapper
 * @param data The data to decompress
 * @param opts The decompression options
 * @returns The decompressed version of the data
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `any`

**Calls:**

- `inflt`

<details><summary>Code</summary>

```typescript
export function inflateSync(data, opts) {
    return inflt(data, { i: 2 }, opts && opts.out, opts && opts.dictionary);
}
```
</details>

### `Gzip(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `crc`
- `Deflate.call`

<details><summary>Code</summary>

```typescript
function Gzip(opts, cb) {
        this.c = crc();
        this.l = 0;
        this.v = 1;
        Deflate.call(this, opts, cb);
    }
```
</details>

### `AsyncGzip(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `astrmify`
- `StrmOpt.call`
- `astrm`

<details><summary>Code</summary>

```typescript
function AsyncGzip(opts, cb) {
        astrmify([
            bDflt,
            gze,
            function () { return [astrm, Deflate, Gzip]; }
        ], this, StrmOpt.call(this, opts, cb), function (ev) {
            var strm = new Gzip(ev.data);
            onmessage = astrm(strm);
        }, 8, 1);
    }
```
</details>

### `gzip(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `cbify`
- `pbf`
- `gzipSync`

<details><summary>Code</summary>

```typescript
export function gzip(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    return cbify(data, opts, [
        bDflt,
        gze,
        function () { return [gzipSync]; }
    ], function (ev) { return pbf(gzipSync(ev.data[0], ev.data[1])); }, 2, cb);
}
```
</details>

### `gzipSync(data: any, opts: any): Uint8Array<any>`

**JSDoc:**
```typescript
/**
 * Compresses data with GZIP
 * @param data The data to compress
 * @param opts The compression options
 * @returns The gzipped version of the data
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `crc`
- `c.p`
- `dopt`
- `gzhl`
- `gzh`
- `wbytes`
- `c.d`

<details><summary>Code</summary>

```typescript
export function gzipSync(data, opts) {
    if (!opts)
        opts = {};
    var c = crc(), l = data.length;
    c.p(data);
    var d = dopt(data, opts, gzhl(opts), 8), s = d.length;
    return gzh(d, opts), wbytes(d, s - 8, c.d()), wbytes(d, s - 4, l), d;
}
```
</details>

### `Gunzip(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `Inflate.call`

<details><summary>Code</summary>

```typescript
function Gunzip(opts, cb) {
        this.v = 1;
        this.r = 0;
        Inflate.call(this, opts, cb);
    }
```
</details>

### `AsyncGunzip(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `astrmify`
- `StrmOpt.call`
- `postMessage`
- `astrm`
- `_this.onmember`

<details><summary>Code</summary>

```typescript
function AsyncGunzip(opts, cb) {
        var _this = this;
        astrmify([
            bInflt,
            guze,
            function () { return [astrm, Inflate, Gunzip]; }
        ], this, StrmOpt.call(this, opts, cb), function (ev) {
            var strm = new Gunzip(ev.data);
            strm.onmember = function (offset) { return postMessage(offset); };
            onmessage = astrm(strm);
        }, 9, 0, function (offset) { return _this.onmember && _this.onmember(offset); });
    }
```
</details>

### `gunzip(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `cbify`
- `pbf`
- `gunzipSync`

<details><summary>Code</summary>

```typescript
export function gunzip(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    return cbify(data, opts, [
        bInflt,
        guze,
        function () { return [gunzipSync]; }
    ], function (ev) { return pbf(gunzipSync(ev.data[0], ev.data[1])); }, 3, cb);
}
```
</details>

### `gunzipSync(data: any, opts: any): any`

**JSDoc:**
```typescript
/**
 * Expands GZIP data
 * @param data The data to decompress
 * @param opts The decompression options
 * @returns The decompressed version of the data
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `any`

**Calls:**

- `gzs`
- `err`
- `inflt`
- `data.subarray`
- `gzl`

<details><summary>Code</summary>

```typescript
export function gunzipSync(data, opts) {
    var st = gzs(data);
    if (st + 8 > data.length)
        err(6, 'invalid gzip data');
    return inflt(data.subarray(st, -8), { i: 2 }, opts && opts.out || new u8(gzl(data)), opts && opts.dictionary);
}
```
</details>

### `Zlib(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `adler`
- `Deflate.call`

<details><summary>Code</summary>

```typescript
function Zlib(opts, cb) {
        this.c = adler();
        this.v = 1;
        Deflate.call(this, opts, cb);
    }
```
</details>

### `AsyncZlib(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `astrmify`
- `StrmOpt.call`
- `astrm`

<details><summary>Code</summary>

```typescript
function AsyncZlib(opts, cb) {
        astrmify([
            bDflt,
            zle,
            function () { return [astrm, Deflate, Zlib]; }
        ], this, StrmOpt.call(this, opts, cb), function (ev) {
            var strm = new Zlib(ev.data);
            onmessage = astrm(strm);
        }, 10, 1);
    }
```
</details>

### `zlib(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `cbify`
- `pbf`
- `zlibSync`

<details><summary>Code</summary>

```typescript
export function zlib(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    return cbify(data, opts, [
        bDflt,
        zle,
        function () { return [zlibSync]; }
    ], function (ev) { return pbf(zlibSync(ev.data[0], ev.data[1])); }, 4, cb);
}
```
</details>

### `zlibSync(data: any, opts: any): Uint8Array<any>`

**JSDoc:**
```typescript
/**
 * Compress data with Zlib
 * @param data The data to compress
 * @param opts The compression options
 * @returns The zlib-compressed version of the data
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `adler`
- `a.p`
- `dopt`
- `zlh`
- `wbytes`
- `a.d`

<details><summary>Code</summary>

```typescript
export function zlibSync(data, opts) {
    if (!opts)
        opts = {};
    var a = adler();
    a.p(data);
    var d = dopt(data, opts, opts.dictionary ? 6 : 2, 4);
    return zlh(d, opts), wbytes(d, d.length - 4, a.d()), d;
}
```
</details>

### `Unzlib(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `Inflate.call`

<details><summary>Code</summary>

```typescript
function Unzlib(opts, cb) {
        Inflate.call(this, opts, cb);
        this.v = opts && opts.dictionary ? 2 : 1;
    }
```
</details>

### `AsyncUnzlib(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `astrmify`
- `StrmOpt.call`
- `astrm`

<details><summary>Code</summary>

```typescript
function AsyncUnzlib(opts, cb) {
        astrmify([
            bInflt,
            zule,
            function () { return [astrm, Inflate, Unzlib]; }
        ], this, StrmOpt.call(this, opts, cb), function (ev) {
            var strm = new Unzlib(ev.data);
            onmessage = astrm(strm);
        }, 11, 0);
    }
```
</details>

### `unzlib(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `cbify`
- `pbf`
- `unzlibSync`
- `gopt`

<details><summary>Code</summary>

```typescript
export function unzlib(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    return cbify(data, opts, [
        bInflt,
        zule,
        function () { return [unzlibSync]; }
    ], function (ev) { return pbf(unzlibSync(ev.data[0], gopt(ev.data[1]))); }, 5, cb);
}
```
</details>

### `unzlibSync(data: any, opts: any): any`

**JSDoc:**
```typescript
/**
 * Expands Zlib data
 * @param data The data to decompress
 * @param opts The decompression options
 * @returns The decompressed version of the data
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `any`

**Calls:**

- `inflt`
- `data.subarray`
- `zls`

<details><summary>Code</summary>

```typescript
export function unzlibSync(data, opts) {
    return inflt(data.subarray(zls(data, opts && opts.dictionary), -4), { i: 2 }, opts && opts.out, opts && opts.dictionary);
}
```
</details>

### `Decompress(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `StrmOpt.call`

<details><summary>Code</summary>

```typescript
function Decompress(opts, cb) {
        this.o = StrmOpt.call(this, opts, cb) || {};
        this.G = Gunzip;
        this.I = Inflate;
        this.Z = Unzlib;
    }
```
</details>

### `AsyncDecompress(opts: any, cb: any): void`

**Parameters:**

- **`opts`** `any`
- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `Decompress.call`

<details><summary>Code</summary>

```typescript
function AsyncDecompress(opts, cb) {
        Decompress.call(this, opts, cb);
        this.queuedSize = 0;
        this.G = AsyncGunzip;
        this.I = AsyncInflate;
        this.Z = AsyncUnzlib;
    }
```
</details>

### `decompress(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `gunzip`
- `inflate`
- `unzlib`

<details><summary>Code</summary>

```typescript
export function decompress(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    return (data[0] == 31 && data[1] == 139 && data[2] == 8)
        ? gunzip(data, opts, cb)
        : ((data[0] & 15) != 8 || (data[0] >> 4) > 7 || ((data[0] << 8 | data[1]) % 31))
            ? inflate(data, opts, cb)
            : unzlib(data, opts, cb);
}
```
</details>

### `decompressSync(data: any, opts: any): any`

**JSDoc:**
```typescript
/**
 * Expands compressed GZIP, Zlib, or raw DEFLATE data, automatically detecting the format
 * @param data The data to decompress
 * @param opts The decompression options
 * @returns The decompressed version of the data
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `any`

**Calls:**

- `gunzipSync`
- `inflateSync`
- `unzlibSync`

<details><summary>Code</summary>

```typescript
export function decompressSync(data, opts) {
    return (data[0] == 31 && data[1] == 139 && data[2] == 8)
        ? gunzipSync(data, opts)
        : ((data[0] & 15) != 8 || (data[0] >> 4) > 7 || ((data[0] << 8 | data[1]) % 31))
            ? inflateSync(data, opts)
            : unzlibSync(data, opts);
}
```
</details>

### `fltn(d: any, p: any, t: any, o: any): void`

**Parameters:**

- **`d`** `any`
- **`p`** `any`
- **`t`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `mrg`
- `fltn`

<details><summary>Code</summary>

```typescript
function (d, p, t, o) {
    for (var k in d) {
        var val = d[k], n = p + k, op = o;
        if (Array.isArray(val))
            op = mrg(o, val[1]), val = val[0];
        if (val instanceof u8)
            t[n] = [val, op];
        else {
            t[n += '/'] = [new u8(0), op];
            fltn(val, n, t, o);
        }
    }
}
```
</details>

### `dutf8(d: any): { s: string; r: Uint8Array<any>; }`

**Parameters:**

- **`d`** `any`

**Returns:** `{ s: string; r: Uint8Array<any>; }`

**Calls:**

- `slc`
- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function (d) {
    for (var r = '', i = 0;;) {
        var c = d[i++];
        var eb = (c > 127) + (c > 223) + (c > 239);
        if (i + eb > d.length)
            return { s: r, r: slc(d, i - 1) };
        if (!eb)
            r += String.fromCharCode(c);
        else if (eb == 3) {
            c = ((c & 15) << 18 | (d[i++] & 63) << 12 | (d[i++] & 63) << 6 | (d[i++] & 63)) - 65536,
                r += String.fromCharCode(55296 | (c >> 10), 56320 | (c & 1023));
        }
        else if (eb & 1)
            r += String.fromCharCode((c & 31) << 6 | (d[i++] & 63));
        else
            r += String.fromCharCode((c & 15) << 12 | (d[i++] & 63) << 6 | (d[i++] & 63));
    }
}
```
</details>

### `DecodeUTF8(cb: any): void`

**JSDoc:**
```typescript
/**
     * Creates a UTF-8 decoding stream
     * @param cb The callback to call whenever data is decoded
     */
```

**Parameters:**

- **`cb`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function DecodeUTF8(cb) {
        this.ondata = cb;
        if (tds)
            this.t = new TextDecoder();
        else
            this.p = et;
    }
```
</details>

### `EncodeUTF8(cb: any): void`

**JSDoc:**
```typescript
/**
     * Creates a UTF-8 decoding stream
     * @param cb The callback to call whenever data is encoded
     */
```

**Parameters:**

- **`cb`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function EncodeUTF8(cb) {
        this.ondata = cb;
    }
```
</details>

### `strToU8(str: any, latin1: any): Uint8Array<any>`

**JSDoc:**
```typescript
/**
 * Converts a string into a Uint8Array for use with compression/decompression methods
 * @param str The string to encode
 * @param latin1 Whether or not to interpret the data as Latin-1. This should
 *               not need to be true unless decoding a binary string.
 * @returns The string encoded in UTF-8/Latin-1 binary
 */
```

**Parameters:**

- **`str`** `any`
- **`latin1`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `str.charCodeAt`
- `te.encode`
- `n.set`
- `w`
- `slc`

<details><summary>Code</summary>

```typescript
export function strToU8(str, latin1) {
    if (latin1) {
        var ar_1 = new u8(str.length);
        for (var i = 0; i < str.length; ++i)
            ar_1[i] = str.charCodeAt(i);
        return ar_1;
    }
    if (te)
        return te.encode(str);
    var l = str.length;
    var ar = new u8(str.length + (str.length >> 1));
    var ai = 0;
    var w = function (v) { ar[ai++] = v; };
    for (var i = 0; i < l; ++i) {
        if (ai + 5 > ar.length) {
            var n = new u8(ai + 8 + ((l - i) << 1));
            n.set(ar);
            ar = n;
        }
        var c = str.charCodeAt(i);
        if (c < 128 || latin1)
            w(c);
        else if (c < 2048)
            w(192 | (c >> 6)), w(128 | (c & 63));
        else if (c > 55295 && c < 57344)
            c = 65536 + (c & 1023 << 10) | (str.charCodeAt(++i) & 1023),
                w(240 | (c >> 18)), w(128 | ((c >> 12) & 63)), w(128 | ((c >> 6) & 63)), w(128 | (c & 63));
        else
            w(224 | (c >> 12)), w(128 | ((c >> 6) & 63)), w(128 | (c & 63));
    }
    return slc(ar, 0, ai);
}
```
</details>

### `w(v: any): void`

**Parameters:**

- **`v`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (v) { ar[ai++] = v; }
```
</details>

### `strFromU8(dat: any, latin1: any): string`

**JSDoc:**
```typescript
/**
 * Converts a Uint8Array to a string
 * @param dat The data to decode to string
 * @param latin1 Whether or not to interpret the data as Latin-1. This should
 *               not need to be true unless encoding to binary string.
 * @returns The original UTF-8/Latin-1 string
 */
```

**Parameters:**

- **`dat`** `any`
- **`latin1`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode.apply`
- `dat.subarray`
- `td.decode`
- `dutf8`
- `err`

<details><summary>Code</summary>

```typescript
export function strFromU8(dat, latin1) {
    if (latin1) {
        var r = '';
        for (var i = 0; i < dat.length; i += 16384)
            r += String.fromCharCode.apply(null, dat.subarray(i, i + 16384));
        return r;
    }
    else if (td) {
        return td.decode(dat);
    }
    else {
        var _a = dutf8(dat), s = _a.s, r = _a.r;
        if (r.length)
            err(8);
        return s;
    }
}
```
</details>

### `dbf(l: any): 1 | 2 | 3 | 0`

**Parameters:**

- **`l`** `any`

**Returns:** `1 | 2 | 3 | 0`

<details><summary>Code</summary>

```typescript
function (l) { return l == 1 ? 3 : l < 6 ? 2 : l == 9 ? 1 : 0; }
```
</details>

### `slzh(d: any, b: any): any`

**Parameters:**

- **`d`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `b2`

<details><summary>Code</summary>

```typescript
function (d, b) { return b + 30 + b2(d, b + 26) + b2(d, b + 28); }
```
</details>

### `zh(d: any, b: any, z: any): any[]`

**Parameters:**

- **`d`** `any`
- **`b`** `any`
- **`z`** `any`

**Returns:** `any[]`

**Calls:**

- `b2`
- `strFromU8`
- `d.subarray`
- `b4`
- `z64e`

<details><summary>Code</summary>

```typescript
function (d, b, z) {
    var fnl = b2(d, b + 28), fn = strFromU8(d.subarray(b + 46, b + 46 + fnl), !(b2(d, b + 8) & 2048)), es = b + 46 + fnl, bs = b4(d, b + 20);
    var _a = z && bs == 4294967295 ? z64e(d, es) : [bs, b4(d, b + 24), b4(d, b + 42)], sc = _a[0], su = _a[1], off = _a[2];
    return [b2(d, b + 10), sc, su, fn, es + b2(d, b + 30) + b2(d, b + 32), off];
}
```
</details>

### `z64e(d: any, b: any): number[]`

**Parameters:**

- **`d`** `any`
- **`b`** `any`

**Returns:** `number[]`

**Calls:**

- `b2`
- `b8`

<details><summary>Code</summary>

```typescript
function (d, b) {
    for (; b2(d, b) != 1; b += 4 + b2(d, b + 2))
        ;
    return [b8(d, b + 12), b8(d, b + 4), b8(d, b + 20)];
}
```
</details>

### `exfl(ex: any): number`

**Parameters:**

- **`ex`** `any`

**Returns:** `number`

**Calls:**

- `err`

<details><summary>Code</summary>

```typescript
function (ex) {
    var le = 0;
    if (ex) {
        for (var k in ex) {
            var l = ex[k].length;
            if (l > 65535)
                err(9);
            le += l + 4;
        }
    }
    return le;
}
```
</details>

### `wzh(d: any, b: any, f: any, fn: any, u: any, c: any, ce: any, co: any): any`

**Parameters:**

- **`d`** `any`
- **`b`** `any`
- **`f`** `any`
- **`fn`** `any`
- **`u`** `any`
- **`c`** `any`
- **`ce`** `any`
- **`co`** `any`

**Returns:** `any`

**Calls:**

- `exfl`
- `wbytes`
- `Date.now`
- `dt.getFullYear`
- `err`
- `dt.getMonth`
- `dt.getDate`
- `dt.getHours`
- `dt.getMinutes`
- `dt.getSeconds`
- `d.set`

<details><summary>Code</summary>

```typescript
function (d, b, f, fn, u, c, ce, co) {
    var fl = fn.length, ex = f.extra, col = co && co.length;
    var exl = exfl(ex);
    wbytes(d, b, ce != null ? 0x2014B50 : 0x4034B50), b += 4;
    if (ce != null)
        d[b++] = 20, d[b++] = f.os;
    d[b] = 20, b += 2; // spec compliance? what's that?
    d[b++] = (f.flag << 1) | (c < 0 && 8), d[b++] = u && 8;
    d[b++] = f.compression & 255, d[b++] = f.compression >> 8;
    var dt = new Date(f.mtime == null ? Date.now() : f.mtime), y = dt.getFullYear() - 1980;
    if (y < 0 || y > 119)
        err(10);
    wbytes(d, b, (y << 25) | ((dt.getMonth() + 1) << 21) | (dt.getDate() << 16) | (dt.getHours() << 11) | (dt.getMinutes() << 5) | (dt.getSeconds() >> 1)), b += 4;
    if (c != -1) {
        wbytes(d, b, f.crc);
        wbytes(d, b + 4, c < 0 ? -c - 2 : c);
        wbytes(d, b + 8, f.size);
    }
    wbytes(d, b + 12, fl);
    wbytes(d, b + 14, exl), b += 16;
    if (ce != null) {
        wbytes(d, b, col);
        wbytes(d, b + 6, f.attrs);
        wbytes(d, b + 10, ce), b += 14;
    }
    d.set(fn, b);
    b += fl;
    if (exl) {
        for (var k in ex) {
            var exf = ex[k], l = exf.length;
            wbytes(d, b, +k);
            wbytes(d, b + 2, l);
            d.set(exf, b + 4), b += 4 + l;
        }
    }
    if (col)
        d.set(co, b), b += col;
    return b;
}
```
</details>

### `wzf(o: any, b: any, c: any, d: any, e: any): void`

**Parameters:**

- **`o`** `any`
- **`b`** `any`
- **`c`** `any`
- **`d`** `any`
- **`e`** `any`

**Returns:** `void`

**Calls:**

- `wbytes`

<details><summary>Code</summary>

```typescript
function (o, b, c, d, e) {
    wbytes(o, b, 0x6054B50); // skip disk
    wbytes(o, b + 8, c);
    wbytes(o, b + 10, c);
    wbytes(o, b + 12, d);
    wbytes(o, b + 16, e);
}
```
</details>

### `ZipPassThrough(filename: any): void`

**JSDoc:**
```typescript
/**
     * Creates a pass-through stream that can be added to ZIP archives
     * @param filename The filename to associate with this data stream
     */
```

**Parameters:**

- **`filename`** `any`

**Returns:** `void`

**Calls:**

- `crc`

<details><summary>Code</summary>

```typescript
function ZipPassThrough(filename) {
        this.filename = filename;
        this.c = crc();
        this.size = 0;
        this.compression = 0;
    }
```
</details>

### `ZipDeflate(filename: any, opts: any): void`

**JSDoc:**
```typescript
/**
     * Creates a DEFLATE stream that can be added to ZIP archives
     * @param filename The filename to associate with this data stream
     * @param opts The compression options
     */
```

**Parameters:**

- **`filename`** `any`
- **`opts`** `any`

**Returns:** `void`

**Calls:**

- `ZipPassThrough.call`
- `_this.ondata`
- `dbf`

<details><summary>Code</summary>

```typescript
function ZipDeflate(filename, opts) {
        var _this = this;
        if (!opts)
            opts = {};
        ZipPassThrough.call(this, filename);
        this.d = new Deflate(opts, function (dat, final) {
            _this.ondata(null, dat, final);
        });
        this.compression = 8;
        this.flag = dbf(opts.level);
    }
```
</details>

### `AsyncZipDeflate(filename: any, opts: any): void`

**JSDoc:**
```typescript
/**
     * Creates an asynchronous DEFLATE stream that can be added to ZIP archives
     * @param filename The filename to associate with this data stream
     * @param opts The compression options
     */
```

**Parameters:**

- **`filename`** `any`
- **`opts`** `any`

**Returns:** `void`

**Calls:**

- `ZipPassThrough.call`
- `_this.ondata`
- `dbf`

<details><summary>Code</summary>

```typescript
function AsyncZipDeflate(filename, opts) {
        var _this = this;
        if (!opts)
            opts = {};
        ZipPassThrough.call(this, filename);
        this.d = new AsyncDeflate(opts, function (err, dat, final) {
            _this.ondata(err, dat, final);
        });
        this.compression = 8;
        this.flag = dbf(opts.level);
        this.terminate = this.d.terminate;
    }
```
</details>

### `Zip(cb: any): void`

**JSDoc:**
```typescript
/**
     * Creates an empty ZIP archive to which files can be added
     * @param cb The callback to call whenever data for the generated ZIP archive
     *           is available
     */
```

**Parameters:**

- **`cb`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Zip(cb) {
        this.ondata = cb;
        this.u = [];
        this.d = 1;
    }
```
</details>

### `pAll_1(): void`

**Returns:** `void`

**Calls:**

- `_this.ondata`

<details><summary>Code</summary>

```typescript
function () {
                for (var _i = 0, chks_2 = chks_1; _i < chks_2.length; _i++) {
                    var chk = chks_2[_i];
                    _this.ondata(null, chk, false);
                }
                chks_1 = [];
            }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `_this.u.splice`
- `_this.e`

<details><summary>Code</summary>

```typescript
function () {
                    if (!(_this.d & 1))
                        return;
                    _this.u.splice(-1, 1);
                    _this.e();
                }
```
</details>

### `t(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `_this.u.splice`
- `_this.e`

<details><summary>Code</summary>

```typescript
function () {
                    if (!(_this.d & 1))
                        return;
                    _this.u.splice(-1, 1);
                    _this.e();
                }
```
</details>

### `t(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `t(): void`

**Returns:** `void`

**Calls:**

- `file.terminate`

<details><summary>Code</summary>

```typescript
function () {
                    if (file.terminate)
                        file.terminate();
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `pAll_1`
- `nxt.r`

<details><summary>Code</summary>

```typescript
function () {
                    pAll_1();
                    if (tr_1) {
                        var nxt = _this.u[ind_1 + 1];
                        if (nxt)
                            nxt.r();
                        else
                            _this.d = 1;
                    }
                    tr_1 = 1;
                }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `_this.u.splice`
- `_this.e`

<details><summary>Code</summary>

```typescript
function () {
                    if (!(_this.d & 1))
                        return;
                    _this.u.splice(-1, 1);
                    _this.e();
                }
```
</details>

### `t(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { }
```
</details>

### `r(): void`

**Returns:** `void`

**Calls:**

- `_this.u.splice`
- `_this.e`

<details><summary>Code</summary>

```typescript
function () {
                    if (!(_this.d & 1))
                        return;
                    _this.u.splice(-1, 1);
                    _this.e();
                }
```
</details>

### `t(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { }
```
</details>

### `zip(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `fltn`
- `Object.keys`
- `complex_call_73037`
- `mt`
- `cb`
- `wzh`
- `exfl`
- `out.set`
- `cbd`
- `wzf`
- `cbf`
- `crc`
- `c.p`
- `strToU8`
- `tAll`
- `mrg`
- `c.d`
- `cbl`
- `deflateSync`
- `term.push`
- `deflate`
- `_loop_1`

**Internal Comments:**
```
// Cannot use lft because it can decrease
```

<details><summary>Code</summary>

```typescript
export function zip(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    var r = {};
    fltn(data, '', r, opts);
    var k = Object.keys(r);
    var lft = k.length, o = 0, tot = 0;
    var slft = lft, files = new Array(lft);
    var term = [];
    var tAll = function () {
        for (var i = 0; i < term.length; ++i)
            term[i]();
    };
    var cbd = function (a, b) {
        mt(function () { cb(a, b); });
    };
    mt(function () { cbd = cb; });
    var cbf = function () {
        var out = new u8(tot + 22), oe = o, cdl = tot - o;
        tot = 0;
        for (var i = 0; i < slft; ++i) {
            var f = files[i];
            try {
                var l = f.c.length;
                wzh(out, tot, f, f.f, f.u, l);
                var badd = 30 + f.f.length + exfl(f.extra);
                var loc = tot + badd;
                out.set(f.c, loc);
                wzh(out, o, f, f.f, f.u, l, tot, f.m), o += 16 + badd + (f.m ? f.m.length : 0), tot = loc + l;
            }
            catch (e) {
                return cbd(e, null);
            }
        }
        wzf(out, o, files.length, cdl, oe);
        cbd(null, out);
    };
    if (!lft)
        cbf();
    var _loop_1 = function (i) {
        var fn = k[i];
        var _a = r[fn], file = _a[0], p = _a[1];
        var c = crc(), size = file.length;
        c.p(file);
        var f = strToU8(fn), s = f.length;
        var com = p.comment, m = com && strToU8(com), ms = m && m.length;
        var exl = exfl(p.extra);
        var compression = p.level == 0 ? 0 : 8;
        var cbl = function (e, d) {
            if (e) {
                tAll();
                cbd(e, null);
            }
            else {
                var l = d.length;
                files[i] = mrg(p, {
                    size: size,
                    crc: c.d(),
                    c: d,
                    f: f,
                    m: m,
                    u: s != fn.length || (m && (com.length != ms)),
                    compression: compression
                });
                o += 30 + s + exl + l;
                tot += 76 + 2 * (s + exl) + (ms || 0) + l;
                if (!--lft)
                    cbf();
            }
        };
        if (s > 65535)
            cbl(err(11, 0, 1), null);
        if (!compression)
            cbl(null, file);
        else if (size < 160000) {
            try {
                cbl(null, deflateSync(file, p));
            }
            catch (e) {
                cbl(e, null);
            }
        }
        else
            term.push(deflate(file, p, cbl));
    };
    // Cannot use lft because it can decrease
    for (var i = 0; i < slft; ++i) {
        _loop_1(i);
    }
    return tAll;
}
```
</details>

### `tAll(): void`

**Returns:** `void`

**Calls:**

- `complex_call_73037`

<details><summary>Code</summary>

```typescript
function () {
        for (var i = 0; i < term.length; ++i)
            term[i]();
    }
```
</details>

### `cbd(a: any, b: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `void`

**Calls:**

- `mt`
- `cb`

<details><summary>Code</summary>

```typescript
function (a, b) {
        mt(function () { cb(a, b); });
    }
```
</details>

### `cbf(): void`

**Returns:** `void`

**Calls:**

- `wzh`
- `exfl`
- `out.set`
- `cbd`
- `wzf`

<details><summary>Code</summary>

```typescript
function () {
        var out = new u8(tot + 22), oe = o, cdl = tot - o;
        tot = 0;
        for (var i = 0; i < slft; ++i) {
            var f = files[i];
            try {
                var l = f.c.length;
                wzh(out, tot, f, f.f, f.u, l);
                var badd = 30 + f.f.length + exfl(f.extra);
                var loc = tot + badd;
                out.set(f.c, loc);
                wzh(out, o, f, f.f, f.u, l, tot, f.m), o += 16 + badd + (f.m ? f.m.length : 0), tot = loc + l;
            }
            catch (e) {
                return cbd(e, null);
            }
        }
        wzf(out, o, files.length, cdl, oe);
        cbd(null, out);
    }
```
</details>

### `_loop_1(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `crc`
- `c.p`
- `strToU8`
- `exfl`
- `tAll`
- `cbd`
- `mrg`
- `c.d`
- `cbf`
- `cbl`
- `err`
- `deflateSync`
- `term.push`
- `deflate`

<details><summary>Code</summary>

```typescript
function (i) {
        var fn = k[i];
        var _a = r[fn], file = _a[0], p = _a[1];
        var c = crc(), size = file.length;
        c.p(file);
        var f = strToU8(fn), s = f.length;
        var com = p.comment, m = com && strToU8(com), ms = m && m.length;
        var exl = exfl(p.extra);
        var compression = p.level == 0 ? 0 : 8;
        var cbl = function (e, d) {
            if (e) {
                tAll();
                cbd(e, null);
            }
            else {
                var l = d.length;
                files[i] = mrg(p, {
                    size: size,
                    crc: c.d(),
                    c: d,
                    f: f,
                    m: m,
                    u: s != fn.length || (m && (com.length != ms)),
                    compression: compression
                });
                o += 30 + s + exl + l;
                tot += 76 + 2 * (s + exl) + (ms || 0) + l;
                if (!--lft)
                    cbf();
            }
        };
        if (s > 65535)
            cbl(err(11, 0, 1), null);
        if (!compression)
            cbl(null, file);
        else if (size < 160000) {
            try {
                cbl(null, deflateSync(file, p));
            }
            catch (e) {
                cbl(e, null);
            }
        }
        else
            term.push(deflate(file, p, cbl));
    }
```
</details>

### `cbl(e: any, d: any): void`

**Parameters:**

- **`e`** `any`
- **`d`** `any`

**Returns:** `void`

**Calls:**

- `tAll`
- `cbd`
- `mrg`
- `c.d`
- `cbf`

<details><summary>Code</summary>

```typescript
function (e, d) {
            if (e) {
                tAll();
                cbd(e, null);
            }
            else {
                var l = d.length;
                files[i] = mrg(p, {
                    size: size,
                    crc: c.d(),
                    c: d,
                    f: f,
                    m: m,
                    u: s != fn.length || (m && (com.length != ms)),
                    compression: compression
                });
                o += 30 + s + exl + l;
                tot += 76 + 2 * (s + exl) + (ms || 0) + l;
                if (!--lft)
                    cbf();
            }
        }
```
</details>

### `zipSync(data: any, opts: any): Uint8Array<ArrayBuffer>`

**JSDoc:**
```typescript
/**
 * Synchronously creates a ZIP file. Prefer using `zip` for better performance
 * with more than one file.
 * @param data The directory structure for the ZIP archive
 * @param opts The main options, merged with per-file options
 * @returns The generated ZIP archive
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `Uint8Array<ArrayBuffer>`

**Calls:**

- `fltn`
- `strToU8`
- `exfl`
- `err`
- `deflateSync`
- `crc`
- `c.p`
- `files.push`
- `mrg`
- `c.d`
- `wzh`
- `out.set`
- `wzf`

<details><summary>Code</summary>

```typescript
export function zipSync(data, opts) {
    if (!opts)
        opts = {};
    var r = {};
    var files = [];
    fltn(data, '', r, opts);
    var o = 0;
    var tot = 0;
    for (var fn in r) {
        var _a = r[fn], file = _a[0], p = _a[1];
        var compression = p.level == 0 ? 0 : 8;
        var f = strToU8(fn), s = f.length;
        var com = p.comment, m = com && strToU8(com), ms = m && m.length;
        var exl = exfl(p.extra);
        if (s > 65535)
            err(11);
        var d = compression ? deflateSync(file, p) : file, l = d.length;
        var c = crc();
        c.p(file);
        files.push(mrg(p, {
            size: file.length,
            crc: c.d(),
            c: d,
            f: f,
            m: m,
            u: s != fn.length || (m && (com.length != ms)),
            o: o,
            compression: compression
        }));
        o += 30 + s + exl + l;
        tot += 76 + 2 * (s + exl) + (ms || 0) + l;
    }
    var out = new u8(tot + 22), oe = o, cdl = tot - o;
    for (var i = 0; i < files.length; ++i) {
        var f = files[i];
        wzh(out, f.o, f, f.f, f.u, f.c.length);
        var badd = 30 + f.f.length + exfl(f.extra);
        out.set(f.c, f.o + badd);
        wzh(out, o, f, f.f, f.u, f.c.length, f.o, f.m), o += 16 + badd + (f.m ? f.m.length : 0);
    }
    wzf(out, o, files.length, cdl, oe);
    return out;
}
```
</details>

### `UnzipPassThrough(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function UnzipPassThrough() {
    }
```
</details>

### `UnzipInflate(): void`

**JSDoc:**
```typescript
/**
     * Creates a DEFLATE decompression that can be used in ZIP archives
     */
```

**Returns:** `void`

**Calls:**

- `_this.ondata`

<details><summary>Code</summary>

```typescript
function UnzipInflate() {
        var _this = this;
        this.i = new Inflate(function (dat, final) {
            _this.ondata(null, dat, final);
        });
    }
```
</details>

### `AsyncUnzipInflate(_: any, sz: any): void`

**JSDoc:**
```typescript
/**
     * Creates a DEFLATE decompression that can be used in ZIP archives
     */
```

**Parameters:**

- **`_`** `any`
- **`sz`** `any`

**Returns:** `void`

**Calls:**

- `_this.ondata`

<details><summary>Code</summary>

```typescript
function AsyncUnzipInflate(_, sz) {
        var _this = this;
        if (sz < 320000) {
            this.i = new Inflate(function (dat, final) {
                _this.ondata(null, dat, final);
            });
        }
        else {
            this.i = new AsyncInflate(function (err, dat, final) {
                _this.ondata(err, dat, final);
            });
            this.terminate = this.i.terminate;
        }
    }
```
</details>

### `Unzip(cb: any): void`

**JSDoc:**
```typescript
/**
     * Creates a ZIP decompression stream
     * @param cb The callback to call whenever a file in the ZIP archive is found
     */
```

**Parameters:**

- **`cb`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Unzip(cb) {
        this.onfile = cb;
        this.k = [];
        this.o = {
            0: UnzipPassThrough
        };
        this.p = et;
    }
```
</details>

### `_loop_2(): string`

**Returns:** `string`

**Calls:**

- `b4`
- `b2`
- `this_1.k.unshift`
- `strFromU8`
- `buf.subarray`
- `z64e`
- `err`
- `file_1.ondata`
- `d_1.push`
- `d_1.terminate`
- `this_1.onfile`

<details><summary>Code</summary>

```typescript
function () {
                var _a;
                var sig = b4(buf, i);
                if (sig == 0x4034B50) {
                    f = 1, is = i;
                    this_1.d = null;
                    this_1.c = 0;
                    var bf = b2(buf, i + 6), cmp_1 = b2(buf, i + 8), u = bf & 2048, dd = bf & 8, fnl = b2(buf, i + 26), es = b2(buf, i + 28);
                    if (l > i + 30 + fnl + es) {
                        var chks_3 = [];
                        this_1.k.unshift(chks_3);
                        f = 2;
                        var sc_1 = b4(buf, i + 18), su_1 = b4(buf, i + 22);
                        var fn_1 = strFromU8(buf.subarray(i + 30, i += 30 + fnl), !u);
                        if (sc_1 == 4294967295) {
                            _a = dd ? [-2] : z64e(buf, i), sc_1 = _a[0], su_1 = _a[1];
                        }
                        else if (dd)
                            sc_1 = -1;
                        i += es;
                        this_1.c = sc_1;
                        var d_1;
                        var file_1 = {
                            name: fn_1,
                            compression: cmp_1,
                            start: function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            },
                            terminate: function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
                        };
                        if (sc_1 >= 0)
                            file_1.size = sc_1, file_1.originalSize = su_1;
                        this_1.onfile(file_1);
                    }
                    return "break";
                }
                else if (oc) {
                    if (sig == 0x8074B50) {
                        is = i += 12 + (oc == -2 && 8), f = 3, this_1.c = 0;
                        return "break";
                    }
                    else if (sig == 0x2014B50) {
                        is = i -= 4, f = 3, this_1.c = 0;
                        return "break";
                    }
                }
            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `err`
- `file_1.ondata`
- `d_1.push`

<details><summary>Code</summary>

```typescript
function () {
                                if (!file_1.ondata)
                                    err(5);
                                if (!sc_1)
                                    file_1.ondata(null, et, true);
                                else {
                                    var ctr = _this.o[cmp_1];
                                    if (!ctr)
                                        file_1.ondata(err(14, 'unknown compression type ' + cmp_1, 1), null, false);
                                    d_1 = sc_1 < 0 ? new ctr(fn_1) : new ctr(fn_1, sc_1, su_1);
                                    d_1.ondata = function (err, dat, final) { file_1.ondata(err, dat, final); };
                                    for (var _i = 0, chks_4 = chks_3; _i < chks_4.length; _i++) {
                                        var dat = chks_4[_i];
                                        d_1.push(dat, false);
                                    }
                                    if (_this.k[0] == chks_3 && _this.c)
                                        _this.d = d_1;
                                    else
                                        d_1.push(et, true);
                                }
                            }
```
</details>

### `terminate(): void`

**Returns:** `void`

**Calls:**

- `d_1.terminate`

<details><summary>Code</summary>

```typescript
function () {
                                if (d_1 && d_1.terminate)
                                    d_1.terminate();
                            }
```
</details>

### `unzip(data: any, opts: any, cb: any): () => void`

**Parameters:**

- **`data`** `any`
- **`opts`** `any`
- **`cb`** `any`

**Returns:** `() => void`

**Calls:**

- `err`
- `complex_call_85481`
- `mt`
- `cb`
- `b4`
- `cbd`
- `b2`
- `zh`
- `slzh`
- `tAll`
- `fltr`
- `cbl`
- `slc`
- `data.subarray`
- `inflateSync`
- `term.push`
- `inflate`
- `_loop_3`

**Internal Comments:**
```
// Synchronously decompress under 512KB, or barely-compressed data
```

<details><summary>Code</summary>

```typescript
export function unzip(data, opts, cb) {
    if (!cb)
        cb = opts, opts = {};
    if (typeof cb != 'function')
        err(7);
    var term = [];
    var tAll = function () {
        for (var i = 0; i < term.length; ++i)
            term[i]();
    };
    var files = {};
    var cbd = function (a, b) {
        mt(function () { cb(a, b); });
    };
    mt(function () { cbd = cb; });
    var e = data.length - 22;
    for (; b4(data, e) != 0x6054B50; --e) {
        if (!e || data.length - e > 65558) {
            cbd(err(13, 0, 1), null);
            return tAll;
        }
    }
    ;
    var lft = b2(data, e + 8);
    if (lft) {
        var c = lft;
        var o = b4(data, e + 16);
        var z = o == 4294967295 || c == 65535;
        if (z) {
            var ze = b4(data, e - 12);
            z = b4(data, ze) == 0x6064B50;
            if (z) {
                c = lft = b4(data, ze + 32);
                o = b4(data, ze + 48);
            }
        }
        var fltr = opts && opts.filter;
        var _loop_3 = function (i) {
            var _a = zh(data, o, z), c_1 = _a[0], sc = _a[1], su = _a[2], fn = _a[3], no = _a[4], off = _a[5], b = slzh(data, off);
            o = no;
            var cbl = function (e, d) {
                if (e) {
                    tAll();
                    cbd(e, null);
                }
                else {
                    if (d)
                        files[fn] = d;
                    if (!--lft)
                        cbd(null, files);
                }
            };
            if (!fltr || fltr({
                name: fn,
                size: sc,
                originalSize: su,
                compression: c_1
            })) {
                if (!c_1)
                    cbl(null, slc(data, b, b + sc));
                else if (c_1 == 8) {
                    var infl = data.subarray(b, b + sc);
                    // Synchronously decompress under 512KB, or barely-compressed data
                    if (su < 524288 || sc > 0.8 * su) {
                        try {
                            cbl(null, inflateSync(infl, { out: new u8(su) }));
                        }
                        catch (e) {
                            cbl(e, null);
                        }
                    }
                    else
                        term.push(inflate(infl, { size: su }, cbl));
                }
                else
                    cbl(err(14, 'unknown compression type ' + c_1, 1), null);
            }
            else
                cbl(null, null);
        };
        for (var i = 0; i < c; ++i) {
            _loop_3(i);
        }
    }
    else
        cbd(null, {});
    return tAll;
}
```
</details>

### `tAll(): void`

**Returns:** `void`

**Calls:**

- `complex_call_85481`

<details><summary>Code</summary>

```typescript
function () {
        for (var i = 0; i < term.length; ++i)
            term[i]();
    }
```
</details>

### `cbd(a: any, b: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `void`

**Calls:**

- `mt`
- `cb`

<details><summary>Code</summary>

```typescript
function (a, b) {
        mt(function () { cb(a, b); });
    }
```
</details>

### `_loop_3(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `zh`
- `slzh`
- `tAll`
- `cbd`
- `fltr`
- `cbl`
- `slc`
- `data.subarray`
- `inflateSync`
- `term.push`
- `inflate`
- `err`

**Internal Comments:**
```
// Synchronously decompress under 512KB, or barely-compressed data
```

<details><summary>Code</summary>

```typescript
function (i) {
            var _a = zh(data, o, z), c_1 = _a[0], sc = _a[1], su = _a[2], fn = _a[3], no = _a[4], off = _a[5], b = slzh(data, off);
            o = no;
            var cbl = function (e, d) {
                if (e) {
                    tAll();
                    cbd(e, null);
                }
                else {
                    if (d)
                        files[fn] = d;
                    if (!--lft)
                        cbd(null, files);
                }
            };
            if (!fltr || fltr({
                name: fn,
                size: sc,
                originalSize: su,
                compression: c_1
            })) {
                if (!c_1)
                    cbl(null, slc(data, b, b + sc));
                else if (c_1 == 8) {
                    var infl = data.subarray(b, b + sc);
                    // Synchronously decompress under 512KB, or barely-compressed data
                    if (su < 524288 || sc > 0.8 * su) {
                        try {
                            cbl(null, inflateSync(infl, { out: new u8(su) }));
                        }
                        catch (e) {
                            cbl(e, null);
                        }
                    }
                    else
                        term.push(inflate(infl, { size: su }, cbl));
                }
                else
                    cbl(err(14, 'unknown compression type ' + c_1, 1), null);
            }
            else
                cbl(null, null);
        }
```
</details>

### `cbl(e: any, d: any): void`

**Parameters:**

- **`e`** `any`
- **`d`** `any`

**Returns:** `void`

**Calls:**

- `tAll`
- `cbd`

<details><summary>Code</summary>

```typescript
function (e, d) {
                if (e) {
                    tAll();
                    cbd(e, null);
                }
                else {
                    if (d)
                        files[fn] = d;
                    if (!--lft)
                        cbd(null, files);
                }
            }
```
</details>

### `unzipSync(data: any, opts: any): {}`

**JSDoc:**
```typescript
/**
 * Synchronously decompresses a ZIP archive. Prefer using `unzip` for better
 * performance with more than one file.
 * @param data The raw compressed ZIP file
 * @param opts The ZIP extraction options
 * @returns The decompressed files
 */
```

**Parameters:**

- **`data`** `any`
- **`opts`** `any`

**Returns:** `{}`

**Calls:**

- `b4`
- `err`
- `b2`
- `zh`
- `slzh`
- `fltr`
- `slc`
- `inflateSync`
- `data.subarray`

<details><summary>Code</summary>

```typescript
export function unzipSync(data, opts) {
    var files = {};
    var e = data.length - 22;
    for (; b4(data, e) != 0x6054B50; --e) {
        if (!e || data.length - e > 65558)
            err(13);
    }
    ;
    var c = b2(data, e + 8);
    if (!c)
        return {};
    var o = b4(data, e + 16);
    var z = o == 4294967295 || c == 65535;
    if (z) {
        var ze = b4(data, e - 12);
        z = b4(data, ze) == 0x6064B50;
        if (z) {
            c = b4(data, ze + 32);
            o = b4(data, ze + 48);
        }
    }
    var fltr = opts && opts.filter;
    for (var i = 0; i < c; ++i) {
        var _a = zh(data, o, z), c_2 = _a[0], sc = _a[1], su = _a[2], fn = _a[3], no = _a[4], off = _a[5], b = slzh(data, off);
        o = no;
        if (!fltr || fltr({
            name: fn,
            size: sc,
            originalSize: su,
            compression: c_2
        })) {
            if (!c_2)
                files[fn] = slc(data, b, b + sc);
            else if (c_2 == 8)
                files[fn] = inflateSync(data.subarray(b, b + sc), { out: new u8(su) });
            else
                err(14, 'unknown compression type ' + c_2);
        }
    }
    return files;
}
```
</details>


---