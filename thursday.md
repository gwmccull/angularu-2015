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
