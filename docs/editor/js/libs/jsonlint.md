[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `jsonlint.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 306 |
| 📊 Variables & Constants | 34 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/jsonlint.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `$0` | `number` | let/var | `$$.length - 1` | ✗ |
| `self` | `{ trace: () => void; yy: {}; symbols_...` | let/var | `this` | ✗ |
| `stack` | `number[]` | let/var | `[0]` | ✗ |
| `vstack` | `any[]` | let/var | `[null]` | ✗ |
| `lstack` | `any[]` | let/var | `[]` | ✗ |
| `table` | `({ 3: number; 4: number[]; 5: number;...` | let/var | `this.table` | ✗ |
| `yytext` | `string` | let/var | `''` | ✗ |
| `yylineno` | `number` | let/var | `0` | ✗ |
| `yyleng` | `number` | let/var | `0` | ✗ |
| `recovering` | `number` | let/var | `0` | ✗ |
| `TERROR` | `number` | let/var | `2` | ✗ |
| `EOF` | `number` | let/var | `1` | ✗ |
| `yyloc` | `any` | let/var | `this.lexer.yylloc` | ✗ |
| `token` | `any` | let/var | `*not shown*` | ✗ |
| `symbol` | `any` | let/var | `*not shown*` | ✗ |
| `preErrorSymbol` | `any` | let/var | `*not shown*` | ✗ |
| `state` | `any` | let/var | `*not shown*` | ✗ |
| `action` | `any` | let/var | `*not shown*` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `yyval` | `{ $: any; _$: { first_line: any; last...` | let/var | `{}` | ✗ |
| `p` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `newState` | `any` | let/var | `*not shown*` | ✗ |
| `expected` | `any` | let/var | `*not shown*` | ✗ |
| `errStr` | `string` | let/var | `''` | ✗ |
| `parser` | `{ trace: () => void; yy: {}; symbols_...` | let/var | `{trace: function trace() { }, yy: {}, symbols_: {"error":2,"JSONString":3,"ST...` | ✗ |
| `ch` | `any` | let/var | `this._input[0]` | ✗ |
| `next` | `any` | let/var | `this.match` | ✗ |
| `token` | `any` | let/var | `*not shown*` | ✗ |
| `match` | `any` | let/var | `*not shown*` | ✗ |
| `tempMatch` | `any` | let/var | `*not shown*` | ✗ |
| `index` | `any` | let/var | `*not shown*` | ✗ |
| `lines` | `any` | let/var | `*not shown*` | ✗ |
| `lexer` | `{ EOF: number; parseError: (str: any,...` | let/var | `({EOF:1, parseError:function parseError(str, hash) { if (this.yy.parseError) ...` | ✗ |


---

## Functions

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `popStack(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `self.lexer.lex`

**Internal Comments:**
```
// if token isn't its numeric value, convert
```

<details><summary>Code</summary>

```typescript
function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `trace(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function trace() { }
```
</details>

### `performAction(yytext: any, yyleng: any, yylineno: any, yy: any, yystate: any, $$: any, _$: any): any`

**Parameters:**

- **`yytext`** `any`
- **`yyleng`** `any`
- **`yylineno`** `any`
- **`yy`** `any`
- **`yystate`** `any`
- **`$$`** `any`
- **`_$`** `any`

**Returns:** `any`

**Calls:**

- `yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace`
- `Number`
- `$$[$0-2].push`

<details><summary>Code</summary>

```typescript
function anonymous(yytext,yyleng,yylineno,yy,yystate,$$,_$) {

var $0 = $$.length - 1;
switch (yystate) {
case 1: // replace escaped characters with actual character
          this.$ = yytext.replace(/\\(\\|")/g, "$"+"1")
                     .replace(/\\n/g,'\n')
                     .replace(/\\r/g,'\r')
                     .replace(/\\t/g,'\t')
                     .replace(/\\v/g,'\v')
                     .replace(/\\f/g,'\f')
                     .replace(/\\b/g,'\b');

break;
case 2:this.$ = Number(yytext);
break;
case 3:this.$ = null;
break;
case 4:this.$ = true;
break;
case 5:this.$ = false;
break;
case 6:return this.$ = $$[$0-1];
break;
case 13:this.$ = {};
break;
case 14:this.$ = $$[$0-1];
break;
case 15:this.$ = [$$[$0-2], $$[$0]];
break;
case 16:this.$ = {}; this.$[$$[$0][0]] = $$[$0][1];
break;
case 17:this.$ = $$[$0-2]; $$[$0-2][$$[$0][0]] = $$[$0][1];
break;
case 18:this.$ = [];
break;
case 19:this.$ = $$[$0-1];
break;
case 20:this.$ = [$$[$0]];
break;
case 21:this.$ = $$[$0-2]; $$[$0-2].push($$[$0]);
break;
}
}
```
</details>

### `parseError(str: any, hash: any): never`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
    throw new Error(str);
}
```
</details>

### `parse(input: any): any`

**Parameters:**

- **`input`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.setInput`
- `lstack.push`
- `self.lexer.lex`
- `lex`
- `expected.push`
- `this.lexer.showPosition`
- `expected.join`
- `this.parseError`
- `TERROR.toString`
- `popStack`
- `stack.push`
- `vstack.push`
- `this.performAction.call`
- `stack.slice`
- `vstack.slice`
- `lstack.slice`

**Internal Comments:**
```
//this.reductionCount = this.shiftCount = 0; (x5)
// if token isn't its numeric value, convert
// retrieve state number from top of stack (x3)
// use default actions if available
// read action for current state and first input (x3)
// handle parse error (x2)
// Report error (x3)
// just recovered from another error
// discard current lookahead and grab another (x3)
// try to recover from error
// check for error recovery rule in this state
// this shouldn't happen, unless resolve defaults are off
//this.shiftCount++; (x4)
//this.reductionCount++; (x3)
// perform semantic action (x4)
// default location, uses first token for firsts, last for lasts (x4)
// pop off stack
// goto new state = table[STATE][NONTERMINAL] (x3)
```

<details><summary>Code</summary>

```typescript
function parse(input) {
    var self = this,
        stack = [0],
        vstack = [null], // semantic value stack
        lstack = [], // location stack
        table = this.table,
        yytext = '',
        yylineno = 0,
        yyleng = 0,
        recovering = 0,
        TERROR = 2,
        EOF = 1;

    //this.reductionCount = this.shiftCount = 0;

    this.lexer.setInput(input);
    this.lexer.yy = this.yy;
    this.yy.lexer = this.lexer;
    if (typeof this.lexer.yylloc == 'undefined')
        this.lexer.yylloc = {};
    var yyloc = this.lexer.yylloc;
    lstack.push(yyloc);

    if (typeof this.yy.parseError === 'function')
        this.parseError = this.yy.parseError;

    function popStack (n) {
        stack.length = stack.length - 2*n;
        vstack.length = vstack.length - n;
        lstack.length = lstack.length - n;
    }

    function lex() {
        var token;
        token = self.lexer.lex() || 1; // $end = 1
        // if token isn't its numeric value, convert
        if (typeof token !== 'number') {
            token = self.symbols_[token] || token;
        }
        return token;
    }

    var symbol, preErrorSymbol, state, action, r, yyval={},p,len,newState, expected;
    while (true) {
        // retrieve state number from top of stack
        state = stack[stack.length-1];

        // use default actions if available
        if (this.defaultActions[state]) {
            action = this.defaultActions[state];
        } else {
            if (symbol == null)
                symbol = lex();
            // read action for current state and first input
            action = table[state] && table[state][symbol];
        }

        // handle parse error
        _handle_error:
        if (typeof action === 'undefined' || !action.length || !action[0]) {

            if (!recovering) {
                // Report error
                expected = [];
                for (p in table[state]) if (this.terminals_[p] && p > 2) {
                    expected.push("'"+this.terminals_[p]+"'");
                }
                var errStr = '';
                if (this.lexer.showPosition) {
                    errStr = 'Parse error on line '+(yylineno+1)+":\n"+this.lexer.showPosition()+"\nExpecting "+expected.join(', ') + ", got '" + this.terminals_[symbol]+ "'";
                } else {
                    errStr = 'Parse error on line '+(yylineno+1)+": Unexpected " +
                                  (symbol == 1 /*EOF*/ ? "end of input" :
                                              ("'"+(this.terminals_[symbol] || symbol)+"'"));
                }
                this.parseError(errStr,
                    {text: this.lexer.match, token: this.terminals_[symbol] || symbol, line: this.lexer.yylineno, loc: yyloc, expected: expected});
            }

            // just recovered from another error
            if (recovering == 3) {
                if (symbol == EOF) {
                    throw new Error(errStr || 'Parsing halted.');
                }

                // discard current lookahead and grab another
                yyleng = this.lexer.yyleng;
                yytext = this.lexer.yytext;
                yylineno = this.lexer.yylineno;
                yyloc = this.lexer.yylloc;
                symbol = lex();
            }

            // try to recover from error
            while (1) {
                // check for error recovery rule in this state
                if ((TERROR.toString()) in table[state]) {
                    break;
                }
                if (state == 0) {
                    throw new Error(errStr || 'Parsing halted.');
                }
                popStack(1);
                state = stack[stack.length-1];
            }

            preErrorSymbol = symbol; // save the lookahead token
            symbol = TERROR;         // insert generic error symbol as new lookahead
            state = stack[stack.length-1];
            action = table[state] && table[state][TERROR];
            recovering = 3; // allow 3 real symbols to be shifted before reporting a new error
        }

        // this shouldn't happen, unless resolve defaults are off
        if (action[0] instanceof Array && action.length > 1) {
            throw new Error('Parse Error: multiple actions possible at state: '+state+', token: '+symbol);
        }

        switch (action[0]) {

            case 1: // shift
                //this.shiftCount++;

                stack.push(symbol);
                vstack.push(this.lexer.yytext);
                lstack.push(this.lexer.yylloc);
                stack.push(action[1]); // push state
                symbol = null;
                if (!preErrorSymbol) { // normal execution/no error
                    yyleng = this.lexer.yyleng;
                    yytext = this.lexer.yytext;
                    yylineno = this.lexer.yylineno;
                    yyloc = this.lexer.yylloc;
                    if (recovering > 0)
                        recovering--;
                } else { // error just occurred, resume old lookahead f/ before error
                    symbol = preErrorSymbol;
                    preErrorSymbol = null;
                }
                break;

            case 2: // reduce
                //this.reductionCount++;

                len = this.productions_[action[1]][1];

                // perform semantic action
                yyval.$ = vstack[vstack.length-len]; // default to $$ = $1
                // default location, uses first token for firsts, last for lasts
                yyval._$ = {
                    first_line: lstack[lstack.length-(len||1)].first_line,
                    last_line: lstack[lstack.length-1].last_line,
                    first_column: lstack[lstack.length-(len||1)].first_column,
                    last_column: lstack[lstack.length-1].last_column
                };
                r = this.performAction.call(yyval, yytext, yyleng, yylineno, this.yy, action[1], vstack, lstack);

                if (typeof r !== 'undefined') {
                    return r;
                }

                // pop off stack
                if (len) {
                    stack = stack.slice(0,-1*len*2);
                    vstack = vstack.slice(0, -1*len);
                    lstack = lstack.slice(0, -1*len);
                }

                stack.push(this.productions_[action[1]][0]);    // push nonterminal (reduce)
                vstack.push(yyval.$);
                lstack.push(yyval._$);
                // goto new state = table[STATE][NONTERMINAL]
                newState = table[stack[stack.length-2]][stack[stack.length-1]];
                stack.push(newState);
                break;

            case 3: // accept
                return true;
        }

    }

}
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>

### `parseError(str: any, hash: any): void`

**Parameters:**

- **`str`** `any`
- **`hash`** `any`

**Returns:** `void`

**Calls:**

- `this.yy.parseError`

<details><summary>Code</summary>

```typescript
function parseError(str, hash) {
        if (this.yy.parseError) {
            this.yy.parseError(str, hash);
        } else {
            throw new Error(str);
        }
    }
```
</details>

### `setInput(input: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`input`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (input) {
        this._input = input;
        this._more = this._less = this.done = false;
        this.yylineno = this.yyleng = 0;
        this.yytext = this.matched = this.match = '';
        this.conditionStack = ['INITIAL'];
        this.yylloc = {first_line:1,first_column:0,last_line:1,last_column:0};
        return this;
    }
```
</details>

### `input(): any`

**Returns:** `any`

**Calls:**

- `ch.match`
- `this._input.slice`

<details><summary>Code</summary>

```typescript
function () {
        var ch = this._input[0];
        this.yytext+=ch;
        this.yyleng++;
        this.match+=ch;
        this.matched+=ch;
        var lines = ch.match(/\n/);
        if (lines) this.yylineno++;
        this._input = this._input.slice(1);
        return ch;
    }
```
</details>

### `unput(ch: any): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Parameters:**

- **`ch`** `any`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function (ch) {
        this._input = ch + this._input;
        return this;
    }
```
</details>

### `more(): { EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

**Returns:** `{ EOF: number; parseError: (str: any, hash: any) => void; setInput: typeof setInput; input: typeof input; unput: typeof unput; more: typeof more; less: typeof less; pastInput: () => string; upcomingInput: () => string; ... 7 more ...; pushState: (condition: any) => void; }`

<details><summary>Code</summary>

```typescript
function () {
        this._more = true;
        return this;
    }
```
</details>

### `less(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `this.match.slice`

<details><summary>Code</summary>

```typescript
function (n) {
        this._input = this.match.slice(n) + this._input;
    }
```
</details>

### `pastInput(): string`

**Returns:** `string`

**Calls:**

- `this.matched.substr`
- `past.substr(-20).replace`

<details><summary>Code</summary>

```typescript
function () {
        var past = this.matched.substr(0, this.matched.length - this.match.length);
        return (past.length > 20 ? '...':'') + past.substr(-20).replace(/\n/g, "");
    }
```
</details>

### `upcomingInput(): string`

**Returns:** `string`

**Calls:**

- `this._input.substr`
- `(next.substr(0,20)+(next.length > 20 ? '...':'')).replace`
- `next.substr`

<details><summary>Code</summary>

```typescript
function () {
        var next = this.match;
        if (next.length < 20) {
            next += this._input.substr(0, 20-next.length);
        }
        return (next.substr(0,20)+(next.length > 20 ? '...':'')).replace(/\n/g, "");
    }
```
</details>

### `showPosition(): string`

**Returns:** `string`

**Calls:**

- `this.pastInput`
- `new Array(pre.length + 1).join`
- `this.upcomingInput`

<details><summary>Code</summary>

```typescript
function () {
        var pre = this.pastInput();
        var c = new Array(pre.length + 1).join("-");
        return pre + this.upcomingInput() + "\n" + c+"^";
    }
```
</details>

### `next(): any`

**Returns:** `any`

**Calls:**

- `this._currentRules`
- `this._input.match`
- `match[0].match`
- `this._input.slice`
- `this.performAction.call`
- `this.parseError`
- `this.showPosition`

<details><summary>Code</summary>

```typescript
function () {
        if (this.done) {
            return this.EOF;
        }
        if (!this._input) this.done = true;

        var token,
            match,
            tempMatch,
            index,
            lines;
        if (!this._more) {
            this.yytext = '';
            this.match = '';
        }
        var rules = this._currentRules();
        for (var i=0;i < rules.length; i++) {
            tempMatch = this._input.match(this.rules[rules[i]]);
            if (tempMatch && (!match || tempMatch[0].length > match[0].length)) {
                match = tempMatch;
                index = i;
                if (!this.options.flex) break;
            }
        }
        if (match) {
            lines = match[0].match(/\n.*/g);
            if (lines) this.yylineno += lines.length;
            this.yylloc = {first_line: this.yylloc.last_line,
                           last_line: this.yylineno+1,
                           first_column: this.yylloc.last_column,
                           last_column: lines ? lines[lines.length-1].length-1 : this.yylloc.last_column + match[0].length};
            this.yytext += match[0];
            this.match += match[0];
            this.yyleng = this.yytext.length;
            this._more = false;
            this._input = this._input.slice(match[0].length);
            this.matched += match[0];
            token = this.performAction.call(this, this.yy, this, rules[index],this.conditionStack[this.conditionStack.length-1]);
            if (this.done && this._input) this.done = false;
            if (token) return token;
            else return;
        }
        if (this._input === "") {
            return this.EOF;
        } else {
            this.parseError('Lexical error on line '+(this.yylineno+1)+'. Unrecognized text.\n'+this.showPosition(),
                    {text: "", token: null, line: this.yylineno});
        }
    }
```
</details>

### `lex(): any`

**Returns:** `any`

**Calls:**

- `this.next`
- `this.lex`

<details><summary>Code</summary>

```typescript
function lex() {
        var r = this.next();
        if (typeof r !== 'undefined') {
            return r;
        } else {
            return this.lex();
        }
    }
```
</details>

### `begin(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.conditionStack.push`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.conditionStack.push(condition);
    }
```
</details>

### `popState(): any`

**Returns:** `any`

**Calls:**

- `this.conditionStack.pop`

<details><summary>Code</summary>

```typescript
function popState() {
        return this.conditionStack.pop();
    }
```
</details>

### `_currentRules(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function _currentRules() {
        return this.conditions[this.conditionStack[this.conditionStack.length-1]].rules;
    }
```
</details>

### `topState(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {
        return this.conditionStack[this.conditionStack.length-2];
    }
```
</details>

### `pushState(condition: any): void`

**Parameters:**

- **`condition`** `any`

**Returns:** `void`

**Calls:**

- `this.begin`

<details><summary>Code</summary>

```typescript
function begin(condition) {
        this.begin(condition);
    }
```
</details>


---