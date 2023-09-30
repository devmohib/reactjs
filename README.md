- [Set-Up](#set-up)
- [Documentation](#documentation)
- [Notes](#notes)
- [create-react-app](#create-react-app)
- [Definition](#definition)
- [Components](#components)
- [JSX](#jsx)
- [Props](#props)
- [State](#state)
- [React Router](#react-router)
- [Deployment Guide](#deployment-guide)

## Set-Up

`Downloads`  
VS-Code Editor  
Node-npm

`Chrome Extensions`  
React Dev Tools

`VS Code Extensions`  
Live Server  
Thunder Client  
ES7 React/Redux/GraphQL/React-Native snippets  
Prettier-Code Formatter  
Auto Close Tag  
Auto Rename Tag  
JellyFish Theme

## Documentation

https://react.dev/  
https://legacy.reactjs.org/docs/introducing-jsx.html  
https://devmohib.github.io/reactjs/  

## Notes

`NPM` - Node Package Manager  
`React` - JavaScript Library

### Difference between NPM vs NPX

-NPM is a package manager used to install, delete, and update Javascript packages on your machine.  
-NPX is a package executer, and it is used to execute javascript packages directly, without installing them.

## create-react-app

To create a new react.js project, run in your terminal:

```
npx create-react-app my-app
//or
npx create-react-app . -- for not making another folder for reack.js project
```

To run react.js project, run in your terminal:

```
npm start
//or
npm run start
```

`using dev tools`

inspect>components ----to see all the component which react.js project is using

## Definition

`COMOPNENTS:` Components are independent and reusable bits of code  
`PROPS:` Props are arguments passed into React components  
`STATE:` The state object is where you store property values that belong to the component

hirarchy:  
components > App.js > index.js > index.html

## Components

Class Based Components  
Function Based Components  
(create-react-app uses function based components, it is easy to work with)

(Naming Convention of Components)
-Name of Components always start with `Capital Letter`

## JSX

JSX stands for JavaScript XML. JSX allows us to write HTML in React. JSX makes it easier to write and add HTML in React.

-React prefers camelCase naming convention
-class => className
-for => htmlFor

-In react, if you using JSX, it only returns one tag, more tag give an error
-To use many tag, use `JSX Fragment`,

```
<>
//all tags here
<>
```

-Curly braces {}, let you bring JavaScript logic and variables into your markup
-Babel compiles JSX down to React.createElement() calls.
-React.createElement() performs a few checks to help you write bug-free code

## Props

`Props are Read-Only:`  
Whether you declare a component as a function or a class, it must never modify its own props.

`Typechecking With PropTypes:`

```
Navbar.propTypes = {
 title: PropTypes.string.isRequired,
 about: PropTypes.string
}
```

`Setting Default Props:`

```
Navbar.defaultProps = {
 title: "title-here",
 about: "about-here"
}
```

## State

`state` is a built-in React object that is used to contain data or information about the component. A component's state can change over time; whenever it changes, the component re-renders.

`Hooks` are functions that let you “hook into” React state and lifecycle features from function components. Hooks don't work inside classes — they let you use React without classes.

--The React `useState Hook` allows us to track state in a function component.
--State generally refers to data or properties that need to be tracking in an application.

```
import React, { useState } from "react";
```

```
const [mode, setMode] = useState("light");
setMode("Dark");
```

## React Router

`installation`

```
npm install react-router-dom
or
yarn add react-router-dom
```

`Guides`

For App.js:

```
npm install react-router-dom;
```
```
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
```

```
return (
<Router>
<Routes>
{/_ Define your routes using <Route> _/}
<Route path="/" element={<Home />} />
<Route path="/about" element={<About />} />
{/_ Add more routes as needed _/}
</Routes>
</Router>
);
```

use `exact path` in Route as following:

```
<Route exact path="/" element={<Home />} />
```

For Components:

```
import { Link } from "react-router-dom";
```

```
//Use This
<Link to="/">Home</Link>

//Not That
<a href="/">Home</a>
```

## Deployment Guide
Deploymemt of `create-react-app`  
Docs:  
https://create-react-app.dev/docs/deployment/#github-pages  

`steps`  
`npm run build`: It creates a build directory with a production build of your app.  
```
npm run build
```

`step-1 :` Add `homepage` to package.json  
```
"homepage": "https://myusername.github.io/my-app",
```
`step-2 :` Install `gh-pages` and add deploy to scripts in package.json  
```
npm install --save gh-pages
```
```
  "scripts": {
+   "predeploy": "npm run build",
+   "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
```
`step-3 :` Deploy the site by running `npm run deploy`  
```
npm run deploy
```

## React Commponent Lifecycle
- [Lifecycle Daigram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)

`Mounting` - Birth of your component
`Update` - Growth of componet
`Unmount` - Death of components