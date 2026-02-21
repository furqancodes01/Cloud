<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Chatbot with Amazon Lex

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-ai-lex1)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Build a Chatbot with Amazon Lex

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex1_505be5b8)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate... I'm doing this project to learn... 

### What is Amazon Lex?

Amazon Lex is  a aws service that helps to built chatbot .

### Key tools and concepts

Services I used were amazon lex Key concepts I learnt include intents, fallbackintents, utterences and confidence score thershold.

### Personal reflections

One thing I didn't expect in this project was how easy to create a chat bot without any coding experience...

### Project timeline

This project took me approximately half and hour .The most challenging part was deciding help voice to go with . It was most rewarding to see my bot in action in a way that i wanted.

---

## Setting up a Lex chatbot

### Approach to chatbot setup

In this step, I will create amazon lex bot ... because... i wanna learn

### Chatbot creation process

I created my chatbot from scratch with Amazon Lex. Setting it up took me..7 minutes.

### IAM role configuration

While creating my chatbot, I also created a role with basic permissions because... because amazon lex need other permissions to interact with other aws resources like aws lambda

### Intent classification confidence score

In terms of the intent classification confidence score, I kept the default value of 0.40. This means the chatbot we are creating needs to be atleast 40% confidence to be able to interact with the user 

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex1_97dc2351)

---

## Intents

In this step, I will... because learn to create my bot's forst intent


### Creating my first intent

Intents are user goals that the chatbot needs to understand..

I created my first intent, WelcomeIntent, to greet users when they hello or ask for help

### Testing chatbot responses

I launched and tested my chatbot, which could respond successfully if I enter 'hello' and 'hiya' .

---

## Handling unrecognized inputs

My chatbot returned the error message 'Intent FallbackIntent is fulfilled' when I entered 'how are you' This error message occurred because my bot coud'nt match to initially define intents.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex1_505be5b8)

---

## Configuring FallbackIntent

In this step, I will customize the fallbackintent  because i would like to be my bot to be friendly.

### When FallbackIntent triggers

FallbackIntent is a default intent in every chatbot that gets triggered when the chatbot dosen't understand the user's input

I wanted to configure FallbackIntent because i want my bot to respond to the users in a friendly way even when there is errors.

### My FallbackIntent configuration

To configure FallbackIntent, I customized the closing response messages and added variations so it sounded more natural.

I also added variations! What this means for an end user is that they will see a slightly response each time they response each time to that the bot dosent understand.

---

## FallbackIntent with Variations

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-ai-lex1_c4fc89af)

---

## Initial Responses

### Setting up initial responses

### Initial response implementation

---

---
