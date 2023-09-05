# The Factor Language Blog Mirror

This site is intended to archive the Blogger post of Slava Pestov.
It contains many early ideas, technical details, and designs that 
went into the Factor Programming Language. In order to guard 
against Google obsolescing Blogger, this mirror was created.

<a href="https://capitalex.codeberg.page/factor-language-blog/@pages/">&gt; Enter mirror of factor-language.blogspot.com &lt;</a></p>

## What is Factor?
Factor is a concatenative, stack-based programming language. It includes
high-level features such as dynamic types, extensible syntax, macros, 
and garbage collection. It has a feature rich library and is fully 
compiled with support for x86-64 Windows, Linux, and MacOS.

Learn more at <a href="https://factorcode.org">factorcode.org</a>.

### An Example of Factor:
```factor
USING: combinators io kernel math.order math.parser random
ranges ;
IN: simple-guessing-game

: intro ( -- )
    "I'm thinking of a number between 1 and 100" print ;

: pick-number ( -- n )
    100 [1..b] random ;

: read-number ( -- n )
    "Enter a guess: " write readln dec> ;

: guessing-game ( n -- )
    dup read-number <=> {
        { +lt+ [ "Too high!" print t ] }
        { +gt+ [ "Too low!"  print t ] }
        [ drop   "You won!"  print f ]
    } case [ guessing-game ] [ drop ] if ;

MAIN: [
    intro
    pick-number
    guessing-game
]  
```



## Relivatne Links
- <a href="https://factorcode.org/">Factor's main website</a>
- <a href="https://www.youtube.com/watch?v=OLh61q4c4XE">SVFIG Talk about Factor</a>
- <a href="https://rosettacode.org/wiki/Factor">Factor on Rosetta Code</a>
- <a href="https://concatenative.org/wiki/view/Front%20Page">The Concatenative Wiki</a>
