---
hidden: true
---

# Deployment

Implement a strategic deployment plan when rolling out a new version to your users. Delight AI agent supports a strategic deployment system for a stable introduction of updates with two different deployment plans.&#x20;

## How it works

AI agent changes move through three environments before reaching users.

### **Deployment flow**

* **Development**\
  Explore AI agent features and configure the agent for your service.\
  Deploy completed changes to the **Staging** environment.
* **Staging**\
  Test updates deployed from **Development** before releasing them to users.\
  Once validation is complete, deploy the latest version to **Production**.
* **Production**\
  Monitor the AI agent’s performance and CSAT ratings.\
  Analyze operational metrics and identify opportunities for improvement.

### **Production deployment strategies**

Deployments from **Staging** to **Production** support two rollout strategies:

<table><thead><tr><th width="156.59375">Strategy</th><th width="351.453125">Description</th><th>Affected users</th></tr></thead><tbody><tr><td>Full deployment</td><td>Deploys the new version to all users at once.</td><td>Apply to 100% of users.</td></tr><tr><td>Gradual deployment</td><td>Deploys the new version to a small portion of the user base first then gradually expand the coverage.</td><td>Can adjust the traffic split.<br>e.g., 10% → 30% → 100%</td></tr></tbody></table>

## How to use

Follow the instructions below for deployment.

1. Navigate to **Overview** of your AI agent's **Staging** environment.
2. If there is a new version to deploy to **Production**, click the **Changes to deploy** button at the bottom in the left menu bar.
3.  You can choose between gradual deployment and full deployment.&#x20;

    1. **Gradual deployment**: Set the traffic split for the current version and the new version. You can always come back to the Deployment settings page and adjust the ratio.
    2. **Full deployment**: Select a version to roll out. Once deployed, the change will impact all users.

    <figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Gradual vs. Full deployment</p></figcaption></figure>
4.  If you opted for gradual deployment, the traffic ratio will be displayed in the Overview page as highlighted below. To change the traffic ratio to roll back or fully roll out the new version, click the **Deployment settings** button.

    <figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>
5.  Then click the **Edit deployment strategy** button underneath the close button to update the configurations.<br>

    <figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
You can always go back and forth between gradual deployment and full deployment. Adjust the rollout plan according to your service environment.
{% endhint %}
