## DustBuster
##### v1.1.0
by Mike Delucchi | [zanuka](https://github.com/zanuka)

***
DustBuster is an enhanced syntax definition for .dust files that includes sublime completions of dustjs-helper snippets. More info on currently supported helpers can be found at the links below.

- [{linkedin/dustjs-helpers}](https://github.com/linkedin/dustjs-helpers)
- [{linkedin/dustjs-helpers/wiki}](https://github.com/linkedin/dustjs-helpers/wiki)
- [{dust/helper/test/tool}](http://linkedin.github.io/dustjs/test/test.html?q=helpers)

### Primary Features
- syntax definition for .dust files
- sublime completions for supported dustjs-helpers

### Prerequisites
- [Sublime Text 2](http://www.sublimetext.com/2) or [Sublime Text 3](http://www.sublimetext.com/3)
- [Package Control](https://packagecontrol.io/)


### Installing the package
- via Package Control (search for DustBuster)

### Activating the Dust syntax definition for all .dust files
-  open any .dust file and then select View > Syntax > Dust

***

### New Dust Completions

- to use these completions, just start typing the completion name and hit tab
- for example, you could type "sect" and hit tab for the dust section to render
- once completion renders, you can then tab through the snippet accordingly
- you can also type "d" and control+spacebar to view all of the completions

```
ds|dust-section
    {#name}
    {/name}

db|dust-block
    {+block}
    {/block}
    
dby|dust-block-yes
    {?name}
    {/name}

dbn|dust-block-no
    {^name}
    {/name}

dp|dust-partial
    {>"path/to/partial"/} 

dpp|dust-partial-with-params
    {>"path/to/partial"  params /}

dpd|dust-partial-dynamic
    {>"path/to/partial{dynamic-param}"/}

deq-typed
    {@eq key="foo" value="foo" type="string"}
    {:else}
    {/eq}

deq-untyped
    {@eq key="foo" value="foo"}
    {else}
    {/eq}

dne-matching-string
    {@ne key="foo" value="foo"}
      not equal
    {/ne}

dne-non-matching-string
    {@ne key="foo" value="bar"}
      not equal
    {/ne}

dne-non-equal-numbers-case
    {@ne key="3" value="5" type="number"}
      not equal
    {/ne}

dne-non-equal-boolean-case
    {@ne key="false" value="true" type="boolean"}
      not equal
    {/ne}

dlt
    {@lt key="{a}" value="27" type="number"}
    {:else}
    {/lt}

dlte
    {@lte key="20" value="27" type="number"}
    {:else}
    {/lt}

dgt
    {@gt key="27" value="20" type="number"}
    {:else}
    {/gt}

dgte
    {@gte key="27" value="27" type="number"}
    {:else}
    {/gte}

dmath
    {@math key="number" method="mod,add,abs,substract..." operand="number" round="true or false"/}

dmath-floor
    {@math key="27.5" method="floor"/}

dmath-ceil
    {@math key="27.5" method="ceil"/}

dmath-round
    {@math key="27.5" method="round"/}

dmath-abs
    {@math key="27.5" method="abs"/}

dmath-subtract
    {@math key="27" method="subtract" operand="7"/}

dmath-add
    {@math key="27" method="add" operand="7"/}

dmath-multiply
    {@math key="27" method="multiply" operand="7"/}

dmath-divide
    {@math key="27" method="divide" operand="7"/}

dmath-eq-filter
    {@math key="-27" method="abs"}
      {@eq value=27}
        Test is true
      {/eq}
    {/math}   

dmath-greater-than-with-default
    {@math key="27" method="add" operand="100"}
      {@gt value=120}
        Greater than
      {/gt}
      {@default}
        Not greater than
      {/default}
    {/math}

dmath-even-odd-bodies
    {@math key=$idx method="mod" operand=2}
      {@eq value=0}
        even
      {:else}
        odd
      {/eq}
    {/math}

dmath-multiply-and-round
    {@math key="27.5" method="multiply" operand="7" round="true"/}

dselect-block-with-key-and-type
    {@select key="foo" type="string"}

    {/select}

dselect-multi-condition-default|dus
    {@select key="foo"}
      {@eq value="bar"}bar{/eq}
      {@eq value="baz"}baz{/eq}
      {@eq value="biz"}biz{/eq}
      {@default value="default"}default{/default}
    {/select}

dselect-inside-array
    {#array}
      {@select key=.}
        {@eq value="foo"}foo{/eq}
        {@eq value="bar"}bar{/eq}
        {@default value="default"}default{/default}
      {/select}
    {/array}

dsize-with-empty-key
    {@size key=""/}

dsize-with-string-key
    {mystring} has {@size key=mystring/} letters

dcontext-dump
    {@contextDump/}

dcontext-dump-to-console
    {@contextDump to="console"/}

dcontext-dump-full-test
    {@contextDump key="full"/}

dcontext-dump-function-dump-test
    {#aa param="{p}"}{@contextDump key="full"/}{/aa}

dsep-partial-in-array
    {#n}{>hello_there name=. count="30"/}{@sep} {/sep}{/n}

dsep-partial-in-async-iterator
    {#numbers}{#delay}{.}{/delay}{@sep}, {/sep}{/numbers}

darray
    {#array}
      
    {/array}

darray-with-index
    {#list}
      {idx}. {.}
    {/list} 

darray-implicit
    {#array}{.}{~n}{/array}

```

***

##### Existing Dust.js Completions (from previous version)
by [gpbl](https://github.com/gpbl)



##### Addition Credits
DustBuster was created as a complete rewrite of a package by [sntran](https://github.com/sntran). If you already had this package installed, SublimeText will auto-update it with current version of DustBuster on next app startup.

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

