## DustBuster
by Mike Delucchi - [zanuka](https://github.com/zanuka)

![DustBuster](images/dust-buster-syntax.png?raw=true "DustBuster")

***
DustBuster is an enhanced syntax definition for .dust files that includes sublime completions of dustjs-helpers and dustjs logic syntax.

### Features
- syntax definition for .dust files (with html support)
- sublime completions for supported dustjs-helpers and dustjs logic

### Requirements
- [Sublime Text 2](http://www.sublimetext.com/2) or [Sublime Text 3](http://www.sublimetext.com/3)
- [Package Control](https://packagecontrol.io/)

### Installing DustBuster
- cmd+shift+p, Install Package, search for DustBuster or Dust

### Activating the Dust syntax definition for all .dust files
-  open any .dust file and then select View > Syntax > Dust

### Supported Helpers ###
- [{linkedin/dustjs-helpers}](https://github.com/linkedin/dustjs-helpers)
- [{linkedin/dustjs-helpers/wiki}](https://github.com/linkedin/dustjs-helpers/wiki)
- [{linkedin/dustjs-test-tool}](http://linkedin.github.io/dustjs/test/test.html?q=helpers)

***

### Sublime Completions

- to use these completions, just start typing the completion name and hit tab
- for example, type "ds", hit tab and `{#name}{/name}` will be rendered
- you can then tab through the snippet and change values
- type "d", then control+spacebar to view all of the completions


#### `ds|dust-section`
```
    {#section-name}
    {/section-name}
```

#### `db|dust-block`
```
    {+block-name}
    {/block-name}
```

#### `dy|dust-yes-exist`
```
    {?name} {/name}
```

#### `dn|dust-no-exist` 
```
    {^name} {/name}
```

#### `dp|dust-partial`
```
    {>"path/to/partial"/}
```

#### `dpi|dust-partial-inline`
```
    {<inline-partial-name}
    {/inline-partial-name}
```

#### `dpp|dust-partial-params`
```
    {>"path/to/partial" params /}
```

#### `dpd|dust-partial-dynamic`
```
    {>"path/to/partial{dynamic-param}" /}
```

#### `deq|dust-equals`
```
    {@eq value="bar"} {/eq}
```

#### `dne|dust-not-equals`
```
    {@ne key="foo" value="foo"} {/ne}
```

#### `dlt|dust-less-than`
```
    {@lt value=XX} {/lt}
```

#### `dlte|dust-less-than-equals`
```
    {@lte value=XX} {/lte}
```

#### `dgt|dust-greater-than`
```
    {@gt key="XX" value="20" type="number"} {/gt}
```

#### `dgte|dust-greater-than-equals`
```
    {@gte key="XX" value="XX" type="number"} {/gte}
```

#### `dm|dust-math`
```
    {@math key="XX" method="XX" operand="XX" round="true|false"/}
```

#### `dma|dust-math-add`
```
    {@math key="XX" method="add" operand="XX"/}
```

#### `dms|dust-math-subtract`
```
    {@math key="XX" method="subtract" operand="XX"/}
```

#### `dmm|dust-math-multiply`
```
    {@math key="XX" method="multiply" operand="XX"/}
```

#### `dmd|dust-math-divide`
```
    {@math key="XX" method="divide" operand="XX"/}
```

#### `dmr|dust-math-round`
```
    {@math key="XX.5" method="round"/}
```

#### `dmf|dust-math-floor`
```
    {@math key="XX.5" method="floor"/}
```

#### `dmc|dust-math-ceil`
```
    {@math key="XX.5" method="ceil"/}
```

#### `dmabs|dust-math-abs`
```
    {@math key="XX.5" method="ceil"/}
```

#### `dmeq|dust-math-eq-filter`
```
    {@math key="-XX" method="abs"}
      {@eq value=XX}
      {/eq}
    {/math}  
```

#### `dskt|dust-select-with-key-and-type`
```
    {@select key="foo" type="string"}
    {/select}
```

#### `dsmcd|dust-select-multi-condition-with-default`
```
    {@select key="foo"}
      {@eq value="bar"}bar{/eq}
      {@eq value="baz"}baz{/eq}
      {@eq value="biz"}biz{/eq}
      {@default value="default"}default{/default}
    {/select}
```

#### `dsia|dust-select-inside-array`
```
    {#array}
      {@select key=.}
        {@eq value="foo"}foo{/eq}
        {@eq value="bar"}bar{/eq}
        {@default value="default"}default{/default}
      {/select}
    {/array}
```

#### `dsize|dust-size`
```
    {@size key=XX/}
```

#### `ddump|dust-context-dump`
```
    {@contextDump/}
```

#### `dsep|dust-separator`
```
    {@sep} {/sep}
```

#### `dfs|dust-filter-suppress-auto-escape`
```
    {name|s}
```

#### `dfh|dust-filter-force-html-escaping`
```
    {name|h}
```

#### `dfj|dust-filter-force-javascript-escaping`
```
    {name|j}
```

#### `dfu|dust-filter-native-encodeURI`
```
    {name|u}
```

#### `dfuc|dust-filter-native-encodeURIComponent`
```
    {name|uc}
```

#### `dfjs|dust-filter-stringify-json`
```
    {name|js}
```

#### `dfjp|dust-filter-parse-json`
```
    {name|jp}
```



###### Additional Credits
DustBuster is a complete rewrite of a previous package by [sntran](https://github.com/sntran) and [gpbl](https://github.com/gpbl).

## License

(The MIT License)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
