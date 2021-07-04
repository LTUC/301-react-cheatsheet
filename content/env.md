# .ENV Cheat Sheet

- `.env` are files that are used to hold variables that we use throughout our whole application.

- It acts as a source of truth for these values, so if you were to update any of that variables values, then you will simply change it in the files.

- It is also used to hide sensitive information such as API keys or application passwords, since `.env` is by default in the `.gitignore` generated file when you create a new repo and choose the `.gitignore` under `Node`.

___

## How to work with .env

- create a `.env` file in the root directory of your application project.

```shell
touch .env
```

- add some variable names a values:

```env
SOME_VAR=SomeValue
API_KEY=yourApiKey
```

- its a standard to use all caps and snake case when it comes to naming the variables.

___

### Working with .env in react

- When working in a react app, you will need to include the prefix `REACT_APP_` to your variable name to make it visible for the react app and use it directly.

```env
REACT_APP_SOME_VAR=SomeValue
REACT_APP_API_KEY=yourKey
```

- To you it in your app or components simple:

```js
const myKey = process.env.REACT_APP_API_KEY
```

___

### Working with .env in Express

- In express is a little different you will need to install a package named [dotenv](https://www.npmjs.com/package/dotenv) to help us access and read our env variable from the `.env` file, otherwise you will get an `undefined` error.

- Here there is no need for prefixes, just create the `.env` file, install and require the `dotenv` package. And you can start using the variable values from the `process.env.`

___

### Best practices

- its always a good practice for developers to create a `.env.sample` or `.env.example` file containing the names of the variables names without their values so they can know what variables they need to use, without having to go through the code to figure that out.

- in express

```env
SOME_VAR=
API_KEY=
```

- or in react

```env
REACT_APP_SOME_VAR=
REACT_APP_API_KEY=
```

___