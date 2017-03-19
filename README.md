# Neutrino React Boilerplate

### But neutrino is about making it so simple that you don't need a boilerplate. Why?!?
Because it's still easier to just clone this repo and go.

Neutrino is easy and it's a welcome relief to babel and webpack configs. And the documentation gets you a basic app fast. But inevitably you will have to do simple or advanced customizations and it's nice to have a reference implementation on top of the documentation.

I've created 3 repos to serve as these reference implementations. All 3 are a work in progress but they should get your up and running with Neutrino.js version 4 (version 5 isn't officially released yet).

#### [1. neutrino-react-reference](https://github.com/jefffriesen/neutrino-react-reference)
Simple React app. Uses Mobx as a state container mainly just to show use of decorators.
  * [Class properties](https://github.com/jefffriesen/neutrino-preset-class-properties)
  * [Decorators](https://github.com/jefffriesen/neutrino-preset-decorators)
  * [Typechecking with tcomb](https://github.com/gcanti/babel-plugin-tcomb) (It's Flow compatible but there are some advantages over Flow)
  * Linting
  * Jest with tests colocated with feature components


#### [2. neutrino-electron-reference](https://github.com/jefffriesen/neutrino-electron-reference)
Same app as above but uses Electron for publishing into a distributable app on Mac, Windows and Linux.

#### [3. neutrino-react-boilerplate](https://github.com/jefffriesen/neutrino-react-boilerplate)
Same functionality as the reference app but a few more opinionated decisions. Uses Mobx but it's easy to replace with Redux or whatever else you prefer.
  * [Mobx](https://mobx.js.org) with colocated stores
  * [Bootstrap](http://getbootstrap.com)
  * [React-Bootstrap](https://react-bootstrap.github.io)
  * [React Router 4](https://reacttraining.com/react-router/web/guides/quick-start)
  * [Scaffolding generator (Plop)](https://plopjs.com) to easily create feature-first components
  * [Remotedev](https://github.com/zalmoxisus/mobx-remotedev) Remote debugging for Mobx with [Redux Devtools extension](https://github.com/zalmoxisus/redux-devtools-extension)

#### TODO:
* Wait until neutrino v5 lands and then update these dependencies with neutrino-react-reference as the upstream.
* Clean up function generators
* Add current route to store (Link to mwestrate's blog post)
* Add 404 route
* Add active link


#### To Document
* tcomb & Flowtypes use
* Plop generators
* mobx remotedev
* How to use lint and prettier together
* Feature-first architecture: https://medium.com/front-end-hacking/the-secret-to-organization-in-functional-programming-913484e85fc9#.4zpdahe2f

## Writing Tests
You can create app features in their own directory. Normally for neutrino.js, Jest will only look in the test/ folder. Because of an override in neutrino-custom.js, Jest will look for and run any test file as long as it follows one of these naming patterns:
* *.test.js
* *_.test.js
* *.spec.js
* *_spec.js
* .jsx


## Scaffolding Generator (Plop)
Quickly build a feature component but running `yarn gen` or `npm run gen`. For example, you want a Navbar component:
```
yarn gen  // follow instructions. You will be able to create a React function, class and optionally hook it up to a store.
```
This scaffolds out:
```
-src
  -navbar
    - index.js        // serves as an export
    - navbar.css      // CSS Module for the React component
    - navbar.jsx      // React component
    - navbar.test.jsx // Test scaffold with a 'will it render' sanity check
```

dependencies: `plop`, `inquirer-directory`
