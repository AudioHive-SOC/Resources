# Important

## Updates
- I have added the detailed react project setup below, will elaborate later on the git setup and the nodejs project setup.

## React Project Structure
1. For Windows users, install Powershell latest version from [here](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.3). Download and run the `MSI package` (x64 version) ![Image](https://i.imgur.com/L5qlZXh.png) ![Image](https://i.imgur.com/uRBh13Q.png)
2. Go through the Powershell installation program ![Image](https://i.imgur.com/SsKfvm8.png). However, on this screen, enable these 2 options ![Image](https://i.imgur.com/NI0NSEz.png) Continue the rest of the installation normally.
3. Open a folder where you want to create the react project. Right click and open a powershell window there. ![Image](https://i.imgur.com/un2ROet.png)
4. Go to the [Tailwind Installation Documentation pertaining to the Vite framework](https://tailwindcss.com/docs/guides/vite). 
5. Replace `my-project` with your project name, then follow the rest of the commands. ![Image](https://i.imgur.com/MRhM4pQ.png)
6. After the 2nd section, you can run `code .` to open VSCode in your project folder. You can then close your Windows Explorer and the Powershell Window, since both can be opened inside VSCode itself. ![Image](https://i.imgur.com/zNAoo9z.png)
7. Your VSCode project should look like this. ![Image](https://i.imgur.com/YakO8pT.png)
8. Install the ES7 extension and the Prettier extension in VSCode if you haven't already. Then close the Extensions tab. ![Image](https://i.imgur.com/kZ3LYRu.png) ![Image](https://i.imgur.com/f1A5Aqo.png)
9. Go to settings ![Image](https://i.imgur.com/qfciwRH.png)
10. Search for `format on save`, then enable the marked checkbox ![Image](https://i.imgur.com/GRwg528.png)
11. Then search for `autosave`, then set the marked field to `afterDelay`. Then close the settings tab. ![Image](https://i.imgur.com/CYPpPMS.png) 
12. You can press `Ctrl+J` to open a Powershell Window within VSCode. It can also be used to hide an already opened Powershell Window ![Image](https://i.imgur.com/UYtEOYI.png)
13. In the `src` directory, delete the `assets` folder, and the `App.css` file. Just select them and press the Delete key.
14. Remove all lines from `index.css` and `App.jsx` ![Image](https://i.imgur.com/b4W7Ivu.png) ![Image](https://i.imgur.com/P1S9C5l.png)
15. Follow the rest of the instructions on the Tailwind page ![Image](https://i.imgur.com/0UNXqoB.png)
16. After step 6 in the tailwind installation docs, go to the `App.jsx` file, right click anywhere near the code lines and select `Format document with...` ![Image](https://i.imgur.com/crX3aok.png)
17. Select the `Prettier - Code formatter` option. ![Image](https://i.imgur.com/b3lMc7T.png)
18. This will format your code like this. Also, because of our previous setup, VSCode will autosave and autoformat the current file whenever you stop typing. ![Image](https://i.imgur.com/U1DFxDM.png). 
19. Finally, Press `Ctrl+J` to unhide the Powershell Window, then run `npm run dev` to start the React app. ![Image](https://i.imgur.com/aE1CECX.png)
20. Here is the React app running on port `5173` ![Image](https://i.imgur.com/R7nVq3G.png)

## NodeJS Project Structure
1. First run the above react setup atleast once in your lifetime, since some instructions involve VSCode configuration, which will also be useful here.
2. Create a new directory with the name of your nodejs project, say `backend`. Go inside it, then right click and select `Open with Code`. You can close Windows Explorer. ![Image](https://i.imgur.com/9rqbL4M.png) ![Image](https://i.imgur.com/Wp9qaCP.png)
3. Use `Ctrl+J` to open a Powershell Window inside VSCode. Run `npm init -y` to initialize a project, with the `-y` flag meaning to use default settings. ![Image](https://i.imgur.com/usR7Wla.png)
4. Now run `npm i express mongoose dotenv cors nodemon`. ![Image](https://i.imgur.com/7EL6tZR.png)
5. Press `Ctrl+J` to hide the Powershell Window. Create a new file named `.gitignore`, and add the following lines in the file

   ```gitignore
   node_modules/
   package-lock.json
   .env
   ```
   Thus, git will ignore the `node_modules` folder, as well as the other 2 files. Such a configuration is already present when we create a react project using vite. 
6. Close this file, and open `package.json` file. Below `"description": "",`, add this line `"type": "module",`. This will allow us to use the latest ES6 Javascript syntax. ![Image](https://i.imgur.com/YAXrHVh.png)
7. In the `scripts` key, remove this line `"test": "echo \"Error: no test specified\" && exit 1"`. Instead, add this line `"dev": "nodemon index.js"`. This way, we can run the command `npm run dev`, which will actually run the command `nodemon index.js`. Since different projects may use different file structures, it's better to keep a common alias command like `npm run dev` or `npm start` to start the app. Close this file. ![Image](https://i.imgur.com/iHMmlVp.png)
8. Create a new `index.js` file, and copy this boilerplate code. 

   ```javascript
   import express from "express";
   import cors from "cors";
   import dotenv from "dotenv";

   dotenv.config(); // without this line, process.env on line 22 will be undefined, thus you won't be able to read the .env file
   const app = express();
   app.use(express.json());
   app.use(cors());

   app.get("/hey", (req, res) => {
   	return res.status(200).send("hi");
   });

   app.get("/getData", (req, res) => {
   	const data = [
   		{ city: "Mumbai", temperature: 30 },
   		{ city: "Delhi", temperature: 25 },
   	];
   	return res.status(200).json(data);
   });

   const port = process.env.PORT || 5001;
   // in the .env file, we used PORT = 5000, but in case that variable is undefined in the .env file, use port 5001

   app.listen(port, () => console.log(`SERVER: ${port}`));
   // just a formality, print SERVER: port when server starts
   ```

9. Create a new `.env` file. Here, you can store any secret variables like API keys, MONGODB_URI, hash secrets, payment salts, etc. Remember that this `.env` file will be ignored by git, so it's your responsibility to keep a local backup of this file in case of data loss. 
Define the following variable in this file `PORT = 5000` ![Image](https://i.imgur.com/qiVZVQK.png)
10. Finally, press `Ctrl+J` to unhide the Powershell Window and run your code using `npm run dev`. ![Image](https://i.imgur.com/uk0j1SF.png)
11. Here are the 2 APIs we made in the boilerplate code. ![Image](https://i.imgur.com/WOfbEU4.png) ![Image](https://i.imgur.com/M8W9i2g.png) 