
# URL SHORTENER

&nbsp;
# Description
This is a simple url shortening app made using node.js, express.js and mongoDB as database. It uses "nano id" for generating short urls and "MongoClient" class for making connections to MongoDB Instance. These are the dependencies that have been used in this project: "body-parser" (to process data sent in an HTTP request body), "dotenv" ( to create environment variables in a . env file), "express", "mongod", "mongodb", "mongoose", "mongosh", "nanoid".

&nbsp;
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

Now, To connect with database, you can do it using MongoDB either with local port or making MongoDB Atlas instance. For this make .env file in the root directory of project and add variable name "DATABASE" and assign MongoDB connection string either local (mongodb://localhost:27017) or Atlas Connection string.
```bash
  DATABASE="Paste your MongoDB connection string here"
```

Now, you are ready to run this app. Use commnad in the terminal:
```bash
  npm run start
```

&nbsp;

## Brief Guide (For Using)

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
Or You can also use your Atlas connection string;


Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```

Navigate to http://localhost:5000

&nbsp;

# Internal Working
# Here are the steps that this URL Shortening app take to give results: 

The first thing we need to do is access the JSON data that was sent from the client in the request body. To do this, we need to use of the body-parser package.

Before we shorten the URL, we validate if the URL that was submitted is valid or not. Client side validation is handled for us in the browser because we’ve set the type of the input to url so the form won’t be submitted if the value doesn’t have a valid URL structure.
To make the application more robust, we validate the URL on the server as well using node module "DNS".

Then we set up environment variables with .env file. we use dotenv module to confiq data from .env file.

To store data, we use MongoDB database. We use MongoClient to connect with MongoDB instance. If the connection is successful, we get a reference to the MongoDB instance client and can select a database using the client.db() method. Note that this method creates the database if it does not already exist.

Here, we are select a reference to the shortener database and storing that reference in app.locals which is an object provided by express. This object allows us to set local variables that persist throughout the life of the application, and can be accessed in other middleware functions (functions that have access to the req or res objects) via req.app.locals.

In the next step is to actually shorten the URL and store it in the database. To create a unique short id for each url, we use the nanoid package.

Before we add any data into the database, We need to reference a collection. We do so using the using the db.collection() method. If the collection does not exist yet, it’s created.

Before we shorten the URL and add it to the database, we need to check if the URL has not been shortened already to prevent duplicate database entries for one URL. We do it using the findOneAndUpdate() method on the collection which allows us to modify a document that already exists in the database collection or create it if it doesn’t exist.

We also use $setOnInsert operator allows us to set the value of the document only if its being inserted. This means that the document will not be modified if it already exists, but if it doesn’t, it will be created with its value set to whatever we set in $setOnInsert.

Hence, the document will have two properties: original_url which is the url to be shortened, and short_id which is a unique 7 character id for that url.

Finally, setting returnOriginal to false ensures that findOneAndUpdate returns the new document if one is upserted, which is what we want in this case.



# Takeaways:
Very UseFul project for learning all node.js, express.js and MongoDB. Good one for refreshing some frontend concepts also.