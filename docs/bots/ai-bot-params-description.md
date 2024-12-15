---
sidebar_position: 4
---

# AI Bot Params Description

* Prompt. Describe the instructions and information contained in the bot.
* Model: OpenAI model.
* CC all messages to the real address. This option lets you copy all incoming conversations with the bot to your real address attached to the proxy-email. You can use it to track how your bot is working or to participate/stop the conversation depending on the interruption flag. You will get both messages from the bot and the user.
* Allow interruption. If you put the Demand CC option, you will be able to stop the bot by replying to any email in the bot-user conversation. After the first reply but will stop and you will be 1-1 with the bot user.
* Session length, minutes. This option shows how long is the user-bot conversation window. If you set it to 30 minutes bot will forget all previous messages with the user and start the conversation over if the last message in the conversation is older than that period of time.

![Params illustration](/img/paramsillustrate.png)