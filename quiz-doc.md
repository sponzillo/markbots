A simple "quiz on Javascript" submitted through a Chatbot 🤓

You can use this chatbot to submit a simple test to your audience.

This test makes wide use of "attributes" and "conditions" (aka the "flow").

## Quiz Design

The test uses "attributes". Attributes are a great way to manage your chatbot flow, and they are especially useful to store some in-flow data that can be also used later to manage your flow with conditions (you can use your attributes in any actions). 

<img width="900" alt="image" src="https://user-images.githubusercontent.com/32564846/229458815-17de81e8-55b1-403e-8773-d2e584514b77.png">

The test starts with the “Start quiz” button in the **“start” block**. Set up the _total_ attribute to his initial value of zero when the button is pressed.

> TIP: Button’s “Attributes” option allows you to set up as many attributes as you want on a single button pressure.

<img width="700" alt="image" src="https://user-images.githubusercontent.com/32564846/229460968-d180dc71-e92d-464b-88ce-79f7b61139c1.png">

<img width="528" alt="image" src="https://user-images.githubusercontent.com/32564846/229474089-13f48286-2c11-4d36-8803-1668f9a2412a.png">

The first question (**question1 block**) simply proposes four possible replies (plus a "Cancel test" option), where only one is true.

We always use the Button's Attributes feature to set the current test score. Every time the user pressed the correct reply's botton the total score increases of the corresponding amount. When an incorrect reply is selected the score is set to zero.

<img width="1132" alt="image" src="https://user-images.githubusercontent.com/32564846/229462520-f656e68e-5912-45b0-b9d4-63ef91e61ae4.png">

<img width="900" alt="image" src="https://user-images.githubusercontent.com/32564846/229464270-bbdce1af-7efb-4095-8a34-52009384e0f0.png">

Now move to **question2**. From now on, until the last question, each question will have the same identical structure.
On each question we simply increase the "total" score adding the current reply's score coming from the previuos button press.

<img width="900" alt="image" src="https://user-images.githubusercontent.com/32564846/229466456-b72a3dc9-b3f6-44a8-9aa2-a6c83de5c199.png">

The first action of each question always computes the new total, adding the actual question score - the one you got by pressing the choosen reply-button.

After all, it’s a simple _add_ operation:

```
total = total + score
```

On the last question, as soon as the test comes to the end, the chatbot will branch on specific replies, based on your total score.

Take a look at the branh_result block. It's made by threee condition-actions. Each action will move to the reply specific for the score.

![image](https://user-images.githubusercontent.com/32564846/229618419-6f4a3b93-e556-473a-acb8-6820e56742d8.png)

And the result...

![image](https://user-images.githubusercontent.com/32564846/229619734-f3863691-d384-4b7e-824c-d9e1e76ff938.png)


## Proactive rules

We also created a rule to proactively engage your visitors to open and complete the test.

![image](https://user-images.githubusercontent.com/32564846/229613928-601a56e4-971d-4e0e-b6c8-6b89b80013d7.png)

Setup your proactive rule in the rules section:

<img width="300" alt="image" src="https://user-images.githubusercontent.com/32564846/228898518-fab82c21-422b-435d-b18b-76a3104e39ca.png">

This rule simply states that whatever link you open the proactive block will be invoked:

![image](https://user-images.githubusercontent.com/32564846/229614324-c0665ce9-de02-4132-95fd-a2e6b24b61f4.png)


## Ask visitor name

We also used "forms" to ask your visitor's data (his name). You can find the Form setup in the "start" block.

![image](https://user-images.githubusercontent.com/32564846/229614743-e6004919-750c-43b5-af7d-379de1f83de6.png)

## Whatsapp

It also works on Whatsapp!

Just push the green button et...voilà, it's ready designed to run on Whatsapp!

![image](https://user-images.githubusercontent.com/32564846/229617345-f2e406ed-3a61-442b-8fd0-333769a328fc.png)

## Conclusions

Feel free to import and modify this test as you prefer.

Let us know if you have some questions about this template writing a message to *andrea@tiledesk.com*
