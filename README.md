
# URL SHORTENER

This is a simple url shortening app made using node.js, express.js and mongoDB as database. It uses "nano id" for generating short urls and "MongoClient" class for making connections to MongoDB.


# Prerequisites

You need to have Node.js, npm, Express.js, MongoDB installed on your computer.

&nbsp;

# Getting started

Clone this repository to your filesystem.

Open the project folder in your VS code or any other Editor.

Do update ( /install ) all the dependencies mentioned in the package.json file (All of them needed to run this app).
You can do it just by using commnad:
```bash
  npm i "dependency-name".
```

Also Don't forget to check check whether you have Node.js, npm, Express.js, MongoDB installed on your computer or not. If not, Install all of them.
This app uses local MongoDB server.

Here are the MongoDB installation instructions for [linux](https://docs.mongodb.com/manual/administration/install-on-linux/), [macOS](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/) and [Windows](https://docs.mongodb.com/v3.2/tutorial/install-mongodb-on-windows/).

You must be having folder named Node Modules . If not use below commnad:
 ```bash
  npm install
```

Now, make .env file in the root directory of project and add following code to it: 
```bash
  DATABASE=mongodb://localhost:27017
```

Now, you are ready to run this app. Use commnad in the terminal: npm start


&nbsp; &nbsp;

## Brief Guide (Summary of Above)

Clone the project

```bash
  git clone https://link-to-project
```

Go to the project directory

```bash
  cd my-project
```

Make .env file in the root directory of project and add following code to it: 
```bash
  DATABASE=mongodb://localhost:27017
```


Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```
