# Authentication Server

This is a simple authentication server that uses JSON Web Tokens

## Tech Stack

Low-level request handling:

- **HTTP Module** - Handling HTTP requests

Routing, Server logic:

- **Express** Parse response + Routing
- **Morgan** Logging relevant data about the requests
- **BodyParser** Help parse incoming HTTP requests

Database:

- **MongoDB** Storing Data
- **Mongoose** Working with MongoDB

Authentication:

- **Bcrypt-Nodejs** Storing a users password safely
- **Passport-JWT** Authenticating users with a JWT
- **Passport-local** Authenticating users with a username/password
- **Passport JS** Authenticating users

## Instalation

Install the node modules by running `npm install`

start a local or hosted instance of MongoDB and create a config file ass follows

```javascript
// config/database.js
module.exports = {
  db_url: 'mongodb://localhost:auth/auth',
  jwt_secret: 'jljcc8j3rq8fjec8jreijrcle' // this can be anything you want
};
```

## try it out

For you to get familiarized with this basic authentication server you need to run the server using `node index` and then you can test different request using [postman](https://www.getpostman.com/)

### Sign up

To try to sign in go to postman and make a POST request to <http://localhost:3000/signin> using some JSON data like this:

```json
{
    "email": "some@email.com",
    "username": "testuser",
    "password": "securepw"
}
```

(Copy the token you get as response for the next part)

### Sign in

make a POST request to <http://localhost:3000/signin> using a the your username and password as the body and on the header and 'authorization' key with the value copied from the token

### Retrieve a private route

Make a GET request to <http://localhost:3000/> using the 'authorization' key with the value copied from the token

And thats basically it!
