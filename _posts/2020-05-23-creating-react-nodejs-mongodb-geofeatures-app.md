---
layout: post
title: Creating a React+NodeJS+MongoDB app to query geofeatures
subtitle: Episode 1 - Installation
tags: [nodeJS, Javascript, mongoose, mongoDB]
---

### Intro ###

In this series of episodes I will be describing the steps to build a proyect with the following elements:

1) React Client: This client will be running on port 3000 and querying the server

2) NodeJS server: The server will control the logic and interaction with our MongoDB database

3) MongoDB: The database will store a collection of geofeatures (Avalanche areas, Ski touring routes, Local areas, Ski shops and chilean volcanos with their proper description of important variables to take desitions before going to the backcountry)

The area in the world that I've selected to populate with data about is Malalcahuello, one of my favourite places on earth that I have had the luck to explore for quite a few years until now. I'm stoked to share this project with you and I do really hope that more than one backcountry skier that needs info about the zone gets it throught this app.

## Installation ##
Requirements:
- NodeJS (@12.16.1) - [Install node](https://nodejs.org/es/download/)
- MongoDB (@4.2) - [How to install mongoDB](https://www.mongodb.com/download-center/community)
- express (@5.9.15)

## Directory structure ## 

```
/nidipserver
    /Client
    /server
        /config
            config.js
        /middleware
            middleware.js
        /models
            avalancheAreas.js
            localAreas.js
            skiShops.js
            skiTouringRoutes.js
            user.js
            volcanos.js
        server.js
```

## Installing the react client ##
1) First of all, run npm init inside the root folder (/nidipserver)
``` /nidipserver > npm init ```
    This will create the package.json file, we can skip all the info requested at the prompt and deal with that later.

2) ``` /nidipserver > npm install bcrypt@4.0.1  body-parser@1.18.2 concurrently@3.5.1 cookie-parser@1.4.3```

3) Let's install express and jsonwebtoken
    ``` /nidipserver > npm install express@4.16.2 jsonwebtoken@8.0.1 moment-js@1.11.15 mongoose@5.9.15 --save ```

*** If you are learning react it's very likely that you have installed the create-react-app package, if not type the following inside at the root directory:**

``` npm install create-react-app --save ```

4) Let's install all the folder structure for our react app inside the "client" folder.

``` /client > npm install create-react-app . ``` 
(using the dot "." skips the argument of a folder name and installs ell the react folders+files in the current directory)

After finishing all this, your directory structure should look like this:
```
/nidipserver
    /Client
        /node_modules
        /public
        /src
        package-lock.json
        package.json
        README.md
    /node_modules
        < "all the node packages installed" >
    /server
        /config
            config.js
        /middleware
            middleware.js
        /models
            avalancheAreas.js
            localAreas.js
            skiShops.js
            skiTouringRoutes.js
            user.js
            volcanos.js
        server.js
    package-lock.json
    package.json
```

### Additional installations ###

Inside the client folder we'll install the last packages that we will need for now. Run
``` /client >  npm install axios@0.19.2 react-redux@5.0.6 react-router-dom@4.2.2 redux@3.7.2 redux-promise@0.5.3 --save  ``` 

``` /client > npm install react-fontawesome@1.7.1 react-simple_sidenav@2.0.0 redux-thunk@2.2.0 --save  ``` 
