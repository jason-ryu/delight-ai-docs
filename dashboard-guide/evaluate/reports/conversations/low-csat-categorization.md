# Low CSAT categorization

In Delight AI agent, when a user gives a low CSAT (Customer Satisfaction) score — one or two out of five — the AI agent automatically analyzes the conversation and classifies it into up to two categories that explain the likely cause of dissatisfaction.

Each categorized conversation includes an AI-generated reason summary, so you can quickly understand what went wrong without reviewing the full conversation.

{% hint style="info" %}
Low CSAT categories and reasons are available for conversations created after March 3, 2026.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/conversation_list.png" alt="Conversations list in the Evaluate tab showing CSAT scores" width="800"><figcaption></figcaption></figure>

---

## What you can do

With Low CSAT categorization, you can:

- Filter conversations with low CSAT scores by dissatisfaction category.
- View the AI-generated category and reason in the conversation detail view.
- Identify patterns across dissatisfaction categories to improve AI agent performance.

| Category | Description |
|----------|-------------|
| Inadequate compensation | Compensation offered — such as coupons or refunds — may not have met user expectations. |
| Inadequate response | AI agent's response may not have adequately addressed the user's question, possibly due to gaps in your knowledge base or instructions. |
| Escalation refusal | User declined the offer to connect with a human agent, despite the AI suggesting a handoff. |
| Situation frustration | User likely expressed frustration with the situation itself — such as shipping delays, service outages, or product issues — rather than the AI agent's response. |
| Others | Does not fall under any of the above categories. |

{% hint style="info" %}
Each conversation can be assigned up to two categories. When **Escalation refusal** and **Situation frustration** co-occur, the refusal likely stems from high situational frustration or an issue beyond the AI's capabilities.
{% endhint %}

---

## How to use Low CSAT categorization

### Step 1: Filter conversations in dashboard

1. Navigate to **Evaluate** > **Conversations**.
2. Click the **CSAT** filter dropdown and select **Low CSAT scores (1, 2)**. The list updates to show only conversations with a low CSAT score.

<figure><img src="../../../../.gitbook/assets/CSAT_score_clicked.png" alt="CSAT filter dropdown with Low CSAT selected" width="375"><figcaption></figcaption></figure>

3. When the **Low CSAT category** filter appears, select one or more categories to narrow the results.

<figure><img src="../../../../.gitbook/assets/CSAT_category_clicked.png" alt="Low CSAT category multi-select filter with category options" width="375"><figcaption></figcaption></figure>

{% hint style="info" %}
To narrow results further, apply the **AI confidence** filter to focus on high-certainty categorizations, or use the **Date range** filter.
{% endhint %}

### Step 2: Review the AI-generated reason

Click a conversation in the filtered list to open the conversation detail view. For low CSAT conversations, the **Insights** panel on the right displays a **Low CSAT** section with the category and reason for dissatisfaction.

<figure><img src="../../../../.gitbook/assets/conversation_details.png" alt="Conversation detail view with Insights panel showing Low CSAT category and reason" width="800"><figcaption></figcaption></figure>

---

## What's next

Once you've reviewed Low CSAT conversations and identified patterns, consider the following:

### Focus on AI-attributable categories first

Conversations categorized as **Inadequate response** or **Inadequate compensation** are the most direct signal that changes to your AI agent configuration may help. Start by reviewing a sample of these conversations to understand what's going wrong.

### Use categories to prioritize, not just to track volume

A high volume of **Situation frustration** may reflect external service issues rather than AI problems. Separating these from AI-attributable categories helps you focus your efforts where they matter most.

### Revisit after making changes

After updating your AI agent's instructions, knowledge sources, or flows, use the date range filter to compare Low CSAT category distribution before and after your changes.

### Monitor Others for emerging patterns

Periodically review conversations categorized as **Others** to identify recurring issues that may warrant a new category or specific action.

