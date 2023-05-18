# ReactJS
## Resources and Tools

### Tools
- If you go to the Installation section in the React docs, they recommend "create-react-app" and it's similar counterparts. However, "create-react-app" is really slow, and so instead we will be using [Vite](https://vitejs.dev/). A video for react setup is [here](https://drive.google.com/file/d/17NpLyWpeW58vijDKlsW4ZlQxFg3vpNFP/view?usp=share_link)

### Start here
- [React in 100 seconds | fireship.io](https://www.youtube.com/watch?v=Tn6-PIqc4UM)

### Now, focus here
- No videos this time 🙃. The course videos are too much (45). The latest [React documentation](https://react.dev) released a few months ago is stupid-simple. Your task is to finish the following 3 pages: [Quickstart](https://react.dev/learn), [Tutorial:tic-tac-toe](https://react.dev/learn/tutorial-tic-tac-toe), and [Thinking in React](https://react.dev/learn/thinking-in-react).

### Useful docs
- [React Docs](https://react.dev)

### Assignments (these are in continuation, so you have to do them in order)
1. Going through the above stuff should be done by Monday ig. Start the assignment after that. Any doubts relating the assignment are welcome, but I won't entertain any react-conceptual doubts till Sunday. That's your learning phase. Also, this assignment deadline is `28 May 2023, EOD`
2. Make a simple todolist app like [this](https://imgur.com/uJncfLu). You should store the todos in an array, whose each element will be a dictionary. Here's an example, 
```json
[
  {
    "timeStamp": "2023-05-18T09:24:24.210Z",
    "text": "Buy some snacks for the trip"
  },
  {
    "timeStamp": "2023-05-18T09:25:27.604Z",
    "text": "Water the plants"
  }
]
```
The timestamp string is an ISODateString, and can be generated using `(new Date()).toISOString()`, where `new Date()` creates a datetime object storing the current date and time. Ignore the options on the bottom-green bar for now, it should only have the ADD (+) button to add todos, but cannot delete/filter/search the todos. Each todo should have a checkbox to denote completion. Do not use any CSS styling for now, just make the damn thing work.

**Note**: You guys might think we could have simply stored an array of strings to store the todos, like `["Buy some snacks for the trip", "Water the plants"]`. The thing is, when using `map` to render multiple objects, for efficient rendering each object needs to have a unique key. Some people use the index as the key as no two todos will have the same index, but it's not the best way since on deleting todos (which we will do in assignment 2), the indexes will change for some todos. Timestamp denoting the creation time of a todo is a really good key to use for such purposes.

2. Install [this](https://www.npmjs.com/package/use-long-press) package to detect if a user long-presses on an object. Read the basic usage guide on that same npm page on that link and implement deleting any todo item if the user long-presses on it (the long-press area should be according to [this](https://imgur.com/qEA42jM) image).
3. Right now, if you refresh the webpage, the previous todos are gone. Read [this](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) page on the `localStorage` javascript API to implement storing the todos. Since you can only store strings, you also need to search about [JSON.parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) and [JSON.stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify). (For god's sake, don't read through the entire pages and get confused. Even the "Try It" example will be more than enough.).
4. Let's add some CSS now like [this image](https://imgur.com/uJncfLu). On clicking the checkbox, the todo text should have 75% opacity, and should be striked-out. Add some basic padding and margins to add space for aesthetics. Add some colors and some border-radius for a cleaner look. Add more things from your side if you want a more fancy look, but don't just get stuck here for the PERFECT look. Move on to the next assignments.
5. Now, instead of storing your todos locally, we will store them on my server. Since you guys don't know how to make APIs in backend, I will create a few APIs for you. I will give a unique ID for everyone, on which whenever the todolist is updated, instead of storing the JSON string in localStorage, you have to send this data to my POST API using the [fetch function](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch#uploading_json_data) (Read the "Uploading JSON data" section since some other sections before it contain too many parameters and can be confusing). The request body format should be

```json
{
  "_id" : "12e81uvwvvw98vhfis",
  "data": "[{'timeStamp':'2023-05-18T09:24:24.210Z','text':'Buy some snacks for the trip'},{'timeStamp':'2023-05-18T09:25:27.604Z','text':'Water the plants'}]"
}
```
, where `12e81uvwvvw98vhfis` is your ID. This way, I can store your todos on my server. Finally, you can use the `useEffect` hook with an empty array `[]` to do something when the page is first loaded, and use my GET API to retrive your todos from my server and display them on your screen. Since GET APIs do not have a body, you have to use query parameters. Here's an example. Let's say my GET API has this url `https://random.com/abc`
```url
https://random.com/abc/?param1=value1&param2=value2
```
Here, the query parameters start after the `?` mark. The first parameter is `param1`, whose value is `value1`. The second parameter is `param2`, whose value is `value2`.

In our case, the request would look like this
```url
https://random.com/abc/?id=12e81uvwvvw98vhfis
```
Using this `12e81uvwvvw98vhfis` ID, I can identify whose todos I have to find, and then I will send back those todos like this
```json
[
  {
    "timeStamp": "2023-05-18T09:24:24.210Z",
    "text": "Buy some snacks for the trip"
  },
  {
    "timeStamp": "2023-05-18T09:25:27.604Z",
    "text": "Water the plants"
  }
]
```
Then, you can show these todos on your screen. 
Overall, till here we will have implemented a todo app, capable of storing your todos on a server when the todo list changes, and fetching the todolist from wherever you open your webpage from, be it your mobile, pc or xbox. Pretty cool imo.

### Extras
- [React for the Haters in 100 Seconds | fireship.io](https://www.youtube.com/watch?v=HyWYpM_S-2c)

---

# Credits
- [fireship.io](https://fireship.io/)