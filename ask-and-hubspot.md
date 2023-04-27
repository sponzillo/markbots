This simple chatbot gets user data through a dyna-form and then creates (or updates) a Contact on [Hubspot](https://www.hubspot.com/).

To use this integration you need a **Hubspot Access token**. We'll learn how to create one.

The main block is _askandsend_.

This block uses a form to ask the follwing data, creating the corresponding chatbot attributes:

* User first name. Attribute: _firstname_
* User full name. Attribute: _lastname_
* User email. Attribute: _userEmail_

<img width="800" alt="form to ask data" src="https://user-images.githubusercontent.com/32564846/234824686-74090871-eee7-44a9-8875-3865385a87ae.png">

Once the form is configured you can move to the next step, sending contact's data to Hubspot.

To achieve this goal first [create a new Private App](https://developers.hubspot.com/docs/api/migrate-an-api-key-integration-to-a-private-app#create-a-new-private-app) on Hubspot. In this way you will get a new **Access token** to connect to their APIs.

## Hubspot Private app

When asked, select the "scope" of your app, taking care of selectiong "contacts" and assigning at least the Write permission (that we use for our chatbot).

<img width="800" src="https://user-images.githubusercontent.com/32564846/234829939-5eba44cd-5839-44e6-bfd1-64850f6fd8d1.png">

Once created you can go to the App's details page where you can get your **Access token**. We'll use this later.

<img width="800" src="https://user-images.githubusercontent.com/32564846/234831540-222c7e03-3379-483f-a98c-a956e79ef1d5.png">

## Configure your connection

Now back to our chatbot. Add a _WebRequest_ Action from the side menu.

The WebRequest Action simply executes an HTTP call to the Hubspot "create a contact" REST API. See related [https://developers.hubspot.com/docs/api/crm/contacts](https://developers.hubspot.com/docs/api/crm/contacts) documentation.

<img width="800" src="https://user-images.githubusercontent.com/32564846/234832565-71d03e20-4afa-4383-9363-a0a0636c340d.png">

Setup the HTTP url with the documented API endpoint using the **POST** HTTP method.

Hubspot contact's **API endpoint**:

```
https://api.hubapi.com/crm/v3/objects/contacts
```

Then setup all the HTTP headers fields as in the picture, taking care to set the Authorization header field with your own **Access token**.

Now move to the body section and set the dyna-form related attributes in the Hubspot JSON body, as shown in the picture:

<img width="700" src="https://user-images.githubusercontent.com/32564846/234833085-4e3a60cc-538a-45db-a6fb-dd18fce5c926.png">

**Contact JSON body**:

```
{
	"properties": {
		"email": "${userEmail}",
		"firstname": "${firstname}",
		"lastname": "${lastname}"
	}
}
```
Well, now press _Test it out_ to see the chatbot in action:

<img width="400" src="https://user-images.githubusercontent.com/32564846/234834425-7f08f8e8-ef08-4f69-8f02-8ceae56996b4.png">

As soon as the conversation ends The WebRequest action sends all the contact data to Hubspot Contacts. You we'll see your updated contact in the Hubspot's Contact center:

<img width="800" src="https://user-images.githubusercontent.com/32564846/234834974-950e0856-6218-4f0d-99ea-a7a7e2998389.png">

Hope you enjoy this simple chatbot 🤖

If you need any help please feel free to contact me at _andrea_ _at_ _tiledesk.com_ 🤓
