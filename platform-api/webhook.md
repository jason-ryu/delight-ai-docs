# Webhook

With Delight AI agent, you can programmatically configure webhook endpoints. Use this API to set the destination URL, choose which events to subscribe to, and manage settings per AI agent or at the application level.

{% hint style="info" %}
To learn more about webhook events and their payload formats, see the [Webhook guide](../dashboard-guide/webhook.md).
{% endhint %}

***

## Platform API Authentication

A typical HTTP request to the Chat API includes the following headers for authentication:

### Headers

- `app_id` and `ai_agent_id`: Can be found in Delight AI dashboard or its URL
- Content-Type: Every request must include a `Content-Type` header.
- Api-Token: Either the master API token or a secondary API token is required for the Sendbird server to [authenticate](https://sendbird.com/docs/chat/platform-api/v3/prepare-to-use-api) your API requests.

### Base URL

The base URL used for the AI agent APIs is formatted as shown below:

```
https://api-{app_id}.sendbird.com/v3
```

{% hint style="info" %}
To learn more about how to use Platform APIs for Delight AI agent, see [How to use Platform API](how-to-use-platform-api.md).
{% endhint %}

***

## Get webhook setting

Retrieves the current webhook configuration. By default, this returns the application-level setting. To retrieve the setting for a specific AI agent, pass the `ai_agent_id` query parameter.

### API specification

#### HTTP request

```http
GET https://api-{application_id}.sendbird.com/v3/ai_agent/settings/webhook
```

#### Query parameters

<table><thead><tr><th width="180">Parameter name</th><th width="130">Type</th><th>Description</th></tr></thead><tbody><tr><td>ai_agent_id</td><td>string</td><td>Specifies the unique ID of the AI agent. If omitted, the application-level webhook setting is returned.</td></tr></tbody></table>

### Response

If successful, this action returns the webhook setting in the response body like the following:

```json
{
  "app_id": "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
  "ai_agent_id": "my_agent_001",
  "enabled": true,
  "url": "https://example.com/webhook",
  "category_subscriptions": [
    "*"
  ],
  "signature_secret": "a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
  "available_categories": [
    "conversation:started",
    "conversation:closed",
    "conversation:redacted",
    "conversation:analyzed",
    "message:user_sent",
    "message:ai_agent_sent",
    "message:human_agent_sent",
    "flagged_message:hallucination_detected",
    "handoff"
  ]
}
```

<table><thead><tr><th width="230">Property</th><th width="130">Type</th><th>Description</th></tr></thead><tbody><tr><td>app_id</td><td>string</td><td>Specifies the application ID.</td></tr><tr><td>ai_agent_id</td><td>string</td><td>Specifies the AI agent ID. Empty string for application-level settings.</td></tr><tr><td>enabled</td><td>boolean</td><td>Indicates whether the webhook is enabled.</td></tr><tr><td>url</td><td>string</td><td>Specifies the webhook endpoint URL.</td></tr><tr><td>category_subscriptions</td><td>array</td><td>Lists the event categories currently subscribed to. <code>"*"</code> means all events.</td></tr><tr><td>signature_secret</td><td>string</td><td>Specifies the HMAC-SHA256 signing secret used to verify webhook deliveries.</td></tr><tr><td>available_categories</td><td>array</td><td>Lists all event categories available for subscription.</td></tr></tbody></table>

***

## Create or update webhook setting

Creates or updates the webhook configuration. If no setting exists for the given scope, a new one is created with an auto-generated `signature_secret`. If a setting already exists, it is updated — the `signature_secret` is never overwritten by this endpoint.

To configure a specific AI agent, include `ai_agent_id` in the request body. If omitted, the application-level setting is updated.

### API specification

#### HTTP request

```http
PUT https://api-{application_id}.sendbird.com/v3/ai_agent/settings/webhook
```

### Request body

<table><thead><tr><th width="230">Property</th><th width="130">Type</th><th>Description</th></tr></thead><tbody><tr><td>ai_agent_id</td><td>string</td><td>(Optional) Specifies the unique ID of the AI agent. If omitted, the application-level setting is updated.</td></tr><tr><td>enabled</td><td>boolean</td><td>(Required) Determines whether to enable or disable the webhook.</td></tr><tr><td>url</td><td>string</td><td>(Required) Specifies the webhook endpoint URL. Must start with <code>http://</code> or <code>https://</code>.</td></tr><tr><td>category_subscriptions</td><td>array</td><td>(Required) Lists the event categories to subscribe to. Use <code>["*"]</code> to subscribe to all events, or specify individual categories. <code>"*"</code> cannot be combined with other categories.</td></tr></tbody></table>

### Response

If successful, this action returns the updated webhook setting in the same format as the [Get webhook setting](webhook.md#get-webhook-setting) response.

***

## Subscribable event categories

The following event categories are available for subscription via `category_subscriptions`:

<table><thead><tr><th width="320">Category</th><th>Description</th></tr></thead><tbody><tr><td>*</td><td>Subscribe to all events. Cannot be combined with individual categories.</td></tr><tr><td>conversation:started</td><td>A conversation started.</td></tr><tr><td>conversation:closed</td><td>A conversation has been closed.</td></tr><tr><td>conversation:redacted</td><td>PII redaction has been completed for a closed conversation.</td></tr><tr><td>conversation:analyzed</td><td>Analytics processing has been completed for a closed conversation.</td></tr><tr><td>handoff</td><td>Handoff to a human agent takes place.</td></tr><tr><td>message:user_sent</td><td>A user sends a message to AI agent.</td></tr><tr><td>message:ai_agent_sent</td><td>Your AI agent sends a message to the user.</td></tr><tr><td>message:human_agent_sent</td><td>A human agent sends a message to the user after handoff.</td></tr><tr><td>flagged_message:hallucination_detected</td><td>Your AI agent generated a response at a low confidence level.</td></tr></tbody></table>

***

## Signature verification

Every webhook delivery includes an `X-SendBird-Signature` header containing an HMAC-SHA256 signature. Use the `signature_secret` from your webhook setting to verify the authenticity of incoming webhooks.

### How to verify

1. Retrieve the raw request body as a string.
2. Compute the HMAC-SHA256 hash using your `signature_secret` as the key and the request body as the message.
3. Compare the computed hash with the value in the `X-SendBird-Signature` header.
