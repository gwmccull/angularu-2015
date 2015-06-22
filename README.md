# AngularU 2015

These are my notes for the AngularU 2015 conference.

## Sunday  
- Arrived at hotel at 7:30.
- checked in at hotel, checked in at conference
- parked car - $18-$25?
- got swag bag
- went to dinner at Greek restaurant

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
  - <div [hidden]="isAvailable">asdf</di>
  - <div bind-hidden="isAvailable">
- (event)
  - <div (click)="sort()">
  - <div on-click="sort()">
- [(ng-model)] bind to event & property
  - bindon-property="model"
  - two-way data binding - bind to both the property and the update (event) of the property
- for loop
  - <tr *ng-for="box in boxes">
- Components
  - new way to write directives


  
