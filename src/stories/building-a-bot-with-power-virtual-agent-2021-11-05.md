---
title: Building a bot with Power Virtual Agent
shortDesc: With Microsoft's Power Virtual Agent, you can create a chatbot
  intuitively with a low-code/no-code approach and little-to-no understanding of
  natural language
badge: hero
author: Benedict
authorImage: /assets/images/ato-1-.jpg
authorBio: Benedict Ifeanyi Iheagwara is a Tech Enthusiast with the volunteer
  spirit. He is a graduate of the University of Ghana where he studied
  pharmacology. Benedict is a Data analyst and technical writer. He specializes
  in Microsoft Power BI and Power Platforms, and machine learning. He loves
  working community building and sharing valuable tips.
timeRead: 10 min
date: 2021-11-06T12:07:49.135Z
tags:
  - post
  - Technology
image: /assets/images/hero.jpg
imageAlt: boot
---
### Introduction

If you’ve ever used customer support LiveChat service, Pan Macmillan, Nerdify, U-Report, Google Assistant, or Siri, you’ve made use of a bot. Just like the crazy but impressive AI, we have seen in the movies, such as Terminator, Resident Evil’s Red Queen, and JARVIS from Iron Man, chatbots are quite conversational and useful.

In this article, you will learn:

* What Power Virtual Agents are?
* How to create your first bot with no-code
* How to create a topic
* Test and publish your first no-code bot.

### Prerequisites

You require the following to create and manage bots:

* A "per-user license" as an individual
  or 
* A "tenant license" if building for an organization

### Table of Contents

* Building a chatbot with Power Virtual Agent
* Prerequisites
* Power Virtual Agents
* Let’s build a bot
* Publishing your bot
* Monitoring your bot
* Key takeaways
* Conclusion
* Further reading

### Power Virtual Agents

Power Virtual Agents is part of the Microsoft Power Platform. It allows you to create intelligent bots easily and quickly to help guide your customers, employees, users, or viewers of your website. Compared to the traditional hand-coded computer programming, Power Virtual Agents provides a low-code/no-code development environment. 

The Power Virtual Agents platform is user-friendly with no real infrastructure to maintain in terms of deployment. Thus, making Power Virtual Agents a powerful, low code Chatbot engine. 

Sounds exciting right? Let's build a simple Pan Macmillan bot! Pan Macmillan is a book recommendation assistant owned by Pan Macmillan Publishing.

#### Let’s build a bot

 To get started, go to the Power Virtual Agent website and sign up for an account. If you don't have a license, that’s alright. A free trial is available on the website to get you started.

1. Creating  a new bot:

 i.  At the top-right, click the robot icon, then “New bot.”

![power vitual agent ](/assets/images/image1.jpg "Creating new bot")

 ii. The ‘Create a new bot’ dialog box pops up.

 iii. Enter a name for your bot along with a language and environment of choice.

![](/assets/images/image3.jpg)

#### 2. Create some topics:

 i. Click on ‘Topic’ at the left-hand navigation pane.

![Creating new bot](/assets/images/image2.jpg "Creating new topic")

ii. Click on a new topic and give your topic a name; ‘Novel suggestion’

iii. Next, we need to create trigger phrases; here you give words or phrases your users will most likely use. Power Virtual Agents’ natural language capacity uses these trigger phrases to understand the intent of your users.

iv. Save the topic.

v. Click on **‘authoring canvas.’**

Usually, the first step is to display a message to the user; **“I can totally help you out”**. We would follow that message with a question; **“What’s your favorite genre?”**

vi. Click the **'+'** button and follow by **‘Ask a question.’**

![](/assets/images/image5.jpg)

You need to change the identity to **‘multiple-choice options'** and list all the options available to our users. You would notice as you type in a choice, it automatically branches out.

We would keep it nice and simple. In each of our options, you would type in a link to a novel from that genre.

We use the "+" and end the conversation with a survey and click **Save**.

![Multi-choice options in Power bot](/assets/images/image4.jpg "Multi choices options")

### Test your bot:

To test our bot, we would make use of **‘Test bot’** at the left-hand navigation pane.

We would start the conversation with the bot by asking for something, this triggers our topic.

As the conversation progresses, the designer highlights active steps with a green banner and a tick icon in the right canvas.

![Testing a bot in Powe virtual agent.](/assets/images/image7.jpg "Test your bot")

### Publishing your bot

To make your bot available for live use, click **publish**. To complete this process, you need to select the channel you wish to deploy your bot by clicking on **Go to channels**

![Publishing bot to channels](/assets/images/image6.jpg "Publishing bot")

### Monitoring your bot

You can monitor your bot’s usage and performance through the analytics menu in the left-hand navigation pane. On this page, you would see statistics on sessions abandoned, number of sessions resolved, number of conversations, and customer satisfaction ratings.

![Monitoring bot performans](/assets/images/image8.jpg "Monitoring your bot")

We can do much more with our bot, such as transferring the conversation to a human agent, sending users’ information to a team, scheduling meetings as well implementing Power Automation’s functionality. 

### Conclusion
In summary, Power Virtual Agents:
- Helps you build a bot with no coding or AI expertise.
- Makes use of built-in trigger phrases and pre-authored conversations.
- Makes bot building user-friendly and easy.

Thanks for reading! Don’t forget to check my [Github repository](https://github.com/Bennykillua) for intresting open source projects I am working on, follow me on [Twitter](https://twitter.com/Bennykillua) and connect with me on [Linkedin](https://www.linkedin.com/in/ifeanyi-iheagwara)

### Further reading
- [Power Virtual Agents overview](https://docs.microsoft.com/en-us/power-virtual-agents/fundamentals-what-is-power-virtual-agents)


- [Create and delete Power Virtual Agents bots](https://docs.microsoft.com/en-us/power-virtual-agents/authoring-first-bot)


- [Microsoft Power Automate documentation]
(https://docs.microsoft.com/en-us/power-automate/)