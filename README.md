# Killer Mutant Robogotchis 🤖👽👾

Demo: [Robogotchi](https://trilogy-project-2.herokuapp.com/).
## About 📖
Robogotchi is a browser based game where the user creates a cyber pet and must maintain its health status.

<br>
<img src= "https://imgur.com/CiIIwC5" alt="Robogotchi" width="75%">
<hr>

## How to Use 🤔
1. First users get to choose their Robogotchi. By picking a robot, alien or human and choosing a name a character will be randomly generated for them. 

2. After choosing their 'gotchi they will then be asked to fill out an authentication form with name, email and password. 

3. Once account is created, user will be taken to a page with their health points and option to feed, entertain or exercise their 'gotchi. 

4. Overtime the hunger, boredom and laziness will grow as their health points decrease. When you feed, entertain or exercise your 'gotchi their overall health will increase as their hunger, boredom and laziness goes back down. 

After searching for a band or musician the user is provided with a short biography, images, social media links and even music videos.

 
They can also search by artist or location to find relevant concerts.
<br>
<img src= "https://media.giphy.com/media/lRvnnZpJQSJgsLBb7D/giphy.gif" alt="Concert Search" width="75%">
<hr>
 
The app is available to anyone but only after logging in the user will be able to save favorites to their own personal feed.
<br>
<img src= "https://media.giphy.com/media/S6HhmrC3mfmkzcBVSe/giphy.gif" alt="Favorites Feed" width="75%">
<hr>

## How it Works 🔨
The application uses two seperate API's to retrieve data.
1. TheAudioDB API <br>
*A community Database of audio artwork and data*
```
router.get("/search", (req, res) => {
    const artistName = req.query.artistName.replace(/\s/g, "+");
    let artistData;
    axios.get(`https://www.theaudiodb.com/api/v1/json/${apiKey}/search.php?s=${artistName}`)
        .then(results => results.data.artists.map(result => {
            // === create artist object with original api call data
            let artist = {
                artistId: result.idArtist,
                artistName: result.strArtist,
                label: result.strLabel,
                genre: result.strGenre,
                website: "http://" + result.strWebsite, // concat http:// for link compatability
                facebook: "http://" + result.strFacebook, // concat http:// for link compatability
                twitter: "http://" + result.strTwitter, // concat http:// for link compatability
                biography: result.strBiographyEN,
                country: result.strCountry ,
                artistThumb: result.strArtistThumb ,
                artistLogo: result.strArtistLogo,
                artistFanart: result.strArtistFanart,
                artistFanart2: result.strArtistFanart2,
                artistFanart3: result.strArtistFanart3
            }
            artistData = artist;
            return artistData;
        }))
```

2. SongKick API <br>
*Gives easy access to the biggest live music database in the world*
```
router.get("/search" , (req, res) => {
    const artistName = req.query.artistName.replace(/\s/g, "+");
    axios.get(`https://api.songkick.com/api/3.0/events.json?artist_name=${artistName}&per_page=10&apikey=${apiKey}`)
        .then(results => songkickParse(results))
        .then(mappedResults => res.json(mappedResults))
        .catch(err => res.status(422).json(err));
});
```
## Pre-Requisites ✔️
To power this app locally, you'll need to a install a couple `NPM Packages`. Downloading the following Node packages is crucial for this applications functionality.

* Axios `npm i axios`
* Bcrypt `npm i bcrypt`
* Concurrently `npm i concurrently`
* Connect-Flash `npm i connect-flash`
* Dotevn `npm i dotenv`
* Express `npm i express`
* Express-Session `npm i express-session`
* Express-Validation `npm i express-validation`
* If-Env `npm i if-env` 
* Moment `npm i moment`
* Mongoose `npm i mongoose`
* Nodemon `npm i nodemon`
* Passport `npm i passport`
* Passport-Local `npm i passport-local`
* Path `npm i path`
* React `npm i react`
* React-Dom `npm i react-dom`
* React-Router-Dom `npm i react-router-dom`

--or--

Shorthand `npm i` (short-hand)

## Getting Started Locally🏁
These instructions will get you a copy of the project up and running on your local machine for grading and testing purposes. 

1. Clone repository. Click on the clone button next to the repository (clone with SSH). 
2. Open Terminal and git clone (paste) into directory of your choice. 
3. Open folder in VS Code. 
4. Obtain api keys from theaudiodb and SongKick, then place them in your own .env file.
5. Install all neccessary npm packages by opening your terminal, navigating to the directory, and typing `npm i`.
6. Type `npm start` to run the application.
7. The chosen port should automatically open in your browser and ENJOY!

## Built With 🔧
* [CSS3](https://www.w3schools.com/css/) - CSS is a language that describes the style of an HTML document.
* [Express](https://www.npmjs.com/package/express) - Node.js web app framework designed to make developing websites, web apps, & API's much easier.
* [Heroku](https://www.heroku.com/) - A cloud based platform that lets companies build, deliver, monitor and scale applications.
* [HTML5](https://www.w3schools.com/html/) - HTML is the standard markup language for Web pages.
* [Javascript](https://www.javascript.com/) - JavaScript is the programming language of HTML and the Web
* [JSON](https://www.json.org/) - Javascript object notation, syntax for storing and exchanging information. 
* [MVC](https://www.geeksforgeeks.org/mvc-design-pattern/) - The Model-View-Controller is an architectural pattern that separates an application into three main logical components: the model, the view, and the controller.
* [MySQL](https://www.mysql.com/) - Open source relational database management system (RDBMS) based on Structured Query Language (SQL)
* [Node](https://nodejs.org/en/download/) - As an asynchronous event driven JavaScript runtime, Node is designed to build scalable network applications. 
* [PassportJS](http://www.passportjs.org/) - Authentication middleware for NodeJS. 
* [ReactJS](https://reactjs.org) - A JavaScript library for building user interfaces.
* [Sequelize](https://sequelize.readthedocs.io/en/v3/) - Connects objects with relational database systems.
* [Studio3T](https://studio3t.com) - Studio 3T is the professional GUI and IDE for MongoDB.

## Creators ✋
*** Amanda Dovel *** - [amandadovel](https://github.com/amandadovel)
<br>

*** Joey Kubalak *** - [TreezCode](https://github.com/TreezCode)
<br>

*** Kyle Knox *** - [KyleK86](https://github.com/KyleK86)
<br>

## Acknowledgments 🌟
[SongKick](https://www.songkick.com)

[TheAudioDB](https://www.theaudiodb.com/)





## Functionality 💪
#### Here's how the app works: 


## Getting Started 🏁

These instructions will get you a copy of the project up and running on your local machine for grading and testing purposes. 

1. Clone repository. Click on the clone button next to the repository (clone with SSH). 
2. Open Terminal and git clone (paste) into directory of your choice. 
3. Open folder in VS Code. 
4. The `config` folder holds each of the database objects, one for the deployed app, one for testing and one for JAWSDB which is necessary for the heroku connection. Also contains `middleware` and `passport.js`file which holds the authentication logic.
5. Inside of the `models` folder is the `gotchi.js` with the intial table data, and the `index.js` which connects to the database using sequelize. 
6. The `schema.sql` holds the timers needed for automatically updating the MYSQL table by incrementing the health of the 'gotchis. 
7. The `apiRoutes.js` holds validation logic and connects to the database where the `htmlRoutes.js` sends information from the database to the front end of the application. 
8. `public` holds the assets, css, images and the javascript connecting to the html
9. The `views` folder has all of handlebars files, which replaces html and displays the information to the user. 
10. `server.js` connects the app to the server and the correct port.

## Pre-Requisites ✔️

1. Node - use this site to install node into your computer: https://nodejs.org/en/download/
    *to check if node is installed type node -v into your terminal. If installed it will print the version number on the screen.
2. NPM (https://www.npmjs.com/) - Node Package Manager. Use this site to assist in downloading packages or modules. 

## Built With 🔧

* [Node] (https://nodejs.org/en/download/) - As an asynchronous event driven JavaScript runtime, Node is designed to build scalable network applications. 
* [Javascript] (https://www.javascript.com/) - JavaScript is the programming language of HTML and the Web
* [JSON] (https://www.json.org/) - Javascript object notation, syntax for storing and exchanging information. 
* [Express] (https://www.npmjs.com/package/express) - Node.js web app framework designed to make developing websites, web apps, & API's much easier.
* [MySQL] (https://www.mysql.com/) - Open source relational database management system (RDBMS) based on Structured Query Language (SQL)
* [Sequelize] - (https://sequelize.readthedocs.io/en/v3/) - Connects objects with relational database systems. 
* [Handlebars] (https://handlebarsjs.com/) - Handlebars allows you to separate the generation of HTML from the rest of your JavaScript and write cleaner code.
* [MVC] - (https://www.geeksforgeeks.org/mvc-design-pattern/) - The Model-View-Controller is an architectural pattern that separates an application into three main logical components: the model, the view, and the controller.
* [PassportJs] - (http://www.passportjs.org/) - Authentication middleware for NodeJS. 
* [Heroku] - (https://www.heroku.com/) - A cloud based platform that lets companies build, deliver, monitor and scale applications.
 

## Authors ⌨️

*** Andy Hardy *** - [ahardy42](https://github.com/ahardy42)
<br>
*** Joey Kubalak *** - [TreezCode](https://github.com/TreezCode)
<br>
*** Kyle Knox *** - [KyleK86](https://github.com/KyleK86)
<br>
*** Amanda Dovel *** - [amandadovel](https://github.com/amandadovel)
<br>

## Acknowledgments 🌟

Free Stock Footage by: 
<a href="http://www.videezy.com">Videezy</a>
