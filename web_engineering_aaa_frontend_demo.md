# aaa-frontend-demo guideline

### 0. Clone the sample repository

```bash
# clone and change cwd
git clone https://github.com/majodev/aaa-frontend-demo.git
cd aaa-frontend-demo

# checkout the initial (fixed) commit
git checkout fc9e950098e735d8ab547e886b5c54487b114398
git checkout -b <your username, e.g. mranftl>

# install the project dependencies
yarn

# open VSCode (eventually disable "files.autoSave": "afterDelay" in your VSCode config)
code .

# start the dev-server
yarn start

# let's get familiar with the project...
```

All the following sections are bound to specific commits e.g. `fc9e950098e735d8ab547e886b5c54487b114398` related to the [aaa-frontend-demo](https://github.com/majodev/aaa-frontend-demo.git) git repo and are marked accordingly at the beginning of the section (the end result). 

### 1. Add a dependency to handle Routing

> `80aa8d58a5a8ce3babfb7e6091e081b15ad05f8f`

- [react-router-dom npm package](https://www.npmjs.com/package/react-router-dom)
- `yarn add react-router-dom @types/react-router-dom`
- [react-router Quickstart](https://reacttraining.com/react-router/web/guides/quick-start)

### 2. Lifecycle and event handlers

>  `09287ec060c375cc1cc472442e4e93ed6cb16b3c`

#### 2.1 Component Lifecycle

* [Understanding the React Component Lifecycle](http://busypeoples.github.io/post/react-component-lifecycle/)
* [React.Component (facebook)](https://reactjs.org/docs/react-component.html)
* [State and Lifecycle (facebook)](https://reactjs.org/docs/state-and-lifecycle.html)
* `componentDidMount() {}`

#### 2.2 Bound functions (event handlers)

* [Handle events by arrow functions in React app](https://medium.com/@machnicki/handle-events-in-react-with-arrow-functions-ede88184bbb)
* `fetchRemoteTime = async () => {}` !== `async fetchRemoteTime() {}`
  * *An arrow function does not create its own `this;` the `this` value of the enclosing execution context is used.* see [MDN Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

### 3. Material UI: Drawer and AppBar

> `12ea8992dac0bd42499f2fd6213a215bc5564376`

* [mui.Drawer](http://www.material-ui.com/#/components/drawer)
  * undocked
  * Link to outside
* [mui.AppBar](http://www.material-ui.com/#/components/app-bar)
* Your first [styled-component](https://github.com/styled-components/styled-components)

### 4. Stateless Components

> `87b9bb0df15b3b0666468151ef2c41ddaed2f088`

* previous `StyledLink` MenuItem to new Component `MenuItemLink`
* [Functional and Class Components (facebook)](https://reactjs.org/docs/components-and-props.html#functional-and-class-components)
* [Stateless Component](https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc) (no lifecycle methods, no state, no class, just a function receiving props returning a react element)

### 5. Decorators, advanced types, context and `props.children`: i18n

> `05e493e96a5e64c425dc3393c509356ae5e7f275`

* [Context (facebook advanced guide)](https://reactjs.org/docs/context.html)
* [Decorators (TypeScript)](https://www.typescriptlang.org/docs/handbook/decorators.html)
* [Advanced Types](https://www.typescriptlang.org/docs/handbook/advanced-types.html): `Partial` and Union Types
* `@i18n.injectIntl` + `i18n.InjectedIntlProps`
  * [TypeScript strict mode](https://blog.mariusschulz.com/2017/06/09/typescript-2-3-the-strict-compiler-option) `this.props.intl!.formatMessage(...)`
* `FormattedMessage` works because of the set context (`IntlProvider`), similar to how to:
  *  `Link` works because of  `Router` context
  *  `mui.*` works because of `MuiThemeProvider` context
* [Higher-Order Components (facebook advanced guide)](https://reactjs.org/docs/higher-order-components.html) —> `injectIntl`

#### 5.1 Make the `location` context available for i18n

> `ac0f7de42795150e884212472096d254304c5007`

* [Casting with TypeScript](http://acdcjunior.github.io/typescript-cast-object-to-other-type-or-instanceof.html): We can opt out of compile time safetly for i18n key anytime. This might be useful for mapping paths to i18n keys
* [react-router `location`](https://reacttraining.com/react-router/web/api/location) inject via `withRouter` and `Partial<RouteComponentProps<any>>`
* This works with [TypeScript Generics](https://www.typescriptlang.org/docs/handbook/generics.html) under the hood

### 6. Let's have some beers!

* [PUNK API v2](https://punkapi.com/documentation/v2)

#### 6.1 Implement beers remaining counter and a simple list 

> `7471b31689698070ad571790daa5171aad48a6c4`

> Attention: Only `3600` requests per hour `~1 req/sec` are allowed
>
> Special header: `x-ratelimit-remaining` —>`remainingRequests` state

* [json2ts](http://json2ts.com/) to get the `IBeer` and child [TypeScript interfaces](https://www.typescriptlang.org/docs/handbook/interfaces.html).
* Install [lodash](https://lodash.com/docs) `yarn add lodash @types/lodash` (map over a)
* Let's use [mui.List](http://www.material-ui.com/#/components/list) to show `name`, `tagline` and `description` of a `Beer`
  * [Promise](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Promise)
  * [Async Await](https://basarat.gitbooks.io/typescript/docs/async-await.html)

#### 6.2 Implement a beer detail route

> `50d740862a6096ca79f04f00e4cdadc80c364847`

* We want a new unrelated route and use [react-router url parameters](https://reacttraining.com/react-router/web/example/url-params)
* `RouteComponentProps`

### 7. State Management

First discuss some background on application state (`setState` vs Flux vs Redux vs MobX)...

#### 7.1 Refactor `BeersRoute` to observe state change from a global store

> `17b0ecf9590007716b0a1e6bd059c7f126401b4e`

Let's share beer information between the 2 routes —> Application-Wide *singleton* store for our beers

* [mobx](https://github.com/mobxjs/mobx) — `yarn add mobx mobx-react`
* [`@observable`](https://mobx.js.org/refguide/observable-decorator.html)
* [`@action`](https://mobx.js.org/refguide/action.html)
* [`@observer`](https://github.com/mobxjs/mobx-react#observercomponentclass)

#### 7.2 Access raw beer information in beerDetailRoute

> `01a86ce7d15ebe89b3b7dd1f829ed7d8ee916293`

* Reuse already fetched beer if possible
* `selectBeer(id: number)`

[ES6 / TypeScript Spread Operator](https://basarat.gitbooks.io/typescript/docs/spread-operator.html)

#### 7.3 Bugs and features...

So you've shown your current prototype your project owner come back with a list of **bugs and new features:**

* (7.3.1, *code smell*): Remove duplicated code (duplicate `loading` flags, fetch handling)
* (7.3.1, *bug*): Go from single beer site to beer list should actually work
* (7.3.1, *bug*): Beer should not be visible if we revisit the site (while loading a new single beer)
* (7.3.1, *feature*): Sort beer list alphabetically
* (7.3.2, *feature*): Single Beer or beers list were already loaded? Use that!. However still only load the single beer if on the detail page!
* (7.3.2, *feature*): Single shared loading information if the store is currently fetching something from any endpoint.
* (7.3.2, *feature*): Counter how many requests were currently successfully made by the store
* (7.3.3 *feature*): Error handling: Alert on fetch errors (`mui.SnackBar`): e.g. id was not found, id is not a number or on request errors
* (7.3.3 *feature*): The beer detail page should use the same header as the beer list page.

##### 7.3.1 Remove code smell, `deselectBeer` and sort

> `d049151912ca31915cbcbe7cd6c7f759f2d86948`

* Start by defining a single `getBeersApi(id?: number): Promise<IBeer[]>` fn
* All requests pipe through `unionAndSortBeers(newBeers: IBeer[]):IBeer[]`
* [`_.sortBy`](https://lodash.com/docs/4.17.4#sortBy)
* [`_.unionWith`](https://lodash.com/docs/4.17.4#unionWith)

##### 7.3.2 `@computed`  and `ObservableMap` 

> `ca9ebb5d651ed2edd46f3b55aeab390749beb2d5`

* Track by dynamically populated `uriMap`
* [`ObservableMap`](https://mobx.js.org/refguide/map.html)
* [`@computed`](https://mobx.js.org/refguide/computed-decorator.html)
* [`_.reduce`](https://lodash.com/docs/4.17.4#reduce)

##### 7.3.3 Same title bar on both beer related pages and error alerts

> `c5ae2408da3b06d516c42782ccac98229242f103`

* We need to have an Alert like functionality if something is not right.
  * `try/catch` handle this in our state store but allow to dismiss it
* Furthermore we need to further split our components to show this alert (and the title heading) on both routes —> Child Routes 
  * `Route` can appear anywhere in your component, but not as direct a
* [`mui.Snackbar`](http://www.material-ui.com/#/components/snackbar)

### 8. Beer detail page

> `21e849d7b4093be41043536fbe1b61594c91f19a`

Lets style the beer detail!

* [`mui.Card`](http://www.material-ui.com/#/components/card)
* [`mui.Chip`](http://www.material-ui.com/#/components/chip)
* [`mui.FloatingButton`](http://www.material-ui.com/#/components/floating-action-button)
* [Material Icons](https://material.io/icons/) - `navigation/chevron-left/right`
* [React `style`](https://reactjs.org/docs/dom-elements.html#style)

### 9. Persist state client side and flexbox alignments

> `13da51ba24cfab374bd168c0ae109281c0861cc8`

* [mobx-persist](https://github.com/pinqy520/mobx-persist)
* [localforage](https://github.com/localForage/localForage)
* [flexbox alignment](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

### 10. *Like* (& *unlike*) beers

> `80c7ff8dc8b6ad24425acefe035b16b98e8815ab`

* Use a combination of `@observable`, `@computed`.
  * [`_.filter`](https://lodash.com/docs/4.17.4#filter) and `_.includes`
* Icon: `action/thumb-up`
* `mui.CardActions` inside `mui.Card`
* Icon Example of [`mui.RaisedButton`](http://www.material-ui.com/#/components/raised-button) (Icon only, 2 states!)
* `ListIcon` use `rightIcon`

#### 10.1 Show liked beers in sidebar and add a counter

> `f00f4859cf90c65c7b72d638d0dfe5ecc0addf41`

* [ES6 …spread](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/Spread_operator)
* [React JSX spread](https://reactjs.org/docs/jsx-in-depth.html#spread-attributes)
* inline conditionals

#### 10.2 `autorun` and caching (+ fix unlike bug)

> `740b3541424f89bbc1d0b32aa84dcd098d358afe`

* In preparation for server side loading: what if we have multiple liked beers in our store, but no information on them yet
* [autorun](https://mobx.js.org/refguide/autorun.html): *Autoruns are about initiating effects, not about producing new values.*
* [`_.remove`](https://lodash.com/docs/4.17.4#remove) fix.

#### 10.3 *(optional)* wipe dialog

> `7ace09826fdd5df835fae608cb1d4c487efbfeca`

* View state vs. global state
* [`mui.Dialog`](http://www.material-ui.com/#/components/dialog) for `beerState.wipe()`

### 11. Forms: Comment your beer

* TextInput and Submit-Button
  - Submit Button should only be enabled if the form was changed since the last submit
* Comment validations (feedback must be shown to the user):
  * Should not start or end with a space
  * Should have max length of 35 characters
  * Should not have multiple spaces
  * An empty comment is allowed and will trigger a delete of the comment

#### 11.1 `BeerCommentForm`

> `6e275cdf9f97e85f6c84f2f7b6daf9e0ff9d9f09`

- Let's allow to add a simple multiline comment for a beer and finally submit that value to the store
- [Uncontrolled Components](https://reactjs.org/docs/uncontrolled-components.html) vs [Controlled Components](https://reactjs.org/docs/forms.html#controlled-components)
- [`mui.TextField`](http://www.material-ui.com/#/components/text-field) — see *Controlled Example*
- `(e: React.ChangeEvent<{ value: string }>) => {...}`

#### 11.2 Connect to state

> `d642364f086ff3873eb44b1712eea75bfa74c285`

* Another map in our state.

### 12. Login: *Guest* access token

> `bf055ea3214782f00dbffa179eae6c1e3f953e08`

* Env update (restart `yarn start`)
* Add a `authState` store
* Integrate with [`POST /api/v1/auth/token`](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/documentation#!/api%2Fv1%2Fauth/postApiV1AuthToken) and [`GET /api/v1/auth/profile`](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/documentation#!/api%2Fv1%2Fauth/getApiV1AuthProfile) (`admin/demo`)
* Special `guest` grantType issues Bearer `accessTokens` that will never expire.

### 13. Save likes and comments on the server

> `bc68b97edc15ff6d3fe63888cf467634d8849942`

*  [`PATCH /app/v1/user/profile `](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/documentation#!/app%2Fv1%2Fuser/patchAppV1UserProfile) allows to set save any `JSON ` `data`  on the user profile
  * your likes / comments count
*  Push local changes to the server if we are authenticated...
*  We won't get it again (no synchronization will take place, local state will always overwrite user server state)
  * Could be easily done while rehydration, same as getting the user profile (testing the connection) in the `authState`

### 14. Show global liked count and other user comments

> `bcf43a9e0e077ad4c1657ad141587675105ea7a6`

* [`GET /app/v1/beers-info`](https://aaa-backend-demo-dev-public.allaboutapps.at/demo/documentation#!/app%2Fv1%2Fbeers-info/getAppV1Beersinfo) allows to retrieve all updated likes and comments from all beers
  * Public endpoint, try it out.

```javascript
type IBeersInfo = {
    globalLikes: { [id: string]: number },
    globalComments: { [id: string]: { user: string, comment: string }[] }
};
```





