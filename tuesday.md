# Tuesday
## TypeScript
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

## Server-side rendering
### Jeff Whelpley
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
### Patrick Stapleton
- server delivers the page so it shows up immediately
- client side JS is loading in background
- if user tries to do anything, they get a spinner to tell them to wait

## Crazy Fast Prototyping with Lukas Ruebbelke
- how do we know where/how/why users want something?
- know faster with prototyping
  - use intuition but then test so that you "know"
- home team / away team
  - home team works on the app
  - away team will demo the app in public and ask for feedback
  - home team then fixes the app based on the input so that away team can re-test
  - iterations can even happen in the same day
https://github.com/jacobscarter/angular-crazy-fast-prototyping/tree/Phase1
- Ionic is good for fast prototypes
  - CLI helps with getting started

## Firebase w/ Sara Robinson
- real time database
- noSQL data store
- can use it as an API
- intermittent offline
  - data is stored locally and then updated when you re-gain connectivity
  - data is inserted based on time it was recorded (using .push())
- authentication
  - easy to use with popular methods
  - $firebaseAuth allows you to authenticate with client-side code only
- security
  - json model supporting authenticated
- cross-platform (JS, iOS, Android)
- Bindings for popular JS frameworks
  - Angular Fire

## Foundation with Jeanie Chung
- Foundation is a frontend framework for sites, apps (responsive web apps) and soon to be emails
- uses SASS for CSS
- features
  - flexbox-powered grid
  - independently scrolling panels
  - collapsing panels
  - can write front-matter at top of page and have Foundation compile it into the AngularJS for routes, animations, etc
  - Motion UI - transitions and other animations for the apps
  - Modular Components
    - so you can use features from one framework in another (eventually)
    - Off Canvas Menu
    - In App Notifications
  
## Creating D3 components with Angular w/ Aysegul Yonet
- components = controllers + scopes + directives
- D3 is for data visualizations and DOM manipulations
- but they're hard to reuse
- D3 components help this
- watch out for:
  - D3 login should be in a directive
  - use HTML declarative syntax and attributes to feed data to directives
  - store data in controller
  - create NG filters using D3 methods
- directive should have a linking function to link D3 code
- enter/exit is one of the most confusing aspects
  - any time you have new data, you enter and add it
  - any time you have less data, you exit & remove
- D3 has methods for getting data but they don't work with Angular
  - use Angular methods unless they come from CSV (which d3 handles)
- d3 has methods for manipulating data into format that you want
  - you can add attribute to HTML for accessor and then create a function that manipulates the data
### NG2
- typescript
  - typing can help make sure data is in correct format for graphs
  - resources
    - learnxinyminutes
- NG2
  - must bootstrap the entry point to app

## A Token walks into a SPA
