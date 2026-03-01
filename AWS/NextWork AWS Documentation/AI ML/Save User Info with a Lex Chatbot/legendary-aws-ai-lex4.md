<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Save User Info with a Lex Chatbot

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-ai-lex4)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Save User Info with a Lex Chatbot

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex4_505be5b8)

---

## Introducing Today's Project!

### What is Amazon Lex?

Amazon Lex is AWS service and it is useful because it allows you to create chatbots without too much coding.

### How I used Amazon Lex in this project

Today's Project: Built an Amazon Lex banking bot that greets users, handles errors gracefully, and returns random balances based on account type and date of birth - with memory to avoid repeated verification.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how easy it was to change the duration of the bot's memory.

### This project took me...

This project took me about one and half hour including creting the bot from scratch and creating the documentation.

---

## Context Tags

Context tags are Like sticky notes that the Bot keeps between intents.

There are two types of context tags, we can setup an output context to store info after an intent is completed or an input context to check for info before an intent is triggered.

I created a context tag called contextCheckBalance. This context tag was created in the intentCheckBalance. This tag stores information about our user's date of birth.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex4_97dc2351)

---

## FollowUpCheckBalance

I created a new intent called FollowupCheckBalance. The purpose of this intent is to allow user's to ask a follow up question about another account balance.

This intent is connected to the previous intent I made, CheckBalance, because it performs the same function returning a random number for the bank account when the account type and date of birth is provided).

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex4_12345678)

---

## Input Context Tag

I created an input context, contextCheckBalance, that remembers the date of birth of the user before the FollowupCheckBalance.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex4_c4fc89af)

---

## The final result!

To test context tags and follow-up intent, I first triggered the CheckBalance intent by entering “check my balance,” which gave a random bank balance. Then I asked “what about checking” to trigger the FollowupCheckBalance intent.

If I had gone straight to triggering FollowUpCheckBalance without setting any context, BankerBot would have asked me for my verification details (date of birth).But once the context was set, it didn’t ask again when I checked another account balance.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex4_505be5b8)

---

## Managing context expiry

---

---
