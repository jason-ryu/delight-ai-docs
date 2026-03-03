# Conversation group

**Conversation Group** enables the AI agent to communicate with users across multiple channels, including SMS, email, in-app messaging, and voice calls. This helps you build a seamless, unified communication experience for your users.

***

## How it works

A **Conversation group** represents a single customer journey that continues across multiple channels without interruption. It enables the AI agent to communicate with a user through in-app messaging, SMS, e-mail, and voice calls as part of one unified support experience.

When a conversation ends on one channel, you can use the **Follow-up trigger** to automatically start a new conversation on another channel at a scheduled time. The new conversation remains independent, but it is grouped under the same Conversation Group for seamless cross-channel tracking.

### Event trigger and follow-up conversation

When a **Follow-up trigger** is enabled, AI agent creates a seamless omni-channel customer experience by consolidating scattered conversations into a single, unified customer support stream.

Follow-up conversations can be supported for the following channels:

* Messenger
* Voice

When a conversation ends in one of the above, a follow-up conversation starts in:

* SMS

{% hint style="info" %}
To learn more, see [our guide on Follow-up triggers](../../../shared-assets/follow-up-triggers.md).
{% endhint %}

***

## Conversation view

Various channels used to address a user's inquiry will be grouped into one conversation group called **Conversation group** as shown in the screenshot below.

<figure><img src="../../../../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

### Channel sequence

In the conversation details view, you can track the cross-channel interactions between your AI agent and a user. This section offers a clear overview and detailed metrics on omni-channel communications, known as the Channel sequence.

### Conversation group insights

The timeline and summary in the **Conversation group** panel provide a quick understanding of conversation history and valuable customer insights. When all conversations are closed, it offers a comprehensive analysis on the entire conversation group, including:

* Category
* Overall summary
* Resolution status
* AI handle time
* User sentiment

### Conversation group message count

The number of AI-generated messages and user messages from all channels in the channel sequence. This is also provided when all conversations in the group are closed.

### First conversation ID

When a conversation group is formed, use the first conversation's ID as its unique identifier. You can also find this in **Conversation information > Basic information** in the conversation detail view or **Evaluate > Report > Conversations**.
