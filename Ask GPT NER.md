Get user data decoding entities like email and fullname directly from the user text.

<img width="1702" alt="image" src="https://github.com/sponzillo/markbots/assets/32564846/abdbd3c7-b5c8-46dc-8139-9e1b71eb9708">

In this chatbot I used a special prompt to ask ChatGPT to reply me with a JSON structure with the entites I asked it to decode from the user text.

Decoded entities are then put moved into the conversation attributes, so they can be used with a form.

The form will ask the user for all the missing entities automatically.

