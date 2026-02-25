# Follow-up triggers

Utilize follow-up triggers to enhance communication for users by providing seamless omnichannel support. These triggers activate specific actions, such as shifting conversations to different channels or making an API call, offering improved assistance with user inquiries.

***

## Types

Delight AI agent supports triggers for two types of events: conversation event and actionbook event.

<table><thead><tr><th width="163.03125">Event</th><th>Trigger condition</th><th>Action</th></tr></thead><tbody><tr><td>Conversation</td><td>When a conversation ends</td><td>it create a new conversation.</td></tr></tbody></table>

### Supported channels

When a **Follow-up trigger** is enabled, AI agent creates a seamless omni-channel customer experience by consolidating scattered conversations into a single, unified customer support stream.

Follow-up conversations can be supported for the following channels:

* Messenger
* Voice

When a conversation ends in one of the above, a follow-up conversation starts in:

* SMS

***

## How to create

You can create and manage triggers under **Workspace settings > Shared assets > Follow-up triggers**.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

### Conversation event trigger

1. Navigate to the **Conversation event** tab in **Workspace settings > Shared assets > Follow-up triggers**.
2. Click **Add+** in the top-right corner of the screen.
3.  Configure the name and flow of the trigger.

    <figure><img src="../../.gitbook/assets/convo trigger.png" alt=""><figcaption></figcaption></figure>

    1. Flow - Condition: you can set a condition when the trigger should be initiated
       1. Channel
       2. Resolution status
    2. Flow - Acton: you can determine which channel to use when starting a follow-up conversation with the user. When creating a new conversation, AI will send an opening message to the user.
       1. Channel
       2. Resolution status
       3. Message: Provide an instruction and a message sample for your AI agent to reference. You can determine whether to let the agent refer to user memories when generating the message.

{% hint style="info" %}
Follow-up triggers create a Conversation group. To learn more, [see our guide under Evaluate > Conversations > Conversation group](../evaluate/reports/conversations/conversation-group.md).
{% endhint %}
