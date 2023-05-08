This chatbot demonstrates how to use all the new features of the WebRequest Action.

Now you can use all the attributes set in your chatbot in all WebRequest Action's metadata, as shown in the following figure:

![image](https://user-images.githubusercontent.com/32564846/236867311-86ee319e-c192-4af5-bd48-12c51728b5de.png)

And in JSON Body too!

![image](https://user-images.githubusercontent.com/32564846/236867695-c5c6af19-77e8-4abf-99b1-25bfc044f954.png)

We set initial data for the test in "start" block:

**user_SSN** attribute:

<img width="600" alt="image" src="https://user-images.githubusercontent.com/32564846/236867899-720a092e-4a10-484f-b999-a9cdf43820f9.png">

And **apikey** attribute:

<img width="1006" alt="image" src="https://user-images.githubusercontent.com/32564846/236868088-d0a1cf12-127a-42cf-816e-4171d0e98447.png">

## Assign custom attributes from remote JSON

We use [handlebars syntax](https://handlebarsjs.com/guide/expressions.html) to get data back from JSON and assign those data to custom attributes

<img width="600" alt="image" src="https://user-images.githubusercontent.com/32564846/236868589-6cb7a4b3-25f4-4448-9f1d-f76960aa9720.png">

We got the JSON using this [replit app](https://replit.com/@tiledesk/test-webrequest-json-attributes#index.js)

```
app.get('/jorgearray/:userid', (req, res) => {
  console.log('/test called! headers:', req.headers);
  const userid = req.params["userid"]
  const apikey = req.headers["apikey"]
  const data = [[{
    "userid": userid,
    "username": "flopiaballay4@gmail.com",
    "lastname": "Aballay",
    "firstname": "Anahi Florencia",
    "email": "flopiaballay4@gmail.com",
    "confirmed": "true",
    "suspended": "false",
    "deleted": "true",
    "retApikey": apikey
  }]];
  console.log("ret data:", data);
  res.send(data);
});
```

You can omit {{{ }}} symbols, the system automatically will use the inner syntax to get data.

If your expression starts instead with { the interpreter will switch to the full syntax as in the following example, where we got the last element in "kids" array:

```
app.get('/testjson', (req, res) => {
  console.log('/testcomplesso called!');
  const data = { 
    "name": "Alan",
    "hometown": "Somewhere, TX",
    "time": 123,
    "owner": {
        "name": "Andrea",
        "CF": "SPN"
    },
    "html": "<div>HTML Content!</div>",
    "kids": [
        {
            "name": "Jimmy",
            "age": "12"
        }, 
        {
            "name": "Sally",
            "age": "4"
        }
    ],
    "names": [
        "Andrea",
        "Marco",
        "Mery",
        "Nico",
        "Antonio",
        "Stefania",
        "Luca"
    ]
  };
  res.send(data)
});
```

With the following syntax:

"{{#each kids}}{{#if @last}}{{this.name}}{{/if}}{{/each}}"

Look there:

<img width="600" alt="image" src="https://user-images.githubusercontent.com/32564846/236870499-cd0e93b1-c832-47da-83d7-6e9bd88c150a.png">

Hope this helps you enjoy the power of the new Tiledesk WebRequest Action!

Feel free to write to andrea@tiledesk.com for issues or more info

