<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Add Custom Slots to a Lex Chatbot

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-ai-lex2)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Add Custom Slots to a Lex Chatbot

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex2_c4fc89af)

---

## Introducing Today's Project!

In today's project, I used Amazon Lex to ceate a chatbot, BankerBot to collect user details for banking intents.

### What is Amazon Lex?

Amazon Lex is a chatbot service that understands natural human language, allowing users to interact with the bot easily. It’s especially useful for creating friendly conversations and automating support flows.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how creative we can be in designing the ways in which in the chatbot can interact with the users.

### This project took me...

This project took me about an hour and a half to complete, including building the chatbot from scratch and finishing the documentation.

---

## Slots

Slots are inputs collected during a conversation with the chatbot. They help the bot gather specific details, like dates or account types, so it can complete the user’s request.

By adding custom slots to utterances, my chatbot can capture inputs like savings, checking, or credit - all customized by me.

In this project, I created a custom slot type to make sure Lex accepts the account type that my imaginary bank supports.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex2_97dc2351)

---

## Connecting slots with intents

This slot type has restricted slot values, which means Lex will only accept values that i defined and reject anything else.

I associated my custom slot with CheckBalance, which is an intent that collects the usr data to help them check their bank balance.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex2_c4fc89af)

---

## Slot values in utterances

I included slot values in some of the utterances (i.e. user inputs) by using { }For example, What's the balance in my {accountType} account?

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex2_505be5b8)

---

## Handling failures in slot values

---

---
