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

## A Token walks into a SPA w/ Martin Gontovnikas
### currently
1. browser posts to server
2. server creates user session
3. returns a logged in cookie to the browser
4. browser auto sends auth cookie back to server
5. check the session based on the cookie & authenticate the user
6. server responds to browser

- cookies don't play well with CORS
- cookies require stateful servers
  - to store the sessions
- APIs should be stateless
- Cookies don't flow
  - user info might flow from one server to another or amongst a pool of servers but cookies don't work well

### JSON Web Tokens
1. browser posts to server
2. server creates a JWT with a secret
  3. nothing saved on server
4. returns JWT to the browser
5. Browser sends the JWT on the authorization header
6. Server checks the JWT signature using the secret
7. Server sends the response to the client
- JWT protocol was recently defined

https://auth0.com/events/angularu-single-page-app-authentication

## Design + Performance with Steve Souders
- need to bring designers & devs closer together to work on Design & Performance
  - in many cases both want to deliver good experience to users
- designers and devs often work in silos
- some designs are hard to make fast

- how to fix
  - small interdisciplinary teams
    - work together & colocated - product owners, designers, devs, etc.
  - guiding principles
    - example: speed is more important than design embellishment
      - might even set performance goals
  - prototype early
  - measure performance from the start
    - but don't try to prematurely optimize
    - know where the challenge areas are
    - surface the performance metrics for everyone to see and a baseline for what is acceptable
      - widget that shows up on page for devs
    - show what's beaconed (what data is gathered)
      - use bookmarklets
- Metrics
  - don't use window.onload or document.ready
    - doesn't accurately measure performance any more with SPAs and API calls
  - [webpagetest.org](www.webpagetest.org)

- Design paradigms
  - hero images can take a long time to download
    - but JS & CSS can be a bigger problem because they'll block your hero image
  - JS and CSS are big blockers for speed
    - browser will load JS & CSS with higher priority and block rendering thread.  even if they're at the bottom of the page
    - mark them async so that browser knows they can downloaded later
    - browser has to unzip and parse the JS
- solution
  - inline the important styles and async load the unimportant styles
  - sync download the important js and async download the unimportant js
- custom metrics
  - define the most important elements on the page
  - measure when those important elements are rederered to user using User Timing
  - track with RUM and synthetic
  - track image performance (for example, for a hero image) by tracking image.onload and by putting a script tag after the image tag (performance.now()) and then take the max
- takeaways
  - identify what matters most
  - focus on UX performance
  - track most important things for user
http://www.stevesouders.com/talks.php

- can get the hero image in front of user faster by putting it in a img tag and then putting it in front of JS/CSS
- custom fonts can be blockers too
  - may have a fall back font that the app switches to if the font is taking too long
  - you have to decide if it's so important that the user not see unstyled fonts
