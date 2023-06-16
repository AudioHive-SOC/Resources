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
18. This will format your code like this. Also, because of our previous setup, VSCode will autosave and autoformat the current file whenever you stop typing. ![Image](https://i.imgur.com/U1DFxDM.png)