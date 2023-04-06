This simple chatbot gets user data through a dyna-form then creates (or updates) a Contact on Sendinblue.

To use this integration you need a Sendinblue API-KEY.

The main block is _askandsend_

This block first asks has a form configured to ask the follwing data, creating the corresponding attributes:

* User first name. Attribute: _firstname_
* User full name. Attribute: _lastname_
* User email. Attribute: _userEmail_

<img width="800" src="https://user-images.githubusercontent.com/32564846/230483768-3da10f9e-19dc-4eb6-9bf1-4b878578ae05.png">

Once the form is configured you can move to the next step, sending contact's data to Sendinblue.

To achieve this goal first add a _WebRequest_ Action from the side menu.

The WebRequest Action simply executes an HTTP call to the Sendinblue "create a contact" REST API (See related [create a contact](https://developers.sendinblue.com/reference/createcontact) documentation)

<img width="800" src="https://user-images.githubusercontent.com/32564846/230486051-77035d0e-97be-48a2-bc37-5418134aa952.png">

Setup the HTTP url with the documented API endpoint using the **POST** HTTP method.

```
https://api.sendinblue.com/v3/contacts
```

Then setup all the HTTP headers fields as in the picture, taking care to set the api-key header field with your own Seindinblue API-KEY.

