## DustBuster
##### v1.0.3
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
- for example, you coult type "sect" and hit tab for the dust section to render
- once completion renders, you can then tab through the snippet accordingly
- you can also just hit control+spacebar to access all of the completions

```
    > section
        {#name}
        {/name}

    > block
        {+block}
        {/block}
        
    > exists-yes
        {?name}
        {/name}

    > exists-no
        {^name}
        {/name}

    > partial
        {>"path/to/partial"/} 

    > partial-with-params
        {>"path/to/partial"  params /}

    > partial-dynamic
        {>"path/to/partial{dynamic-param}"/}

    > eq-typed
        {@eq key="foo" value="foo" type="string"}
        {:else}
        {/eq}

    > eq-untyped
        {@eq key="foo" value="foo"}
        {else}
        {/eq}

    > ne-matching-string
        {@ne key="foo" value="foo"}
          not equal
        {/ne}

    > ne-non-matching-string
        {@ne key="foo" value="bar"}
          not equal
        {/ne}

    > ne-non-equal-numbers-case
        {@ne key="3" value="5" type="number"}
          not equal
        {/ne}

    > ne-non-equal-boolean-case
        {@ne key="false" value="true" type="boolean"}
          not equal
        {/ne}

    > lt
        {@lt key="{a}" value="27" type="number"}
        {:else}
        {/lt}

    > lte
        {@lte key="20" value="27" type="number"}
        {:else}
        {/lt}

    > gt
        {@gt key="27" value="20" type="number"}
        {:else}
        {/gt}

    > gte
        {@gte key="27" value="27" type="number"}
        {:else}
        {/gte}

    > math
        {@math key="number" method="mod,add,abs,substract..." operand="number" round="true or false"/}

    > math-floor
        {@math key="27.5" method="floor"/}

    > math-ceil
        {@math key="27.5" method="ceil"/}

    > math-round
        {@math key="27.5" method="round"/}

    > math-abs
        {@math key="27.5" method="abs"/}

    > math-subtract
        {@math key="27" method="subtract" operand="7"/}

    > math-add
        {@math key="27" method="add" operand="7"/}

    > math-multiply
        {@math key="27" method="multiply" operand="7"/}

    > math-divide
        {@math key="27" method="divide" operand="7"/}

    > math-eq-filter
        {@math key="-27" method="abs"}
          {@eq value=27}
            Test is true
          {/eq}
        {/math}   

    > math-greater-than-with-default
        {@math key="27" method="add" operand="100"}
          {@gt value=120}
            Greater than
          {/gt}
          {@default}
            Not greater than
          {/default}
        {/math}

    > math-even-odd-bodies
        {@math key=$idx method="mod" operand=2}
          {@eq value=0}
            even
          {:else}
            odd
          {/eq}
        {/math}

    > math-multiply-and-round
        {@math key="27.5" method="multiply" operand="7" round="true"/}

    > select-block-with-key-and-type
        {@select key="foo" type="string"}
  
        {/select}

    > select-multi-condition-default|dus
        {@select key="foo"}
          {@eq value="bar"}bar{/eq}
          {@eq value="baz"}baz{/eq}
          {@eq value="biz"}biz{/eq}
          {@default value="default"}default{/default}
        {/select}

    > select-inside-array
        {#array}
          {@select key=.}
            {@eq value="foo"}foo{/eq}
            {@eq value="bar"}bar{/eq}
            {@default value="default"}default{/default}
          {/select}
        {/array}

    > size-with-empty-key
        {@size key=""/}

    > size-with-string-key
        {mystring} has {@size key=mystring/} letters

    > context-dump
        {@contextDump/}

    > context-dump-to-console
        {@contextDump to="console"/}

    > context-dump-full-test
        {@contextDump key="full"/}

    > context-dump-function-dump-test
        {#aa param="{p}"}{@contextDump key="full"/}{/aa}

    > sep-partial-in-array
        {#n}{>hello_there name=. count="30"/}{@sep} {/sep}{/n}

    > sep-partial-in-async-iterator
        {#numbers}{#delay}{.}{/delay}{@sep}, {/sep}{/numbers}

    > array
        {#array}
          
        {/array}

    > array-with-index
        {#list}
          {idx}. {.}
        {/list} 

    > array-implicit
        {#array}{.}{~n}{/array}

```

***

#### Existing Dust.js Completions (from previous version)
by Giampaolo Bellavite [gpbl](https://github.com/gpbl)

<table align="center">
    <thead>
        <tr>
            <th>Trigger</th>
            <th>Meaning</th>
            <th>Snippet</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>ds</code></td>
            <td>
                <b>d</b>ust <b>s</b>ection
            </td>
            <td>
                <code>{#section}...{/section}</code>
            </td>
        </tr>
        <tr>
            <td><code>dn</code></td>
            <td>
                <b>d</b>ust <b>n</b>o
            </td>
            <td><code>{^name}...{/name}</code></td>
        </tr>
        <tr>
            <td><code>dy</code></td>
            <td>
                <b>d</b>ust <b>y</b>es
            </td>
            <td><code>{?name}...{/name}</code></td>
        </tr>
        <tr>
            <td><code>dp</code></td>
            <td>
                <b>d</b>ust <b>p</b>artial
            </td>
            <td><code>{>partial}...{/partial}</code></td>
        </tr>
        <tr>
            <td><code>db</code></td>
            <td>
                <b>d</b>ust <b>b</b>lock
            </td>
            <td><code>{>block}...{/block}</code></td>
        </tr>
        <tr>
            <td><code>deq</code></td>
            <td>
                <b>d</b>ust <b>eq</b>uals
            </td>
            <td><code>{@eq}...{:else}...{/eq}</code></td>
        </tr>
        <tr>
            <td><code>dne</code></td>
            <td>
                <b>d</b>ust <b>n</b>ot <b>e</b>quals
            </td>
            <td><code>{@ne}...{:else}...{/ne}</code></td>
        </tr>
        <tr>
            <td><code>dlt</code></td>
            <td>
                <b>d</b>ust <b>l</b>ess <b>t</b>han
            </td>
            <td><code>{@lt}...{:else}...{/lt}</code></td>
        </tr>
        <tr>
            <td><code>dlte</code></td>
            <td>
                <b>d</b>ust <b>l</b>ess <b>t</b>han or <b>e</b>quals
            </td>
            <td><code>{@lte}...{:else}...{/lte}</code></td>
        </tr>
        <tr>
            <td><code>dgt</code></td>
            <td>
                <b>d</b>ust <b>g</b>reater <b>t</b>han
            </td>
            <td><code>{@gt}...{:else}...{/gt}</code></td>
        </tr>
        <tr>
            <td><code>dgte</code></td>
            <td>
                <b>d</b>ust <b>g</b>reater <b>t</b>han or <b>e</b>quals
            </td>
            <td><code>{@gte}...{:else}...{/gte}</code></td>
        </tr>
         <tr>
            <td><code>dmath</code></td>
            <td>
                <b>d</b>ust <b>math</b>
            </td>
            <td><code>{@math key="..." method="..." ...}</code></td>
        </tr>
        <tr>
            <td><code>dsel</code></td>
            <td>
                <b>d</b>ust <b>sel</b>ect
            </td>
            <td><code>{@select}...{/select}</code></td>
        </tr>
    </tbody>
</table>

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

