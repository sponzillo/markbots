A simple quiz about Javascript submitted through a Chatbot 🤓

You can use this chatbot to submit a simple test to your audience.

This test makes wide use of "attributes" and "conditions" (aka the "flow").

## Quiz Design

The test makes wide use of attributes. Attributes are a great way to manage your chatbot flow, and they are especially useful to store some in-flow data that can be also used later to manage your flow with conditions (you can use your attributes in other actions too). 

<img width="900" alt="image" src="https://user-images.githubusercontent.com/32564846/229458815-17de81e8-55b1-403e-8773-d2e584514b77.png">

The test starts with the “Start quiz” button in the **“start” block**. Set up the _total_ attribute to his initial value of zero when the button is pressed.
**TIP**: Button’s “Attributes” option allows you to set up as many attributes as you want on a single button pressure.

<img width="1132" alt="image" src="https://user-images.githubusercontent.com/32564846/229460968-d180dc71-e92d-464b-88ce-79f7b61139c1.png">

<img width="528" alt="image" src="https://user-images.githubusercontent.com/32564846/229474089-13f48286-2c11-4d36-8803-1668f9a2412a.png">

The first question (**question1 block**) simply proposes four possible replies (plus a "Cancel test" option), where only one is true.

We always use the Button's Attributes feature to set the current test score. Every time the user pressed the correct reply's botton the total score increases of the corresponding amount. When an incorrect reply is selected the score is set to zero.

<img width="1132" alt="image" src="https://user-images.githubusercontent.com/32564846/229462520-f656e68e-5912-45b0-b9d4-63ef91e61ae4.png">

<img width="1920" alt="image" src="https://user-images.githubusercontent.com/32564846/229464270-bbdce1af-7efb-4095-8a34-52009384e0f0.png">

Now move to **question2**. From now on, until the last question, each question will have the same identical structure.
On each question we simply increase the "total" score adding the current reply's score coming from the previuos button press.

<img width="1195" alt="image" src="https://user-images.githubusercontent.com/32564846/229466456-b72a3dc9-b3f6-44a8-9aa2-a6c83de5c199.png">

The first action of each question always computes the new total, adding the actual question score - the one you got by pressing the choosen reply-button.

After all, it’s a simple _add_ operation:

```
total = total + score
```

## Proactive rules

We also created a rule to proactively engage your visitors to open and complete the test.

<img width="300" alt="image" src="https://user-images.githubusercontent.com/32564846/228898518-fab82c21-422b-435d-b18b-76a3104e39ca.png">

We also used "forms" to ask your visitor's data.

It also works on Whatsapp!

Feel free to import and modify this test as you prefer.

Let us know if you have some questions about this template writing a message to andrea@tiledesk.com
