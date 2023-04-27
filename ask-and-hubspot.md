This simple chatbot gets user data through a dyna-form and then creates (or updates) a Contact on [Hubspot](https://www.hubspot.com/).

To use this integration you need a **Sendinblue API-KEY**. Please follow the corresponding [Sendinblue docs](https://developers.sendinblue.com/docs) to learn how to create one.

The main block is _askandsend_.

This block uses a form to ask the follwing data, creating the corresponding chatbot attributes:

* User first name. Attribute: _firstname_
* User full name. Attribute: _lastname_
* User email. Attribute: _userEmail_

<img width="800" alt="form to ask data" src="https://user-images.githubusercontent.com/32564846/234824686-74090871-eee7-44a9-8875-3865385a87ae.png">

Once the form is configured you can move to the next step, sending contact's data to Hubspot.

To achieve this goal first add a _WebRequest_ Action from the side menu.

The WebRequest Action simply executes an HTTP call to the Hubspot "create a contact" REST API. See related [https://developers.hubspot.com/docs/api/crm/contacts](https://developers.hubspot.com/docs/api/crm/contacts) documentation.


<img width="800" src="https://user-images.githubusercontent.com/32564846/230486051-77035d0e-97be-48a2-bc37-5418134aa952.png">


Setup the HTTP url with the documented API endpoint using the **POST** HTTP method.

```
https://api.sendinblue.com/v3/contacts
```

Then setup all the HTTP headers fields as in the picture, taking care to set the api-key header field with your own **Seindinblue API-KEY**.

Now move to the body section and set the dyna-form related attributes in the Sendinblue JSON body, as shown in the picture:


<img width="700" src="https://user-images.githubusercontent.com/32564846/230486589-c0cf1333-7281-4808-91e6-b891717aaf7d.png">


Well, now press _Test it out_ to see the chatbot in action:


<img width="400" src="https://user-images.githubusercontent.com/32564846/230487247-29c9af2d-f20c-449f-9267-9d8ab9047632.png">


As soon as the conversation ends The WebRequest action sends all the contact data to Sendinblue Contacts. You we'll see your updated contact in the Sendinblue's Contact center:

<img width="800" src="https://user-images.githubusercontent.com/32564846/230488362-fee01c5f-d499-4f24-a64d-299a491a72fd.png">


Hope you enjoy this simple chatbot 🤖

If you need any help please feel free to contact me at _andrea_ _at_ _tiledesk.com_ 🤓
