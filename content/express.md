# Express Cheat Sheet

- Express is a minimal and flexible Node.js web application framework.
- Express is used to build backend applications (server side web services) such as APIs.
- Web API's are web services that usually are used to send and request information over the internet.

___

## Initialization

- Create in your repo an empty `server.js` file.

```shell
touch server.js
```

- initialize your node app to start installing packages
  - This step will create for your a `package.json` that contains basic info about your app.

```shell
npm init 
```

- or use the -y flag parameter to have all data set to default in your package.json

```shell
npm init -y
```

- install express framework in your node app

```shell
npm install express
```

- Add the express js starter code to test if your app is up and running

```js
const express = require('express') // require the express package
const app = express() // initialize your express app instance
 
// a server endpoint 
app.get('/', // our endpoint name
 function (req, res) { // callback function of what we should do with our request
  res.send('Hello World') // our endpoint function response
})
 
app.listen(3000) // kick start the express server to work
```

___

## Express Used Packages in this course

[express](https://www.npmjs.com/package/express) "Our express Framework"

- install

```shell
npm install express
```

- Usage

```js
const express = require('express') // require the express package
const app = express() // initialize your express app instance
```

___

[cors](https://www.npmjs.com/package/cors) "Used to allow resource sharing between the frontend and the backend"

- install

```shell
npm install cors
```

- Usage

```js
const cors = require('cors');

app.use(cors()) // after you initialize your express app instance
```

___

[dotenv](https://www.npmjs.com/package/dotenv) "A package to help us read our env variables"

- install

```shell
npm install dotenv
```

- usage

```js
require('dotenv').config();
```

___

[superagent](https://www.npmjs.com/package/axios) "A package used to send requests over the internet to other servers or APIs"

- install

```shell
npm install axios
```

- usage

```js
const axios = require('axios'); // require the package

// inside your callback function
axios.get(url).then(response => response.data).catch(error => console.log(error));
```

___
