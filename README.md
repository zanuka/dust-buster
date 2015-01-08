## DustBuster
##### v1.0.0
***
DustBuster is an enhanced syntax definition for .dust files that includes sublime completions of dustjs-helper snippets. More info on currently supported helpers can be found at the links below.

- [{linkedin/dustjs-helpers}](https://github.com/linkedin/dustjs-helpers)
- [{linkedin/dustjs-helpers/wiki}](https://github.com/linkedin/dustjs-helpers/wiki)
- [{dust/helper/test/tool}](http://linkedin.github.io/dustjs/test/test.html?q=helpers)

### Primary Features
- syntax definition for .dust files
- sublime completions for supported dustjs-helpers

### Prerequisites
- Desire for optimal workflow
- [Sublime Text 2](http://www.sublimetext.com/2) or [Sublime Text 3](http://www.sublimetext.com/3)
- [Package Control](https://packagecontrol.io/)


### Installing the package
- via Package Control (search for DustBuster)
- clone this repo and then symlink it into your packages folder
    + ST2 (cd ~/Library/Application\\ \\Support/Sublime\\ \\Text \\2/Packages)
    + ST3 (cd ~/Library/Application\\ \\Support/Sublime\\ \\Text\\ \\3/Packages)
    + symlink like so (ln -s path/to/cloned/repo/dust-buster)

***

###### Dust Completions

```
    > section
        {#name}
          
        {/name}

    > exists-yes
        {?name}
          
        {/name}

    > exists-no
        {^name}
          
        {/name}

    > partial
        {>partial params /}

    > block
        {+block/}

    > block-with-default
        {+block}

        {/block}

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

##### Author
Mike Delucchi - [zanuka](https://github.com/zanuka)