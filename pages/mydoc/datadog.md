---
title: Datadog
tags: [integration, datadog]
sidebar: mydoc_sidebar
permalink: docs/datadog.html
summary: "Send events to Squadcast from Datadog"
folder: mydoc
---

See how you can configure a service on Squadcast to get alerts from Datadog.

{{site.data.alerts.note}}
<br/><br/><p>1. Only the users with Account Owner or Admin privileges can configure Services on Squadcast.<br/>
2. At least one <a href="escalation-policies.html">Escalation Policy</a> must be configured before you can add a service.</p>
{{site.data.alerts.end}}

## Using Datadog as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Datadog** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/datadog_1.png)

## Now follow these steps on Datadog:
1.Open **Integrations** page from the sidebar

2.Use the search bar to search for **Webhooks**

3.Once the Webhooks tile appears, hover and click on "Install"

4.Navigate to the **Configuration** tab and scroll to the bottom of the page

5.Under the section **Name and URL**, enter a meaningful name and paste the **Datadog Webhook URL** provided by Squadcast 

![](images/datadog_2.png)

6.Tick the checkbox under the section **Use custom payload**

7.Copy-paste the following JSON in the text box under the **Custom Payload section** 

```json
{

"alertId": "$ALERT_ID",
"eventMessage": "$TEXT_ONLY_MSG",
"title": "$EVENT_TITLE",
"url": "$LINK",
"alertTransition": "$ALERT_TRANSITION"

}
```

8.Click on “Install Integration” to complete the service integration

That's it :) You are now good to go with your Datadog integration!