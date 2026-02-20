---
hidden: true
---

# Follow-up triggers

Utilize follow-up triggers to enhance communication for users by providing seamless omnichannel support. These triggers activate specific actions, such as shifting conversations to different channels or making an API call, offering improved assistance with user inquiries.

***

## Types

Delight AI agent supports triggers for two types of events: conversation event and actionbook event.

<table><thead><tr><th width="163.03125">Event</th><th>Trigger condition</th><th>Action</th></tr></thead><tbody><tr><td>Conversation</td><td>When a conversation ends</td><td>it create a new conversation.</td></tr></tbody></table>

***

## How to create&#x20;

You can create and manage triggers under **Workspace settings > Shared assets > Follow-up triggers**.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### Conversation event trigger

1. Navigate to the **Conversation event** tab in **Workspace settings > Shared assets > Follow-up triggers**.
2. Click **Add+** in the top-right corner of the screen.
3.  Configure the name and flow of the trigger.



    <figure><img src="../../.gitbook/assets/convo trigger.png" alt=""><figcaption></figcaption></figure>

    1. Flow - Condition: you can set a condition when the trigger should be initiated
       1. Channel
       2. Resolution status
    2. Flow - Acton: you can determine which channel to use when starting a follow-up conversation with the user. When creating a new conversation, AI will send an opening message to the user.&#x20;
       1. Channel
       2. Resolution status
       3. Message: Provide an instruction and a message sample for your AI agent to reference. You can determine whether to let the agent refer to user memories when generating the message.

{% hint style="info" %}
user memory - link to FYC message
{% endhint %}

***

## How to manage&#x20;

You can determine which follow-up triggers to use under **Build > Follow-up triggers**. Toggle on and off each trigger to enable triggers.&#x20;

To update the settings of the triggers, do either of the following:&#x20;

* Click **Manage follow-up trigger** in the top-right corner of the screen or&#x20;
* Navigate directly to **Workspace settings > Shared assets > Follow-up triggers** in Delight AI agent dashboard.&#x20;

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Follow-up triggers inevitably create a Conversation group. To learn more about the conversation group, [see our guide under Evaluate > Conversations > Conversation group](../evaluate/conversations/conversation-group.md).
{% endhint %}
