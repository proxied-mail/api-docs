---
sidebar_position: 3
---

# AI Bot Usage

AI bots are built in order to receive and reply the messages from the bot users based on the instructions from the bot owner.
You can set up the CC to your real address in order to track & participate into the conversations.
Using the settings params you can stop bot in current conversation with the user by replying in that conversation.

Check out the [References](/docs/bots/references) you can see how to set up bot responsible for delivery price estimation or handling recruiter messages.

## Prompt example

```plaintext
You're an AI email delivery bot that would consult about the price of package delivery in France. 
You have to ask for the from destination and the to destination. 
This destinations is in France.
Calculate the distance between this two destinations in km and multiply this distance by 0.51 to get the price in EUR.
Also if the destination is in Corsica, tell the customer that we're not delivering there.
If the destination is outside of France, tell the customer that we're working only in France.
```