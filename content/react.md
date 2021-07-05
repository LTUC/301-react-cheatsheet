# React Cheat Sheet

- React is a JavaScript library for building user interfaces.
- React is used to build single page applications.
- React allows us to create reusable UI components.

___

## Initialization

- install react js boilerplate:
  - replace `_your_app_name_` with the name of your app.

```shell
npx create-react-app _your_app_name_
```

___

- Creating your react app can be done in an existing cloned repo.

- If you didn't have an initialized repo you can do the following:

```shell
cd _your_app_name_
git checkout -b main
git init
git branch -M main
git remote add origin
git push -u origin main
```

- Or Basically , create a repo on github, then clone and create the app inside of it.

___

## React Used Packages in this course

- [React Bootstrap](https://react-bootstrap.netlify.app/getting-started/introduction) "A React package that add the bootstrap css Library as component"

```shell
npm install react-bootstrap bootstrap
```

- To use the bootstrap Library you will nee to import the css library first.
- You will need it in order to start using the styles.

```js
import 'bootstrap/dist/css/bootstrap.min.css';
```

- [Axios](https://www.npmjs.com/package/axios) "Used to send url requests to our backend or and APIs"

```shell
npm install axios
```

```js
import axios from 'axios';
```

- [React Router Dom](https://www.npmjs.com/package/react-router-dom) "Used to add routes to your single page application"

```shell
npm i react-router-dom
```

App.js

```js
import React from 'react';
import {
  BrowserRouter as Router,
  Switch,
  Route
} from "react-router-dom";

class App extends React.Component {

  render() {
    return(
      <>
        <Router>
          <Switch>
            <Route exact path="/"></Route>
          </Switch>
        </Router>
      </>
    )
  }
}

export default App;
```

___

## React Terminologies

### Components

- Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML via a render() function.

- Components come in two types, Class components and Function components, in this tutorial we will concentrate on Class components.

### Props

- Props are arguments passed into React components.
- Props are passed to components via HTML attributes.

### States

- React components has a built-in state object.

- The state object is where you store property values that belongs to the component.

- When the state object changes, the component re-renders.

___

[⇐ GO BACK](../README.md)
