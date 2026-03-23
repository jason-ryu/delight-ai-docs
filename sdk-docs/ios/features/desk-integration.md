# Desk integration

In Delight AI agent, when a conversation has been handed off to Sendbird Desk, you can retrieve Desk ticket information directly from the AI Agent SDK. This allows you to access ticket details — such as status, priority, assigned agent, and custom fields — without integrating a separate Desk SDK.

{% hint style="info" %}
Desk ticket information is only available for conversations that have been handed off to Desk. The channel must have a linked Desk ticket for this feature to work.
{% endhint %}

This guide covers:
- [Retrieve a Desk ticket](#retrieve-a-desk-ticket)
- [Refresh ticket data](#refresh-ticket-data)
- [API references](#api-references)
- [Limitations](#limitations)

---

## Retrieve a Desk ticket

You can retrieve a Desk ticket by its ID using the `getTicket` method. The ticket ID is available through `channel.conversation?.handoff?.ticketId` when a conversation has been handed off to Desk. The `getTicket` method is a static async function that throws on failure.

```swift
import SendbirdAIAgent

guard let ticketId = channel.conversation?.handoff?.ticketId else { return }

do {
    let ticket = try await DeskTicket.getTicket(id: ticketId)
    // Access ticket properties
    let status = ticket.status
    let priority = ticket.priority
    let assignedAgent = ticket.agent
} catch {
    // Handle error
}
```

---

## Refresh ticket data

To get the latest ticket data, call the `refresh` method on an existing `DeskTicket` instance. This updates the ticket object with the most recent information from the server.

```swift
do {
    try await ticket.refresh()
    // The ticket now contains updated data
    let updatedStatus = ticket.status
} catch {
    // Handle error
}
```

---

## API references

### DeskTicket

`DeskTicket` represents a Sendbird Desk ticket linked to a conversation.

#### List of properties

| Property name | Type | Description |
|---|---|---|
| id | Int64 | The unique ID of the ticket. |
| name | String | The name of the ticket. |
| status | DeskTicket.Status | Indicates the current status of the ticket. |
| priority | DeskTicket.Priority | Indicates the priority level of the ticket. |
| agent | DeskTicket.Agent? | The agent currently assigned to the ticket. |
| channelUrl | String | The URL of the channel associated with the ticket. |
| info | String? | Additional information about the ticket. |
| customFields | [String: String] | Custom fields associated with the ticket. |
| createdAt | Int64 | The timestamp when the ticket was created, in Unix milliseconds format. |

#### List of methods

| Method | Description |
|---|---|
| getTicket(id: Int64) | Retrieves a Desk ticket by its ID. This is a static async function that throws on failure. |
| refresh() | Refreshes the ticket data with the latest information from the server. This is an async function that throws on failure. |

### DeskTicket.Status

`DeskTicket.Status` represents the status of a Desk ticket.

#### List of values

| Value | Description |
|---|---|
| initialized | The ticket has been created but not yet processed. |
| unassigned | The ticket is not assigned to any agent. |
| assigned | The ticket is assigned to an agent. |
| workInProgress | The agent is actively working on the ticket. |
| waitForCustomer | The agent is waiting for a response from the customer. |
| closed | The ticket has been resolved and closed. |
| proactive | The ticket was created proactively by an agent. |
| unknown | An unrecognized status value. |

### DeskTicket.Priority

`DeskTicket.Priority` represents the priority level of a Desk ticket.

#### List of values

| Value | Description |
|---|---|
| low | Low priority. |
| medium | Medium priority. |
| high | High priority. |
| urgent | Urgent priority. |
| unknown | An unrecognized priority value. |

### DeskTicket.Agent

`DeskTicket.Agent` represents the agent assigned to a Desk ticket.

#### List of properties

| Property name | Type | Description |
|---|---|---|
| id | String | The unique ID of the agent. |
| name | String | The display name of the agent. |
| profileUrl | String? | The URL of the agent's profile image. |

---

## Limitations

- This feature provides read-only access to ticket information. You can retrieve and refresh ticket data, but cannot create, update, or close tickets.
- This feature does not fully replace the Desk SDK. Ticket creation, agent actions, and real-time ticket events still require the Desk SDK.
- Desk ticket information is only available for conversations that have been handed off to Desk.
