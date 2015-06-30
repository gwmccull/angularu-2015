## Monday  
### Keynote  
#### Brad Green  
- Benchpress
  - Angular 2 is ~3x faster than Angular 1
  - Angular 2 is ~4x better with memory than A1

#### Igor  
- focusing on making things fast & smooth
- Web workers
  - allows browser to process some things on a separate thread
  - no access to DOM
  - uses ASYNC message passing to communicate with main thread
  - add additional overhead
- Angular 2 will split out the DOM renderer from other parts (dirty checking, etc)
  - the renderer will run on the main thread with other code on web worker
  - much faster and good for mobile
- mobile
  - Ionic and OnsenUI are two mobile solutions
- since the renderer is separated, you can now have alternate renderers for iOS and Android
  - code is JS but renderer is native
- NativeScript is cross platform application for 
  - Angular 2 will work with NativeScript
- React Native 
  - Angular 2 will integrate with React Native
  - mixes Angular with React Native views
- Angular 2
  - ___ Template + Data = ____ View
  - render into canvas or webgl
- Server side
  - faster startup, SEO, Previews (previewing a deep link on FB for example)

#### Brad  
- Languages
  - JS -> ES6 -> Types (Typescript) -> Decorators (Typescript or ES7)
  - all of NG2 has been converted to use new language stack

#### Misko  
- Ng2 is 1-way data binding by default
- you can combine the ng-model data binding and event though for shortcut
  - `[(ng-model)] = "username"`

#### Brad
- Ng 1.5 will be about migration support
- Animate will support timeline animations

#### Q&A
- Angular is building a CLI to help with scaffolding at beginning of project
- Typescript makes refactoring easier
- ng2 works seamlessly with web components
- trying to build in more support to tell you when you forgot something
- Misko - Module loading is built into ES6.  SystemJS handles most different ways of loading.  

### John Papp and Dan Wahlin
#### choosing a direction
- http://jpapa.me/ngstyles
- ng2 styleguide will be out once the code has been out for a while
- ES6 will help yoiu align with ng2
- USE ng1.x with ES6 or Typescript for all new projects

#### Typescript
- interfaces in TypeScript help with defining the contract for a class
- /// to inject type files at top of file
  - you can define all of the type files in one file any where in the project
  - type files are located centerally for libraries so you can download them
    - definitelytyped.org

#### Modules
- use systemjs to load them

#### Angular 2
- [DOM property]
  - `<div [hidden]="isAvailable">asdf</div>`
  - `<div bind-hidden="isAvailable">`
- (event)
  - `<div (click)="sort()">`
  - `<div on-click="sort()">`
- [(ng-model)] bind to event & property
  - bindon-property="model"
  - two-way data binding - bind to both the property and the update (event) of the property
- for loop
  - `<tr *ng-for="box in boxes">`
- Components
  - new way to write directives


### John Lindquist / Egghead.io / Angular 2 speedrun
- [see speedrun on github](http://github.com/johnlindquist/speed-run)

### Scott Moss - ES6 now with Ng1.x
#### Why?
- it'll push things forward
- use Babel (recommended)
- SystemJS (module loader)  & JSPM (package manager)
  - true universal dynamic module loader
  - plugin system
  - JSPM uses SystemJS
- Webpack
  - loads & bundles modules
  - plugin system
    - has stylist plugin
    - easy setup w/ little config

#### Classes for controllers
- remember to bind things to this (if they're being passed in)

#### Modules
- cannot conditionally import things like you can with require
- must be top of file
- cannot use variables for source name

#### Arrow Functions
- be careful because unexpected side effects
  - this is same as "outside"

#### Object property & method shortcuts
- some method shortcuts diverge from spec after compiler.  Watch out!

`function({data}) { data.whatever() }`  get the data property from the object passed in

#### Decorators
- experimental - ES7 draft
- only works with Classes
- must be written above the target

### Doris Chen
#### Edge
- single codebase for all devices that scales fluidly
- evergreen browser


### David East
- [RX library for observables](https://github.com/Reactive-Extensions/RxJS/blob/master/doc/api/core/observable.md)

### Tomomi Imura
#### Shadow DOM
- enables markup to be:
  - modular
  - encapsulated
- only supported by Chrome & Opera (maybe Edge)
  - there's a polyfill for other browsers
- you see the tag you created in the element inspector but below it, you can see a shadow DOM that you can expand and see what's inside the custom element
- Shadow DOM can be styled with CSS pseudo-selector/pseudo-elements

### Yuri Takheyev & HackStack.js: AngularJS Applications Broken APIs Delivered Late
- Hackstack is a method for working with a broken API delivered late
  - set of best practices
  - now there's a library also
- involves server mockup
- `bower install angular-hackstack`
- `https://github.com/rangle/hackstack`
- centralize your services into an api service that knows about the mocked services
- allows you to mock likely problems
  - slow connections
  - server-side errors
  - dropped connections
  - loss of authentication
  - values too short or too long
- can use it to extend an incomplete API to add endpoints that haven't been built yet


### Ward Bell & MEAN stack
#### Node
- run time server or client environment
#### Express
- server framework for Node
- middleware
  - middleware is a function
  - 3 params: request, response, & do-next
#### MongoDB
- collection ~ Table
- document ~ row
- nested-documents = "view"
- no joins = fast but requires thought on what to store.  Have to go back to the db for extra info if you need it
- no transactions = scalable but info might not make it....


### Douglas Crockford & Upgrading the Web
#### Web Security
- no one is addressing security issues
- passwords
  - created once we had remote disks & timeshares
  - both for data access and billing of processor time
  - can't remember very many passwords so bad practices develop
- what's wrong with the web?
  - insecure - most insecurity arrives from the complexity
  - complex
  - web standards only adds new stuff, doesn't remove bugs that are already in it and can't reduce complexity
- HTTP
  - key : value pairs
  - Negotiation - server/browser need to agree on formats of communication
  - request/response protocol
- DNS
  - convenience so you don't have to type ip addresses
  - not compatible with the Trademark system
  - not trustworthy
- SSL
  - too complicated & doesn't work well
  - relies on Certificate Authorities
    - can't trust certificate authorities because they just give certificates to people that give them money
    - many have been hacked
- HTML
  - terrible for many things (technical documents, SPAs, pretty much everything)
  - inspires use of templates which Crockford hates
    - templates allow injection attacks
  - causes people to be stuck on HTML
- DOM
  - "worst api ever created"
  - horrendously insecure, slow, etc
- CSS
  - 'crappy style sheets'
- JavaScript
  - 'hot mess'
  - "there's a good language inside ECMAScript"
  - get ride of everything else but keep JavaScript
- many companies (MS, Adobe, Apple, etc) have tried creating a close-sourced option that is better than web stack
  - but no transition
- Upgrade the web
  - keep the things it does well & throw out the bad
- Modeled after HDTV
  - originally there was NTSC but we decided to switch to digital
  - cutoff date with the Super Bowl right after that so it'd better work!
  - gov't gave out set top boxes to help the transition
- Helper App (analog to set top boxes)
  - plugin for browser that opens an application to display a file that browser can't handle
- Transition plan
  - convince one progressive browser to integrate the helper app
  - convince one secure site to require its customers to use that browser
  - Risk mitigation will compel the other sites to require that browser
  - other browsers will then have to follow
  - then the world will have to follow
  - Nothing breaks!
- no HTTP
  - Secure JSON over TCP
- everything will be strong crypto.  Only one password to remember and then they know it's you
- url will be
  - web : publickey @ ipaddress / capability
  - web is the standard (like http)
  - publickey is 105 digit ECC public key
  - ipaddress is the ip address of server
  - capability is an identifier supplied by the company
- cooperation under mutual suspicion
- everything is kept in a 'vat' (like a sandbox)
- system has two parts
  - JS Message Server (Node)
  - Qt - front end framework
  - Message server can use filer and network
  - Qt can access the display
  - separated concerns
- keep doing what you're doing for now....
  - this may be coming some day....
