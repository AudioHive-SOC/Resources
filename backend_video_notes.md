# My Review of the videos (watched at 10x 😂)

## Chapter 16
1. You don't need the HyperTerminal app. You can simply use Powershell.
2. Basic commands

## Chapter 17
![Image](https://i.imgur.com/t9dUWnf.png)

## Chapter 18
1. You already installed NodeJS because of React
2. You can simply make an empty folder, create an `index.js` file with some javascript, then run `node index.js` to run the javascript file outside your browser using the NodeJS runtime. 
3. Currently, we are only experimenting with NodeJS without actually creating a backend project.

## Chapter 19
1. Express.js is a framework for writing APIs using Javascript. 
2. If you remember, we used the command `"dev": "nodemon index.js"` in the `package.json` file of our backend. Nodemon is a package which essentially runs the command `node`, but without this package everytime you make changes to your code, you have to manually terminate the running `node` command, then run the command again. Nodemon autodetects changes to `.js` files when you save any `.js` file, and automatically restarts the `node` command. 
3. We can send strings, numbers, JSON data, as well as HTML data through APIs.
4. To parse the data in any API request, Angela used the `body-parser` package and the lines 
   ```node
   import bodyParser from "body-parser"
   import express from "express"

   const app = express();
   app.use(bodyParser.urlencoded({extended: true}))

   // ... and so on
   ```
   However, in the `important.md` file I uploaded to the repo, we will instead not use the `body-parser` package and use this code
   ```node
   import express from "express"

   const app = express();
   app.use(express.json())

   // ... and so on
   ```

## Chapter 20
1. In our backend, we can specify URL endpoints/routes for each individual API.
2. Publicly available APIs like weather APIs are hosted on a server, and since maintaining such a server involves some cost, most API providers first invoke authentication so that only signed-up users can access those APIs, then a pricing system (which may include a free trial) depending upon how many API requests does an account need. For example, in the extra react assignment I mentioned in the `extras.md` in the AudioHive Resources repo, we used a weather API from RapidAPI, which gave us a free trial usage of about 100 API calls per month. If our weather app were to become famous, more people would end up using our app, thus increasing the number of API calls to the weather API, and eventually we will have to buy an adequate plan to support so many users.
3. We can use apps like Postman/Hoppscotch, or VSCode extensions like ThunderClient to make API calls.
4. As mentioned earlier, we can also send HTML data using APIs. This way, we can create a `server-side-rendered website`. Until now, we were making `client-side-render-website`. [Here](https://www.freecodecamp.org/news/what-exactly-is-client-side-rendering-and-hows-it-different-from-server-side-rendering-bd5c786b340d/) is a reference for more info.
5. For a server-side-rendered website, if you want to use static assets like images, you can use the line `app.use(express.static("public"))`, where `public` is the name of the directory in your project where you will be storing your static assets.

## Chapter 24
No comments. Video and google are self sufficient to explain the differences.

## Chapter 26 and 27
1. For local database testing, you can install `MongoDB Compass`, which includes `mongosh` and a GUI for viewing databases.
2. In our projects, we will not use a local database, and instead use an online mongodb database. I have already explained this part in [my 2nd video](https://youtu.be/ADijbeaXjmM?t=7414) starting from `2hrs 3mins 34secs`. 
3. Mostly, we will not be directly using MongoDB commands, and instead use the [Mongoose](https://www.npmjs.com/package/mongoose) npm package to interact with our MongoDB database. 