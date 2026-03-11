---
hidden: true
---

# Deployment

Implement a strategic deployment plan when rolling out a new version to your users. Delight AI agent supports a strategic deployment system for a stable introduction of updates with two different deployment plans.&#x20;

## How it works

In Delight AI agent, deployment flow among environments follows as described below:

Development environment: explore features offered within the AI agent and tailor the agent to best suit your service needs. Deploy the changes you've made to the **Staging** environment.

Staging environment: test out the update introduced from the **Development** environment before rolling it out to live service. Make sure that your AI agent is ready for real-life interaction with your users. Once it's ready, deploy the latest version to **Production**.

Production environment: monitor AI agent's performance and customer satisfaction (CSAT) ratings. Analyze its key metrics and find room for improvement.&#x20;

As AI agent deployment from Staging to Production merits more discreet approach, Delight AI agent supports two different rollout strategy — full deployment and gradual deployment.

### Full deployment vs. gradual deployment

When deploying changes in your AI agent from **Staging** to **Production**, you can choose either options:

<table><thead><tr><th width="156.59375">Strategy</th><th width="351.453125">Description</th><th>Affected users</th></tr></thead><tbody><tr><td>Gradual deployment</td><td>Deploys the new version to a small portion of the user base first then gradually expand the coverage.</td><td>Can adjust the traffic split at any time.<br>e.g., 10% → 30% → 100%</td></tr><tr><td>Full deployment</td><td>Deploys the new version to all users at once.</td><td>Apply to 100% of users</td></tr></tbody></table>

## How to use

Follow the instructions below for deployment.

1. Navigate to **Overview** of your AI agent's **Staging** environment.
2. If there is a new version to deploy to **Production**, click the **Changes to deploy** button at the bottom in the left menu bar.
3.  You can choose between gradual deployment and full deployment.&#x20;

    1. **Gradual deployment**: Set the traffic split for the current version and the new version. You can always come back to the Deployment settings page and adjust the ratio.
    2. **Full deployment**: Select a version to roll out. Once deployed, the change will impact all users.

    <figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Gradual vs. Full deployment</p></figcaption></figure>
4.  If you opted for gradual deployment, the traffic ratio will be displayed in the Overview page as highlighted below. To change the traffic ratio to roll back or fully roll out the new version, click the **Deployment settings** button.

    <figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>
5.  Then click the **Edit deployment strategy** button to update the configurations.

    <figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>
