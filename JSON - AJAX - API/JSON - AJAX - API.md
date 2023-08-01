# JSON - API - AJAX
# <span style="background-color:#fce4ec; color: #000; border-radius: 5px; padding: 4px">JSON</span>
##### What is JSON?
- JavaScript Object Notation
- Format for sharing data between server and client
- JSON is derived from JavaScript
- Alternative to XML
- File extension is `file.json`

##### Why JSON?
- Easy to use and read
- Used by most programming languages and its framework
- You can convert JSON object to JS object and vice versa


==JSON vs XMl==
- Text based format - Markup language
- Lightweight - heavier
- Dose not use tagss - using tags
- Shorter - Not shorter
- Can use arrays - cannot use arrays
- Not support comments - Supports commnets

#### JSON Syntax
- Data must be written inside {...}
- It's an object consists of key and value
- Keys must be doublequoted
- Use comma `,` to separate between each key and value
- Don't write trailing commas
- Available data to share is 
  - string
  - number
  - boolean
  - array
  - object
  - null
  
<!-- <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512" width="15" style="stock-color:red"><path d="M64 0C28.7 0 0 28.7 0 64V448c0 35.3 28.7 64 64 64H320c35.3 0 64-28.7 64-64V160H256c-17.7 0-32-14.3-32-32V0H64zM256 0V128H384L256 0zM153 289l-31 31 31 31c9.4 9.4 9.4 24.6 0 33.9s-24.6 9.4-33.9 0L71 337c-9.4-9.4-9.4-24.6 0-33.9l48-48c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9zM265 255l48 48c9.4 9.4 9.4 24.6 0 33.9l-48 48c-9.4 9.4-24.6 9.4-33.9 0s-9.4-24.6 0-33.9l31-31-31-31c-9.4-9.4-9.4-24.6 0-33.9s24.6-9.4 33.9 0z"/></svg> <span>data.json<span> -->
```JSON
{
  "string" : "Abdulazim",
  "number" : 20,
  "object" : {
    "Problem solver" : true,
    "Front-end developer": true
  },
  "myArr": [1,2,3],
  "null" : null
}
```
***

# <span style="background-color:#fce4ec; color: #000; border-radius: 5px; padding: 4px">API</span>
 API stands for "Application prtogramming interface"
`api.hithub.com/users/abdulazimRabie`
```JSON
{
  "login": "abdulazimRabie",
  "id": 114117038,
  "node_id": "U_kgDOBs1Jrg",
  "avatar_url": "https://avatars.githubusercontent.com/u/114117038?v=4",
  "gravatar_id": "",
  "url": "https://api.github.com/users/abdulazimRabie",
  "html_url": "https://github.com/abdulazimRabie",
  "followers_url": "https://api.github.com/users/abdulazimRabie/followers",
  "following_url": "https://api.github.com/users/abdulazimRabie/following{/other_user}",
  "gists_url": "https://api.github.com/users/abdulazimRabie/gists{/gist_id}",
  "starred_url": "https://api.github.com/users/abdulazimRabie/starred{/owner}{/repo}",
  "subscriptions_url": "https://api.github.com/users/abdulazimRabie/subscriptions",
  "organizations_url": "https://api.github.com/users/abdulazimRabie/orgs",
  "repos_url": "https://api.github.com/users/abdulazimRabie/repos",
  "events_url": "https://api.github.com/users/abdulazimRabie/events{/privacy}",
  "received_events_url": "https://api.github.com/users/abdulazimRabie/received_events",
  "type": "User",
  "site_admin": false,
  "name": "Abdulazim Rabie",
  "company": null,
  "blog": "",
  "location": "Egypt",
  "email": null,
  "hireable": null,
  "bio": "CS Student ",
  "twitter_username": null,
  "public_repos": 3,
  "public_gists": 0,
  "followers": 0,
  "following": 2,
  "created_at": "2022-09-21T23:21:13Z",
  "updated_at": "2023-07-23T05:24:32Z"
}
```
Api consist of JSON file which contains information the user can use and know.

You can manipulate with this JSON file and extract what you need.

So, to manipulate with json file , there are tow method you should know.

- `JSON.parse(string)` : convert data text to JS object
- `JSON.stringfy(obj)` : convert the object to JSON string

```JS
const myJsonFileFromServer = '{"username":"abdu", "age": 20}';
console.log(typeof myJsonFileFromServer); // string
console.log(myJsonFileFromServer); // {"username":"abdu", "age": 20}

const obj = JSON.parse(myJsonFileFromServer);
console.log(typeof obj); // Object
console.log(obj); // {username: 'abdu', age: 20}

obj["username"] = "Yahia";
obj["age"] = 13;

console.log(obj); // username":Yahia, age:13

const myJsonFileToServer = JSON.stringify(obj);
console.log(typeof myJsonFileToServer); // string
console.log(myJsonFileToServer); // {"username":"Yahia","age":13}
```

# <span style="background-color:#fce4ec; color: #000; border-radius: 5px; padding: 4px">Synchronous & Asynchronous</span>
### Synchronous
- Operations run in sequence
- Each operation must wait for the previous one to complete


```JS
console.log("1");
console.log("2");
alert("plpla");
console.log("3"); // it won't execute untill the alert is done
```

### Asynchronous
- Operations run in parallel
- This means that the operation can occur while another one is still being processed

```JS
console.log("1");
console.log("2");
setTimeout(() => console.log("iam asynchronous"), 3000);
console.log("3");
```

# <span style="background-color:#fce4ec; color: #000; border-radius: 5px; padding: 4px">Callstack & Web API</span>

### Web API
- Methods available from the environment => browser

### Call Stack & Stack Trace
- JavaScript engine uses a call stack to manage execution contexts
- Mechanism to make the interpreter track your calls
- When the function is called, it is added to the stack
- when the function is executed, it is removed from the stack
- After the function is finsished, the interpreter continue from the last point
- Work using LIFO principle (Last In First Out)
- Code Execution is synchronous

```Js
function one() {
  console.log("one");
}

function two() {
  one();
  console.log("two");
}

function three() {
  two();
  console.log("three");
}

three();
// one
// two
// three
```

if there is a web api method, it will be excuted in the last.
```JS
setTimeout(() => {
  console.log("web api method");
}, 0)

function one() {
  console.log("one");
}

function two() {
  one();
  console.log("two");
}

function three() {
  two();
  console.log("three");
}

three();

// one
// two
// three
// web api method
```