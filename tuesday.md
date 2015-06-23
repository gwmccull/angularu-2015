## Tuesday
### TypeScript
- superset of JS
- Modern Type System
  - type inference
  - gradual/optional typing
  - configurable typing
    - turn off using the `any` type
- four main principles
  1. future ready
  2. flexible development
    1. you can use typing with any sort of lang (es5, es6, etc)
  2. Tooling
  3. Dependency Injection
- will still compile even if TS detects errors
- types only there for dev time; stripped out for run time
- allows tooling to look at types and within classes
- you can specifiy your type of modules so that when you export things types are caught and TypeScript writes some of your boilerplate code

### Server-side rendering
#### Jeff Whelpley
- benefits:
  - can help with the initial page load
  - SEO
  - page previews in social media (or search engines)
- ways to reduce time
  - reduce latency
  - split up files so user only downloads what they need
  - server rendering
    - the initial page is delivered fully rendered while the SPA downloads in the back
    - NG2 is built from ground up to enable server rendering
- how to use:
  1. write client-side NG2 app
    - don't touch the DOM!
  2. install the NG2 server plugin
- user events while the client-side app is downloading in the background...
  - preboot library helps this
    - it records the user interaction and then plays it back once the SPA loads up
#### Patrick Stapleton
- server delivers the page so it shows up immediately
- client side JS is loading in background
- if user tries to do anything, they get a spinner to tell them to wait

### Crazy Fast Prototyping with Lucas Rubelke
