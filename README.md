# Robogotchi 🤖👽👾

Demo: [Robogotchi](https://trilogy-project-2.herokuapp.com)
## About 📖
Robogotchi is a browser based game where the user creates a cyber pet and must maintain its health status.

<img src= "https://media.giphy.com/media/IeXInprW3rLrnSSz9C/giphy.gif" alt="Robogotchi" width="75%">
<hr>

## How to Use 🤔
1. First users get to choose their Robogotchi. By picking a robot, alien or human and choosing a name a character will be randomly generated for them. 

2. After choosing their 'gotchi they will then be asked to fill out an authentication form with name, email and password. 

3. Once account is created, user will be taken to a page with their health points and option to feed, entertain or exercise their 'gotchi. 

4. Overtime the hunger, boredom and laziness will grow as their health points decrease. When you feed, entertain or exercise your 'gotchi their overall health will increase as their hunger, boredom and laziness goes back down. 

## How it Works 🔨
* The `config` folder holds each of the database objects, one for the deployed app, one for testing and one for JAWSDB which is necessary for the heroku connection. Also contains `middleware` and `passport.js`file which holds the authentication logic.
* Inside of the `models` folder is the `gotchi.js` with the intial table data, and the `index.js` which connects to the database using sequelize. 
* The `schema.sql` holds the timers needed for automatically updating the MYSQL table by incrementing the health of the 'gotchis. 
* The `apiRoutes.js` holds validation logic and connects to the database where the `htmlRoutes.js` sends information from the database to the front end of the application. 
* `public` holds the assets, css, images and the javascript connecting to the html
* The `views` folder has all of handlebars files, which replaces html and displays the information to the user. 
* `server.js` connects the app to the server and the correct port.
The application uses two seperate API's to retrieve data.

## Pre-Requisites ✔️
To power this app locally, you'll need to a install a couple `NPM Packages`. Downloading the following Node packages is crucial for this applications functionality.
* Bcrypt `npm i bcrypt`
* Dotevn `npm i dotenv`
* Express `npm i express`
* Express-Handlebars `npm i express-handlebars`
* Express-Session `npm i express-session`
* Express-Validation `npm i express-validation`
* MySQL2 `npm i mysql2`
* Passport `npm i passport`
* Passport-Local `npm i passport-local`
* Path `npm i path`
* Sequelize `npm i sequelize`

-- or(preferably) --

* Shorthand `npm i` (short-hand)

## Getting Started Locally🏁
These instructions will get you a copy of the project up and running on your local machine for grading and testing purposes. 
1. Clone repository. Click on the clone button next to the repository (clone with SSH). 
2. Open Terminal and git clone (paste) into directory of your choice. 
3. Open folder in VS Code. 
4. Install all neccessary npm packages by opening your terminal, navigating to the directory, and typing `npm i`.
5. Type `node server.js` to run the application.
6. Navigate to the chosen port in your browser and ENJOY!

## Built With 🔧
* [Express](https://www.npmjs.com/package/express) - Node.js web app framework designed to make developing websites, web apps, & API's much easier.
* [Handlebars](https://handlebarsjs.com/) - Handlebars allows you to separate the generation of HTML from the rest of your JavaScript and write cleaner code.
* [Heroku](https://www.heroku.com/) - A cloud based platform that lets companies build, deliver, monitor and scale applications.
* [Javascript](https://www.javascript.com/) - JavaScript is the programming language of HTML and the Web
* [JSON](https://www.json.org/) - Javascript object notation, syntax for storing and exchanging information. 
* [MVC](https://www.geeksforgeeks.org/mvc-design-pattern/) - The Model-View-Controller is an architectural pattern that separates an application into three main logical components: the model, the view, and the controller.
* [MySQL](https://www.mysql.com/) - Open source relational database management system (RDBMS) based on Structured Query Language (SQL)
* [Node](https://nodejs.org/en/download/) - As an asynchronous event driven JavaScript runtime, Node is designed to build scalable network applications. 
* [PassportJs](http://www.passportjs.org/) - Authentication middleware for NodeJS. 
* [Sequelize](https://sequelize.readthedocs.io/en/v3/) - Connects objects with relational database systems. 

## Creators ✋
*** Amanda Dovel *** - [amandadovel](https://github.com/amandadovel)
<br>

*** Andy Hardy *** - [ahardy42](https://github.com/ahardy42)
<br>

*** Joey Kubalak *** - [TreezCode](https://github.com/TreezCode)
<br>

*** Kyle Knox *** - [KyleK86](https://github.com/KyleK86)
<br>

## Acknowledgments 🌟
Free Stock Footage by: <a href="http://www.videezy.com">Videezy</a>
[RoboHash](https://robohash.org)