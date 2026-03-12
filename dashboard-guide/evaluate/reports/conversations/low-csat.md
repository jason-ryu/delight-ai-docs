# Low CSAT

In Delight AI agent, Low CSAT helps you identify conversations where users gave a low CSAT (Customer Satisfaction) score — one or two out of five. When a user submits a low score, the AI agent automatically analyzes the conversation and assigns up to two categories that explain the likely cause of dissatisfaction.

Instead of manually reviewing each conversation, you can filter by dissatisfaction category and check the AI-generated reason to understand what went wrong.

{% hint style="info" %}
Low CSAT categories and reasons are available for conversations created after March 3, 2026.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/conversation_list.png" alt="Conversations list in the Evaluate tab showing CSAT scores" width="800"><figcaption></figcaption></figure>

---

## What you can do

With **Low CSAT**, you can:

- Filter conversations with low CSAT scores by dissatisfaction category.
- View the AI-generated category and reason in the conversation detail view.
- Identify patterns across dissatisfaction categories to improve AI agent performance.

The AI agent classifies each low CSAT conversation into up to two of the following categories, listed in order of impact.

| Category | Description |
|----------|-------------|
| Inadequate compensation | Dissatisfaction with compensation offered, such as coupons or refunds. |
| Inadequate response | AI agent's response did not adequately address the user's question. |
| Escalation refusal | User declined the offer to connect with a human agent. |
| Situation frustration | Frustration with external factors such as delays or service quality issues. |
| Others | Does not fall under any of the above categories. |

---

## How to use Low CSAT

### Step 1: Filter conversations in dashboard

1. Navigate to **Evaluate** > **Conversations**.
2. Click the **CSAT** filter dropdown and select **Low CSAT**. The list updates to show only conversations with a score of one or two.

<figure><img src="../../../../.gitbook/assets/CSAT_score_clicked.png" alt="CSAT filter dropdown with Low CSAT selected" width="375"><figcaption></figcaption></figure>

3. After selecting **Low CSAT**, a **Low CSAT category** filter automatically appears. Select one or more categories to narrow the results.

<figure><img src="../../../../.gitbook/assets/CSAT_category_clicked.png" alt="Low CSAT category multi-select filter with category options" width="375"><figcaption></figcaption></figure>

4. To narrow results further, apply the **AI confidence** filter to focus on high-certainty categorizations, or use the **Date range** filter.

### Step 2: Review the AI-generated reason

Click a conversation in the filtered list to open the conversation detail view. For conversations with a CSAT score of one or two, the **Insights** panel on the right displays a **Low CSAT** section with the category and reason for the dissatisfaction.

<figure><img src="../../../../.gitbook/assets/conversation_details.png" alt="Conversation detail view with Insights panel showing Low CSAT category and reason" width="800"><figcaption></figcaption></figure>

