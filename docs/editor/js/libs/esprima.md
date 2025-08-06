[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `esprima.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 110 |
| 📊 Variables & Constants | 449 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/esprima.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `installedModules` | `{}` | let/var | `{}` | ✗ |
| `module` | `{ exports: {}; id: any; loaded: boole...` | let/var | `installedModules[moduleId] = { /******/ exports: {}, /******/ id: moduleId, /...` | ✗ |
| `commentHandler` | `any` | let/var | `null` | ✗ |
| `parserDelegate` | `(node: any, metadata: any) => void` | let/var | `(typeof delegate === 'function') ? proxyDelegate : null` | ✗ |
| `collectComment` | `boolean` | let/var | `false` | ✗ |
| `attachComment` | `any` | let/var | `(typeof options.attachComment === 'boolean' && options.attachComment)` | ✗ |
| `parser` | `any` | let/var | `*not shown*` | ✗ |
| `ast` | `any` | let/var | `(parser.parseProgram())` | ✗ |
| `tokenizer` | `any` | let/var | `new tokenizer_1.Tokenizer(code, options)` | ✗ |
| `tokens` | `any` | let/var | `*not shown*` | ✗ |
| `innerComments` | `any[]` | let/var | `[]` | ✗ |
| `entry` | `any` | let/var | `this.leading[i]` | ✗ |
| `trailingComments` | `any[]` | let/var | `[]` | ✗ |
| `entry_1` | `any` | let/var | `this.trailing[i]` | ✗ |
| `entry` | `any` | let/var | `this.stack[this.stack.length - 1]` | ✗ |
| `firstComment` | `any` | let/var | `entry.node.trailingComments[0]` | ✗ |
| `leadingComments` | `any[]` | let/var | `[]` | ✗ |
| `target` | `any` | let/var | `*not shown*` | ✗ |
| `entry` | `any` | let/var | `this.stack[this.stack.length - 1]` | ✗ |
| `count` | `any` | let/var | `target.leadingComments ? target.leadingComments.length : 0` | ✗ |
| `comment` | `any` | let/var | `target.leadingComments[i]` | ✗ |
| `type` | `string` | let/var | `(node.type[0] === 'L') ? 'Line' : 'Block'` | ✗ |
| `comment` | `{ type: string; value: any; }` | let/var | `{ type: type, value: node.value }` | ✗ |
| `entry` | `{ comment: { type: string; value: any...` | let/var | `{ comment: { type: type, value: node.value, range: [metadata.start.offset, me...` | ✗ |
| `CommentHandler` | `typeof CommentHandler` | let/var | `(function () { function CommentHandler() { this.attach = false; this.comments...` | ✗ |
| `ArrowParameterPlaceHolder` | `string` | let/var | `'ArrowParameterPlaceHolder'` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `index` | `any` | let/var | `this.lastMarker.index` | ✗ |
| `line` | `any` | let/var | `this.lastMarker.lineNumber` | ✗ |
| `column` | `number` | let/var | `this.lastMarker.index - this.lastMarker.lineStart + 1` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `index` | `any` | let/var | `this.lastMarker.index` | ✗ |
| `line` | `any` | let/var | `this.scanner.lineNumber` | ✗ |
| `column` | `number` | let/var | `this.lastMarker.index - this.lastMarker.lineStart + 1` | ✗ |
| `msg` | `any` | let/var | `message \|\| messages_1.Messages.UnexpectedToken` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `index` | `any` | let/var | `token.start` | ✗ |
| `line` | `any` | let/var | `token.lineNumber` | ✗ |
| `column` | `number` | let/var | `token.start - this.lastMarker.lineStart + 1` | ✗ |
| `e` | `any` | let/var | `comments[i]` | ✗ |
| `node` | `any` | let/var | `void 0` | ✗ |
| `metadata` | `{ start: { line: any; column: any; of...` | let/var | `{ start: { line: e.loc.start.line, column: e.loc.start.column, offset: e.rang...` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `metadata` | `{ start: { line: any; column: any; of...` | let/var | `{ start: { line: meta.line, column: meta.column, offset: meta.index }, end: {...` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `op` | `any` | let/var | `this.lookahead.value` | ✗ |
| `previousIsBindingElement` | `boolean` | let/var | `this.context.isBindingElement` | ✗ |
| `previousIsAssignmentTarget` | `boolean` | let/var | `this.context.isAssignmentTarget` | ✗ |
| `previousFirstCoverInitializ...` | `any` | let/var | `this.context.firstCoverInitializedNameError` | ✗ |
| `previousIsBindingElement` | `boolean` | let/var | `this.context.isBindingElement` | ✗ |
| `previousIsAssignmentTarget` | `boolean` | let/var | `this.context.isAssignmentTarget` | ✗ |
| `previousFirstCoverInitializ...` | `any` | let/var | `this.context.firstCoverInitializedNameError` | ✗ |
| `expr` | `any` | let/var | `*not shown*` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `token` | `any` | let/var | `*not shown*` | ✗ |
| `raw` | `any` | let/var | `*not shown*` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |
| `previousStrict` | `boolean` | let/var | `this.context.strict` | ✗ |
| `isGenerator` | `boolean` | let/var | `false` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `key` | `any` | let/var | `null` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `kind` | `any` | let/var | `*not shown*` | ✗ |
| `key` | `any` | let/var | `*not shown*` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `computed` | `boolean` | let/var | `false` | ✗ |
| `method` | `boolean` | let/var | `false` | ✗ |
| `shorthand` | `boolean` | let/var | `false` | ✗ |
| `properties` | `any[]` | let/var | `[]` | ✗ |
| `hasProto` | `{ value: boolean; }` | let/var | `{ value: false }` | ✗ |
| `value` | `{ raw: any; cooked: any; }` | let/var | `{ raw: token.value.raw, cooked: token.value.cooked }` | ✗ |
| `value` | `{ raw: any; cooked: any; }` | let/var | `{ raw: token.value.raw, cooked: token.value.cooked }` | ✗ |
| `expressions` | `any[]` | let/var | `[]` | ✗ |
| `quasis` | `any[]` | let/var | `[]` | ✗ |
| `expr` | `any` | let/var | `*not shown*` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `arrow` | `boolean` | let/var | `false` | ✗ |
| `expressions` | `any[]` | let/var | `[]` | ✗ |
| `params_1` | `any` | let/var | `(expr.type === syntax_1.Syntax.SequenceExpression ? expr.expressions : [expr])` | ✗ |
| `args` | `any[]` | let/var | `[]` | ✗ |
| `expr` | `any` | let/var | `this.match('...') ? this.parseSpreadElement() : this.isolateCoverGrammar(this...` | ✗ |
| `expr` | `any` | let/var | `*not shown*` | ✗ |
| `args` | `any[]` | let/var | `this.match('(') ? this.parseArguments() : []` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `previousAllowIn` | `boolean` | let/var | `this.context.allowIn` | ✗ |
| `expr` | `any` | let/var | `*not shown*` | ✗ |
| `expr` | `any` | let/var | `(this.matchKeyword('super') && this.context.inFunctionBody) ? this.parseSuper...` | ✗ |
| `expr` | `any` | let/var | `*not shown*` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `prefix` | `boolean` | let/var | `true` | ✗ |
| `operator` | `any` | let/var | `this.nextToken().value` | ✗ |
| `expr` | `any` | let/var | `*not shown*` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `left` | `any` | let/var | `expr` | ✗ |
| `op` | `any` | let/var | `token.value` | ✗ |
| `precedence` | `any` | let/var | `*not shown*` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `markers` | `any[]` | let/var | `[startToken, this.lookahead]` | ✗ |
| `left` | `any` | let/var | `expr` | ✗ |
| `stack` | `any[]` | let/var | `[left, token, right]` | ✗ |
| `operator` | `any` | let/var | `stack.pop().value` | ✗ |
| `i` | `number` | let/var | `stack.length - 1` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `previousAllowIn` | `boolean` | let/var | `this.context.allowIn` | ✗ |
| `params` | `any[]` | let/var | `[expr]` | ✗ |
| `options` | `any` | let/var | `*not shown*` | ✗ |
| `param` | `any` | let/var | `params[i]` | ✗ |
| `token` | `any` | let/var | `this.context.strict ? options.stricted : options.firstRestricted` | ✗ |
| `expr` | `any` | let/var | `*not shown*` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `token` | `any` | let/var | `startToken` | ✗ |
| `previousStrict` | `boolean` | let/var | `this.context.strict` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `body` | `any` | let/var | `this.match('{') ? this.parseFunctionSourceElements() : this.isolateCoverGramm...` | ✗ |
| `expression` | `boolean` | let/var | `body.type !== syntax_1.Syntax.BlockStatement` | ✗ |
| `id` | `any` | let/var | `(expr)` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `expressions` | `any[]` | let/var | `[]` | ✗ |
| `statement` | `any` | let/var | `null` | ✗ |
| `block` | `any[]` | let/var | `[]` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `init` | `any` | let/var | `null` | ✗ |
| `list` | `any[]` | let/var | `[this.parseLexicalBinding(kind, options)]` | ✗ |
| `previousIndex` | `any` | let/var | `this.scanner.index` | ✗ |
| `previousLineNumber` | `any` | let/var | `this.scanner.lineNumber` | ✗ |
| `previousLineStart` | `any` | let/var | `this.scanner.lineStart` | ✗ |
| `kind` | `any` | let/var | `this.nextToken().value` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |
| `computed` | `boolean` | let/var | `false` | ✗ |
| `shorthand` | `boolean` | let/var | `false` | ✗ |
| `method` | `boolean` | let/var | `false` | ✗ |
| `key` | `any` | let/var | `*not shown*` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `keyToken` | `any` | let/var | `this.lookahead` | ✗ |
| `properties` | `any[]` | let/var | `[]` | ✗ |
| `pattern` | `any` | let/var | `*not shown*` | ✗ |
| `startToken` | `any` | let/var | `this.lookahead` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `init` | `any` | let/var | `null` | ✗ |
| `opt` | `{ inFor: any; }` | let/var | `{ inFor: options.inFor }` | ✗ |
| `list` | `any[]` | let/var | `[]` | ✗ |
| `consequent` | `any` | let/var | `*not shown*` | ✗ |
| `alternate` | `any` | let/var | `null` | ✗ |
| `previousInIteration` | `boolean` | let/var | `this.context.inIteration` | ✗ |
| `body` | `any` | let/var | `*not shown*` | ✗ |
| `previousInIteration` | `boolean` | let/var | `this.context.inIteration` | ✗ |
| `init` | `any` | let/var | `null` | ✗ |
| `test` | `any` | let/var | `null` | ✗ |
| `update` | `any` | let/var | `null` | ✗ |
| `forIn` | `boolean` | let/var | `true` | ✗ |
| `left` | `any` | let/var | `*not shown*` | ✗ |
| `right` | `any` | let/var | `*not shown*` | ✗ |
| `previousAllowIn` | `boolean` | let/var | `this.context.allowIn` | ✗ |
| `decl` | `any` | let/var | `declarations[0]` | ✗ |
| `kind` | `any` | let/var | `this.nextToken().value` | ✗ |
| `initStartToken` | `any` | let/var | `this.lookahead` | ✗ |
| `initSeq` | `any[]` | let/var | `[init]` | ✗ |
| `body` | `any` | let/var | `*not shown*` | ✗ |
| `previousInIteration` | `boolean` | let/var | `this.context.inIteration` | ✗ |
| `label` | `any` | let/var | `null` | ✗ |
| `key` | `string` | let/var | `'$' + label.name` | ✗ |
| `label` | `any` | let/var | `null` | ✗ |
| `key` | `string` | let/var | `'$' + label.name` | ✗ |
| `hasArgument` | `boolean` | let/var | `!this.match(';') && !this.match('}') && !this.hasLineTerminator && this.looka...` | ✗ |
| `argument` | `any` | let/var | `hasArgument ? this.parseExpression() : null` | ✗ |
| `test` | `any` | let/var | `*not shown*` | ✗ |
| `consequent` | `any[]` | let/var | `[]` | ✗ |
| `previousInSwitch` | `boolean` | let/var | `this.context.inSwitch` | ✗ |
| `cases` | `any[]` | let/var | `[]` | ✗ |
| `defaultFound` | `boolean` | let/var | `false` | ✗ |
| `statement` | `any` | let/var | `*not shown*` | ✗ |
| `id` | `any` | let/var | `(expr)` | ✗ |
| `key` | `string` | let/var | `'$' + id.name` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `paramMap` | `{}` | let/var | `{}` | ✗ |
| `key` | `string` | let/var | `'$' + params[i].value` | ✗ |
| `handler` | `any` | let/var | `this.matchKeyword('catch') ? this.parseCatchClause() : null` | ✗ |
| `finalizer` | `any` | let/var | `this.matchKeyword('finally') ? this.parseFinallyClause() : null` | ✗ |
| `statement` | `any` | let/var | `null` | ✗ |
| `value` | `any` | let/var | `this.lookahead.value` | ✗ |
| `previousLabelSet` | `{}` | let/var | `this.context.labelSet` | ✗ |
| `previousInIteration` | `boolean` | let/var | `this.context.inIteration` | ✗ |
| `previousInSwitch` | `boolean` | let/var | `this.context.inSwitch` | ✗ |
| `previousInFunctionBody` | `boolean` | let/var | `this.context.inFunctionBody` | ✗ |
| `key` | `string` | let/var | `'$' + name` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `param` | `any` | let/var | `this.match('...') ? this.parseRestElement(params) : this.parsePatternWithDefa...` | ✗ |
| `options` | `any` | let/var | `*not shown*` | ✗ |
| `message` | `any` | let/var | `*not shown*` | ✗ |
| `id` | `any` | let/var | `null` | ✗ |
| `firstRestricted` | `any` | let/var | `null` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `params` | `any[]` | let/var | `formalParameters.params` | ✗ |
| `stricted` | `any` | let/var | `formalParameters.stricted` | ✗ |
| `previousStrict` | `boolean` | let/var | `this.context.strict` | ✗ |
| `message` | `any` | let/var | `*not shown*` | ✗ |
| `id` | `any` | let/var | `null` | ✗ |
| `firstRestricted` | `any` | let/var | `*not shown*` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `params` | `any[]` | let/var | `formalParameters.params` | ✗ |
| `stricted` | `any` | let/var | `formalParameters.stricted` | ✗ |
| `previousStrict` | `boolean` | let/var | `this.context.strict` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `directive` | `any` | let/var | `null` | ✗ |
| `firstRestricted` | `any` | let/var | `null` | ✗ |
| `body` | `any[]` | let/var | `[]` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `directive` | `any` | let/var | `statement.directive` | ✗ |
| `isGenerator` | `boolean` | let/var | `false` | ✗ |
| `params` | `{ params: any[]; stricted: any; first...` | let/var | `{ params: [], stricted: null, firstRestricted: null, message: null }` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `options` | `{ params: any[]; firstRestricted: any...` | let/var | `{ params: [], firstRestricted: null, paramSet: {} }` | ✗ |
| `isGenerator` | `boolean` | let/var | `false` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `isGenerator` | `boolean` | let/var | `true` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `start` | `boolean` | let/var | `true` | ✗ |
| `value` | `any` | let/var | `this.lookahead.value` | ✗ |
| `argument` | `any` | let/var | `null` | ✗ |
| `delegate` | `boolean` | let/var | `false` | ✗ |
| `previousAllowYield` | `boolean` | let/var | `this.context.allowYield` | ✗ |
| `token` | `any` | let/var | `this.lookahead` | ✗ |
| `kind` | `any` | let/var | `*not shown*` | ✗ |
| `key` | `any` | let/var | `*not shown*` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `computed` | `boolean` | let/var | `false` | ✗ |
| `method` | `boolean` | let/var | `false` | ✗ |
| `isStatic` | `boolean` | let/var | `false` | ✗ |
| `id` | `any` | let/var | `key` | ✗ |
| `body` | `any[]` | let/var | `[]` | ✗ |
| `hasConstructor` | `{ value: boolean; }` | let/var | `{ value: false }` | ✗ |
| `previousStrict` | `boolean` | let/var | `this.context.strict` | ✗ |
| `id` | `any` | let/var | `(identifierIsOptional && (this.lookahead.type !== token_1.Token.Identifier)) ...` | ✗ |
| `superClass` | `any` | let/var | `null` | ✗ |
| `previousStrict` | `boolean` | let/var | `this.context.strict` | ✗ |
| `id` | `any` | let/var | `(this.lookahead.type === token_1.Token.Identifier) ? this.parseVariableIdenti...` | ✗ |
| `superClass` | `any` | let/var | `null` | ✗ |
| `imported` | `any` | let/var | `*not shown*` | ✗ |
| `local` | `any` | let/var | `*not shown*` | ✗ |
| `specifiers` | `any[]` | let/var | `[]` | ✗ |
| `src` | `any` | let/var | `*not shown*` | ✗ |
| `specifiers` | `any[]` | let/var | `[]` | ✗ |
| `message` | `any` | let/var | `this.lookahead.value ? messages_1.Messages.UnexpectedToken : messages_1.Messa...` | ✗ |
| `exported` | `any` | let/var | `local` | ✗ |
| `exportDeclaration` | `any` | let/var | `*not shown*` | ✗ |
| `message` | `any` | let/var | `this.lookahead.value ? messages_1.Messages.UnexpectedToken : messages_1.Messa...` | ✗ |
| `specifiers` | `any[]` | let/var | `[]` | ✗ |
| `source` | `any` | let/var | `null` | ✗ |
| `isExportFromIdentifier` | `boolean` | let/var | `false` | ✗ |
| `Parser` | `typeof Parser` | let/var | `(function () { function Parser(code, options, delegate) { if (options === voi...` | ✗ |
| `error` | `Error` | let/var | `new Error(msg)` | ✗ |
| `msg` | `string` | let/var | `'Line ' + line + ': ' + description` | ✗ |
| `ErrorHandler` | `typeof ErrorHandler` | let/var | `(function () { function ErrorHandler() { this.errors = []; this.tolerant = fa...` | ✗ |
| `Token` | `any` | let/var | `exports.Token` | ✗ |
| `comments` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `any` | let/var | `*not shown*` | ✗ |
| `loc` | `any` | let/var | `*not shown*` | ✗ |
| `entry` | `{ multiLine: boolean; slice: any[]; r...` | let/var | `{ multiLine: false, slice: [start + offset, this.index - 1], range: [start, t...` | ✗ |
| `comments` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `any` | let/var | `*not shown*` | ✗ |
| `loc` | `any` | let/var | `*not shown*` | ✗ |
| `entry` | `{ multiLine: boolean; slice: number[]...` | let/var | `{ multiLine: true, slice: [start + 2, this.index - 2], range: [start, this.in...` | ✗ |
| `comments` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `boolean` | let/var | `(this.index === 0)` | ✗ |
| `first` | `any` | let/var | `cp` | ✗ |
| `len` | `number` | let/var | `(prefix === 'u') ? 4 : 2` | ✗ |
| `code` | `number` | let/var | `0` | ✗ |
| `ch` | `any` | let/var | `this.source[this.index]` | ✗ |
| `code` | `number` | let/var | `0` | ✗ |
| `start` | `number` | let/var | `this.index++` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `octal` | `boolean` | let/var | `(ch !== '0')` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `number` | let/var | `this.index` | ✗ |
| `id` | `any` | let/var | `(this.source.charCodeAt(start) === 0x5C) ? this.getComplexIdentifier() : this...` | ✗ |
| `token` | `{ type: any; value: string; lineNumbe...` | let/var | `{ type: token_1.Token.Punctuator, value: '', lineNumber: this.lineNumber, lin...` | ✗ |
| `str` | `any` | let/var | `this.source[this.index]` | ✗ |
| `number` | `string` | let/var | `''` | ✗ |
| `number` | `string` | let/var | `''` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `number` | `string` | let/var | `''` | ✗ |
| `octal` | `boolean` | let/var | `false` | ✗ |
| `ch` | `any` | let/var | `this.source[i]` | ✗ |
| `start` | `number` | let/var | `this.index` | ✗ |
| `ch` | `any` | let/var | `this.source[start]` | ✗ |
| `number` | `string` | let/var | `''` | ✗ |
| `start` | `number` | let/var | `this.index` | ✗ |
| `quote` | `any` | let/var | `this.source[start]` | ✗ |
| `octal` | `boolean` | let/var | `false` | ✗ |
| `str` | `string` | let/var | `''` | ✗ |
| `ch` | `any` | let/var | `this.source[this.index++]` | ✗ |
| `cooked` | `string` | let/var | `''` | ✗ |
| `terminated` | `boolean` | let/var | `false` | ✗ |
| `start` | `number` | let/var | `this.index` | ✗ |
| `head` | `boolean` | let/var | `(this.source[start] === '`')` | ✗ |
| `tail` | `boolean` | let/var | `false` | ✗ |
| `rawOffset` | `number` | let/var | `2` | ✗ |
| `ch` | `any` | let/var | `this.source[this.index++]` | ✗ |
| `restore` | `number` | let/var | `this.index` | ✗ |
| `astralSubstitute` | `string` | let/var | `'\uFFFF'` | ✗ |
| `tmp` | `any` | let/var | `pattern` | ✗ |
| `self` | `this` | let/var | `this` | ✗ |
| `ch` | `any` | let/var | `this.source[this.index]` | ✗ |
| `str` | `any` | let/var | `this.source[this.index++]` | ✗ |
| `classMarker` | `boolean` | let/var | `false` | ✗ |
| `terminated` | `boolean` | let/var | `false` | ✗ |
| `str` | `string` | let/var | `''` | ✗ |
| `flags` | `string` | let/var | `''` | ✗ |
| `ch` | `any` | let/var | `this.source[this.index]` | ✗ |
| `restore` | `number` | let/var | `this.index` | ✗ |
| `start` | `number` | let/var | `this.index` | ✗ |
| `Scanner` | `typeof Scanner` | let/var | `(function () { function Scanner(code, handler) { this.source = code; this.err...` | ✗ |
| `Regex` | `{ NonAsciiIdentifierStart: RegExp; No...` | let/var | `{ // Unicode v8.0.0 NonAsciiIdentifierStart: NonAsciiIdentifierStart: /[\xAA\...` | ✗ |
| `ArrayExpression` | `typeof ArrayExpression` | let/var | `(function () { function ArrayExpression(elements) { this.type = syntax_1.Synt...` | ✗ |
| `ArrayPattern` | `typeof ArrayPattern` | let/var | `(function () { function ArrayPattern(elements) { this.type = syntax_1.Syntax....` | ✗ |
| `ArrowFunctionExpression` | `typeof ArrowFunctionExpression` | let/var | `(function () { function ArrowFunctionExpression(params, body, expression) { t...` | ✗ |
| `AssignmentExpression` | `typeof AssignmentExpression` | let/var | `(function () { function AssignmentExpression(operator, left, right) { this.ty...` | ✗ |
| `AssignmentPattern` | `typeof AssignmentPattern` | let/var | `(function () { function AssignmentPattern(left, right) { this.type = syntax_1...` | ✗ |
| `logical` | `boolean` | let/var | `(operator === '\|\|' \|\| operator === '&&')` | ✗ |
| `BinaryExpression` | `typeof BinaryExpression` | let/var | `(function () { function BinaryExpression(operator, left, right) { var logical...` | ✗ |
| `BlockStatement` | `typeof BlockStatement` | let/var | `(function () { function BlockStatement(body) { this.type = syntax_1.Syntax.Bl...` | ✗ |
| `BreakStatement` | `typeof BreakStatement` | let/var | `(function () { function BreakStatement(label) { this.type = syntax_1.Syntax.B...` | ✗ |
| `CallExpression` | `typeof CallExpression` | let/var | `(function () { function CallExpression(callee, args) { this.type = syntax_1.S...` | ✗ |
| `CatchClause` | `typeof CatchClause` | let/var | `(function () { function CatchClause(param, body) { this.type = syntax_1.Synta...` | ✗ |
| `ClassBody` | `typeof ClassBody` | let/var | `(function () { function ClassBody(body) { this.type = syntax_1.Syntax.ClassBo...` | ✗ |
| `ClassDeclaration` | `typeof ClassDeclaration` | let/var | `(function () { function ClassDeclaration(id, superClass, body) { this.type = ...` | ✗ |
| `ClassExpression` | `typeof ClassExpression` | let/var | `(function () { function ClassExpression(id, superClass, body) { this.type = s...` | ✗ |
| `ComputedMemberExpression` | `typeof ComputedMemberExpression` | let/var | `(function () { function ComputedMemberExpression(object, property) { this.typ...` | ✗ |
| `ConditionalExpression` | `typeof ConditionalExpression` | let/var | `(function () { function ConditionalExpression(test, consequent, alternate) { ...` | ✗ |
| `ContinueStatement` | `typeof ContinueStatement` | let/var | `(function () { function ContinueStatement(label) { this.type = syntax_1.Synta...` | ✗ |
| `DebuggerStatement` | `typeof DebuggerStatement` | let/var | `(function () { function DebuggerStatement() { this.type = syntax_1.Syntax.Deb...` | ✗ |
| `Directive` | `typeof Directive` | let/var | `(function () { function Directive(expression, directive) { this.type = syntax...` | ✗ |
| `DoWhileStatement` | `typeof DoWhileStatement` | let/var | `(function () { function DoWhileStatement(body, test) { this.type = syntax_1.S...` | ✗ |
| `EmptyStatement` | `typeof EmptyStatement` | let/var | `(function () { function EmptyStatement() { this.type = syntax_1.Syntax.EmptyS...` | ✗ |
| `ExportAllDeclaration` | `typeof ExportAllDeclaration` | let/var | `(function () { function ExportAllDeclaration(source) { this.type = syntax_1.S...` | ✗ |
| `ExportDefaultDeclaration` | `typeof ExportDefaultDeclaration` | let/var | `(function () { function ExportDefaultDeclaration(declaration) { this.type = s...` | ✗ |
| `ExportNamedDeclaration` | `typeof ExportNamedDeclaration` | let/var | `(function () { function ExportNamedDeclaration(declaration, specifiers, sourc...` | ✗ |
| `ExportSpecifier` | `typeof ExportSpecifier` | let/var | `(function () { function ExportSpecifier(local, exported) { this.type = syntax...` | ✗ |
| `ExpressionStatement` | `typeof ExpressionStatement` | let/var | `(function () { function ExpressionStatement(expression) { this.type = syntax_...` | ✗ |
| `ForInStatement` | `typeof ForInStatement` | let/var | `(function () { function ForInStatement(left, right, body) { this.type = synta...` | ✗ |
| `ForOfStatement` | `typeof ForOfStatement` | let/var | `(function () { function ForOfStatement(left, right, body) { this.type = synta...` | ✗ |
| `ForStatement` | `typeof ForStatement` | let/var | `(function () { function ForStatement(init, test, update, body) { this.type = ...` | ✗ |
| `FunctionDeclaration` | `typeof FunctionDeclaration` | let/var | `(function () { function FunctionDeclaration(id, params, body, generator) { th...` | ✗ |
| `FunctionExpression` | `typeof FunctionExpression` | let/var | `(function () { function FunctionExpression(id, params, body, generator) { thi...` | ✗ |
| `Identifier` | `typeof Identifier` | let/var | `(function () { function Identifier(name) { this.type = syntax_1.Syntax.Identi...` | ✗ |
| `IfStatement` | `typeof IfStatement` | let/var | `(function () { function IfStatement(test, consequent, alternate) { this.type ...` | ✗ |
| `ImportDeclaration` | `typeof ImportDeclaration` | let/var | `(function () { function ImportDeclaration(specifiers, source) { this.type = s...` | ✗ |
| `ImportDefaultSpecifier` | `typeof ImportDefaultSpecifier` | let/var | `(function () { function ImportDefaultSpecifier(local) { this.type = syntax_1....` | ✗ |
| `ImportNamespaceSpecifier` | `typeof ImportNamespaceSpecifier` | let/var | `(function () { function ImportNamespaceSpecifier(local) { this.type = syntax_...` | ✗ |
| `ImportSpecifier` | `typeof ImportSpecifier` | let/var | `(function () { function ImportSpecifier(local, imported) { this.type = syntax...` | ✗ |
| `LabeledStatement` | `typeof LabeledStatement` | let/var | `(function () { function LabeledStatement(label, body) { this.type = syntax_1....` | ✗ |
| `Literal` | `typeof Literal` | let/var | `(function () { function Literal(value, raw) { this.type = syntax_1.Syntax.Lit...` | ✗ |
| `MetaProperty` | `typeof MetaProperty` | let/var | `(function () { function MetaProperty(meta, property) { this.type = syntax_1.S...` | ✗ |
| `MethodDefinition` | `typeof MethodDefinition` | let/var | `(function () { function MethodDefinition(key, computed, value, kind, isStatic...` | ✗ |
| `NewExpression` | `typeof NewExpression` | let/var | `(function () { function NewExpression(callee, args) { this.type = syntax_1.Sy...` | ✗ |
| `ObjectExpression` | `typeof ObjectExpression` | let/var | `(function () { function ObjectExpression(properties) { this.type = syntax_1.S...` | ✗ |
| `ObjectPattern` | `typeof ObjectPattern` | let/var | `(function () { function ObjectPattern(properties) { this.type = syntax_1.Synt...` | ✗ |
| `Program` | `typeof Program` | let/var | `(function () { function Program(body, sourceType) { this.type = syntax_1.Synt...` | ✗ |
| `Property` | `typeof Property` | let/var | `(function () { function Property(kind, key, computed, value, method, shorthan...` | ✗ |
| `RegexLiteral` | `typeof RegexLiteral` | let/var | `(function () { function RegexLiteral(value, raw, regex) { this.type = syntax_...` | ✗ |
| `RestElement` | `typeof RestElement` | let/var | `(function () { function RestElement(argument) { this.type = syntax_1.Syntax.R...` | ✗ |
| `ReturnStatement` | `typeof ReturnStatement` | let/var | `(function () { function ReturnStatement(argument) { this.type = syntax_1.Synt...` | ✗ |
| `SequenceExpression` | `typeof SequenceExpression` | let/var | `(function () { function SequenceExpression(expressions) { this.type = syntax_...` | ✗ |
| `SpreadElement` | `typeof SpreadElement` | let/var | `(function () { function SpreadElement(argument) { this.type = syntax_1.Syntax...` | ✗ |
| `StaticMemberExpression` | `typeof StaticMemberExpression` | let/var | `(function () { function StaticMemberExpression(object, property) { this.type ...` | ✗ |
| `Super` | `typeof Super` | let/var | `(function () { function Super() { this.type = syntax_1.Syntax.Super; } return...` | ✗ |
| `SwitchCase` | `typeof SwitchCase` | let/var | `(function () { function SwitchCase(test, consequent) { this.type = syntax_1.S...` | ✗ |
| `SwitchStatement` | `typeof SwitchStatement` | let/var | `(function () { function SwitchStatement(discriminant, cases) { this.type = sy...` | ✗ |
| `TaggedTemplateExpression` | `typeof TaggedTemplateExpression` | let/var | `(function () { function TaggedTemplateExpression(tag, quasi) { this.type = sy...` | ✗ |
| `TemplateElement` | `typeof TemplateElement` | let/var | `(function () { function TemplateElement(value, tail) { this.type = syntax_1.S...` | ✗ |
| `TemplateLiteral` | `typeof TemplateLiteral` | let/var | `(function () { function TemplateLiteral(quasis, expressions) { this.type = sy...` | ✗ |
| `ThisExpression` | `typeof ThisExpression` | let/var | `(function () { function ThisExpression() { this.type = syntax_1.Syntax.ThisEx...` | ✗ |
| `ThrowStatement` | `typeof ThrowStatement` | let/var | `(function () { function ThrowStatement(argument) { this.type = syntax_1.Synta...` | ✗ |
| `TryStatement` | `typeof TryStatement` | let/var | `(function () { function TryStatement(block, handler, finalizer) { this.type =...` | ✗ |
| `UnaryExpression` | `typeof UnaryExpression` | let/var | `(function () { function UnaryExpression(operator, argument) { this.type = syn...` | ✗ |
| `UpdateExpression` | `typeof UpdateExpression` | let/var | `(function () { function UpdateExpression(operator, argument, prefix) { this.t...` | ✗ |
| `VariableDeclaration` | `typeof VariableDeclaration` | let/var | `(function () { function VariableDeclaration(declarations, kind) { this.type =...` | ✗ |
| `VariableDeclarator` | `typeof VariableDeclarator` | let/var | `(function () { function VariableDeclarator(id, init) { this.type = syntax_1.S...` | ✗ |
| `WhileStatement` | `typeof WhileStatement` | let/var | `(function () { function WhileStatement(test, body) { this.type = syntax_1.Syn...` | ✗ |
| `WithStatement` | `typeof WithStatement` | let/var | `(function () { function WithStatement(object, body) { this.type = syntax_1.Sy...` | ✗ |
| `YieldExpression` | `typeof YieldExpression` | let/var | `(function () { function YieldExpression(argument, delegate) { this.type = syn...` | ✗ |
| `__extends` | `any` | let/var | `(this && this.__extends) \|\| function (d, b) { for (var p in b) if (b.hasOwn...` | ✗ |
| `JSXToken` | `any` | let/var | `*not shown*` | ✗ |
| `qualifiedName` | `any` | let/var | `*not shown*` | ✗ |
| `id` | `any` | let/var | `(elementName)` | ✗ |
| `ns` | `any` | let/var | `(elementName)` | ✗ |
| `expr` | `any` | let/var | `(elementName)` | ✗ |
| `result` | `string` | let/var | `'&'` | ✗ |
| `valid` | `boolean` | let/var | `true` | ✗ |
| `terminated` | `boolean` | let/var | `false` | ✗ |
| `numeric` | `boolean` | let/var | `false` | ✗ |
| `hex` | `boolean` | let/var | `false` | ✗ |
| `ch` | `any` | let/var | `this.scanner.source[this.scanner.index]` | ✗ |
| `value` | `any` | let/var | `this.scanner.source[this.scanner.index++]` | ✗ |
| `start` | `any` | let/var | `this.scanner.index` | ✗ |
| `quote` | `any` | let/var | `this.scanner.source[this.scanner.index++]` | ✗ |
| `str` | `string` | let/var | `''` | ✗ |
| `ch` | `any` | let/var | `this.scanner.source[this.scanner.index++]` | ✗ |
| `start` | `any` | let/var | `this.scanner.index` | ✗ |
| `text` | `string` | let/var | `''` | ✗ |
| `ch` | `any` | let/var | `this.scanner.source[this.scanner.index]` | ✗ |
| `token` | `{ type: any; value: string; lineNumbe...` | let/var | `{ type: JSXToken.Text, value: text, lineNumber: this.scanner.lineNumber, line...` | ✗ |
| `previousIndex` | `any` | let/var | `this.scanner.index` | ✗ |
| `previousLineNumber` | `any` | let/var | `this.scanner.lineNumber` | ✗ |
| `previousLineStart` | `any` | let/var | `this.scanner.lineStart` | ✗ |
| `namespace` | `any` | let/var | `elementName` | ✗ |
| `object` | `any` | let/var | `elementName` | ✗ |
| `attributeName` | `any` | let/var | `*not shown*` | ✗ |
| `namespace` | `any` | let/var | `identifier` | ✗ |
| `value` | `any` | let/var | `null` | ✗ |
| `attributes` | `any[]` | let/var | `[]` | ✗ |
| `attribute` | `any` | let/var | `this.matchJSX('{') ? this.parseJSXSpreadAttribute() : this.parseJSXNameValueA...` | ✗ |
| `expression` | `any` | let/var | `*not shown*` | ✗ |
| `children` | `any[]` | let/var | `[]` | ✗ |
| `stack` | `any[]` | let/var | `[]` | ✗ |
| `opening` | `any` | let/var | `(element)` | ✗ |
| `children` | `any[]` | let/var | `[]` | ✗ |
| `closing` | `any` | let/var | `null` | ✗ |
| `JSXParser` | `typeof JSXParser` | let/var | `(function (_super) { __extends(JSXParser, _super); function JSXParser(code, o...` | ✗ |
| `JSXClosingElement` | `typeof JSXClosingElement` | let/var | `(function () { function JSXClosingElement(name) { this.type = jsx_syntax_1.JS...` | ✗ |
| `JSXElement` | `typeof JSXElement` | let/var | `(function () { function JSXElement(openingElement, children, closingElement) ...` | ✗ |
| `JSXEmptyExpression` | `typeof JSXEmptyExpression` | let/var | `(function () { function JSXEmptyExpression() { this.type = jsx_syntax_1.JSXSy...` | ✗ |
| `JSXExpressionContainer` | `typeof JSXExpressionContainer` | let/var | `(function () { function JSXExpressionContainer(expression) { this.type = jsx_...` | ✗ |
| `JSXIdentifier` | `typeof JSXIdentifier` | let/var | `(function () { function JSXIdentifier(name) { this.type = jsx_syntax_1.JSXSyn...` | ✗ |
| `JSXMemberExpression` | `typeof JSXMemberExpression` | let/var | `(function () { function JSXMemberExpression(object, property) { this.type = j...` | ✗ |
| `JSXAttribute` | `typeof JSXAttribute` | let/var | `(function () { function JSXAttribute(name, value) { this.type = jsx_syntax_1....` | ✗ |
| `JSXNamespacedName` | `typeof JSXNamespacedName` | let/var | `(function () { function JSXNamespacedName(namespace, name) { this.type = jsx_...` | ✗ |
| `JSXOpeningElement` | `typeof JSXOpeningElement` | let/var | `(function () { function JSXOpeningElement(name, selfClosing, attributes) { th...` | ✗ |
| `JSXSpreadAttribute` | `typeof JSXSpreadAttribute` | let/var | `(function () { function JSXSpreadAttribute(argument) { this.type = jsx_syntax...` | ✗ |
| `JSXText` | `typeof JSXText` | let/var | `(function () { function JSXText(value, raw) { this.type = jsx_syntax_1.JSXSyn...` | ✗ |
| `previous` | `any` | let/var | `this.values[this.values.length - 1]` | ✗ |
| `regex` | `boolean` | let/var | `(previous !== null)` | ✗ |
| `check` | `any` | let/var | `this.values[this.paren - 1]` | ✗ |
| `check_1` | `any` | let/var | `this.values[this.curly - 4]` | ✗ |
| `check_2` | `any` | let/var | `this.values[this.curly - 5]` | ✗ |
| `Reader` | `typeof Reader` | let/var | `(function () { function Reader() { this.values = []; this.curly = this.paren ...` | ✗ |
| `e` | `any` | let/var | `comments[i]` | ✗ |
| `comment` | `any` | let/var | `void 0` | ✗ |
| `loc` | `any` | let/var | `void 0` | ✗ |
| `token` | `any` | let/var | `void 0` | ✗ |
| `entry` | `any` | let/var | `void 0` | ✗ |
| `Tokenizer` | `typeof Tokenizer` | let/var | `(function () { function Tokenizer(code, config) { this.errorHandler = new err...` | ✗ |


---

## Functions

### `__webpack_require__(moduleId: any): any`

**JSDoc:**
```typescript
/******/
```

**Parameters:**

- **`moduleId`** `any`

**Returns:** `any`

**Calls:**

- `modules[moduleId].call`

**Internal Comments:**
```
/******/ (x33)
// Check if module is in cache
/* istanbul ignore if */
// Create a new module (and put it into the cache) (x2)
// Execute the module function (x5)
// Flag the module as loaded (x4)
// Return the exports of the module
```

<details><summary>Code</summary>

```typescript
function __webpack_require__(moduleId) {

/******/ 		// Check if module is in cache
/* istanbul ignore if */
/******/ 		if(installedModules[moduleId])
/******/ 			return installedModules[moduleId].exports;

/******/ 		// Create a new module (and put it into the cache)
/******/ 		var module = installedModules[moduleId] = {
/******/ 			exports: {},
/******/ 			id: moduleId,
/******/ 			loaded: false
/******/ 		};

/******/ 		// Execute the module function
/******/ 		modules[moduleId].call(module.exports, module, module.exports, __webpack_require__);

/******/ 		// Flag the module as loaded
/******/ 		module.loaded = true;

/******/ 		// Return the exports of the module
/******/ 		return module.exports;
/******/ 	}
```
</details>

### `parse(code: any, options: any, delegate: any): any`

**Parameters:**

- **`code`** `any`
- **`options`** `any`
- **`delegate`** `any`

**Returns:** `any`

**Calls:**

- `delegate`
- `commentHandler.visit`
- `parser.parseProgram`

<details><summary>Code</summary>

```typescript
function parse(code, options, delegate) {
	    var commentHandler = null;
	    var proxyDelegate = function (node, metadata) {
	        if (delegate) {
	            delegate(node, metadata);
	        }
	        if (commentHandler) {
	            commentHandler.visit(node, metadata);
	        }
	    };
	    var parserDelegate = (typeof delegate === 'function') ? proxyDelegate : null;
	    var collectComment = false;
	    if (options) {
	        collectComment = (typeof options.comment === 'boolean' && options.comment);
	        var attachComment = (typeof options.attachComment === 'boolean' && options.attachComment);
	        if (collectComment || attachComment) {
	            commentHandler = new comment_handler_1.CommentHandler();
	            commentHandler.attach = attachComment;
	            options.comment = true;
	            parserDelegate = proxyDelegate;
	        }
	    }
	    var parser;
	    if (options && typeof options.jsx === 'boolean' && options.jsx) {
	        parser = new jsx_parser_1.JSXParser(code, options, parserDelegate);
	    }
	    else {
	        parser = new parser_1.Parser(code, options, parserDelegate);
	    }
	    var ast = (parser.parseProgram());
	    if (collectComment) {
	        ast.comments = commentHandler.comments;
	    }
	    if (parser.config.tokens) {
	        ast.tokens = parser.tokens;
	    }
	    if (parser.config.tolerant) {
	        ast.errors = parser.errorHandler.errors;
	    }
	    return ast;
	}
```
</details>

### `proxyDelegate(node: any, metadata: any): void`

**Parameters:**

- **`node`** `any`
- **`metadata`** `any`

**Returns:** `void`

**Calls:**

- `delegate`
- `commentHandler.visit`

<details><summary>Code</summary>

```typescript
function (node, metadata) {
	        if (delegate) {
	            delegate(node, metadata);
	        }
	        if (commentHandler) {
	            commentHandler.visit(node, metadata);
	        }
	    }
```
</details>

### `tokenize(code: any, options: any, delegate: any): any[]`

**Parameters:**

- **`code`** `any`
- **`options`** `any`
- **`delegate`** `any`

**Returns:** `any[]`

**Calls:**

- `tokenizer.getNextToken`
- `delegate`
- `tokens.push`
- `tokenizer.errorHandler.tolerate`
- `tokenizer.errors`

<details><summary>Code</summary>

```typescript
function tokenize(code, options, delegate) {
	    var tokenizer = new tokenizer_1.Tokenizer(code, options);
	    var tokens;
	    tokens = [];
	    try {
	        while (true) {
	            var token = tokenizer.getNextToken();
	            if (!token) {
	                break;
	            }
	            if (delegate) {
	                token = delegate(token);
	            }
	            tokens.push(token);
	        }
	    }
	    catch (e) {
	        tokenizer.errorHandler.tolerate(e);
	    }
	    if (tokenizer.errorHandler.tolerant) {
	        tokens.errors = tokenizer.errors();
	    }
	    return tokens;
	}
```
</details>

### `CommentHandler(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CommentHandler() {
	        this.attach = false;
	        this.comments = [];
	        this.stack = [];
	        this.leading = [];
	        this.trailing = [];
	    }
```
</details>

### `Parser(code: any, options: any, delegate: any): void`

**Parameters:**

- **`code`** `any`
- **`options`** `any`
- **`delegate`** `any`

**Returns:** `void`

**Calls:**

- `String`
- `this.nextToken`

<details><summary>Code</summary>

```typescript
function Parser(code, options, delegate) {
	        if (options === void 0) { options = {}; }
	        this.config = {
	            range: (typeof options.range === 'boolean') && options.range,
	            loc: (typeof options.loc === 'boolean') && options.loc,
	            source: null,
	            tokens: (typeof options.tokens === 'boolean') && options.tokens,
	            comment: (typeof options.comment === 'boolean') && options.comment,
	            tolerant: (typeof options.tolerant === 'boolean') && options.tolerant
	        };
	        if (this.config.loc && options.source && options.source !== null) {
	            this.config.source = String(options.source);
	        }
	        this.delegate = delegate;
	        this.errorHandler = new error_handler_1.ErrorHandler();
	        this.errorHandler.tolerant = this.config.tolerant;
	        this.scanner = new scanner_1.Scanner(code, this.errorHandler);
	        this.scanner.trackComment = this.config.comment;
	        this.operatorPrecedence = {
	            ')': 0,
	            ';': 0,
	            ',': 0,
	            '=': 0,
	            ']': 0,
	            '||': 1,
	            '&&': 2,
	            '|': 3,
	            '^': 4,
	            '&': 5,
	            '==': 6,
	            '!=': 6,
	            '===': 6,
	            '!==': 6,
	            '<': 7,
	            '>': 7,
	            '<=': 7,
	            '>=': 7,
	            '<<': 8,
	            '>>': 8,
	            '>>>': 8,
	            '+': 9,
	            '-': 9,
	            '*': 11,
	            '/': 11,
	            '%': 11
	        };
	        this.sourceType = (options && options.sourceType === 'module') ? 'module' : 'script';
	        this.lookahead = null;
	        this.hasLineTerminator = false;
	        this.context = {
	            allowIn: true,
	            allowYield: true,
	            firstCoverInitializedNameError: null,
	            isAssignmentTarget: false,
	            isBindingElement: false,
	            inFunctionBody: false,
	            inIteration: false,
	            inSwitch: false,
	            labelSet: {},
	            strict: (this.sourceType === 'module')
	        };
	        this.tokens = [];
	        this.startMarker = {
	            index: 0,
	            lineNumber: this.scanner.lineNumber,
	            lineStart: 0
	        };
	        this.lastMarker = {
	            index: 0,
	            lineNumber: this.scanner.lineNumber,
	            lineStart: 0
	        };
	        this.nextToken();
	        this.lastMarker = {
	            index: this.scanner.index,
	            lineNumber: this.scanner.lineNumber,
	            lineStart: this.scanner.lineStart
	        };
	    }
```
</details>

### `assert(condition: any, message: any): void`

**Parameters:**

- **`condition`** `any`
- **`message`** `any`

**Returns:** `void`

**Internal Comments:**
```
/* istanbul ignore if */
```

<details><summary>Code</summary>

```typescript
function assert(condition, message) {
	    /* istanbul ignore if */
	    if (!condition) {
	        throw new Error('ASSERT: ' + message);
	    }
	}
```
</details>

### `ErrorHandler(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ErrorHandler() {
	        this.errors = [];
	        this.tolerant = false;
	    }
```
</details>

### `hexValue(ch: any): number`

**Parameters:**

- **`ch`** `any`

**Returns:** `number`

**Calls:**

- `'0123456789abcdef'.indexOf`
- `ch.toLowerCase`

<details><summary>Code</summary>

```typescript
function hexValue(ch) {
	    return '0123456789abcdef'.indexOf(ch.toLowerCase());
	}
```
</details>

### `octalValue(ch: any): number`

**Parameters:**

- **`ch`** `any`

**Returns:** `number`

**Calls:**

- `'01234567'.indexOf`

<details><summary>Code</summary>

```typescript
function octalValue(ch) {
	    return '01234567'.indexOf(ch);
	}
```
</details>

### `Scanner(code: any, handler: any): void`

**Parameters:**

- **`code`** `any`
- **`handler`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Scanner(code, handler) {
	        this.source = code;
	        this.errorHandler = handler;
	        this.trackComment = false;
	        this.length = code.length;
	        this.index = 0;
	        this.lineNumber = (code.length > 0) ? 1 : 0;
	        this.lineStart = 0;
	        this.curlyStack = [];
	    }
```
</details>

### `fromCodePoint(cp: any): string`

**Parameters:**

- **`cp`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp < 0x10000) ? String.fromCharCode(cp) :
	            String.fromCharCode(0xD800 + ((cp - 0x10000) >> 10)) +
	                String.fromCharCode(0xDC00 + ((cp - 0x10000) & 1023));
	    }
```
</details>

### `isWhiteSpace(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

**Calls:**

- `[0x1680, 0x2000, 0x2001, 0x2002, 0x2003, 0x2004, 0x2005, 0x2006, 0x2007, 0x2008, 0x2009, 0x200A, 0x202F, 0x205F, 0x3000, 0xFEFF].indexOf`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x20) || (cp === 0x09) || (cp === 0x0B) || (cp === 0x0C) || (cp === 0xA0) ||
	            (cp >= 0x1680 && [0x1680, 0x2000, 0x2001, 0x2002, 0x2003, 0x2004, 0x2005, 0x2006, 0x2007, 0x2008, 0x2009, 0x200A, 0x202F, 0x205F, 0x3000, 0xFEFF].indexOf(cp) >= 0);
	    }
```
</details>

### `isLineTerminator(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x0A) || (cp === 0x0D) || (cp === 0x2028) || (cp === 0x2029);
	    }
```
</details>

### `isIdentifierStart(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

**Calls:**

- `Regex.NonAsciiIdentifierStart.test`
- `exports.Character.fromCodePoint`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x24) || (cp === 0x5F) ||
	            (cp >= 0x41 && cp <= 0x5A) ||
	            (cp >= 0x61 && cp <= 0x7A) ||
	            (cp === 0x5C) ||
	            ((cp >= 0x80) && Regex.NonAsciiIdentifierStart.test(exports.Character.fromCodePoint(cp)));
	    }
```
</details>

### `isIdentifierPart(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

**Calls:**

- `Regex.NonAsciiIdentifierPart.test`
- `exports.Character.fromCodePoint`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x24) || (cp === 0x5F) ||
	            (cp >= 0x41 && cp <= 0x5A) ||
	            (cp >= 0x61 && cp <= 0x7A) ||
	            (cp >= 0x30 && cp <= 0x39) ||
	            (cp === 0x5C) ||
	            ((cp >= 0x80) && Regex.NonAsciiIdentifierPart.test(exports.Character.fromCodePoint(cp)));
	    }
```
</details>

### `isDecimalDigit(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp >= 0x30 && cp <= 0x39); // 0..9
	    }
```
</details>

### `isHexDigit(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp >= 0x30 && cp <= 0x39) ||
	            (cp >= 0x41 && cp <= 0x46) ||
	            (cp >= 0x61 && cp <= 0x66); // a..f
	    }
```
</details>

### `isOctalDigit(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp >= 0x30 && cp <= 0x37); // 0..7
	    }
```
</details>

### `fromCodePoint(cp: any): string`

**Parameters:**

- **`cp`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp < 0x10000) ? String.fromCharCode(cp) :
	            String.fromCharCode(0xD800 + ((cp - 0x10000) >> 10)) +
	                String.fromCharCode(0xDC00 + ((cp - 0x10000) & 1023));
	    }
```
</details>

### `isWhiteSpace(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

**Calls:**

- `[0x1680, 0x2000, 0x2001, 0x2002, 0x2003, 0x2004, 0x2005, 0x2006, 0x2007, 0x2008, 0x2009, 0x200A, 0x202F, 0x205F, 0x3000, 0xFEFF].indexOf`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x20) || (cp === 0x09) || (cp === 0x0B) || (cp === 0x0C) || (cp === 0xA0) ||
	            (cp >= 0x1680 && [0x1680, 0x2000, 0x2001, 0x2002, 0x2003, 0x2004, 0x2005, 0x2006, 0x2007, 0x2008, 0x2009, 0x200A, 0x202F, 0x205F, 0x3000, 0xFEFF].indexOf(cp) >= 0);
	    }
```
</details>

### `isLineTerminator(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x0A) || (cp === 0x0D) || (cp === 0x2028) || (cp === 0x2029);
	    }
```
</details>

### `isIdentifierStart(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

**Calls:**

- `Regex.NonAsciiIdentifierStart.test`
- `exports.Character.fromCodePoint`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x24) || (cp === 0x5F) ||
	            (cp >= 0x41 && cp <= 0x5A) ||
	            (cp >= 0x61 && cp <= 0x7A) ||
	            (cp === 0x5C) ||
	            ((cp >= 0x80) && Regex.NonAsciiIdentifierStart.test(exports.Character.fromCodePoint(cp)));
	    }
```
</details>

### `isIdentifierPart(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

**Calls:**

- `Regex.NonAsciiIdentifierPart.test`
- `exports.Character.fromCodePoint`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp === 0x24) || (cp === 0x5F) ||
	            (cp >= 0x41 && cp <= 0x5A) ||
	            (cp >= 0x61 && cp <= 0x7A) ||
	            (cp >= 0x30 && cp <= 0x39) ||
	            (cp === 0x5C) ||
	            ((cp >= 0x80) && Regex.NonAsciiIdentifierPart.test(exports.Character.fromCodePoint(cp)));
	    }
```
</details>

### `isDecimalDigit(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp >= 0x30 && cp <= 0x39); // 0..9
	    }
```
</details>

### `isHexDigit(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp >= 0x30 && cp <= 0x39) ||
	            (cp >= 0x41 && cp <= 0x46) ||
	            (cp >= 0x61 && cp <= 0x66); // a..f
	    }
```
</details>

### `isOctalDigit(cp: any): boolean`

**Parameters:**

- **`cp`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function (cp) {
	        return (cp >= 0x30 && cp <= 0x37); // 0..7
	    }
```
</details>

### `ArrayExpression(elements: any): void`

**Parameters:**

- **`elements`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ArrayExpression(elements) {
	        this.type = syntax_1.Syntax.ArrayExpression;
	        this.elements = elements;
	    }
```
</details>

### `ArrayPattern(elements: any): void`

**Parameters:**

- **`elements`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ArrayPattern(elements) {
	        this.type = syntax_1.Syntax.ArrayPattern;
	        this.elements = elements;
	    }
```
</details>

### `ArrowFunctionExpression(params: any, body: any, expression: any): void`

**Parameters:**

- **`params`** `any`
- **`body`** `any`
- **`expression`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ArrowFunctionExpression(params, body, expression) {
	        this.type = syntax_1.Syntax.ArrowFunctionExpression;
	        this.id = null;
	        this.params = params;
	        this.body = body;
	        this.generator = false;
	        this.expression = expression;
	    }
```
</details>

### `AssignmentExpression(operator: any, left: any, right: any): void`

**Parameters:**

- **`operator`** `any`
- **`left`** `any`
- **`right`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function AssignmentExpression(operator, left, right) {
	        this.type = syntax_1.Syntax.AssignmentExpression;
	        this.operator = operator;
	        this.left = left;
	        this.right = right;
	    }
```
</details>

### `AssignmentPattern(left: any, right: any): void`

**Parameters:**

- **`left`** `any`
- **`right`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function AssignmentPattern(left, right) {
	        this.type = syntax_1.Syntax.AssignmentPattern;
	        this.left = left;
	        this.right = right;
	    }
```
</details>

### `BinaryExpression(operator: any, left: any, right: any): void`

**Parameters:**

- **`operator`** `any`
- **`left`** `any`
- **`right`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BinaryExpression(operator, left, right) {
	        var logical = (operator === '||' || operator === '&&');
	        this.type = logical ? syntax_1.Syntax.LogicalExpression : syntax_1.Syntax.BinaryExpression;
	        this.operator = operator;
	        this.left = left;
	        this.right = right;
	    }
```
</details>

### `BlockStatement(body: any): void`

**Parameters:**

- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BlockStatement(body) {
	        this.type = syntax_1.Syntax.BlockStatement;
	        this.body = body;
	    }
```
</details>

### `BreakStatement(label: any): void`

**Parameters:**

- **`label`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function BreakStatement(label) {
	        this.type = syntax_1.Syntax.BreakStatement;
	        this.label = label;
	    }
```
</details>

### `CallExpression(callee: any, args: any): void`

**Parameters:**

- **`callee`** `any`
- **`args`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CallExpression(callee, args) {
	        this.type = syntax_1.Syntax.CallExpression;
	        this.callee = callee;
	        this.arguments = args;
	    }
```
</details>

### `CatchClause(param: any, body: any): void`

**Parameters:**

- **`param`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function CatchClause(param, body) {
	        this.type = syntax_1.Syntax.CatchClause;
	        this.param = param;
	        this.body = body;
	    }
```
</details>

### `ClassBody(body: any): void`

**Parameters:**

- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ClassBody(body) {
	        this.type = syntax_1.Syntax.ClassBody;
	        this.body = body;
	    }
```
</details>

### `ClassDeclaration(id: any, superClass: any, body: any): void`

**Parameters:**

- **`id`** `any`
- **`superClass`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ClassDeclaration(id, superClass, body) {
	        this.type = syntax_1.Syntax.ClassDeclaration;
	        this.id = id;
	        this.superClass = superClass;
	        this.body = body;
	    }
```
</details>

### `ClassExpression(id: any, superClass: any, body: any): void`

**Parameters:**

- **`id`** `any`
- **`superClass`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ClassExpression(id, superClass, body) {
	        this.type = syntax_1.Syntax.ClassExpression;
	        this.id = id;
	        this.superClass = superClass;
	        this.body = body;
	    }
```
</details>

### `ComputedMemberExpression(object: any, property: any): void`

**Parameters:**

- **`object`** `any`
- **`property`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ComputedMemberExpression(object, property) {
	        this.type = syntax_1.Syntax.MemberExpression;
	        this.computed = true;
	        this.object = object;
	        this.property = property;
	    }
```
</details>

### `ConditionalExpression(test: any, consequent: any, alternate: any): void`

**Parameters:**

- **`test`** `any`
- **`consequent`** `any`
- **`alternate`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ConditionalExpression(test, consequent, alternate) {
	        this.type = syntax_1.Syntax.ConditionalExpression;
	        this.test = test;
	        this.consequent = consequent;
	        this.alternate = alternate;
	    }
```
</details>

### `ContinueStatement(label: any): void`

**Parameters:**

- **`label`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ContinueStatement(label) {
	        this.type = syntax_1.Syntax.ContinueStatement;
	        this.label = label;
	    }
```
</details>

### `DebuggerStatement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function DebuggerStatement() {
	        this.type = syntax_1.Syntax.DebuggerStatement;
	    }
```
</details>

### `Directive(expression: any, directive: any): void`

**Parameters:**

- **`expression`** `any`
- **`directive`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Directive(expression, directive) {
	        this.type = syntax_1.Syntax.ExpressionStatement;
	        this.expression = expression;
	        this.directive = directive;
	    }
```
</details>

### `DoWhileStatement(body: any, test: any): void`

**Parameters:**

- **`body`** `any`
- **`test`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function DoWhileStatement(body, test) {
	        this.type = syntax_1.Syntax.DoWhileStatement;
	        this.body = body;
	        this.test = test;
	    }
```
</details>

### `EmptyStatement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function EmptyStatement() {
	        this.type = syntax_1.Syntax.EmptyStatement;
	    }
```
</details>

### `ExportAllDeclaration(source: any): void`

**Parameters:**

- **`source`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ExportAllDeclaration(source) {
	        this.type = syntax_1.Syntax.ExportAllDeclaration;
	        this.source = source;
	    }
```
</details>

### `ExportDefaultDeclaration(declaration: any): void`

**Parameters:**

- **`declaration`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ExportDefaultDeclaration(declaration) {
	        this.type = syntax_1.Syntax.ExportDefaultDeclaration;
	        this.declaration = declaration;
	    }
```
</details>

### `ExportNamedDeclaration(declaration: any, specifiers: any, source: any): void`

**Parameters:**

- **`declaration`** `any`
- **`specifiers`** `any`
- **`source`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ExportNamedDeclaration(declaration, specifiers, source) {
	        this.type = syntax_1.Syntax.ExportNamedDeclaration;
	        this.declaration = declaration;
	        this.specifiers = specifiers;
	        this.source = source;
	    }
```
</details>

### `ExportSpecifier(local: any, exported: any): void`

**Parameters:**

- **`local`** `any`
- **`exported`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ExportSpecifier(local, exported) {
	        this.type = syntax_1.Syntax.ExportSpecifier;
	        this.exported = exported;
	        this.local = local;
	    }
```
</details>

### `ExpressionStatement(expression: any): void`

**Parameters:**

- **`expression`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ExpressionStatement(expression) {
	        this.type = syntax_1.Syntax.ExpressionStatement;
	        this.expression = expression;
	    }
```
</details>

### `ForInStatement(left: any, right: any, body: any): void`

**Parameters:**

- **`left`** `any`
- **`right`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ForInStatement(left, right, body) {
	        this.type = syntax_1.Syntax.ForInStatement;
	        this.left = left;
	        this.right = right;
	        this.body = body;
	        this.each = false;
	    }
```
</details>

### `ForOfStatement(left: any, right: any, body: any): void`

**Parameters:**

- **`left`** `any`
- **`right`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ForOfStatement(left, right, body) {
	        this.type = syntax_1.Syntax.ForOfStatement;
	        this.left = left;
	        this.right = right;
	        this.body = body;
	    }
```
</details>

### `ForStatement(init: any, test: any, update: any, body: any): void`

**Parameters:**

- **`init`** `any`
- **`test`** `any`
- **`update`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ForStatement(init, test, update, body) {
	        this.type = syntax_1.Syntax.ForStatement;
	        this.init = init;
	        this.test = test;
	        this.update = update;
	        this.body = body;
	    }
```
</details>

### `FunctionDeclaration(id: any, params: any, body: any, generator: any): void`

**Parameters:**

- **`id`** `any`
- **`params`** `any`
- **`body`** `any`
- **`generator`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function FunctionDeclaration(id, params, body, generator) {
	        this.type = syntax_1.Syntax.FunctionDeclaration;
	        this.id = id;
	        this.params = params;
	        this.body = body;
	        this.generator = generator;
	        this.expression = false;
	    }
```
</details>

### `FunctionExpression(id: any, params: any, body: any, generator: any): void`

**Parameters:**

- **`id`** `any`
- **`params`** `any`
- **`body`** `any`
- **`generator`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function FunctionExpression(id, params, body, generator) {
	        this.type = syntax_1.Syntax.FunctionExpression;
	        this.id = id;
	        this.params = params;
	        this.body = body;
	        this.generator = generator;
	        this.expression = false;
	    }
```
</details>

### `Identifier(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Identifier(name) {
	        this.type = syntax_1.Syntax.Identifier;
	        this.name = name;
	    }
```
</details>

### `IfStatement(test: any, consequent: any, alternate: any): void`

**Parameters:**

- **`test`** `any`
- **`consequent`** `any`
- **`alternate`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function IfStatement(test, consequent, alternate) {
	        this.type = syntax_1.Syntax.IfStatement;
	        this.test = test;
	        this.consequent = consequent;
	        this.alternate = alternate;
	    }
```
</details>

### `ImportDeclaration(specifiers: any, source: any): void`

**Parameters:**

- **`specifiers`** `any`
- **`source`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ImportDeclaration(specifiers, source) {
	        this.type = syntax_1.Syntax.ImportDeclaration;
	        this.specifiers = specifiers;
	        this.source = source;
	    }
```
</details>

### `ImportDefaultSpecifier(local: any): void`

**Parameters:**

- **`local`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ImportDefaultSpecifier(local) {
	        this.type = syntax_1.Syntax.ImportDefaultSpecifier;
	        this.local = local;
	    }
```
</details>

### `ImportNamespaceSpecifier(local: any): void`

**Parameters:**

- **`local`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ImportNamespaceSpecifier(local) {
	        this.type = syntax_1.Syntax.ImportNamespaceSpecifier;
	        this.local = local;
	    }
```
</details>

### `ImportSpecifier(local: any, imported: any): void`

**Parameters:**

- **`local`** `any`
- **`imported`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ImportSpecifier(local, imported) {
	        this.type = syntax_1.Syntax.ImportSpecifier;
	        this.local = local;
	        this.imported = imported;
	    }
```
</details>

### `LabeledStatement(label: any, body: any): void`

**Parameters:**

- **`label`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function LabeledStatement(label, body) {
	        this.type = syntax_1.Syntax.LabeledStatement;
	        this.label = label;
	        this.body = body;
	    }
```
</details>

### `Literal(value: any, raw: any): void`

**Parameters:**

- **`value`** `any`
- **`raw`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Literal(value, raw) {
	        this.type = syntax_1.Syntax.Literal;
	        this.value = value;
	        this.raw = raw;
	    }
```
</details>

### `MetaProperty(meta: any, property: any): void`

**Parameters:**

- **`meta`** `any`
- **`property`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function MetaProperty(meta, property) {
	        this.type = syntax_1.Syntax.MetaProperty;
	        this.meta = meta;
	        this.property = property;
	    }
```
</details>

### `MethodDefinition(key: any, computed: any, value: any, kind: any, isStatic: any): void`

**Parameters:**

- **`key`** `any`
- **`computed`** `any`
- **`value`** `any`
- **`kind`** `any`
- **`isStatic`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function MethodDefinition(key, computed, value, kind, isStatic) {
	        this.type = syntax_1.Syntax.MethodDefinition;
	        this.key = key;
	        this.computed = computed;
	        this.value = value;
	        this.kind = kind;
	        this.static = isStatic;
	    }
```
</details>

### `NewExpression(callee: any, args: any): void`

**Parameters:**

- **`callee`** `any`
- **`args`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function NewExpression(callee, args) {
	        this.type = syntax_1.Syntax.NewExpression;
	        this.callee = callee;
	        this.arguments = args;
	    }
```
</details>

### `ObjectExpression(properties: any): void`

**Parameters:**

- **`properties`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ObjectExpression(properties) {
	        this.type = syntax_1.Syntax.ObjectExpression;
	        this.properties = properties;
	    }
```
</details>

### `ObjectPattern(properties: any): void`

**Parameters:**

- **`properties`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ObjectPattern(properties) {
	        this.type = syntax_1.Syntax.ObjectPattern;
	        this.properties = properties;
	    }
```
</details>

### `Program(body: any, sourceType: any): void`

**Parameters:**

- **`body`** `any`
- **`sourceType`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Program(body, sourceType) {
	        this.type = syntax_1.Syntax.Program;
	        this.body = body;
	        this.sourceType = sourceType;
	    }
```
</details>

### `Property(kind: any, key: any, computed: any, value: any, method: any, shorthand: any): void`

**Parameters:**

- **`kind`** `any`
- **`key`** `any`
- **`computed`** `any`
- **`value`** `any`
- **`method`** `any`
- **`shorthand`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Property(kind, key, computed, value, method, shorthand) {
	        this.type = syntax_1.Syntax.Property;
	        this.key = key;
	        this.computed = computed;
	        this.value = value;
	        this.kind = kind;
	        this.method = method;
	        this.shorthand = shorthand;
	    }
```
</details>

### `RegexLiteral(value: any, raw: any, regex: any): void`

**Parameters:**

- **`value`** `any`
- **`raw`** `any`
- **`regex`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RegexLiteral(value, raw, regex) {
	        this.type = syntax_1.Syntax.Literal;
	        this.value = value;
	        this.raw = raw;
	        this.regex = regex;
	    }
```
</details>

### `RestElement(argument: any): void`

**Parameters:**

- **`argument`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RestElement(argument) {
	        this.type = syntax_1.Syntax.RestElement;
	        this.argument = argument;
	    }
```
</details>

### `ReturnStatement(argument: any): void`

**Parameters:**

- **`argument`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ReturnStatement(argument) {
	        this.type = syntax_1.Syntax.ReturnStatement;
	        this.argument = argument;
	    }
```
</details>

### `SequenceExpression(expressions: any): void`

**Parameters:**

- **`expressions`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SequenceExpression(expressions) {
	        this.type = syntax_1.Syntax.SequenceExpression;
	        this.expressions = expressions;
	    }
```
</details>

### `SpreadElement(argument: any): void`

**Parameters:**

- **`argument`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SpreadElement(argument) {
	        this.type = syntax_1.Syntax.SpreadElement;
	        this.argument = argument;
	    }
```
</details>

### `StaticMemberExpression(object: any, property: any): void`

**Parameters:**

- **`object`** `any`
- **`property`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function StaticMemberExpression(object, property) {
	        this.type = syntax_1.Syntax.MemberExpression;
	        this.computed = false;
	        this.object = object;
	        this.property = property;
	    }
```
</details>

### `Super(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Super() {
	        this.type = syntax_1.Syntax.Super;
	    }
```
</details>

### `SwitchCase(test: any, consequent: any): void`

**Parameters:**

- **`test`** `any`
- **`consequent`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SwitchCase(test, consequent) {
	        this.type = syntax_1.Syntax.SwitchCase;
	        this.test = test;
	        this.consequent = consequent;
	    }
```
</details>

### `SwitchStatement(discriminant: any, cases: any): void`

**Parameters:**

- **`discriminant`** `any`
- **`cases`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SwitchStatement(discriminant, cases) {
	        this.type = syntax_1.Syntax.SwitchStatement;
	        this.discriminant = discriminant;
	        this.cases = cases;
	    }
```
</details>

### `TaggedTemplateExpression(tag: any, quasi: any): void`

**Parameters:**

- **`tag`** `any`
- **`quasi`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function TaggedTemplateExpression(tag, quasi) {
	        this.type = syntax_1.Syntax.TaggedTemplateExpression;
	        this.tag = tag;
	        this.quasi = quasi;
	    }
```
</details>

### `TemplateElement(value: any, tail: any): void`

**Parameters:**

- **`value`** `any`
- **`tail`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function TemplateElement(value, tail) {
	        this.type = syntax_1.Syntax.TemplateElement;
	        this.value = value;
	        this.tail = tail;
	    }
```
</details>

### `TemplateLiteral(quasis: any, expressions: any): void`

**Parameters:**

- **`quasis`** `any`
- **`expressions`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function TemplateLiteral(quasis, expressions) {
	        this.type = syntax_1.Syntax.TemplateLiteral;
	        this.quasis = quasis;
	        this.expressions = expressions;
	    }
```
</details>

### `ThisExpression(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ThisExpression() {
	        this.type = syntax_1.Syntax.ThisExpression;
	    }
```
</details>

### `ThrowStatement(argument: any): void`

**Parameters:**

- **`argument`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ThrowStatement(argument) {
	        this.type = syntax_1.Syntax.ThrowStatement;
	        this.argument = argument;
	    }
```
</details>

### `TryStatement(block: any, handler: any, finalizer: any): void`

**Parameters:**

- **`block`** `any`
- **`handler`** `any`
- **`finalizer`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function TryStatement(block, handler, finalizer) {
	        this.type = syntax_1.Syntax.TryStatement;
	        this.block = block;
	        this.handler = handler;
	        this.finalizer = finalizer;
	    }
```
</details>

### `UnaryExpression(operator: any, argument: any): void`

**Parameters:**

- **`operator`** `any`
- **`argument`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function UnaryExpression(operator, argument) {
	        this.type = syntax_1.Syntax.UnaryExpression;
	        this.operator = operator;
	        this.argument = argument;
	        this.prefix = true;
	    }
```
</details>

### `UpdateExpression(operator: any, argument: any, prefix: any): void`

**Parameters:**

- **`operator`** `any`
- **`argument`** `any`
- **`prefix`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function UpdateExpression(operator, argument, prefix) {
	        this.type = syntax_1.Syntax.UpdateExpression;
	        this.operator = operator;
	        this.argument = argument;
	        this.prefix = prefix;
	    }
```
</details>

### `VariableDeclaration(declarations: any, kind: any): void`

**Parameters:**

- **`declarations`** `any`
- **`kind`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function VariableDeclaration(declarations, kind) {
	        this.type = syntax_1.Syntax.VariableDeclaration;
	        this.declarations = declarations;
	        this.kind = kind;
	    }
```
</details>

### `VariableDeclarator(id: any, init: any): void`

**Parameters:**

- **`id`** `any`
- **`init`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function VariableDeclarator(id, init) {
	        this.type = syntax_1.Syntax.VariableDeclarator;
	        this.id = id;
	        this.init = init;
	    }
```
</details>

### `WhileStatement(test: any, body: any): void`

**Parameters:**

- **`test`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function WhileStatement(test, body) {
	        this.type = syntax_1.Syntax.WhileStatement;
	        this.test = test;
	        this.body = body;
	    }
```
</details>

### `WithStatement(object: any, body: any): void`

**Parameters:**

- **`object`** `any`
- **`body`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function WithStatement(object, body) {
	        this.type = syntax_1.Syntax.WithStatement;
	        this.object = object;
	        this.body = body;
	    }
```
</details>

### `YieldExpression(argument: any, delegate: any): void`

**Parameters:**

- **`argument`** `any`
- **`delegate`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function YieldExpression(argument, delegate) {
	        this.type = syntax_1.Syntax.YieldExpression;
	        this.argument = argument;
	        this.delegate = delegate;
	    }
```
</details>

### `__(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function __() { this.constructor = d; }
```
</details>

### `getQualifiedElementName(elementName: any): any`

**Parameters:**

- **`elementName`** `any`

**Returns:** `any`

**Calls:**

- `getQualifiedElementName`

<details><summary>Code</summary>

```typescript
function getQualifiedElementName(elementName) {
	    var qualifiedName;
	    switch (elementName.type) {
	        case jsx_syntax_1.JSXSyntax.JSXIdentifier:
	            var id = (elementName);
	            qualifiedName = id.name;
	            break;
	        case jsx_syntax_1.JSXSyntax.JSXNamespacedName:
	            var ns = (elementName);
	            qualifiedName = getQualifiedElementName(ns.namespace) + ':' +
	                getQualifiedElementName(ns.name);
	            break;
	        case jsx_syntax_1.JSXSyntax.JSXMemberExpression:
	            var expr = (elementName);
	            qualifiedName = getQualifiedElementName(expr.object) + '.' +
	                getQualifiedElementName(expr.property);
	            break;
	    }
	    return qualifiedName;
	}
```
</details>

### `JSXParser(code: any, options: any, delegate: any): void`

**Parameters:**

- **`code`** `any`
- **`options`** `any`
- **`delegate`** `any`

**Returns:** `void`

**Calls:**

- `_super.call`

<details><summary>Code</summary>

```typescript
function JSXParser(code, options, delegate) {
	        _super.call(this, code, options, delegate);
	    }
```
</details>

### `JSXClosingElement(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXClosingElement(name) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXClosingElement;
	        this.name = name;
	    }
```
</details>

### `JSXElement(openingElement: any, children: any, closingElement: any): void`

**Parameters:**

- **`openingElement`** `any`
- **`children`** `any`
- **`closingElement`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXElement(openingElement, children, closingElement) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXElement;
	        this.openingElement = openingElement;
	        this.children = children;
	        this.closingElement = closingElement;
	    }
```
</details>

### `JSXEmptyExpression(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXEmptyExpression() {
	        this.type = jsx_syntax_1.JSXSyntax.JSXEmptyExpression;
	    }
```
</details>

### `JSXExpressionContainer(expression: any): void`

**Parameters:**

- **`expression`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXExpressionContainer(expression) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXExpressionContainer;
	        this.expression = expression;
	    }
```
</details>

### `JSXIdentifier(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXIdentifier(name) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXIdentifier;
	        this.name = name;
	    }
```
</details>

### `JSXMemberExpression(object: any, property: any): void`

**Parameters:**

- **`object`** `any`
- **`property`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXMemberExpression(object, property) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXMemberExpression;
	        this.object = object;
	        this.property = property;
	    }
```
</details>

### `JSXAttribute(name: any, value: any): void`

**Parameters:**

- **`name`** `any`
- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXAttribute(name, value) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXAttribute;
	        this.name = name;
	        this.value = value;
	    }
```
</details>

### `JSXNamespacedName(namespace: any, name: any): void`

**Parameters:**

- **`namespace`** `any`
- **`name`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXNamespacedName(namespace, name) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXNamespacedName;
	        this.namespace = namespace;
	        this.name = name;
	    }
```
</details>

### `JSXOpeningElement(name: any, selfClosing: any, attributes: any): void`

**Parameters:**

- **`name`** `any`
- **`selfClosing`** `any`
- **`attributes`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXOpeningElement(name, selfClosing, attributes) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXOpeningElement;
	        this.name = name;
	        this.selfClosing = selfClosing;
	        this.attributes = attributes;
	    }
```
</details>

### `JSXSpreadAttribute(argument: any): void`

**Parameters:**

- **`argument`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXSpreadAttribute(argument) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXSpreadAttribute;
	        this.argument = argument;
	    }
```
</details>

### `JSXText(value: any, raw: any): void`

**Parameters:**

- **`value`** `any`
- **`raw`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSXText(value, raw) {
	        this.type = jsx_syntax_1.JSXSyntax.JSXText;
	        this.value = value;
	        this.raw = raw;
	    }
```
</details>

### `Reader(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Reader() {
	        this.values = [];
	        this.curly = this.paren = -1;
	    }
```
</details>

### `Tokenizer(code: any, config: any): void`

**Parameters:**

- **`code`** `any`
- **`config`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Tokenizer(code, config) {
	        this.errorHandler = new error_handler_1.ErrorHandler();
	        this.errorHandler.tolerant = config ? (typeof config.tolerant === 'boolean' && config.tolerant) : false;
	        this.scanner = new scanner_1.Scanner(code, this.errorHandler);
	        this.scanner.trackComment = config ? (typeof config.comment === 'boolean' && config.comment) : false;
	        this.trackRange = config ? (typeof config.range === 'boolean' && config.range) : false;
	        this.trackLoc = config ? (typeof config.loc === 'boolean' && config.loc) : false;
	        this.buffer = [];
	        this.reader = new Reader();
	    }
```
</details>


---