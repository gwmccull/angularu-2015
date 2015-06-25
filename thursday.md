# ES6 w/ Scott Moss  

## WebPack
- webpack simulates node modules but puts code in the concatenated file

## Modules
- import to bring file into your file
- export to export things from your file
  - `export {data}` exports data with an explict name.  Must be imported with `import {data}` or `import {data as thing}`
  - `export default data` can be imported as `import a from './data'`
  - can export with a comma separated list `export {data1, data2}`
  - can export individaully `export var data1; export var data2`
  - can combine exporting default with explicit

## String interpolation
- use back ticks
- variables `${variable}`

## Arrow Functions
`() => { }`
`num => num * 2` no need for parens.  return is implied cause there's only 1 line
`(num, i) => num * 2` multiple params
`num => { num * 2; return num + 2 }` multiple lines
cannot do named arrow functions according to spec (but Babel may name it)

## Objects
- objects can use function short cuts like a class
`var obj = { bob(){ .... } }`
- object shortcut properties
`var things = {pet: pet} === {pet}`
- destructing assingments
`var things = {foods: 1}; var {foods} = things;` same as `var foods = things.foods`
`function({req: request, res}) { ... }` same as `function(obj) { var request = obj.req; var res = obj.res; }`
`let [first, second, , fourth] = [1, 2, 3, 4]` same as `let first = [1,2,3,4][0]; let fourth = [1,2,3,4][3]` done by position

## default params
`(number = 2) => { ... }` if number is undefined, set it to 2.  The default can be a function or a literal or another variable in the outer scope


## Math
`number**2` is exponent

## Rest
`(arg, ...others) => { console.log(others); }` others would be an array of other arguments
cannot use defaults on rest param

## Spread
`(args) => { console.log(...args) }` spread args and apply console.log to each item in array
