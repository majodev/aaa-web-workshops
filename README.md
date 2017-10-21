# Web Engineering

>  Useful resources to understand the big picture of the Web Team at allaboutapps

## Introduction

* [Roadmap to becoming a web developer in 2017](https://github.com/kamranahmedse/developer-roadmap)
* [JavaScript's evolution to a first-class language](http://weared4.com/blog/javascript-firstclass-language/)
  * [Module Systems](https://auth0.com/blog/javascript-module-systems-showdown/)
    * ~2009 [CommonJS](https://en.wikipedia.org/wiki/CommonJS) —> Node.js
    * ~2013 [AMD / RequireJS](http://requirejs.org/docs/whyamd.html) —> Browsers
    * ~2015 [ES6 Modules](http://2ality.com/2014/09/es6-modules-final.html) —> Both (without a transpiler)
  * [ECMAScript 6 / ES6](https://github.com/lukehoban/es6features)
  * [JavaScript Style Guide](https://github.com/airbnb/javascript)
  * [TypeScript Handbook](https://www.typescriptlang.org/docs/home.html)
* [Node.js](https://nodejs.org/en/)
  * [Why use Node.js – A look behind the scenes of web development](https://thinkmobiles.com/blog/why-use-nodejs/)
  * CLI tools
  * Application Servers
  * Build Pipeline, e.g. [webpack](https://webpack.js.org/concepts/)
  * ...
  * How JavaScript works?: Inside [V8](https://de.wikipedia.org/wiki/V8_(JavaScript-Implementierung)) 
    * [Part1](https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf), [Part2](https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e), [Part3](https://blog.sessionstack.com/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec), [Part4](https://blog.sessionstack.com/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5)
* **How we work** (internal aaa confluence pdf)
  * Stack Summary (internal aaa confluence pdf)
  * Onboarding (internal aaa confluence pdf)
* Frontend
  * …jQuery vs React?
    * [jQuery vs React Market Analysis](https://www.similartech.com/compare/jquery-vs-react-js)
    * *Wow, more code, this can’t be better* 
    * [jQuery versus React.js thinking](http://blog.zigomir.com/react.js/jquery/2015/01/11/jquery-versus-react-thinking.html)
  * React vs others
    - [React vs Angular vs Vue.js](https://vuejs.org/v2/guide/comparison.html)
      - Our argument: Domain specific language
    - [Angular 2 versus React: There Will Be Blood](https://medium.freecodecamp.org/angular-2-versus-react-there-will-be-blood-66595faafd51)
  * [Thinking in React (Facebook)](https://reactjs.org/docs/thinking-in-react.html) — Component based architecture
    * *Step 1: Break The UI Into A Component Hierarchy*
    * [Is Model-View-Controller dead on the front end?](https://medium.freecodecamp.org/is-mvc-dead-for-the-frontend-35b4d1fe39ec)
    * JSX
      * [Introducing JSX (Facebook)](https://reactjs.org/docs/introducing-jsx.html)
      * [JSX Looks Like An Abomination - But it’s Good for You](https://medium.com/javascript-scene/jsx-looks-like-an-abomination-1c1ec351a918)
* Backend
  * **Sorry! currently closed source** (licensing is possible)
  * overview monorepo / central internal npm package management
  * demo project —> aaa-backend-demo-dev-public.allaboutapps.at
    * [Open API / Swagger](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/documentation) 
    * [GraphiQL](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/graphiql)
    * [GraphQL-voyager](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/graphql-voyager)
    * (non public) [devtools](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/dev-tools), [pghero](https://github.com/ankane/pghero), 

## Sample frontend project

See 

## Complementary ressources

### React: State management

- ##### [How to handle state in React. The missing FAQ.](https://medium.com/react-ecosystem/how-to-handle-state-in-react-6f2d3cd73a0c)

  - *you might not need them at all, or at least yet*

- Let's talk about immutability...

  - [Pros and Cons of using immutability with React.js](http://reactkungfu.com/2015/08/pros-and-cons-of-using-immutability-with-react-js/)
  - [Handling State in React: Four Immutable Approaches to Consider](https://medium.freecodecamp.org/handling-state-in-react-four-immutable-approaches-to-consider-d1f5c00249d5)

- Flux architecture - Redux / MobX / Relay implementations

  - [Flux Comic](https://code-cartoons.com/a-cartoon-guide-to-flux-6157355ab207#.2r4n9l7va)
  - [Redux Comic](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6#.9dt6uvha1)
  - [Relay Comic](https://code-cartoons.com/a-cartoon-intro-to-facebook-s-relay-part-1-3ec1a127bca5#.fp2nu29vi)
  - [MobX](https://mobx.js.org/getting-started.html)
    - [3 Reasons why I stopped using React.setState](https://blog.cloudboost.io/3-reasons-why-i-stopped-using-react-setstate-ab73fc67a42e)
  - [Flux, Redux, Relay Video Summary](https://www.youtube.com/watch?v=WIqbzHdEPVM&index=2&list=PLb0IAmt7-GS0M8Q95RIc2lOM6nc77q1IY#t=298.66545)
  - Representing GraphQL server-state, Component-Data-Requirements? [apollo-client](http://dev.apollodata.com/react/) (This is actually uses a Redux store)
    - *Apollo Client manages server-side GraphQL data in your React app so you don't have to.*

### Other interesting articles / projects

* [My starred GitHub projects](https://github.com/majodev?tab=stars)
* [Modern JavaScript Cheatsheet](https://github.com/mbeaudru/modern-js-cheatsheet): Cheatsheet for the JavaScript knowledge you will frequently encounter in modern projects.
* [The Ultimate Question of Programming, Refactoring, and Everything (Intel)](https://software.intel.com/en-us/articles/the-ultimate-question-of-programming-refactoring-and-everything)
* [react-native](https://facebook.github.io/react-native/) - Learn once, write anywhere: Build mobile apps with React
* [Gatsby](https://www.gatsbyjs.org/) - Blazing-fast static site generator for React
* [every-programmer-should-know](https://github.com/mr-mig/every-programmer-should-know) - A collection of (mostly) technical things every software developer should know
* [lerna](https://github.com/lerna/lerna) - A tool for managing JavaScript projects with multiple packages.
* [npmrc](https://github.com/deoxxa/npmrc) - Switch between different .npmrc files with ease and grace. (for private npm repos)
* [intro-to-react](https://github.com/ericvicenti/intro-to-react) - (plain JavaScript ES6) A Hands-On Walkthrough of your first React Web App
* [system-design-primer](https://github.com/donnemartin/system-design-primer) - Learn how to design large-scale systems. Prep for the system design interview.
* [developer-roadmap](https://github.com/kamranahmedse/developer-roadmap) - Roadmap to becoming a web developer in 2017
* [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript) - Clean Code concepts adapted for JavaScript
* [ECMAScript 6 Learning](https://github.com/ericdouglas/ES6-Learning) - List of resources to learn ECMAScript 6!
* Older Articles:
  * [9 things every React.js beginner should know](https://camjackson.net/post/9-things-every-reactjs-beginner-should-know) - (attention old)
  * [React.js Introduction For People Who Know Just Enough jQuery To Get By](React.js Introduction For People Who Know Just Enough jQuery To Get By)

#### Useful react related libs (components / frontend libs / eyecandy / universal)

* [nivo](https://github.com/plouc/nivo): provides a rich set of dataviz components, built on top of the awesome d3 and Reactjs libraries
* [vw](https://github.com/hshoff/vx): react + d3 = vx | visualization components
* [react-springy-parallax](https://github.com/drcmda/react-springy-parallax): springy, composable parallax-scroller for React
* [formik](https://github.com/jaredpalmer/formik) (formsy alternative): Build forms in React, without the tears
* [react-trend](https://unsplash.github.io/react-trend/) - Simple, elegant spark lines
* [react-loadable](https://github.com/thejameskyle/react-loadable) - A higher order component for loading components with promises.
* [react-sortable-tree](https://github.com/fritz-c/react-sortable-tree) - Drag-and-drop sortable component for nested data and hierarchies
* [react-virtualized](https://github.com/bvaughn/react-virtualized) - React components for efficiently rendering large lists and tabular data
* [animate.css](https://github.com/daneden/animate.css) - A cross-browser library of CSS animations. As easy to use as an easy thing.
* [iTyped](https://github.com/luisvinicius167/ityped) - Dead simple Javascript animated typing, with no dependencies.
* [react-cropper](https://github.com/roadmanfong/react-cropper) - Cropper as React components
* [next.js](https://github.com/zeit/next.js) - Framework for server-rendered React apps

