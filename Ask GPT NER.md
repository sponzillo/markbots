This chatbot will decode entities like "email" and "fullname" directly from the user text with a simple ChatGPT prompt.

<img width="1702" alt="image" src="https://github.com/sponzillo/markbots/assets/32564846/abdbd3c7-b5c8-46dc-8139-9e1b71eb9708">

In this chatbot I used a special prompt to ask ChatGPT to reply me with a JSON structure with the entites I asked it to decode from the user text.

<img width="1030" alt="image" src="https://github.com/sponzillo/markbots/assets/32564846/cb22ad70-050b-461b-9b4a-c3d0dc3ebe23">

The used prompt:

```
The user provided the info in the "user reply" section below. Can you detect thei fullname and email? Once detected please reply with the following JSON structure, fufilled with the detected entities. Please when the user don't provide some of the previous info fulfill the corrispondent one with null.
{
"userName":"the detected username",
"userEmail": "the detected email"
}
User reply: {{user_reply}}
```

The prompt will reply with a JSON fulfilled with the requested attributes.

I asked to fulfill with "null" values when entities are not recognied, so the corrispondent form fields are automatically triggered.

The returned JSON is automatically converted to a JSON object. The GPT Task action always checks if the returned GPT response ha a JSON structure. In this case the returned payload is automatically converted to a JSON object.

Decoded entities are then moved into the conversation attributes as "flat" attributes, so they can be used within a form.

The form will ask the user for all the missing entities automatically.

Feel free to contact me at support@tiledesk.com
