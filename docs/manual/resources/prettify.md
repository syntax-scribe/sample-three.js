[⬅️ Back to Table of Contents](../../index.md)

# 📄 `prettify.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 26 |
| 📊 Variables & Constants | 173 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/prettify.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `IN_GLOBAL_SCOPE` | `boolean` | let/var | `true` | ✗ |
| `prettyPrintOne` | `any` | let/var | `*not shown*` | ✗ |
| `prettyPrint` | `any` | let/var | `*not shown*` | ✗ |
| `win` | `Window & typeof globalThis` | let/var | `window` | ✗ |
| `FLOW_CONTROL_KEYWORDS` | `string[]` | let/var | `["break,continue,do,else,for,if,return,while"]` | ✗ |
| `C_KEYWORDS` | `(string \| string[])[]` | let/var | `[FLOW_CONTROL_KEYWORDS,"auto,case,char,const,default," + "double,enum,extern,...` | ✗ |
| `COMMON_KEYWORDS` | `(string \| (string \| string[])[])[]` | let/var | `[C_KEYWORDS,"catch,class,delete,false,import," + "new,operator,private,protec...` | ✗ |
| `CPP_KEYWORDS` | `(string \| (string \| (string \| stri...` | let/var | `[COMMON_KEYWORDS,"alignof,align_union,asm,axiom,bool," + "concept,concept_map...` | ✗ |
| `JAVA_KEYWORDS` | `(string \| (string \| (string \| stri...` | let/var | `[COMMON_KEYWORDS, "abstract,assert,boolean,byte,extends,final,finally,impleme...` | ✗ |
| `CSHARP_KEYWORDS` | `(string \| (string \| (string \| stri...` | let/var | `[COMMON_KEYWORDS, "abstract,as,base,bool,by,byte,checked,decimal,delegate,des...` | ✗ |
| `COFFEE_KEYWORDS` | `string` | let/var | `"all,and,by,catch,class,else,extends,false,finally," + "for,if,in,is,isnt,loo...` | ✗ |
| `JSCRIPT_KEYWORDS` | `(string \| (string \| (string \| stri...` | let/var | `[COMMON_KEYWORDS, "debugger,eval,export,function,get,null,set,undefined,var,w...` | ✗ |
| `PERL_KEYWORDS` | `string` | let/var | `"caller,delete,die,do,dump,elsif,eval,exit,foreach,for," + "goto,if,import,la...` | ✗ |
| `PYTHON_KEYWORDS` | `(string \| string[])[]` | let/var | `[FLOW_CONTROL_KEYWORDS, "and,as,assert,class,def,del," + "elif,except,exec,fi...` | ✗ |
| `RUBY_KEYWORDS` | `(string \| string[])[]` | let/var | `[FLOW_CONTROL_KEYWORDS, "alias,and,begin,case,class," + "def,defined,elsif,en...` | ✗ |
| `RUST_KEYWORDS` | `(string \| string[])[]` | let/var | `[FLOW_CONTROL_KEYWORDS, "as,assert,const,copy,drop," + "enum,extern,fail,fals...` | ✗ |
| `SH_KEYWORDS` | `(string \| string[])[]` | let/var | `[FLOW_CONTROL_KEYWORDS, "case,done,elif,esac,eval,fi," + "function,in,local,s...` | ✗ |
| `ALL_KEYWORDS` | `(string \| (string \| (string \| (str...` | let/var | `[ CPP_KEYWORDS, CSHARP_KEYWORDS, JSCRIPT_KEYWORDS, PERL_KEYWORDS, PYTHON_KEYW...` | ✗ |
| `C_TYPES` | `RegExp` | let/var | `/^(DIR\|FILE\|vector\|(de\|priority_)?queue\|list\|stack\|(const_)?iterator\|...` | ✗ |
| `PR_STRING` | `string` | let/var | `'str'` | ✗ |
| `PR_KEYWORD` | `string` | let/var | `'kwd'` | ✗ |
| `PR_COMMENT` | `string` | let/var | `'com'` | ✗ |
| `PR_TYPE` | `string` | let/var | `'typ'` | ✗ |
| `PR_LITERAL` | `string` | let/var | `'lit'` | ✗ |
| `PR_PUNCTUATION` | `string` | let/var | `'pun'` | ✗ |
| `PR_PLAIN` | `string` | let/var | `'pln'` | ✗ |
| `PR_TAG` | `string` | let/var | `'tag'` | ✗ |
| `PR_DECLARATION` | `string` | let/var | `'dec'` | ✗ |
| `PR_SOURCE` | `string` | let/var | `'src'` | ✗ |
| `PR_ATTRIB_NAME` | `string` | let/var | `'atn'` | ✗ |
| `PR_ATTRIB_VALUE` | `string` | let/var | `'atv'` | ✗ |
| `PR_NOCODE` | `string` | let/var | `'nocode'` | ✗ |
| `REGEXP_PRECEDER_PATTERN` | `string` | let/var | `'(?:^^\\.?\|[+-]\|[!=]=?=?\|\\#\|%=?\|&&?=?\|\\(\|\\*=?\|[+\\-]=\|->\|\\/=?\|...` | ✗ |
| `capturedGroupIndex` | `number` | let/var | `0` | ✗ |
| `needToFoldCase` | `boolean` | let/var | `false` | ✗ |
| `ignoreCase` | `boolean` | let/var | `false` | ✗ |
| `regex` | `RegExp` | let/var | `regexs[i]` | ✗ |
| `escapeCharToCodeUnit` | `{ b: number; t: number; n: number; v:...` | let/var | `{ 'b': 8, 't': 9, 'n': 0xa, 'v': 0xb, 'f': 0xc, 'r': 0xd }` | ✗ |
| `ranges` | `any[]` | let/var | `[]` | ✗ |
| `inverse` | `boolean` | let/var | `charsetParts[0] === '^'` | ✗ |
| `out` | `string[]` | let/var | `['[']` | ✗ |
| `p` | `any` | let/var | `charsetParts[i]` | ✗ |
| `end` | `any` | let/var | `*not shown*` | ✗ |
| `consolidatedRanges` | `any[]` | let/var | `[]` | ✗ |
| `lastRange` | `any[]` | let/var | `[]` | ✗ |
| `range` | `any[]` | let/var | `ranges[i]` | ✗ |
| `range` | `any[]` | let/var | `consolidatedRanges[i]` | ✗ |
| `n` | `any` | let/var | `parts.length` | ✗ |
| `capturedGroups` | `any[]` | let/var | `[]` | ✗ |
| `p` | `any` | let/var | `parts[i]` | ✗ |
| `decimalValue` | `number` | let/var | `+p.substring(1)` | ✗ |
| `decimalValue` | `number` | let/var | `+p.substring(1)` | ✗ |
| `rewritten` | `any[]` | let/var | `[]` | ✗ |
| `regex` | `RegExp` | let/var | `regexs[i]` | ✗ |
| `nocode` | `RegExp` | let/var | `/(?:^\|\s)nocode(?:\s\|$)/` | ✗ |
| `chunks` | `any[]` | let/var | `[]` | ✗ |
| `length` | `number` | let/var | `0` | ✗ |
| `spans` | `any[]` | let/var | `[]` | ✗ |
| `k` | `number` | let/var | `0` | ✗ |
| `type` | `any` | let/var | `node.nodeType` | ✗ |
| `text` | `any` | let/var | `node.nodeValue` | ✗ |
| `job` | `{ sourceCode: any; basePos: number; }` | let/var | `{ sourceCode: sourceCode, basePos: basePos }` | ✗ |
| `notWs` | `RegExp` | let/var | `/\S/` | ✗ |
| `wrapper` | `any` | let/var | `undefined` | ✗ |
| `type` | `any` | let/var | `c.nodeType` | ✗ |
| `shortcuts` | `{}` | let/var | `{}` | ✗ |
| `tokenizer` | `any` | let/var | `*not shown*` | ✗ |
| `allRegexs` | `any[]` | let/var | `[]` | ✗ |
| `regexKeys` | `{}` | let/var | `{}` | ✗ |
| `patternParts` | `any` | let/var | `allPatterns[i]` | ✗ |
| `shortcutChars` | `any` | let/var | `patternParts[3]` | ✗ |
| `regex` | `any` | let/var | `patternParts[1]` | ✗ |
| `k` | `string` | let/var | `'' + regex` | ✗ |
| `nPatterns` | `number` | let/var | `fallthroughStylePatterns.length` | ✗ |
| `sourceCode` | `any` | let/var | `job.sourceCode` | ✗ |
| `basePos` | `any` | let/var | `job.basePos` | ✗ |
| `decorations` | `(string \| number)[]` | let/var | `[basePos, PR_PLAIN]` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `tokens` | `any` | let/var | `sourceCode.match(tokenizer) \|\| []` | ✗ |
| `styleCache` | `{}` | let/var | `{}` | ✗ |
| `token` | `any` | let/var | `tokens[ti]` | ✗ |
| `style` | `any` | let/var | `styleCache[token]` | ✗ |
| `match` | `any` | let/var | `void 0` | ✗ |
| `isEmbedded` | `any` | let/var | `*not shown*` | ✗ |
| `patternParts` | `any` | let/var | `shortcuts[token.charAt(0)]` | ✗ |
| `tokenStart` | `number` | let/var | `pos` | ✗ |
| `embeddedSource` | `any` | let/var | `match[1]` | ✗ |
| `embeddedSourceEnd` | `any` | let/var | `embeddedSourceStart + embeddedSource.length` | ✗ |
| `shortcutStylePatterns` | `any[]` | let/var | `[]` | ✗ |
| `fallthroughStylePatterns` | `any[]` | let/var | `[]` | ✗ |
| `hc` | `any` | let/var | `options['hashComments']` | ✗ |
| `regexLiterals` | `any` | let/var | `options['regexLiterals']` | ✗ |
| `regexExcls` | `string` | let/var | `regexLiterals > 1 ? '' // Multiline regex literals : '\n\r'` | ✗ |
| `regexAny` | `string` | let/var | `regexExcls ? '.' : '[\\S\\s]'` | ✗ |
| `REGEX_LITERAL` | `string` | let/var | `( // A regular expression literal starts with a slash that is // not followed...` | ✗ |
| `types` | `any` | let/var | `options['types']` | ✗ |
| `punctuation` | `string` | let/var | `'^.[^\\s\\w.$@\'"`/\\\\]*'` | ✗ |
| `nocode` | `RegExp` | let/var | `/(?:^\|\s)nocode(?:\s\|$)/` | ✗ |
| `lineBreak` | `RegExp` | let/var | `/\r\n?\|\n/` | ✗ |
| `prefixes` | `{ prefix: string; className: string; }[]` | let/var | `[ { prefix: "*", className: "linemodified", }, { prefix: "-", className: "lin...` | ✗ |
| `document` | `Document` | let/var | `node.ownerDocument` | ✗ |
| `listItems` | `HTMLLIElement[]` | let/var | `[li]` | ✗ |
| `type` | `any` | let/var | `node.nodeType` | ✗ |
| `text` | `any` | let/var | `node.nodeValue` | ✗ |
| `parent` | `any` | let/var | `node.parentNode` | ✗ |
| `rightSide` | `any` | let/var | `copy ? limit.cloneNode(false) : limit` | ✗ |
| `parent` | `any` | let/var | `limit.parentNode` | ✗ |
| `next` | `any` | let/var | `limit.nextSibling` | ✗ |
| `classNames` | `any[]` | let/var | `[]` | ✗ |
| `offset` | `number` | let/var | `Math.max(0, (opt_startLineNum - 1 /* zero index */) \| 0) \|\| 0` | ✗ |
| `classNames` | `any[]` | let/var | `[]` | ✗ |
| `type` | `any` | let/var | `node.nodeType` | ✗ |
| `text` | `any` | let/var | `node.nodeValue` | ✗ |
| `prefixInfo` | `{ prefix: string; className: string; }` | let/var | `prefixes[pp]` | ✗ |
| `newlineRe` | `RegExp` | let/var | `/\n/g` | ✗ |
| `source` | `any` | let/var | `job.sourceCode` | ✗ |
| `sourceLength` | `any` | let/var | `source.length` | ✗ |
| `sourceIndex` | `number` | let/var | `0` | ✗ |
| `spans` | `any` | let/var | `job.spans` | ✗ |
| `nSpans` | `any` | let/var | `spans.length` | ✗ |
| `spanIndex` | `number` | let/var | `0` | ✗ |
| `decorations` | `any` | let/var | `job.decorations` | ✗ |
| `nDecorations` | `any` | let/var | `decorations.length` | ✗ |
| `decorationIndex` | `number` | let/var | `0` | ✗ |
| `decPos` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `startPos` | `any` | let/var | `decorations[i]` | ✗ |
| `startDec` | `any` | let/var | `decorations[i + 1]` | ✗ |
| `end` | `any` | let/var | `i + 2` | ✗ |
| `sourceNode` | `any` | let/var | `job.sourceNode` | ✗ |
| `oldDisplay` | `any` | let/var | `*not shown*` | ✗ |
| `spanEnd` | `any` | let/var | `spans[spanIndex + 2] \|\| sourceLength` | ✗ |
| `decEnd` | `any` | let/var | `decorations[decorationIndex + 2] \|\| sourceLength` | ✗ |
| `textNode` | `any` | let/var | `spans[spanIndex + 1]` | ✗ |
| `styledText` | `any` | let/var | `*not shown*` | ✗ |
| `document` | `any` | let/var | `textNode.ownerDocument` | ✗ |
| `parentNode` | `any` | let/var | `textNode.parentNode` | ✗ |
| `langHandlerRegistry` | `{}` | let/var | `{}` | ✗ |
| `ext` | `string` | let/var | `fileExtensions[i]` | ✗ |
| `opt_langExtension` | `any` | let/var | `job.langExtension` | ✗ |
| `source` | `string` | let/var | `sourceAndSpans.sourceCode` | ✗ |
| `job` | `{ langExtension: string; numberLines:...` | let/var | `{ langExtension: opt_langExtension, numberLines: opt_numberLines, sourceNode:...` | ✗ |
| `root` | `HTMLElement \| HTMLDocument` | let/var | `opt_root \|\| document.body` | ✗ |
| `doc` | `Document` | let/var | `root.ownerDocument \|\| document` | ✗ |
| `codeSegments` | `HTMLCollectionOf<any>[]` | let/var | `[byTagName('pre'), byTagName('code'), byTagName('xmp')]` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |
| `clock` | `DateConstructor` | let/var | `Date` | ✗ |
| `k` | `number` | let/var | `0` | ✗ |
| `prettyPrintingJob` | `any` | let/var | `*not shown*` | ✗ |
| `langExtensionRe` | `RegExp` | let/var | `/\blang(?:uage)?-([\w.]+)(?!\S)/` | ✗ |
| `prettyPrintRe` | `RegExp` | let/var | `/\bprettyprint\b/` | ✗ |
| `prettyPrintedRe` | `RegExp` | let/var | `/\bprettyprinted\b/` | ✗ |
| `preformattedTagNameRe` | `RegExp` | let/var | `/pre\|xmp/i` | ✗ |
| `codeRe` | `RegExp` | let/var | `/^code$/i` | ✗ |
| `preCodeXmpRe` | `RegExp` | let/var | `/^(?:pre\|code\|xmp)$/i` | ✗ |
| `EMPTY` | `{}` | let/var | `{}` | ✗ |
| `endTime` | `number` | let/var | `(win['PR_SHOULD_USE_CONTINUATION'] ? clock['now']() + 250 /* ms */ : Infinity)` | ✗ |
| `cs` | `any` | let/var | `elements[k]` | ✗ |
| `attrs` | `{}` | let/var | `EMPTY` | ✗ |
| `nt` | `any` | let/var | `preceder.nodeType` | ✗ |
| `value` | `any` | let/var | `(nt === 7 \|\| nt === 8) && preceder.nodeValue` | ✗ |
| `className` | `any` | let/var | `cs.className` | ✗ |
| `nested` | `boolean` | let/var | `false` | ✗ |
| `tn` | `any` | let/var | `p.tagName` | ✗ |
| `langExtension` | `any` | let/var | `attrs['lang']` | ✗ |
| `wrapper` | `any` | let/var | `*not shown*` | ✗ |
| `preformatted` | `any` | let/var | `*not shown*` | ✗ |
| `currentStyle` | `any` | let/var | `cs['currentStyle']` | ✗ |
| `defaultView` | `Window & typeof globalThis` | let/var | `doc.defaultView` | ✗ |
| `whitespace` | `any` | let/var | `( currentStyle ? currentStyle['whiteSpace'] : (defaultView && defaultView.get...` | ✗ |
| `lineNums` | `any` | let/var | `attrs['linenums']` | ✗ |
| `showLineMods` | `any` | let/var | `attrs['showlinemods']` | ✗ |
| `PR` | `any` | let/var | `win['PR'] = { 'createSimpleLexer': createSimpleLexer, 'registerLangHandler': ...` | ✗ |


---

## Functions

### `combinePrefixPatterns(regexs: RegExp[]): RegExp`

**JSDoc:**
```typescript
/**
   * Given a group of {@link RegExp}s, returns a {@code RegExp} that globally
   * matches the union of the sets of strings matched by the input RegExp.
   * Since it matches globally, if the input strings have a start-of-input
   * anchor (/^.../), it is ignored for the purposes of unioning.
   * @param {Array.<RegExp>} regexs non multiline, non-global regexs.
   * @return {RegExp} a global regex.
   */
```

**Parameters:**

- **`regexs`** `RegExp[]`

**Returns:** `RegExp`

**Calls:**

- `/[a-z]/i.test`
- `regex.source.replace`
- `charsetPart.charCodeAt`
- `charsetPart.charAt`
- `parseInt`
- `charsetPart.substring`
- `charCode.toString`
- `String.fromCharCode`
- `charSet.substring(1, charSet.length - 1).match`
- `out.push`
- `/\\[bdsw]/i.test`
- `decodeEscape`
- `ranges.push`
- `Math.max`
- `Math.min`
- `ranges.sort`
- `consolidatedRanges.push`
- `encodeEscape`
- `out.join`
- `regex.source.match`
- `p.charAt`
- `p.substring`
- `caseFoldCharset`
- `p.replace`
- `ch.charCodeAt`
- `parts.join`
- `rewritten.push`
- `allowAnywhereFoldCaseAndRenumberGroups`
- `rewritten.join`

**Internal Comments:**
```
// If the range might intersect letters, then expand it.
// This case handling is too simplistic.
// It does not deal with non-latin case folding.
// It works for latin source code identifiers though.
// [[1, 10], [3, 4], [8, 12], [14, 14], [16, 16], [17, 17]] (x4)
// -> [[1, 12], [14, 14], [16, 17]] (x4)
// Split into character sets, escape sequences, punctuation strings (x2)
// like ('(', '(?:', ')', '^'), and runs of characters that do not (x2)
// include any of the above. (x2)
// Maps captured group numbers to the number they will occupy in (x2)
// the output or to -1 if that has not been determined, or to (x2)
// undefined if they need not be capturing in the output. (x2)
// Walk over and identify back references to build the capturedGroups
// mapping.
// groups are 1-indexed, so max group index is count of '(' (x2)
// Replace with an unambiguous escape sequence so that (x4)
// an octal escape sequence does not turn into a backreference (x4)
// to a capturing group from an earlier regex. (x4)
// Renumber groups and reduce capturing groups to non-capturing groups
// where possible.
// Remove any prefix anchors so that the output will match anywhere.
// ^^ really does mean an anchored match though.
// Expand letters to groups to handle mixing of case-sensitive and
// case-insensitive patterns if necessary.
// TODO: handle letters in numeric escapes. (x4)
```

<details><summary>Code</summary>

```typescript
function combinePrefixPatterns(regexs) {
    var capturedGroupIndex = 0;
  
    var needToFoldCase = false;
    var ignoreCase = false;
    for (var i = 0, n = regexs.length; i < n; ++i) {
      const regex = regexs[i];
      if (regex.ignoreCase) {
        ignoreCase = true;
      } else if (/[a-z]/i.test(regex.source.replace(
                     /\\u[0-9a-f]{4}|\\x[0-9a-f]{2}|\\[^ux]/gi, ''))) {
        needToFoldCase = true;
        ignoreCase = false;
        break;
      }
    }
  
    var escapeCharToCodeUnit = {
      'b': 8,
      't': 9,
      'n': 0xa,
      'v': 0xb,
      'f': 0xc,
      'r': 0xd
    };
  
    function decodeEscape(charsetPart) {
      var cc0 = charsetPart.charCodeAt(0);
      if (cc0 !== 92 /* \\ */) {
        return cc0;
      }
      var c1 = charsetPart.charAt(1);
      cc0 = escapeCharToCodeUnit[c1];
      if (cc0) {
        return cc0;
      } else if ('0' <= c1 && c1 <= '7') {
        return parseInt(charsetPart.substring(1), 8);
      } else if (c1 === 'u' || c1 === 'x') {
        return parseInt(charsetPart.substring(2), 16);
      } else {
        return charsetPart.charCodeAt(1);
      }
    }
  
    function encodeEscape(charCode) {
      if (charCode < 0x20) {
        return (charCode < 0x10 ? '\\x0' : '\\x') + charCode.toString(16);
      }
      var ch = String.fromCharCode(charCode);
      return (ch === '\\' || ch === '-' || ch === ']' || ch === '^')
          ? "\\" + ch : ch;
    }
  
    function caseFoldCharset(charSet) {
      var charsetParts = charSet.substring(1, charSet.length - 1).match(
          new RegExp(
              '\\\\u[0-9A-Fa-f]{4}'
              + '|\\\\x[0-9A-Fa-f]{2}'
              + '|\\\\[0-3][0-7]{0,2}'
              + '|\\\\[0-7]{1,2}'
              + '|\\\\[\\s\\S]'
              + '|-'
              + '|[^-\\\\]',
              'g'));
      var ranges = [];
      var inverse = charsetParts[0] === '^';
  
      var out = ['['];
      if (inverse) { out.push('^'); }
  
      for (var i = inverse ? 1 : 0, n = charsetParts.length; i < n; ++i) {
        var p = charsetParts[i];
        if (/\\[bdsw]/i.test(p)) {  // Don't muck with named groups.
          out.push(p);
        } else {
          var start = decodeEscape(p);
          var end;
          if (i + 2 < n && '-' === charsetParts[i + 1]) {
            end = decodeEscape(charsetParts[i + 2]);
            i += 2;
          } else {
            end = start;
          }
          ranges.push([start, end]);
          // If the range might intersect letters, then expand it.
          // This case handling is too simplistic.
          // It does not deal with non-latin case folding.
          // It works for latin source code identifiers though.
          if (!(end < 65 || start > 122)) {
            if (!(end < 65 || start > 90)) {
              ranges.push([Math.max(65, start) | 32, Math.min(end, 90) | 32]);
            }
            if (!(end < 97 || start > 122)) {
              ranges.push([Math.max(97, start) & ~32, Math.min(end, 122) & ~32]);
            }
          }
        }
      }
  
      // [[1, 10], [3, 4], [8, 12], [14, 14], [16, 16], [17, 17]]
      // -> [[1, 12], [14, 14], [16, 17]]
      ranges.sort(function (a, b) { return (a[0] - b[0]) || (b[1]  - a[1]); });
      var consolidatedRanges = [];
      var lastRange = [];
      for (var i = 0; i < ranges.length; ++i) {
        const range = ranges[i];
        if (range[0] <= lastRange[1] + 1) {
          lastRange[1] = Math.max(lastRange[1], range[1]);
        } else {
          consolidatedRanges.push(lastRange = range);
        }
      }
  
      for (var i = 0; i < consolidatedRanges.length; ++i) {
        const range = consolidatedRanges[i];
        out.push(encodeEscape(range[0]));
        if (range[1] > range[0]) {
          if (range[1] + 1 > range[0]) { out.push('-'); }
          out.push(encodeEscape(range[1]));
        }
      }
      out.push(']');
      return out.join('');
    }
  
    function allowAnywhereFoldCaseAndRenumberGroups(regex) {
      // Split into character sets, escape sequences, punctuation strings
      // like ('(', '(?:', ')', '^'), and runs of characters that do not
      // include any of the above.
      var parts = regex.source.match(
          new RegExp(
              '(?:'
              + '\\[(?:[^\\x5C\\x5D]|\\\\[\\s\\S])*\\]'  // a character set
              + '|\\\\u[A-Fa-f0-9]{4}'  // a unicode escape
              + '|\\\\x[A-Fa-f0-9]{2}'  // a hex escape
              + '|\\\\[0-9]+'  // a back-reference or octal escape
              + '|\\\\[^ux0-9]'  // other escape sequence
              + '|\\(\\?[:!=]'  // start of a non-capturing group
              + '|[\\(\\)\\^]'  // start/end of a group, or line start
              + '|[^\\x5B\\x5C\\(\\)\\^]+'  // run of other characters
              + ')',
              'g'));
      var n = parts.length;
  
      // Maps captured group numbers to the number they will occupy in
      // the output or to -1 if that has not been determined, or to
      // undefined if they need not be capturing in the output.
      var capturedGroups = [];
  
      // Walk over and identify back references to build the capturedGroups
      // mapping.
      for (let i = 0, groupIndex = 0; i < n; ++i) {
        var p = parts[i];
        if (p === '(') {
          // groups are 1-indexed, so max group index is count of '('
          ++groupIndex;
        } else if ('\\' === p.charAt(0)) {
          const decimalValue = +p.substring(1);
          if (decimalValue) {
            if (decimalValue <= groupIndex) {
              capturedGroups[decimalValue] = -1;
            } else {
              // Replace with an unambiguous escape sequence so that
              // an octal escape sequence does not turn into a backreference
              // to a capturing group from an earlier regex.
              parts[i] = encodeEscape(decimalValue);
            }
          }
        }
      }
  
      // Renumber groups and reduce capturing groups to non-capturing groups
      // where possible.
      for (var i = 1; i < capturedGroups.length; ++i) {
        if (-1 === capturedGroups[i]) {
          capturedGroups[i] = ++capturedGroupIndex;
        }
      }
      for (let i = 0, groupIndex = 0; i < n; ++i) {
        var p = parts[i];
        if (p === '(') {
          ++groupIndex;
          if (!capturedGroups[groupIndex]) {
            parts[i] = '(?:';
          }
        } else if ('\\' === p.charAt(0)) {
          const decimalValue = +p.substring(1);
          if (decimalValue && decimalValue <= groupIndex) {
            parts[i] = '\\' + capturedGroups[decimalValue];
          }
        }
      }
  
      // Remove any prefix anchors so that the output will match anywhere.
      // ^^ really does mean an anchored match though.
      for (var i = 0; i < n; ++i) {
        if ('^' === parts[i] && '^' !== parts[i + 1]) { parts[i] = ''; }
      }
  
      // Expand letters to groups to handle mixing of case-sensitive and
      // case-insensitive patterns if necessary.
      if (regex.ignoreCase && needToFoldCase) {
        for (var i = 0; i < n; ++i) {
          var p = parts[i];
          var ch0 = p.charAt(0);
          if (p.length >= 2 && ch0 === '[') {
            parts[i] = caseFoldCharset(p);
          } else if (ch0 !== '\\') {
            // TODO: handle letters in numeric escapes.
            parts[i] = p.replace(
                /[a-zA-Z]/g,
                function (ch) {
                  var cc = ch.charCodeAt(0);
                  return '[' + String.fromCharCode(cc & ~32, cc | 32) + ']';
                });
          }
        }
      }
  
      return parts.join('');
    }
  
    var rewritten = [];
    for (var i = 0, n = regexs.length; i < n; ++i) {
      const regex = regexs[i];
      if (regex.global || regex.multiline) { throw new Error('' + regex); }
      rewritten.push(
          '(?:' + allowAnywhereFoldCaseAndRenumberGroups(regex) + ')');
    }
  
    return new RegExp(rewritten.join('|'), ignoreCase ? 'gi' : 'g');
  }
```
</details>

### `decodeEscape(charsetPart: any): any`

**Parameters:**

- **`charsetPart`** `any`

**Returns:** `any`

**Calls:**

- `charsetPart.charCodeAt`
- `charsetPart.charAt`
- `parseInt`
- `charsetPart.substring`

<details><summary>Code</summary>

```typescript
function decodeEscape(charsetPart) {
      var cc0 = charsetPart.charCodeAt(0);
      if (cc0 !== 92 /* \\ */) {
        return cc0;
      }
      var c1 = charsetPart.charAt(1);
      cc0 = escapeCharToCodeUnit[c1];
      if (cc0) {
        return cc0;
      } else if ('0' <= c1 && c1 <= '7') {
        return parseInt(charsetPart.substring(1), 8);
      } else if (c1 === 'u' || c1 === 'x') {
        return parseInt(charsetPart.substring(2), 16);
      } else {
        return charsetPart.charCodeAt(1);
      }
    }
```
</details>

### `encodeEscape(charCode: any): string`

**Parameters:**

- **`charCode`** `any`

**Returns:** `string`

**Calls:**

- `charCode.toString`
- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function encodeEscape(charCode) {
      if (charCode < 0x20) {
        return (charCode < 0x10 ? '\\x0' : '\\x') + charCode.toString(16);
      }
      var ch = String.fromCharCode(charCode);
      return (ch === '\\' || ch === '-' || ch === ']' || ch === '^')
          ? "\\" + ch : ch;
    }
```
</details>

### `caseFoldCharset(charSet: any): string`

**Parameters:**

- **`charSet`** `any`

**Returns:** `string`

**Calls:**

- `charSet.substring(1, charSet.length - 1).match`
- `out.push`
- `/\\[bdsw]/i.test`
- `decodeEscape`
- `ranges.push`
- `Math.max`
- `Math.min`
- `ranges.sort`
- `consolidatedRanges.push`
- `encodeEscape`
- `out.join`

**Internal Comments:**
```
// If the range might intersect letters, then expand it.
// This case handling is too simplistic.
// It does not deal with non-latin case folding.
// It works for latin source code identifiers though.
// [[1, 10], [3, 4], [8, 12], [14, 14], [16, 16], [17, 17]] (x4)
// -> [[1, 12], [14, 14], [16, 17]] (x4)
```

<details><summary>Code</summary>

```typescript
function caseFoldCharset(charSet) {
      var charsetParts = charSet.substring(1, charSet.length - 1).match(
          new RegExp(
              '\\\\u[0-9A-Fa-f]{4}'
              + '|\\\\x[0-9A-Fa-f]{2}'
              + '|\\\\[0-3][0-7]{0,2}'
              + '|\\\\[0-7]{1,2}'
              + '|\\\\[\\s\\S]'
              + '|-'
              + '|[^-\\\\]',
              'g'));
      var ranges = [];
      var inverse = charsetParts[0] === '^';
  
      var out = ['['];
      if (inverse) { out.push('^'); }
  
      for (var i = inverse ? 1 : 0, n = charsetParts.length; i < n; ++i) {
        var p = charsetParts[i];
        if (/\\[bdsw]/i.test(p)) {  // Don't muck with named groups.
          out.push(p);
        } else {
          var start = decodeEscape(p);
          var end;
          if (i + 2 < n && '-' === charsetParts[i + 1]) {
            end = decodeEscape(charsetParts[i + 2]);
            i += 2;
          } else {
            end = start;
          }
          ranges.push([start, end]);
          // If the range might intersect letters, then expand it.
          // This case handling is too simplistic.
          // It does not deal with non-latin case folding.
          // It works for latin source code identifiers though.
          if (!(end < 65 || start > 122)) {
            if (!(end < 65 || start > 90)) {
              ranges.push([Math.max(65, start) | 32, Math.min(end, 90) | 32]);
            }
            if (!(end < 97 || start > 122)) {
              ranges.push([Math.max(97, start) & ~32, Math.min(end, 122) & ~32]);
            }
          }
        }
      }
  
      // [[1, 10], [3, 4], [8, 12], [14, 14], [16, 16], [17, 17]]
      // -> [[1, 12], [14, 14], [16, 17]]
      ranges.sort(function (a, b) { return (a[0] - b[0]) || (b[1]  - a[1]); });
      var consolidatedRanges = [];
      var lastRange = [];
      for (var i = 0; i < ranges.length; ++i) {
        const range = ranges[i];
        if (range[0] <= lastRange[1] + 1) {
          lastRange[1] = Math.max(lastRange[1], range[1]);
        } else {
          consolidatedRanges.push(lastRange = range);
        }
      }
  
      for (var i = 0; i < consolidatedRanges.length; ++i) {
        const range = consolidatedRanges[i];
        out.push(encodeEscape(range[0]));
        if (range[1] > range[0]) {
          if (range[1] + 1 > range[0]) { out.push('-'); }
          out.push(encodeEscape(range[1]));
        }
      }
      out.push(']');
      return out.join('');
    }
```
</details>

### `allowAnywhereFoldCaseAndRenumberGroups(regex: any): any`

**Parameters:**

- **`regex`** `any`

**Returns:** `any`

**Calls:**

- `regex.source.match`
- `p.charAt`
- `p.substring`
- `encodeEscape`
- `caseFoldCharset`
- `p.replace`
- `ch.charCodeAt`
- `String.fromCharCode`
- `parts.join`

**Internal Comments:**
```
// Split into character sets, escape sequences, punctuation strings (x2)
// like ('(', '(?:', ')', '^'), and runs of characters that do not (x2)
// include any of the above. (x2)
// Maps captured group numbers to the number they will occupy in (x2)
// the output or to -1 if that has not been determined, or to (x2)
// undefined if they need not be capturing in the output. (x2)
// Walk over and identify back references to build the capturedGroups
// mapping.
// groups are 1-indexed, so max group index is count of '(' (x2)
// Replace with an unambiguous escape sequence so that (x4)
// an octal escape sequence does not turn into a backreference (x4)
// to a capturing group from an earlier regex. (x4)
// Renumber groups and reduce capturing groups to non-capturing groups
// where possible.
// Remove any prefix anchors so that the output will match anywhere.
// ^^ really does mean an anchored match though.
// Expand letters to groups to handle mixing of case-sensitive and
// case-insensitive patterns if necessary.
// TODO: handle letters in numeric escapes. (x4)
```

<details><summary>Code</summary>

```typescript
function allowAnywhereFoldCaseAndRenumberGroups(regex) {
      // Split into character sets, escape sequences, punctuation strings
      // like ('(', '(?:', ')', '^'), and runs of characters that do not
      // include any of the above.
      var parts = regex.source.match(
          new RegExp(
              '(?:'
              + '\\[(?:[^\\x5C\\x5D]|\\\\[\\s\\S])*\\]'  // a character set
              + '|\\\\u[A-Fa-f0-9]{4}'  // a unicode escape
              + '|\\\\x[A-Fa-f0-9]{2}'  // a hex escape
              + '|\\\\[0-9]+'  // a back-reference or octal escape
              + '|\\\\[^ux0-9]'  // other escape sequence
              + '|\\(\\?[:!=]'  // start of a non-capturing group
              + '|[\\(\\)\\^]'  // start/end of a group, or line start
              + '|[^\\x5B\\x5C\\(\\)\\^]+'  // run of other characters
              + ')',
              'g'));
      var n = parts.length;
  
      // Maps captured group numbers to the number they will occupy in
      // the output or to -1 if that has not been determined, or to
      // undefined if they need not be capturing in the output.
      var capturedGroups = [];
  
      // Walk over and identify back references to build the capturedGroups
      // mapping.
      for (let i = 0, groupIndex = 0; i < n; ++i) {
        var p = parts[i];
        if (p === '(') {
          // groups are 1-indexed, so max group index is count of '('
          ++groupIndex;
        } else if ('\\' === p.charAt(0)) {
          const decimalValue = +p.substring(1);
          if (decimalValue) {
            if (decimalValue <= groupIndex) {
              capturedGroups[decimalValue] = -1;
            } else {
              // Replace with an unambiguous escape sequence so that
              // an octal escape sequence does not turn into a backreference
              // to a capturing group from an earlier regex.
              parts[i] = encodeEscape(decimalValue);
            }
          }
        }
      }
  
      // Renumber groups and reduce capturing groups to non-capturing groups
      // where possible.
      for (var i = 1; i < capturedGroups.length; ++i) {
        if (-1 === capturedGroups[i]) {
          capturedGroups[i] = ++capturedGroupIndex;
        }
      }
      for (let i = 0, groupIndex = 0; i < n; ++i) {
        var p = parts[i];
        if (p === '(') {
          ++groupIndex;
          if (!capturedGroups[groupIndex]) {
            parts[i] = '(?:';
          }
        } else if ('\\' === p.charAt(0)) {
          const decimalValue = +p.substring(1);
          if (decimalValue && decimalValue <= groupIndex) {
            parts[i] = '\\' + capturedGroups[decimalValue];
          }
        }
      }
  
      // Remove any prefix anchors so that the output will match anywhere.
      // ^^ really does mean an anchored match though.
      for (var i = 0; i < n; ++i) {
        if ('^' === parts[i] && '^' !== parts[i + 1]) { parts[i] = ''; }
      }
  
      // Expand letters to groups to handle mixing of case-sensitive and
      // case-insensitive patterns if necessary.
      if (regex.ignoreCase && needToFoldCase) {
        for (var i = 0; i < n; ++i) {
          var p = parts[i];
          var ch0 = p.charAt(0);
          if (p.length >= 2 && ch0 === '[') {
            parts[i] = caseFoldCharset(p);
          } else if (ch0 !== '\\') {
            // TODO: handle letters in numeric escapes.
            parts[i] = p.replace(
                /[a-zA-Z]/g,
                function (ch) {
                  var cc = ch.charCodeAt(0);
                  return '[' + String.fromCharCode(cc & ~32, cc | 32) + ']';
                });
          }
        }
      }
  
      return parts.join('');
    }
```
</details>

### `extractSourceSpans(node: Node, isPreformatted: boolean): any`

**JSDoc:**
```typescript
/**
   * Split markup into a string of source code and an array mapping ranges in
   * that string to the text nodes in which they appear.
   *
   * <p>
   * The HTML DOM structure:</p>
   * <pre>
   * (Element   "p"
   *   (Element "b"
   *     (Text  "print "))       ; #1
   *   (Text    "'Hello '")      ; #2
   *   (Element "br")            ; #3
   *   (Text    "  + 'World';")) ; #4
   * </pre>
   * <p>
   * corresponds to the HTML
   * {@code <p><b>print </b>'Hello '<br>  + 'World';</p>}.</p>
   *
   * <p>
   * It will produce the output:</p>
   * <pre>
   * {
   *   sourceCode: "print 'Hello '\n  + 'World';",
   *   //                     1          2
   *   //           012345678901234 5678901234567
   *   spans: [0, #1, 6, #2, 14, #3, 15, #4]
   * }
   * </pre>
   * <p>
   * where #1 is a reference to the {@code "print "} text node above, and so
   * on for the other text nodes.
   * </p>
   *
   * <p>
   * The {@code} spans array is an array of pairs.  Even elements are the start
   * indices of substrings, and odd elements are the text nodes (or BR elements)
   * that contain the text for those substrings.
   * Substrings continue until the next index or the end of the source.
   * </p>
   *
   * @param {Node} node an HTML DOM subtree containing source-code.
   * @param {boolean} isPreformatted true if white-space in text nodes should
   *    be considered significant.
   * @return {Object} source code and the text nodes in which they occur.
   */
```

**Parameters:**

- **`node`** `Node`
- **`isPreformatted`** `boolean`

**Returns:** `any`

**Calls:**

- `nocode.test`
- `walk`
- `node.nodeName.toLowerCase`
- `text.replace`
- `chunks.join('').replace`

**Internal Comments:**
```
// TODO: handle tabs here? (x4)
```

<details><summary>Code</summary>

```typescript
function extractSourceSpans(node, isPreformatted) {
    var nocode = /(?:^|\s)nocode(?:\s|$)/;
  
    var chunks = [];
    var length = 0;
    var spans = [];
    var k = 0;
  
    function walk(node) {
      var type = node.nodeType;
      if (type == 1) {  // Element
        if (nocode.test(node.className)) { return; }
        for (var child = node.firstChild; child; child = child.nextSibling) {
          walk(child);
        }
        var nodeName = node.nodeName.toLowerCase();
        if ('br' === nodeName || 'li' === nodeName) {
          chunks[k] = '\n';
          spans[k << 1] = length++;
          spans[(k++ << 1) | 1] = node;
        }
      } else if (type == 3 || type == 4) {  // Text
        var text = node.nodeValue;
        if (text.length) {
          if (!isPreformatted) {
            text = text.replace(/[ \t\r\n]+/g, ' ');
          } else {
            text = text.replace(/\r\n?/g, '\n');  // Normalize newlines.
          }
          // TODO: handle tabs here?
          chunks[k] = text;
          spans[k << 1] = length;
          length += text.length;
          spans[(k++ << 1) | 1] = node;
        }
      }
    }
  
    walk(node);
  
    return {
      sourceCode: chunks.join('').replace(/\n$/, ''),
      spans: spans
    };
  }
```
</details>

### `walk(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `nocode.test`
- `walk`
- `node.nodeName.toLowerCase`
- `text.replace`

**Internal Comments:**
```
// TODO: handle tabs here? (x4)
```

<details><summary>Code</summary>

```typescript
function walk(node) {
      var type = node.nodeType;
      if (type == 1) {  // Element
        if (nocode.test(node.className)) { return; }
        for (var child = node.firstChild; child; child = child.nextSibling) {
          walk(child);
        }
        var nodeName = node.nodeName.toLowerCase();
        if ('br' === nodeName || 'li' === nodeName) {
          chunks[k] = '\n';
          spans[k << 1] = length++;
          spans[(k++ << 1) | 1] = node;
        }
      } else if (type == 3 || type == 4) {  // Text
        var text = node.nodeValue;
        if (text.length) {
          if (!isPreformatted) {
            text = text.replace(/[ \t\r\n]+/g, ' ');
          } else {
            text = text.replace(/\r\n?/g, '\n');  // Normalize newlines.
          }
          // TODO: handle tabs here?
          chunks[k] = text;
          spans[k << 1] = length;
          length += text.length;
          spans[(k++ << 1) | 1] = node;
        }
      }
    }
```
</details>

### `appendDecorations(basePos: number, sourceCode: any, langHandler: any, out: any): void`

**JSDoc:**
```typescript
/**
   * Apply the given language handler to sourceCode and add the resulting
   * decorations to out.
   * @param {number} basePos the index of sourceCode within the chunk of source
   *    whose decorations are already present on out.
   */
```

**Parameters:**

- **`basePos`** `number`
- **`sourceCode`** `any`
- **`langHandler`** `any`
- **`out`** `any`

**Returns:** `void`

**Calls:**

- `langHandler`
- `out.push.apply`

<details><summary>Code</summary>

```typescript
function appendDecorations(basePos, sourceCode, langHandler, out) {
    if (!sourceCode) { return; }
    var job = {
      sourceCode: sourceCode,
      basePos: basePos
    };
    langHandler(job);
    out.push.apply(out, job.decorations);
  }
```
</details>

### `childContentWrapper(element: any): any`

**JSDoc:**
```typescript
/**
   * Given an element, if it contains only one child element and any text nodes
   * it contains contain only space characters, return the sole child element.
   * Otherwise returns undefined.
   * <p>
   * This is meant to return the CODE element in {@code <pre><code ...>} when
   * there is a single child element that contains all the non-space textual
   * content, but not to return anything where there are multiple child elements
   * as in {@code <pre><code>...</code><code>...</code></pre>} or when there
   * is textual content.
   */
```

**Parameters:**

- **`element`** `any`

**Returns:** `any`

**Calls:**

- `notWs.test`

<details><summary>Code</summary>

```typescript
function childContentWrapper(element) {
    var wrapper = undefined;
    for (var c = element.firstChild; c; c = c.nextSibling) {
      var type = c.nodeType;
      wrapper = (type === 1)  // Element Node
          ? (wrapper ? element : c)
          : (type === 3)  // Text Node
          ? (notWs.test(c.nodeValue) ? element : wrapper)
          : wrapper;
    }
    return wrapper === element ? undefined : wrapper;
  }
```
</details>

### `createSimpleLexer(shortcutStylePatterns: any[], fallthroughStylePatterns: any[]): (arg0: any) => any`

**JSDoc:**
```typescript
/** Given triples of [style, pattern, context] returns a lexing function,
    * The lexing function interprets the patterns to find token boundaries and
    * returns a decoration list of the form
    * [index_0, style_0, index_1, style_1, ..., index_n, style_n]
    * where index_n is an index into the sourceCode, and style_n is a style
    * constant like PR_PLAIN.  index_n-1 <= index_n, and style_n-1 applies to
    * all characters in sourceCode[index_n-1:index_n].
    *
    * The stylePatterns is a list whose elements have the form
    * [style : string, pattern : RegExp, DEPRECATED, shortcut : string].
    *
    * Style is a style constant like PR_PLAIN, or can be a string of the
    * form 'lang-FOO', where FOO is a language extension describing the
    * language of the portion of the token in $1 after pattern executes.
    * E.g., if style is 'lang-lisp', and group 1 contains the text
    * '(hello (world))', then that portion of the token will be passed to the
    * registered lisp handler for formatting.
    * The text before and after group 1 will be restyled using this decorator
    * so decorators should take care that this doesn't result in infinite
    * recursion.  For example, the HTML lexer rule for SCRIPT elements looks
    * something like ['lang-js', /<[s]cript>(.+?)<\/script>/].  This may match
    * '<script>foo()<\/script>', which would cause the current decorator to
    * be called with '<script>' which would not match the same rule since
    * group 1 must not be empty, so it would be instead styled as PR_TAG by
    * the generic tag rule.  The handler registered for the 'js' extension would
    * then be called with 'foo()', and finally, the current decorator would
    * be called with '<\/script>' which would not match the original rule and
    * so the generic tag rule would identify it as a tag.
    *
    * Pattern must only match prefixes, and if it matches a prefix, then that
    * match is considered a token with the same style.
    *
    * Context is applied to the last non-whitespace, non-comment token
    * recognized.
    *
    * Shortcut is an optional string of characters, any of which, if the first
    * character, gurantee that this pattern and only this pattern matches.
    *
    * @param {Array} shortcutStylePatterns patterns that always start with
    *   a known character.  Must have a shortcut string.
    * @param {Array} fallthroughStylePatterns patterns that will be tried in
    *   order if the shortcut ones fail.  May have shortcuts.
    *
    * @return {function (Object)} a
    *   function that takes source code and returns a list of decorations.
    */
```

**Parameters:**

- **`shortcutStylePatterns`** `any[]`
- **`fallthroughStylePatterns`** `any[]`

**Returns:** `(arg0: any) => any`

**Calls:**

- `complex_call_25269`
- `shortcutStylePatterns.concat`
- `shortcutChars.charAt`
- `regexKeys.hasOwnProperty`
- `allRegexs.push`
- `combinePrefixPatterns`
- `sourceCode.match`
- `token.charAt`
- `token.match`
- `style.substring`
- `decorations.push`
- `token.indexOf`
- `appendDecorations`
- `token.substring`
- `langHandlerForExtension`

**Internal Comments:**
```
/**
     * Lexes job.sourceCode and produces an output array job.decorations of
     * style classes preceded by the position at which they start in
     * job.sourceCode in order.
     *
     * @param {Object} job an object like <pre>{
     *    sourceCode: {string} sourceText plain text,
     *    basePos: {int} position of job.sourceCode in the larger chunk of
     *        sourceCode.
     * }</pre>
     */ (x2)
/** Even entries are positions in source in ascending order.  Odd enties
        * are style markers (e.g., PR_COMMENT) that run from that position until
        * the end.
        * @type {Array.<number|string>}
        */ (x2)
// If embeddedSource can be blank, then it would match at the (x3)
// beginning which would cause us to infinitely recurse on the (x3)
// entire token, so we catch the right context in match[2]. (x3)
// Decorate the left of the embedded source (x3)
// Decorate the embedded source (x3)
// Decorate the right of the embedded section (x3)
```

<details><summary>Code</summary>

```typescript
function createSimpleLexer(shortcutStylePatterns, fallthroughStylePatterns) {
    var shortcuts = {};
    var tokenizer;
    (function () {
      var allPatterns = shortcutStylePatterns.concat(fallthroughStylePatterns);
      var allRegexs = [];
      var regexKeys = {};
      for (var i = 0, n = allPatterns.length; i < n; ++i) {
        var patternParts = allPatterns[i];
        var shortcutChars = patternParts[3];
        if (shortcutChars) {
          for (var c = shortcutChars.length; --c >= 0;) {
            shortcuts[shortcutChars.charAt(c)] = patternParts;
          }
        }
        var regex = patternParts[1];
        var k = '' + regex;
        if (!regexKeys.hasOwnProperty(k)) {
          allRegexs.push(regex);
          regexKeys[k] = null;
        }
      }
      allRegexs.push(/[\0-\uffff]/);
      tokenizer = combinePrefixPatterns(allRegexs);
    })();

    var nPatterns = fallthroughStylePatterns.length;

    /**
     * Lexes job.sourceCode and produces an output array job.decorations of
     * style classes preceded by the position at which they start in
     * job.sourceCode in order.
     *
     * @param {Object} job an object like <pre>{
     *    sourceCode: {string} sourceText plain text,
     *    basePos: {int} position of job.sourceCode in the larger chunk of
     *        sourceCode.
     * }</pre>
     */
    var decorate = function (job) {
      var sourceCode = job.sourceCode, basePos = job.basePos;
      /** Even entries are positions in source in ascending order.  Odd enties
        * are style markers (e.g., PR_COMMENT) that run from that position until
        * the end.
        * @type {Array.<number|string>}
        */
      var decorations = [basePos, PR_PLAIN];
      var pos = 0;  // index into sourceCode
      var tokens = sourceCode.match(tokenizer) || [];
      var styleCache = {};

      for (var ti = 0, nTokens = tokens.length; ti < nTokens; ++ti) {
        var token = tokens[ti];
        var style = styleCache[token];
        var match = void 0;

        var isEmbedded;
        if (typeof style === 'string') {
          isEmbedded = false;
        } else {
          var patternParts = shortcuts[token.charAt(0)];
          if (patternParts) {
            match = token.match(patternParts[1]);
            style = patternParts[0];
          } else {
            for (var i = 0; i < nPatterns; ++i) {
              patternParts = fallthroughStylePatterns[i];
              match = token.match(patternParts[1]);
              if (match) {
                style = patternParts[0];
                break;
              }
            }

            if (!match) {  // make sure that we make progress
              style = PR_PLAIN;
            }
          }

          isEmbedded = style.length >= 5 && 'lang-' === style.substring(0, 5);
          if (isEmbedded && !(match && typeof match[1] === 'string')) {
            isEmbedded = false;
            style = PR_SOURCE;
          }

          if (!isEmbedded) { styleCache[token] = style; }
        }

        var tokenStart = pos;
        pos += token.length;

        if (!isEmbedded) {
          decorations.push(basePos + tokenStart, style);
        } else {  // Treat group 1 as an embedded block of source code.
          var embeddedSource = match[1];
          var embeddedSourceStart = token.indexOf(embeddedSource);
          var embeddedSourceEnd = embeddedSourceStart + embeddedSource.length;
          if (match[2]) {
            // If embeddedSource can be blank, then it would match at the
            // beginning which would cause us to infinitely recurse on the
            // entire token, so we catch the right context in match[2].
            embeddedSourceEnd = token.length - match[2].length;
            embeddedSourceStart = embeddedSourceEnd - embeddedSource.length;
          }
          var lang = style.substring(5);
          // Decorate the left of the embedded source
          appendDecorations(
              basePos + tokenStart,
              token.substring(0, embeddedSourceStart),
              decorate, decorations);
          // Decorate the embedded source
          appendDecorations(
              basePos + tokenStart + embeddedSourceStart,
              embeddedSource,
              langHandlerForExtension(lang, embeddedSource),
              decorations);
          // Decorate the right of the embedded section
          appendDecorations(
              basePos + tokenStart + embeddedSourceEnd,
              token.substring(embeddedSourceEnd),
              decorate, decorations);
        }
      }
      job.decorations = decorations;
    };
    return decorate;
  }
```
</details>

### `decorate(job: any): void`

**Parameters:**

- **`job`** `any`

**Returns:** `void`

**Calls:**

- `sourceCode.match`
- `token.charAt`
- `token.match`
- `style.substring`
- `decorations.push`
- `token.indexOf`
- `appendDecorations`
- `token.substring`
- `langHandlerForExtension`

**Internal Comments:**
```
/** Even entries are positions in source in ascending order.  Odd enties
        * are style markers (e.g., PR_COMMENT) that run from that position until
        * the end.
        * @type {Array.<number|string>}
        */ (x2)
// If embeddedSource can be blank, then it would match at the (x3)
// beginning which would cause us to infinitely recurse on the (x3)
// entire token, so we catch the right context in match[2]. (x3)
// Decorate the left of the embedded source (x3)
// Decorate the embedded source (x3)
// Decorate the right of the embedded section (x3)
```

<details><summary>Code</summary>

```typescript
function (job) {
      var sourceCode = job.sourceCode, basePos = job.basePos;
      /** Even entries are positions in source in ascending order.  Odd enties
        * are style markers (e.g., PR_COMMENT) that run from that position until
        * the end.
        * @type {Array.<number|string>}
        */
      var decorations = [basePos, PR_PLAIN];
      var pos = 0;  // index into sourceCode
      var tokens = sourceCode.match(tokenizer) || [];
      var styleCache = {};

      for (var ti = 0, nTokens = tokens.length; ti < nTokens; ++ti) {
        var token = tokens[ti];
        var style = styleCache[token];
        var match = void 0;

        var isEmbedded;
        if (typeof style === 'string') {
          isEmbedded = false;
        } else {
          var patternParts = shortcuts[token.charAt(0)];
          if (patternParts) {
            match = token.match(patternParts[1]);
            style = patternParts[0];
          } else {
            for (var i = 0; i < nPatterns; ++i) {
              patternParts = fallthroughStylePatterns[i];
              match = token.match(patternParts[1]);
              if (match) {
                style = patternParts[0];
                break;
              }
            }

            if (!match) {  // make sure that we make progress
              style = PR_PLAIN;
            }
          }

          isEmbedded = style.length >= 5 && 'lang-' === style.substring(0, 5);
          if (isEmbedded && !(match && typeof match[1] === 'string')) {
            isEmbedded = false;
            style = PR_SOURCE;
          }

          if (!isEmbedded) { styleCache[token] = style; }
        }

        var tokenStart = pos;
        pos += token.length;

        if (!isEmbedded) {
          decorations.push(basePos + tokenStart, style);
        } else {  // Treat group 1 as an embedded block of source code.
          var embeddedSource = match[1];
          var embeddedSourceStart = token.indexOf(embeddedSource);
          var embeddedSourceEnd = embeddedSourceStart + embeddedSource.length;
          if (match[2]) {
            // If embeddedSource can be blank, then it would match at the
            // beginning which would cause us to infinitely recurse on the
            // entire token, so we catch the right context in match[2].
            embeddedSourceEnd = token.length - match[2].length;
            embeddedSourceStart = embeddedSourceEnd - embeddedSource.length;
          }
          var lang = style.substring(5);
          // Decorate the left of the embedded source
          appendDecorations(
              basePos + tokenStart,
              token.substring(0, embeddedSourceStart),
              decorate, decorations);
          // Decorate the embedded source
          appendDecorations(
              basePos + tokenStart + embeddedSourceStart,
              embeddedSource,
              langHandlerForExtension(lang, embeddedSource),
              decorations);
          // Decorate the right of the embedded section
          appendDecorations(
              basePos + tokenStart + embeddedSourceEnd,
              token.substring(embeddedSourceEnd),
              decorate, decorations);
        }
      }
      job.decorations = decorations;
    }
```
</details>

### `sourceDecorator(options: any): (arg0: any) => any`

**JSDoc:**
```typescript
/** returns a function that produces a list of decorations from source text.
    *
    * This code treats ", ', and ` as string delimiters, and \ as a string
    * escape.  It does not recognize perl's qq() style strings.
    * It has no special handling for double delimiter escapes as in basic, or
    * the tripled delimiters used in python, but should work on those regardless
    * although in those cases a single string literal may be broken up into
    * multiple adjacent string literals.
    *
    * It recognizes C, C++, and shell style comments.
    *
    * @param {Object} options a set of optional parameters.
    * @return {function (Object)} a function that examines the source code
    *     in the input job and builds the decoration list.
    */
```

**Parameters:**

- **`options`** `any`

**Returns:** `(arg0: any) => any`

**Calls:**

- `shortcutStylePatterns.push`
- `fallthroughStylePatterns.push`
- `RegExp`
- `("" + options['keywords']).replace`
- `keywords.replace`
- `createSimpleLexer`

**Internal Comments:**
```
// '''multi-line-string''', 'single-line-string', and double-quoted (x4)
// 'multi-line-string', "multi-line-string" (x4)
// 'single-line-string', "single-line-string" (x4)
// verbatim-string-literal production from the C# grammar.  See issue 93. (x4)
// Stop C preprocessor declarations at an unclosed open comment (x4)
// #include <stdio.h> (x4)
/**
       * @const
       */ (x6)
// A regular expression literal starts with a slash that is (x15)
// not followed by * or / so that it is not confused with (x15)
// comments. (x15)
// and then contains any number of raw characters,
// escape sequences (\x5C),
// or non-nesting character sets (\x5B\x5D);
// finally closed by a /.
// The Bash man page says
// A word is a sequence of characters considered as a single
// unit by GRUB. Words are separated by metacharacters,
// which are the following plus space, tab, and newline: { }
// | & $ ; < >
// ...
// A word beginning with # causes that word and all remaining
// characters on that line to be ignored.
// which means that only a '#' after /(?:^|[{}|&$;<>\s])/ starts a
// comment but empirically
// $ echo {#}
// {#}
// $ echo \$#
// $#
// $ echo }#
// }#
// so /(?:^|[|&;<>\s])/ is more appropriate.
// http://gcc.gnu.org/onlinedocs/gcc-2.95.3/cpp_1.html#SEC3
// suggests that this definition is compatible with a
// default mode that tries to use a single token definition
// to recognize both bash/python style comments and C
// preprocessor directives.
// This definition of punctuation does not include # in the list of
// follow-on exclusions, so # will not be broken before if preceeded
// by a punctuation character.  We could try to exclude # after
// [|&;<>] but that doesn't seem to cause many major problems.
// If that does turn out to be a problem, we should change the below
// when hc is truthy to include # in the run of punctuation characters
// only when not followint [|&;<>].
// TODO(mikesamuel): recognize non-latin letters and numerals in idents
// A hex number
// or an octal or decimal number,
// possibly in scientific notation
// with an optional modifier like UL for unsigned long
// Don't treat escaped quotes in bash as starting strings.
// See issue 144.
```

<details><summary>Code</summary>

```typescript
function sourceDecorator(options) {
    var shortcutStylePatterns = [], fallthroughStylePatterns = [];
    if (options['tripleQuotedStrings']) {
      // '''multi-line-string''', 'single-line-string', and double-quoted
      shortcutStylePatterns.push(
          [PR_STRING,  /^(?:\'\'\'(?:[^\'\\]|\\[\s\S]|\'{1,2}(?=[^\']))*(?:\'\'\'|$)|\"\"\"(?:[^\"\\]|\\[\s\S]|\"{1,2}(?=[^\"]))*(?:\"\"\"|$)|\'(?:[^\\\']|\\[\s\S])*(?:\'|$)|\"(?:[^\\\"]|\\[\s\S])*(?:\"|$))/,
           null, '\'"']);
    } else if (options['multiLineStrings']) {
      // 'multi-line-string', "multi-line-string"
      shortcutStylePatterns.push(
          [PR_STRING,  /^(?:\'(?:[^\\\']|\\[\s\S])*(?:\'|$)|\"(?:[^\\\"]|\\[\s\S])*(?:\"|$)|\`(?:[^\\\`]|\\[\s\S])*(?:\`|$))/,
           null, '\'"`']);
    } else {
      // 'single-line-string', "single-line-string"
      shortcutStylePatterns.push(
          [PR_STRING,
           /^(?:\'(?:[^\\\'\r\n]|\\.)*(?:\'|$)|\"(?:[^\\\"\r\n]|\\.)*(?:\"|$))/,
           null, '"\'']);
    }
    if (options['verbatimStrings']) {
      // verbatim-string-literal production from the C# grammar.  See issue 93.
      fallthroughStylePatterns.push(
          [PR_STRING, /^@\"(?:[^\"]|\"\")*(?:\"|$)/, null]);
    }
    var hc = options['hashComments'];
    if (hc) {
      if (options['cStyleComments']) {
        if (hc > 1) {  // multiline hash comments
          shortcutStylePatterns.push(
              [PR_COMMENT, /^#(?:##(?:[^#]|#(?!##))*(?:###|$)|.*)/, null, '#']);
        } else {
          // Stop C preprocessor declarations at an unclosed open comment
          shortcutStylePatterns.push(
              [PR_COMMENT, /^#(?:(?:define|e(?:l|nd)if|else|error|ifn?def|include|line|pragma|undef|warning)\b|[^\r\n]*)/,
               null, '#']);
        }
        // #include <stdio.h>
        fallthroughStylePatterns.push(
            [PR_STRING,
             /^<(?:(?:(?:\.\.\/)*|\/?)(?:[\w-]+(?:\/[\w-]+)+)?[\w-]+\.h(?:h|pp|\+\+)?|[a-z]\w*)>/,
             null]);
      } else {
        shortcutStylePatterns.push([PR_COMMENT, /^#[^\r\n]*/, null, '#']);
      }
    }
    if (options['cStyleComments']) {
      fallthroughStylePatterns.push([PR_COMMENT, /^\/\/[^\r\n]*/, null]);
      fallthroughStylePatterns.push(
          [PR_COMMENT, /^\/\*[\s\S]*?(?:\*\/|$)/, null]);
    }
    var regexLiterals = options['regexLiterals'];
    if (regexLiterals) {
      /**
       * @const
       */
      var regexExcls = regexLiterals > 1
        ? ''  // Multiline regex literals
        : '\n\r';
      /**
       * @const
       */
      var regexAny = regexExcls ? '.' : '[\\S\\s]';
      /**
       * @const
       */
      var REGEX_LITERAL = (
          // A regular expression literal starts with a slash that is
          // not followed by * or / so that it is not confused with
          // comments.
          '/(?=[^/*' + regexExcls + '])'
          // and then contains any number of raw characters,
          + '(?:[^/\\x5B\\x5C' + regexExcls + ']'
          // escape sequences (\x5C),
          +    '|\\x5C' + regexAny
          // or non-nesting character sets (\x5B\x5D);
          +    '|\\x5B(?:[^\\x5C\\x5D' + regexExcls + ']'
          +             '|\\x5C' + regexAny + ')*(?:\\x5D|$))+'
          // finally closed by a /.
          + '/');
      fallthroughStylePatterns.push(
          ['lang-regex',
           RegExp('^' + REGEXP_PRECEDER_PATTERN + '(' + REGEX_LITERAL + ')')
           ]);
    }

    var types = options['types'];
    if (types) {
      fallthroughStylePatterns.push([PR_TYPE, types]);
    }

    var keywords = ("" + options['keywords']).replace(/^ | $/g, '');
    if (keywords.length) {
      fallthroughStylePatterns.push(
          [PR_KEYWORD,
           new RegExp('^(?:' + keywords.replace(/[\s,]+/g, '|') + ')\\b'),
           null]);
    }

    shortcutStylePatterns.push([PR_PLAIN,       /^\s+/, null, ' \r\n\t\xA0']);

    var punctuation =
      // The Bash man page says

      // A word is a sequence of characters considered as a single
      // unit by GRUB. Words are separated by metacharacters,
      // which are the following plus space, tab, and newline: { }
      // | & $ ; < >
      // ...
      
      // A word beginning with # causes that word and all remaining
      // characters on that line to be ignored.

      // which means that only a '#' after /(?:^|[{}|&$;<>\s])/ starts a
      // comment but empirically
      // $ echo {#}
      // {#}
      // $ echo \$#
      // $#
      // $ echo }#
      // }#

      // so /(?:^|[|&;<>\s])/ is more appropriate.

      // http://gcc.gnu.org/onlinedocs/gcc-2.95.3/cpp_1.html#SEC3
      // suggests that this definition is compatible with a
      // default mode that tries to use a single token definition
      // to recognize both bash/python style comments and C
      // preprocessor directives.

      // This definition of punctuation does not include # in the list of
      // follow-on exclusions, so # will not be broken before if preceeded
      // by a punctuation character.  We could try to exclude # after
      // [|&;<>] but that doesn't seem to cause many major problems.
      // If that does turn out to be a problem, we should change the below
      // when hc is truthy to include # in the run of punctuation characters
      // only when not followint [|&;<>].
      '^.[^\\s\\w.$@\'"`/\\\\]*';
    if (options['regexLiterals']) {
      punctuation += '(?!s*/)';
    }

    fallthroughStylePatterns.push(
        // TODO(mikesamuel): recognize non-latin letters and numerals in idents
        [PR_LITERAL,     /^@[a-z_$][a-z_$@0-9]*/i, null],
        [PR_TYPE,        /^(?:[@_]?[A-Z]+[a-z][A-Za-z_$@0-9]*|\w+_t\b)/, null],
        [PR_PLAIN,       /^[a-z_$][a-z_$@0-9]*/i, null],
        [PR_LITERAL,
         new RegExp(
             '^(?:'
             // A hex number
             + '0x[a-f0-9]+'
             // or an octal or decimal number,
             + '|(?:\\d(?:_\\d+)*\\d*(?:\\.\\d*)?|\\.\\d\\+)'
             // possibly in scientific notation
             + '(?:e[+\\-]?\\d+)?'
             + ')'
             // with an optional modifier like UL for unsigned long
             + '[a-z]*', 'i'),
         null, '0123456789'],
        // Don't treat escaped quotes in bash as starting strings.
        // See issue 144.
        [PR_PLAIN,       /^\\[\s\S]?/, null],
        [PR_PUNCTUATION, new RegExp(punctuation), null]);

    return createSimpleLexer(shortcutStylePatterns, fallthroughStylePatterns);
  }
```
</details>

### `numberLines(node: Node, opt_startLineNum: any, isPreformatted: boolean, opt_numberLines: any, opt_calloutModifiedLines: any): void`

**JSDoc:**
```typescript
/**
   * Given a DOM subtree, wraps it in a list, and puts each line into its own
   * list item.
   *
   * @param {Node} node modified in place.  Its content is pulled into an
   *     HTMLOListElement, and each line is moved into a separate list item.
   *     This requires cloning elements, so the input might not have unique
   *     IDs after numbering.
   * @param {boolean} isPreformatted true if white-space in text nodes should
   *     be treated as significant.
   */
```

**Parameters:**

- **`node`** `Node`
- **`opt_startLineNum`** `any`
- **`isPreformatted`** `boolean`
- **`opt_numberLines`** `any`
- **`opt_calloutModifiedLines`** `any`

**Returns:** `void`

**Calls:**

- `str.substring`
- `document.createElement`
- `li.appendChild`
- `nocode.test`
- `breakAfter`
- `node.parentNode.removeChild`
- `walk`
- `text.match`
- `text.substring`
- `parent.insertBefore`
- `document.createTextNode`
- `limit.cloneNode`
- `breakLeftOf`
- `parentClone.appendChild`
- `listItems.push`
- `listItems[0].setAttribute`
- `classNames.push`
- `classNames.join`
- `Math.max`
- `findTextWithPrefix`
- `startsWith`
- `ol.appendChild`
- `node.appendChild`

**Internal Comments:**
```
// An array of lines.  We split below, so this is initialized to one (x2)
// un-split line. (x2)
// Discard the <BR> since it is now flush against a </LI>.
// Don't leave blank text nodes in the DOM. (x5)
// Split a line after the given node.
// If there's nothing to the right, then we can skip ending the line
// here, and move root-wards since splitting just before an end-tag
// would require us to create a bunch of empty copies.
// Clone shallowly if this node needs to be on both sides of the break. (x2)
// We clone the parent chain. (x2)
// This helps us resurrect important styling elements that cross lines. (x2)
// E.g. in <i>Foo<br>Bar</i> (x2)
// should be rewritten to <li><i>Foo</i></li><li><i>Bar</i></li>. (x2)
// Move the clone and everything to the right of the original (x2)
// onto the cloned parent. (x2)
// Walk the parent chain until we reach an unattached LI.
// Check nodeType since IE invents document fragments. (x2)
// Put it on the list of lines for later processing. (x4)
// Split lines while there are lines left to split.
// Make sure numeric indices show correctly.
// Stick a class on the LIs so that stylesheets can (x2)
// color odd/even rows, or any other row pattern that (x2)
// is co-prime with 10. (x2)
// returns undefined to continue, true of found, false if not found
```

<details><summary>Code</summary>

```typescript
function numberLines(node, opt_startLineNum, isPreformatted, opt_numberLines, opt_calloutModifiedLines) {
    var nocode = /(?:^|\s)nocode(?:\s|$)/;
    var lineBreak = /\r\n?|\n/;
    var prefixes = [
      { prefix: "*", className: "linemodified", },
      { prefix: "-", className: "linedeleted", },
      { prefix: "+", className: "lineadded", },
    ];
    opt_numberLines = (opt_numberLines == undefined) ? true : opt_numberLines;

    var startsWith = function(str, prefix) {
      return str.length >= prefix.length && str.substring(0, prefix.length) == prefix;
    };
  
    var document = node.ownerDocument;
  
    var li = document.createElement('li');
    while (node.firstChild) {
      li.appendChild(node.firstChild);
    }
    // An array of lines.  We split below, so this is initialized to one
    // un-split line.
    var listItems = [li];
  
    function walk(node) {
      var type = node.nodeType;
      if (type == 1 && !nocode.test(node.className)) {  // Element
        if ('br' === node.nodeName) {
          breakAfter(node);
          // Discard the <BR> since it is now flush against a </LI>.
          if (node.parentNode) {
            node.parentNode.removeChild(node);
          }
        } else {
          for (var child = node.firstChild; child; child = child.nextSibling) {
            walk(child);
          }
        }
      } else if ((type == 3 || type == 4) && isPreformatted) {  // Text
        var text = node.nodeValue;
        var match = text.match(lineBreak);
        if (match) {
          var firstLine = text.substring(0, match.index);
          node.nodeValue = firstLine;
          var tail = text.substring(match.index + match[0].length);
          if (tail) {
            var parent = node.parentNode;
            parent.insertBefore(
              document.createTextNode(tail), node.nextSibling);
          }
          breakAfter(node);
          if (!firstLine) {
            // Don't leave blank text nodes in the DOM.
            node.parentNode.removeChild(node);
          }
        }
      }
    }
  
    // Split a line after the given node.
    function breakAfter(lineEndNode) {
      // If there's nothing to the right, then we can skip ending the line
      // here, and move root-wards since splitting just before an end-tag
      // would require us to create a bunch of empty copies.
      while (!lineEndNode.nextSibling) {
        lineEndNode = lineEndNode.parentNode;
        if (!lineEndNode) { return; }
      }
  
      function breakLeftOf(limit, copy) {
        // Clone shallowly if this node needs to be on both sides of the break.
        var rightSide = copy ? limit.cloneNode(false) : limit;
        var parent = limit.parentNode;
        if (parent) {
          // We clone the parent chain.
          // This helps us resurrect important styling elements that cross lines.
          // E.g. in <i>Foo<br>Bar</i>
          // should be rewritten to <li><i>Foo</i></li><li><i>Bar</i></li>.
          var parentClone = breakLeftOf(parent, 1);
          // Move the clone and everything to the right of the original
          // onto the cloned parent.
          var next = limit.nextSibling;
          parentClone.appendChild(rightSide);
          for (var sibling = next; sibling; sibling = next) {
            next = sibling.nextSibling;
            parentClone.appendChild(sibling);
          }
        }
        return rightSide;
      }
  
      var copiedListItem = breakLeftOf(lineEndNode.nextSibling, 0);
  
      // Walk the parent chain until we reach an unattached LI.
      for (var parent;
           // Check nodeType since IE invents document fragments.
           (parent = copiedListItem.parentNode) && parent.nodeType === 1;) {
        copiedListItem = parent;
      }
      // Put it on the list of lines for later processing.
      listItems.push(copiedListItem);
    }
  
    // Split lines while there are lines left to split.
    for (var i = 0;  // Number of lines that have been split so far.
         i < listItems.length;  // length updated by breakAfter calls.
         ++i) {
      walk(listItems[i]);
    }
  
    // Make sure numeric indices show correctly.
    if (opt_startLineNum === (opt_startLineNum|0)) {
      listItems[0].setAttribute('value', opt_startLineNum);
    }
  
    var ol = document.createElement(opt_numberLines ? 'ol' : 'ul');
    const classNames = [];
    if (opt_numberLines) {
      classNames.push('linenums');
    }
    if (opt_calloutModifiedLines) {
      classNames.push('modifiedlines');
    }
    ol.className = classNames.join(" ");
    var offset = Math.max(0, (opt_startLineNum - 1 /* zero index */) | 0) || 0;
    for (var i = 0, n = listItems.length; i < n; ++i) {
      li = listItems[i];
      // Stick a class on the LIs so that stylesheets can
      // color odd/even rows, or any other row pattern that
      // is co-prime with 10.
      const classNames = [];
      if (opt_numberLines) {
        classNames.push('L' + ((i + offset) % 10));
      }
      if (!li.firstChild) {
        li.appendChild(document.createTextNode('\xA0'));
      }
      if (opt_calloutModifiedLines) {
        // returns undefined to continue, true of found, false if not found
        function findTextWithPrefix(node) {
          if (!node) {
            return;
          }
          var type = node.nodeType;
          if (type == 1) { // Element
            for (var child = node.firstChild; child; child = child.nextSibling) {
              var result = findTextWithPrefix(child);
              if (result !== undefined) {
                  return result;
              }
            }
          } else if (type == 3 || type == 4) {
            var text = node.nodeValue;
            if (text.length > 0) {
              for (var pp = 0; pp < prefixes.length; ++pp) {
                var prefixInfo = prefixes[pp];
                if (startsWith(text, prefixInfo.prefix)) {
                  node.nodeValue = text.substring(prefixInfo.prefix.length) || ' ';
                  return prefixInfo.className;
                }
              }
              return false;
            }
          }
        }
        var foundPrefix = findTextWithPrefix(li);
        if (foundPrefix) {
          classNames.push(foundPrefix);
        }
      }
      li.className = classNames.join(" ");
      ol.appendChild(li);
    }
  
    node.appendChild(ol);
  }
```
</details>

### `startsWith(str: any, prefix: any): boolean`

**Parameters:**

- **`str`** `any`
- **`prefix`** `any`

**Returns:** `boolean`

**Calls:**

- `str.substring`

<details><summary>Code</summary>

```typescript
function(str, prefix) {
      return str.length >= prefix.length && str.substring(0, prefix.length) == prefix;
    }
```
</details>

### `walk(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `nocode.test`
- `breakAfter`
- `node.parentNode.removeChild`
- `walk`
- `text.match`
- `text.substring`
- `parent.insertBefore`
- `document.createTextNode`

**Internal Comments:**
```
// Discard the <BR> since it is now flush against a </LI>.
// Don't leave blank text nodes in the DOM. (x5)
```

<details><summary>Code</summary>

```typescript
function walk(node) {
      var type = node.nodeType;
      if (type == 1 && !nocode.test(node.className)) {  // Element
        if ('br' === node.nodeName) {
          breakAfter(node);
          // Discard the <BR> since it is now flush against a </LI>.
          if (node.parentNode) {
            node.parentNode.removeChild(node);
          }
        } else {
          for (var child = node.firstChild; child; child = child.nextSibling) {
            walk(child);
          }
        }
      } else if ((type == 3 || type == 4) && isPreformatted) {  // Text
        var text = node.nodeValue;
        var match = text.match(lineBreak);
        if (match) {
          var firstLine = text.substring(0, match.index);
          node.nodeValue = firstLine;
          var tail = text.substring(match.index + match[0].length);
          if (tail) {
            var parent = node.parentNode;
            parent.insertBefore(
              document.createTextNode(tail), node.nextSibling);
          }
          breakAfter(node);
          if (!firstLine) {
            // Don't leave blank text nodes in the DOM.
            node.parentNode.removeChild(node);
          }
        }
      }
    }
```
</details>

### `breakAfter(lineEndNode: any): void`

**Parameters:**

- **`lineEndNode`** `any`

**Returns:** `void`

**Calls:**

- `limit.cloneNode`
- `breakLeftOf`
- `parentClone.appendChild`
- `listItems.push`

**Internal Comments:**
```
// If there's nothing to the right, then we can skip ending the line
// here, and move root-wards since splitting just before an end-tag
// would require us to create a bunch of empty copies.
// Clone shallowly if this node needs to be on both sides of the break. (x2)
// We clone the parent chain. (x2)
// This helps us resurrect important styling elements that cross lines. (x2)
// E.g. in <i>Foo<br>Bar</i> (x2)
// should be rewritten to <li><i>Foo</i></li><li><i>Bar</i></li>. (x2)
// Move the clone and everything to the right of the original (x2)
// onto the cloned parent. (x2)
// Walk the parent chain until we reach an unattached LI.
// Check nodeType since IE invents document fragments. (x2)
// Put it on the list of lines for later processing. (x4)
```

<details><summary>Code</summary>

```typescript
function breakAfter(lineEndNode) {
      // If there's nothing to the right, then we can skip ending the line
      // here, and move root-wards since splitting just before an end-tag
      // would require us to create a bunch of empty copies.
      while (!lineEndNode.nextSibling) {
        lineEndNode = lineEndNode.parentNode;
        if (!lineEndNode) { return; }
      }
  
      function breakLeftOf(limit, copy) {
        // Clone shallowly if this node needs to be on both sides of the break.
        var rightSide = copy ? limit.cloneNode(false) : limit;
        var parent = limit.parentNode;
        if (parent) {
          // We clone the parent chain.
          // This helps us resurrect important styling elements that cross lines.
          // E.g. in <i>Foo<br>Bar</i>
          // should be rewritten to <li><i>Foo</i></li><li><i>Bar</i></li>.
          var parentClone = breakLeftOf(parent, 1);
          // Move the clone and everything to the right of the original
          // onto the cloned parent.
          var next = limit.nextSibling;
          parentClone.appendChild(rightSide);
          for (var sibling = next; sibling; sibling = next) {
            next = sibling.nextSibling;
            parentClone.appendChild(sibling);
          }
        }
        return rightSide;
      }
  
      var copiedListItem = breakLeftOf(lineEndNode.nextSibling, 0);
  
      // Walk the parent chain until we reach an unattached LI.
      for (var parent;
           // Check nodeType since IE invents document fragments.
           (parent = copiedListItem.parentNode) && parent.nodeType === 1;) {
        copiedListItem = parent;
      }
      // Put it on the list of lines for later processing.
      listItems.push(copiedListItem);
    }
```
</details>

### `breakLeftOf(limit: any, copy: any): any`

**Parameters:**

- **`limit`** `any`
- **`copy`** `any`

**Returns:** `any`

**Calls:**

- `limit.cloneNode`
- `breakLeftOf`
- `parentClone.appendChild`

**Internal Comments:**
```
// Clone shallowly if this node needs to be on both sides of the break. (x2)
// We clone the parent chain. (x2)
// This helps us resurrect important styling elements that cross lines. (x2)
// E.g. in <i>Foo<br>Bar</i> (x2)
// should be rewritten to <li><i>Foo</i></li><li><i>Bar</i></li>. (x2)
// Move the clone and everything to the right of the original (x2)
// onto the cloned parent. (x2)
```

<details><summary>Code</summary>

```typescript
function breakLeftOf(limit, copy) {
        // Clone shallowly if this node needs to be on both sides of the break.
        var rightSide = copy ? limit.cloneNode(false) : limit;
        var parent = limit.parentNode;
        if (parent) {
          // We clone the parent chain.
          // This helps us resurrect important styling elements that cross lines.
          // E.g. in <i>Foo<br>Bar</i>
          // should be rewritten to <li><i>Foo</i></li><li><i>Bar</i></li>.
          var parentClone = breakLeftOf(parent, 1);
          // Move the clone and everything to the right of the original
          // onto the cloned parent.
          var next = limit.nextSibling;
          parentClone.appendChild(rightSide);
          for (var sibling = next; sibling; sibling = next) {
            next = sibling.nextSibling;
            parentClone.appendChild(sibling);
          }
        }
        return rightSide;
      }
```
</details>

### `findTextWithPrefix(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `findTextWithPrefix`
- `startsWith`
- `text.substring`

<details><summary>Code</summary>

```typescript
function findTextWithPrefix(node) {
          if (!node) {
            return;
          }
          var type = node.nodeType;
          if (type == 1) { // Element
            for (var child = node.firstChild; child; child = child.nextSibling) {
              var result = findTextWithPrefix(child);
              if (result !== undefined) {
                  return result;
              }
            }
          } else if (type == 3 || type == 4) {
            var text = node.nodeValue;
            if (text.length > 0) {
              for (var pp = 0; pp < prefixes.length; ++pp) {
                var prefixInfo = prefixes[pp];
                if (startsWith(text, prefixInfo.prefix)) {
                  node.nodeValue = text.substring(prefixInfo.prefix.length) || ' ';
                  return prefixInfo.className;
                }
              }
              return false;
            }
          }
        }
```
</details>

### `recombineTagsAndDecorations(job: any): void`

**JSDoc:**
```typescript
/**
   * Breaks {@code job.sourceCode} around style boundaries in
   * {@code job.decorations} and modifies {@code job.sourceNode} in place.
   * @param {Object} job like <pre>{
   *    sourceCode: {string} source as plain text,
   *    sourceNode: {HTMLElement} the element containing the source,
   *    spans: {Array.<number|Node>} alternating span start indices into source
   *       and the text node or element (e.g. {@code <BR>}) corresponding to that
   *       span.
   *    decorations: {Array.<number|string} an array of style classes preceded
   *       by the position at which they start in job.sourceCode in order
   * }</pre>
   * @private
   */
```

**Parameters:**

- **`job`** `any`

**Returns:** `void`

**Calls:**

- `/\bMSIE\s(\d+)/.exec`
- `Math.min`
- `source.substring`
- `styledText.replace`
- `document.createElement`
- `parentNode.replaceChild`
- `span.appendChild`
- `document.createTextNode`
- `parentNode.insertBefore`

**Internal Comments:**
```
// Index into source after the last code-unit recombined. (x2)
// Index into spans after the last span which ends at or before sourceIndex. (x2)
// Index into decorations after the last decoration which ends at or before (x2)
// sourceIndex. (x2)
// Remove all zero-length decorations. (x4)
// Simplify decorations.
// Conflate all adjacent decorations that use the same style. (x2)
// Don't introduce spans around empty text nodes.
// This may seem bizarre, and it is.  Emitting LF on IE causes the
// code to display with spaces instead of line breaks.
// Emitting Windows standard issue linebreaks (CRLF) causes a blank
// space to appear at the beginning of every line but the first.
// Emitting an old Mac OS 9 line separator makes everything spiffy.
// TODO: Possibly optimize by using '' if there's no flicker.
```

<details><summary>Code</summary>

```typescript
function recombineTagsAndDecorations(job) {
    var isIE8OrEarlier = /\bMSIE\s(\d+)/.exec(navigator.userAgent);
    isIE8OrEarlier = isIE8OrEarlier && +isIE8OrEarlier[1] <= 8;
    var newlineRe = /\n/g;
  
    var source = job.sourceCode;
    var sourceLength = source.length;
    // Index into source after the last code-unit recombined.
    var sourceIndex = 0;
  
    var spans = job.spans;
    var nSpans = spans.length;
    // Index into spans after the last span which ends at or before sourceIndex.
    var spanIndex = 0;
  
    var decorations = job.decorations;
    var nDecorations = decorations.length;
    // Index into decorations after the last decoration which ends at or before
    // sourceIndex.
    var decorationIndex = 0;
  
    // Remove all zero-length decorations.
    decorations[nDecorations] = sourceLength;
    var decPos, i;
    for (i = decPos = 0; i < nDecorations;) {
      if (decorations[i] !== decorations[i + 2]) {
        decorations[decPos++] = decorations[i++];
        decorations[decPos++] = decorations[i++];
      } else {
        i += 2;
      }
    }
    nDecorations = decPos;
  
    // Simplify decorations.
    for (i = decPos = 0; i < nDecorations;) {
      var startPos = decorations[i];
      // Conflate all adjacent decorations that use the same style.
      var startDec = decorations[i + 1];
      let end = i + 2;
      while (end + 2 <= nDecorations && decorations[end + 1] === startDec) {
        end += 2;
      }
      decorations[decPos++] = startPos;
      decorations[decPos++] = startDec;
      i = end;
    }
  
    decorations.length = decPos;
  
    var sourceNode = job.sourceNode;
    var oldDisplay;
    if (sourceNode) {
      oldDisplay = sourceNode.style.display;
      sourceNode.style.display = 'none';
    }
    try {
      decoration = null;
      while (spanIndex < nSpans) {
        var spanEnd = spans[spanIndex + 2] || sourceLength;
  
        var decEnd = decorations[decorationIndex + 2] || sourceLength;
  
        const end = Math.min(spanEnd, decEnd);
  
        var textNode = spans[spanIndex + 1];
        var styledText;
        if (textNode.nodeType !== 1  // Don't muck with <BR>s or <LI>s
            // Don't introduce spans around empty text nodes.
            && (styledText = source.substring(sourceIndex, end))) {
          // This may seem bizarre, and it is.  Emitting LF on IE causes the
          // code to display with spaces instead of line breaks.
          // Emitting Windows standard issue linebreaks (CRLF) causes a blank
          // space to appear at the beginning of every line but the first.
          // Emitting an old Mac OS 9 line separator makes everything spiffy.
          if (isIE8OrEarlier) {
            styledText = styledText.replace(newlineRe, '\r');
          }
          textNode.nodeValue = styledText;
          var document = textNode.ownerDocument;
          var span = document.createElement('span');
          span.className = decorations[decorationIndex + 1];
          var parentNode = textNode.parentNode;
          parentNode.replaceChild(span, textNode);
          span.appendChild(textNode);
          if (sourceIndex < spanEnd) {  // Split off a text node.
            spans[spanIndex + 1] = textNode
                // TODO: Possibly optimize by using '' if there's no flicker.
                = document.createTextNode(source.substring(end, spanEnd));
            parentNode.insertBefore(textNode, span.nextSibling);
          }
        }
  
        sourceIndex = end;
  
        if (sourceIndex >= spanEnd) {
          spanIndex += 2;
        }
        if (sourceIndex >= decEnd) {
          decorationIndex += 2;
        }
      }
    } finally {
      if (sourceNode) {
        sourceNode.style.display = oldDisplay;
      }
    }
  }
```
</details>

### `registerLangHandler(handler: (arg0: any) => any, fileExtensions: string[]): void`

**JSDoc:**
```typescript
/** Register a language handler for the given file extensions.
    * @param {function (Object)} handler a function from source code to a list
    *      of decorations.  Takes a single argument job which describes the
    *      state of the computation.   The single parameter has the form
    *      {@code {
    *        sourceCode: {string} as plain text.
    *        decorations: {Array.<number|string>} an array of style classes
    *                     preceded by the position at which they start in
    *                     job.sourceCode in order.
    *                     The language handler should assigned this field.
    *        basePos: {int} the position of source in the larger source chunk.
    *                 All positions in the output decorations array are relative
    *                 to the larger source chunk.
    *      } }
    * @param {Array.<string>} fileExtensions
    */
```

**Parameters:**

- **`handler`** `(arg0: any) => any`
- **`fileExtensions`** `string[]`

**Returns:** `void`

**Calls:**

- `langHandlerRegistry.hasOwnProperty`
- `complex_call_49888`

<details><summary>Code</summary>

```typescript
function registerLangHandler(handler, fileExtensions) {
    for (var i = fileExtensions.length; --i >= 0;) {
      var ext = fileExtensions[i];
      if (!langHandlerRegistry.hasOwnProperty(ext)) {
        langHandlerRegistry[ext] = handler;
      } else if (win['console']) {
        console['warn']('cannot override language handler %s', ext);
      }
    }
  }
```
</details>

### `langHandlerForExtension(extension: any, source: any): any`

**Parameters:**

- **`extension`** `any`
- **`source`** `any`

**Returns:** `any`

**Calls:**

- `langHandlerRegistry.hasOwnProperty`
- `/^\s*</.test`

**Internal Comments:**
```
// Treat it as markup if the first non whitespace character is a < and (x3)
// the last non-whitespace character is a >. (x3)
```

<details><summary>Code</summary>

```typescript
function langHandlerForExtension(extension, source) {
    if (!(extension && langHandlerRegistry.hasOwnProperty(extension))) {
      // Treat it as markup if the first non whitespace character is a < and
      // the last non-whitespace character is a >.
      extension = /^\s*</.test(source)
          ? 'default-markup'
          : 'default-code';
    }
    return langHandlerRegistry[extension];
  }
```
</details>

### `applyDecorator(job: any): void`

**Parameters:**

- **`job`** `any`

**Returns:** `void`

**Calls:**

- `extractSourceSpans`
- `complex_call_55082`
- `recombineTagsAndDecorations`
- `complex_call_55349`

**Internal Comments:**
```
// Extract tags, and convert the source code to plain text. (x2)
/** Plain text. @type {string} */ (x2)
// Apply the appropriate language handler (x4)
// Integrate the decorations and tags back into the source code, (x3)
// modifying the sourceNode in place. (x3)
```

<details><summary>Code</summary>

```typescript
function applyDecorator(job) {
    var opt_langExtension = job.langExtension;

    try {
      // Extract tags, and convert the source code to plain text.
      var sourceAndSpans = extractSourceSpans(job.sourceNode, job.pre);
      /** Plain text. @type {string} */
      var source = sourceAndSpans.sourceCode;
      job.sourceCode = source;
      job.spans = sourceAndSpans.spans;
      job.basePos = 0;

      // Apply the appropriate language handler
      langHandlerForExtension(opt_langExtension, source)(job);

      // Integrate the decorations and tags back into the source code,
      // modifying the sourceNode in place.
      recombineTagsAndDecorations(job);
    } catch (e) {
      if (win['console']) {
        console['log'](e && e['stack'] || e);
      }
    }
  }
```
</details>

### `$prettyPrintOne(sourceCodeHtml: string, opt_langExtension: string, opt_numberLines: number | boolean): string`

**JSDoc:**
```typescript
/**
   * Pretty print a chunk of code.
   * @param sourceCodeHtml {string} The HTML to pretty print.
   * @param opt_langExtension {string} The language name to use.
   *     Typically, a filename extension like 'cpp' or 'java'.
   * @param opt_numberLines {number|boolean} True to number lines,
   *     or the 1-indexed number of the first line in sourceCodeHtml.
   */
```

**Parameters:**

- **`sourceCodeHtml`** `string`
- **`opt_langExtension`** `string`
- **`opt_numberLines`** `number | boolean`

**Returns:** `string`

**Calls:**

- `document.createElement`
- `numberLines`
- `applyDecorator`

**Internal Comments:**
```
// This could cause images to load and onload listeners to fire. (x4)
// E.g. <img onerror="alert(1337)" src="nosuchimage.png">. (x4)
// We assume that the inner HTML is from a trusted source. (x4)
// The pre-tag is required for IE8 which strips newlines from innerHTML (x4)
// when it is injected into a <pre> tag. (x4)
// http://stackoverflow.com/questions/451486/pre-tag-loses-line-breaks-when-setting-innerhtml-in-ie (x4)
// http://stackoverflow.com/questions/195363/inserting-a-newline-into-a-pre-tag-ie-javascript (x4)
```

<details><summary>Code</summary>

```typescript
function $prettyPrintOne(sourceCodeHtml, opt_langExtension, opt_numberLines) {
    var container = document.createElement('div');
    // This could cause images to load and onload listeners to fire.
    // E.g. <img onerror="alert(1337)" src="nosuchimage.png">.
    // We assume that the inner HTML is from a trusted source.
    // The pre-tag is required for IE8 which strips newlines from innerHTML
    // when it is injected into a <pre> tag.
    // http://stackoverflow.com/questions/451486/pre-tag-loses-line-breaks-when-setting-innerhtml-in-ie
    // http://stackoverflow.com/questions/195363/inserting-a-newline-into-a-pre-tag-ie-javascript
    container.innerHTML = '<pre>' + sourceCodeHtml + '</pre>';
    container = container.firstChild;
    if (opt_numberLines) {
      numberLines(container, opt_numberLines, true);
    }

    var job = {
      langExtension: opt_langExtension,
      numberLines: opt_numberLines,
      sourceNode: container,
      pre: 1
    };
    applyDecorator(job);
    return container.innerHTML;
  }
```
</details>

### `$prettyPrint(opt_whenDone: Function, opt_root: HTMLElement | HTMLDocument): void`

**JSDoc:**
```typescript
/**
    * Find all the {@code <pre>} and {@code <code>} tags in the DOM with
    * {@code class=prettyprint} and prettify them.
    *
    * @param {Function} opt_whenDone called when prettifying is done.
    * @param {HTMLElement|HTMLDocument} opt_root an element or document
    *   containing all the elements to pretty print.
    *   Defaults to {@code document.body}.
    */
```

**Parameters:**

- **`opt_whenDone`** `Function`
- **`opt_root`** `HTMLElement | HTMLDocument`

**Returns:** `void`

**Calls:**

- `root.getElementsByTagName`
- `byTagName`
- `elements.push`
- `complex_call_58452`
- `complex_call_58552`
- `/^\??prettify\b/.test`
- `/\S/.test`
- `value.replace`
- `prettyPrintRe.test`
- `prettyPrintedRe.test`
- `preCodeXmpRe.test`
- `className.match`
- `childContentWrapper`
- `codeRe.test`
- `wrapper.className.match`
- `preformattedTagNameRe.test`
- `defaultView.getComputedStyle(cs, null)
                  .getPropertyValue`
- `whitespace.substring`
- `numberLines`
- `applyDecorator`
- `setTimeout`
- `opt_whenDone`
- `doWork`

**Internal Comments:**
```
// fetch a list of nodes to rewrite (x2)
// The loop is broken into a series of continuations to make sure that we (x2)
// don't make the browser unresponsive when rewriting a large page. (x2)
// Look for a preceding comment like (x2)
// <?prettify lang="..." linenums="..."?> (x2)
// <?foo?> is parsed by HTML 5 to a comment node (8) (x2)
// like <!--?foo?-->, but in XML is a processing instruction (x2)
// Skip over white-space text nodes but not others.
// Don't redo this if we've already done it.
// This allows recalling pretty print to just prettyprint elements
// that have been added to the page since last call.
// make sure this is not nested in an already prettified element (x2)
// Mark done.  If we fail to prettyprint for whatever reason, (x4)
// we shouldn't try again. (x4)
// If the classes includes a language extensions, use it. (x2)
// Language extensions can be specified like (x2)
//     <pre class="prettyprint lang-cpp"> (x2)
// the language extension "cpp" is used to find a language handler (x2)
// as passed to PR.registerLangHandler. (x2)
// HTML5 recommends that a language be specified using "language-" (x2)
// as the prefix instead.  Google Code Prettify supports both. (x2)
// http://dev.w3.org/html5/spec-author-view/the-code-element.html (x2)
// Support <pre class="prettyprint"><code class="language-c"> (x2)
// Look for a class like linenums or linenums:<n> where <n> is the (x2)
// 1-indexed number of the first line. (x2)
// do the pretty printing (x3)
// finish up in a continuation (x3)
```

<details><summary>Code</summary>

```typescript
function $prettyPrint(opt_whenDone, opt_root) {
    var root = opt_root || document.body;
    var doc = root.ownerDocument || document;
    function byTagName(tn) { return root.getElementsByTagName(tn); }
    // fetch a list of nodes to rewrite
    var codeSegments = [byTagName('pre'), byTagName('code'), byTagName('xmp')];
    var elements = [];
    for (var i = 0; i < codeSegments.length; ++i) {
      for (var j = 0, n = codeSegments[i].length; j < n; ++j) {
        elements.push(codeSegments[i][j]);
      }
    }
    codeSegments = null;

    var clock = Date;
    if (!clock['now']) {
      clock = { 'now': function () { return +(new Date); } };
    }

    // The loop is broken into a series of continuations to make sure that we
    // don't make the browser unresponsive when rewriting a large page.
    var k = 0;
    var prettyPrintingJob;

    var langExtensionRe = /\blang(?:uage)?-([\w.]+)(?!\S)/;
    var prettyPrintRe = /\bprettyprint\b/;
    var prettyPrintedRe = /\bprettyprinted\b/;
    var preformattedTagNameRe = /pre|xmp/i;
    var codeRe = /^code$/i;
    var preCodeXmpRe = /^(?:pre|code|xmp)$/i;
    var EMPTY = {};

    function doWork() {
      var endTime = (win['PR_SHOULD_USE_CONTINUATION'] ?
                     clock['now']() + 250 /* ms */ :
                     Infinity);
      for (; k < elements.length && clock['now']() < endTime; k++) {
        var cs = elements[k];

        // Look for a preceding comment like
        // <?prettify lang="..." linenums="..."?>
        var attrs = EMPTY;
        {
          for (var preceder = cs; (preceder = preceder.previousSibling);) {
            var nt = preceder.nodeType;
            // <?foo?> is parsed by HTML 5 to a comment node (8)
            // like <!--?foo?-->, but in XML is a processing instruction
            var value = (nt === 7 || nt === 8) && preceder.nodeValue;
            if (value
                ? !/^\??prettify\b/.test(value)
                : (nt !== 3 || /\S/.test(preceder.nodeValue))) {
              // Skip over white-space text nodes but not others.
              break;
            }
            if (value) {
              attrs = {};
              value.replace(
                  /\b(\w+)=([\w:.%+-]+)/g,
                function (_, name, value) { attrs[name] = value; });
              break;
            }
          }
        }

        var className = cs.className;
        if ((attrs !== EMPTY || prettyPrintRe.test(className))
            // Don't redo this if we've already done it.
            // This allows recalling pretty print to just prettyprint elements
            // that have been added to the page since last call.
            && !prettyPrintedRe.test(className)) {

          // make sure this is not nested in an already prettified element
          var nested = false;
          for (var p = cs.parentNode; p; p = p.parentNode) {
            var tn = p.tagName;
            if (preCodeXmpRe.test(tn)
                && p.className && prettyPrintRe.test(p.className)) {
              nested = true;
              break;
            }
          }
          if (!nested) {
            // Mark done.  If we fail to prettyprint for whatever reason,
            // we shouldn't try again.
            cs.className += ' prettyprinted';

            // If the classes includes a language extensions, use it.
            // Language extensions can be specified like
            //     <pre class="prettyprint lang-cpp">
            // the language extension "cpp" is used to find a language handler
            // as passed to PR.registerLangHandler.
            // HTML5 recommends that a language be specified using "language-"
            // as the prefix instead.  Google Code Prettify supports both.
            // http://dev.w3.org/html5/spec-author-view/the-code-element.html
            var langExtension = attrs['lang'];
            if (!langExtension) {
              langExtension = className.match(langExtensionRe);
              // Support <pre class="prettyprint"><code class="language-c">
              var wrapper;
              if (!langExtension && (wrapper = childContentWrapper(cs))
                  && codeRe.test(wrapper.tagName)) {
                langExtension = wrapper.className.match(langExtensionRe);
              }

              if (langExtension) { langExtension = langExtension[1]; }
            }

            var preformatted;
            if (preformattedTagNameRe.test(cs.tagName)) {
              preformatted = 1;
            } else {
              var currentStyle = cs['currentStyle'];
              var defaultView = doc.defaultView;
              var whitespace = (
                  currentStyle
                  ? currentStyle['whiteSpace']
                  : (defaultView
                     && defaultView.getComputedStyle)
                  ? defaultView.getComputedStyle(cs, null)
                  .getPropertyValue('white-space')
                  : 0);
              preformatted = whitespace
                  && 'pre' === whitespace.substring(0, 3);
            }

            // Look for a class like linenums or linenums:<n> where <n> is the
            // 1-indexed number of the first line.
            var lineNums = attrs['linenums'];
            if (!(lineNums = lineNums === 'true' || +lineNums)) {
              lineNums = className.match(/\blinenums\b(?::(\d+))?/);
              lineNums =
                lineNums
                ? lineNums[1] && lineNums[1].length
                  ? +lineNums[1] : true
                : false;
            }
            var showLineMods = attrs['showlinemods'];
            if (showLineMods === undefined) {
              showLineMods = className.match(/\bshowlinemods\b/);
            }
            if (lineNums || showLineMods) { numberLines(cs, lineNums, preformatted, lineNums, showLineMods); }

            // do the pretty printing
            prettyPrintingJob = {
              langExtension: langExtension,
              sourceNode: cs,
              numberLines: lineNums,
              pre: preformatted
            };
            applyDecorator(prettyPrintingJob);
          }
        }
      }
      if (k < elements.length) {
        // finish up in a continuation
        setTimeout(doWork, 250);
      } else if ('function' === typeof opt_whenDone) {
        opt_whenDone();
      }
    }

    doWork();
  }
```
</details>

### `byTagName(tn: any): HTMLCollectionOf<any>`

**Parameters:**

- **`tn`** `any`

**Returns:** `HTMLCollectionOf<any>`

**Calls:**

- `root.getElementsByTagName`

<details><summary>Code</summary>

```typescript
function byTagName(tn) { return root.getElementsByTagName(tn); }
```
</details>

### `doWork(): void`

**Returns:** `void`

**Calls:**

- `complex_call_58452`
- `complex_call_58552`
- `/^\??prettify\b/.test`
- `/\S/.test`
- `value.replace`
- `prettyPrintRe.test`
- `prettyPrintedRe.test`
- `preCodeXmpRe.test`
- `className.match`
- `childContentWrapper`
- `codeRe.test`
- `wrapper.className.match`
- `preformattedTagNameRe.test`
- `defaultView.getComputedStyle(cs, null)
                  .getPropertyValue`
- `whitespace.substring`
- `numberLines`
- `applyDecorator`
- `setTimeout`
- `opt_whenDone`

**Internal Comments:**
```
// Look for a preceding comment like (x2)
// <?prettify lang="..." linenums="..."?> (x2)
// <?foo?> is parsed by HTML 5 to a comment node (8) (x2)
// like <!--?foo?-->, but in XML is a processing instruction (x2)
// Skip over white-space text nodes but not others.
// Don't redo this if we've already done it.
// This allows recalling pretty print to just prettyprint elements
// that have been added to the page since last call.
// make sure this is not nested in an already prettified element (x2)
// Mark done.  If we fail to prettyprint for whatever reason, (x4)
// we shouldn't try again. (x4)
// If the classes includes a language extensions, use it. (x2)
// Language extensions can be specified like (x2)
//     <pre class="prettyprint lang-cpp"> (x2)
// the language extension "cpp" is used to find a language handler (x2)
// as passed to PR.registerLangHandler. (x2)
// HTML5 recommends that a language be specified using "language-" (x2)
// as the prefix instead.  Google Code Prettify supports both. (x2)
// http://dev.w3.org/html5/spec-author-view/the-code-element.html (x2)
// Support <pre class="prettyprint"><code class="language-c"> (x2)
// Look for a class like linenums or linenums:<n> where <n> is the (x2)
// 1-indexed number of the first line. (x2)
// do the pretty printing (x3)
// finish up in a continuation (x3)
```

<details><summary>Code</summary>

```typescript
function doWork() {
      var endTime = (win['PR_SHOULD_USE_CONTINUATION'] ?
                     clock['now']() + 250 /* ms */ :
                     Infinity);
      for (; k < elements.length && clock['now']() < endTime; k++) {
        var cs = elements[k];

        // Look for a preceding comment like
        // <?prettify lang="..." linenums="..."?>
        var attrs = EMPTY;
        {
          for (var preceder = cs; (preceder = preceder.previousSibling);) {
            var nt = preceder.nodeType;
            // <?foo?> is parsed by HTML 5 to a comment node (8)
            // like <!--?foo?-->, but in XML is a processing instruction
            var value = (nt === 7 || nt === 8) && preceder.nodeValue;
            if (value
                ? !/^\??prettify\b/.test(value)
                : (nt !== 3 || /\S/.test(preceder.nodeValue))) {
              // Skip over white-space text nodes but not others.
              break;
            }
            if (value) {
              attrs = {};
              value.replace(
                  /\b(\w+)=([\w:.%+-]+)/g,
                function (_, name, value) { attrs[name] = value; });
              break;
            }
          }
        }

        var className = cs.className;
        if ((attrs !== EMPTY || prettyPrintRe.test(className))
            // Don't redo this if we've already done it.
            // This allows recalling pretty print to just prettyprint elements
            // that have been added to the page since last call.
            && !prettyPrintedRe.test(className)) {

          // make sure this is not nested in an already prettified element
          var nested = false;
          for (var p = cs.parentNode; p; p = p.parentNode) {
            var tn = p.tagName;
            if (preCodeXmpRe.test(tn)
                && p.className && prettyPrintRe.test(p.className)) {
              nested = true;
              break;
            }
          }
          if (!nested) {
            // Mark done.  If we fail to prettyprint for whatever reason,
            // we shouldn't try again.
            cs.className += ' prettyprinted';

            // If the classes includes a language extensions, use it.
            // Language extensions can be specified like
            //     <pre class="prettyprint lang-cpp">
            // the language extension "cpp" is used to find a language handler
            // as passed to PR.registerLangHandler.
            // HTML5 recommends that a language be specified using "language-"
            // as the prefix instead.  Google Code Prettify supports both.
            // http://dev.w3.org/html5/spec-author-view/the-code-element.html
            var langExtension = attrs['lang'];
            if (!langExtension) {
              langExtension = className.match(langExtensionRe);
              // Support <pre class="prettyprint"><code class="language-c">
              var wrapper;
              if (!langExtension && (wrapper = childContentWrapper(cs))
                  && codeRe.test(wrapper.tagName)) {
                langExtension = wrapper.className.match(langExtensionRe);
              }

              if (langExtension) { langExtension = langExtension[1]; }
            }

            var preformatted;
            if (preformattedTagNameRe.test(cs.tagName)) {
              preformatted = 1;
            } else {
              var currentStyle = cs['currentStyle'];
              var defaultView = doc.defaultView;
              var whitespace = (
                  currentStyle
                  ? currentStyle['whiteSpace']
                  : (defaultView
                     && defaultView.getComputedStyle)
                  ? defaultView.getComputedStyle(cs, null)
                  .getPropertyValue('white-space')
                  : 0);
              preformatted = whitespace
                  && 'pre' === whitespace.substring(0, 3);
            }

            // Look for a class like linenums or linenums:<n> where <n> is the
            // 1-indexed number of the first line.
            var lineNums = attrs['linenums'];
            if (!(lineNums = lineNums === 'true' || +lineNums)) {
              lineNums = className.match(/\blinenums\b(?::(\d+))?/);
              lineNums =
                lineNums
                ? lineNums[1] && lineNums[1].length
                  ? +lineNums[1] : true
                : false;
            }
            var showLineMods = attrs['showlinemods'];
            if (showLineMods === undefined) {
              showLineMods = className.match(/\bshowlinemods\b/);
            }
            if (lineNums || showLineMods) { numberLines(cs, lineNums, preformatted, lineNums, showLineMods); }

            // do the pretty printing
            prettyPrintingJob = {
              langExtension: langExtension,
              sourceNode: cs,
              numberLines: lineNums,
              pre: preformatted
            };
            applyDecorator(prettyPrintingJob);
          }
        }
      }
      if (k < elements.length) {
        // finish up in a continuation
        setTimeout(doWork, 250);
      } else if ('function' === typeof opt_whenDone) {
        opt_whenDone();
      }
    }
```
</details>


---