<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect Amazon Lex with Lambda

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-ai-lex3)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Connect Amazon Lex with Lambda

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex3_505be5b8)

---

## Introducing Today's Project!

### What is Amazon Lex?

Amazon Lex is a AWS service and it is useful because it allows us to create and customize a bbot for our need.

### How I used Amazon Lex in this project

In today's project, I used Amazon Lex to create a BankerBot that provides a random bank balance to the user when asked.

### One thing I didn't expect in this project was...

One surprising aspect of this project was discovering how simple it is to build and personalize a bot, and how I can make it as entertaining or straightforward as I want.

### This project took me...

This project took me about 40 minutes to complete, including building the chatbot from scratch and finishing the documentation.

---

## AWS Lambda Functions

AWS Lambda is a AWS service that allows as to run code in the backend without having to provision servers!

In this project, I created a Lambda function to generate and return a random bank balance when a user asks for it!!!

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex3_97dc2351)

---

## Chatbot Alias

An alias is pointer to a version of a Bot.


TestBotAlias is a default alias used to test your Lex bot  before deployement.

To connect Lambda with my BankerBot, I visited my bot's TestBotAlias and under the Language settings i was able to select the Lambda function that i created.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex3_c4fc89af)

---

## Code Hooks

A code hook is a ways of connecting Lex to the Backend logic during conversations.

Even though I already connected my Lambda function with my chatbot's alias, I had to use code hooks so that the CheckBalance intent uses the Lambda function.

I could find code hooks at the fulfillment section of the CheckBalance.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex3_505be5b9)

---

## The final result!

I've set up my chatbot to trigger Lambda and return a random dollar figure when the user provides their account type and thier DOB for verification.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex3_505be5b8)

---

## Customizing the Lambda function

---

---
