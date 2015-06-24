# Advanced JavaScript w/ Kyle Simpson  
http://getify.me  
@getify  

- goal is to understand enough that you could read Angular source
- goal is readble code, not necessarily fast

- LABjs is his open source project for loading scripts faster
  - current practice to concatentate files for http1 but http2 will be faster with lots of little files

- grips
  - logicless templates require your controllers to be brittle and you end up with
  - grips is a templating tool

- async
- You don't know JS
  - http://youdontknowjs.com
  - open source or dead tree

- recommended books
  - High Performance JS
  - JavaScript Patterns

# Resources
- MDN
- IdiomaticJS
  - http://github.com/rwldrn/idiomatic.js
- ECMA
  - http://www.ecma-international.org/ecma-262/5.1/
  - this is for ES5 but there's ES6 now
  - moving to a feature by feature release
    - feature is considered released once the spec is set and 2 browser support it
    - get used to transpilers and polyfills

- focus should be on readable and learnable code because the browser is going to read in your code and re-write it and optimize it

# Scope: where to look for things
- what are we looking for?  variables, properties, objects, etc.
- who is looking? JS compiler
  - two passes: compiler & execution
- JS is compiled before run
  - some people disagree with the word `compile` but there is a pass done before the code is run
  - JS's compiler is more sophisticated than any other lang.
    - faster
    - just in time compilation
      - compile functions when it's called
    - hot swapping
      - compiler guesses about the types, but if it is wrong, it must through it out, jit compile it again and hot swap the code back into memory
  - browsers are starting to do run-time type analysis of all possible types
- JS has function scope only (ES6 will have block scope)
- bugs come from people thinking about programming differently than the compiler
  - *try to think more like the compiler*  
`var foo = "bar"`  
- `var foo` has at compilation. `foo = "bar"` happens at runtime
- compiler only handles explicit/formal declarations.  Implicit declarations are handled at runtime
- LHS
  - left hand side
  - target of assignment
- RHS
  - right hand side.  Anything that is not an LHS
  - thing being assigned
- global implicit variable creation is one of bad parts
- strict mode prevents you from doing stupid things that make your program slow
- running a function that hasn't been declared is a reference error because it can't be found

- named functions vs. anonymous
  - named are better for 3 reasons
    - gives a helpful self reference to the function within the function since you can't use `this`  
`var foo = function bar() { bar.... }`  
      - bar is a "trustable" reference to itself but foo is not.  Bar is a readonly variable
    - uses name in the stack trace.  Uglify can leave the name in when it minifies
    - better self-documenting code
    - only reason not to name is if you're lazy and can't come up with a name
- only case of block scope in ES3 and ES5 is the `error` variable in the catch block

- we use lexical scope
- there is also dynamic scope but it's mostly used in bash, one type of Perl and some academic languages
  - the `this` variable for JS is kinda like dynamic scope
- lexical scoping is determined at author-time rather than run time which is better for us
  - lexical scoping is faster
- you can cheat by:
  - using eval()
    - use of eval prevents compile time optimizations because compiler can't tell what scope should be
    - strict mode prevents eval from modifying the lexical scope so it creates a small bubble for the eval to run
  - with keyword  
`with (obj) { a = b + c }`  
    - keeps you from having to write `obj.a` but if `obj.a` doesn't exist, it creates a global called `a`
    - prevents compile time optimizations

# IIFE (Immediately Invoked Functional Expression)
- can make a function a function expression in a lot of ways
`(function() { .... })` or `!function() { .... }` or `+function() { .... }` or `void function() { .... }`
- putting the () after the function expression causes it to be run/invoked
- the good thing about functional expressions is they don't pollute the scope with a named expression
- you can even name the functional expression and it still doesn't pollute the scope because the name is only available in the functional expression
`(function bob() {....})()`

# Block scoping
- ES6 will have block scoping with `let`
- `var` attaches itself to the function no matter where it is in the function
- `let` will attach itself to whatever block it finds itself in
- `let` will help you enforce the stylistic preference that says that a variable is attached to the block it is in
- use `var` for things that should be across scopes
  - use `let` for things that should only be used in one scope
- be careful where you put `let` because it can be tough to tell what block you are in

# Dynamic Scope
- *theoretical discussion only*
- run-time decisions decide the scoping

# Hoisting
- common metaphor but not used in the specs
- think of variable declaration (but not assignment) as being moved to top of block
- functions are also hoisted
- not good to rely on variable hoisting (because things will be undefined)
- function hoisting is useful as a style
  - allows you to write the code that uses a function but declare the function later
- functions are hoisted above variables (metaphorically)
- `var d = function() { ... }` means that d will be hoisted but the assignment to the function will not which some people like
- if you define two functions of the same name, the 2nd one will win.  If you then create a variable of the same name, the variable declaration is ignored
- C header files are a way of manully 
- `let` variables do *not* hoist within their block!
  - if you try to use it before, it is in a "temporal dead zone" and you'll get a reference error
