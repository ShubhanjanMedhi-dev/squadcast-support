---
title: Coralogix
tags: [CopperEgg, Crashlytics]
last_updated:
keywords:
summary: "Get alerts from Coralogix into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/coralogix.html
folder: mydoc
---

This document will help you integrate Coralogix with Squadcast.

Coralogix’s machine learning powered platform turns cluttered log data into meaningful patterns and trends, helping users gain valuable insights. 
Route detailed log alerts from Coralogix to the right users in Squadcast.

## How to integrate Coralogix with Squadcast

### In Squadcast: Using Coralogix as an Alert Source

On the **Sidebar**, click on **Services**.

![](images/integration_1-1.png)

Select an existing Service or **Add service** 

![](images/integration_1-2.png)

Click the corresponding **Alert Sources**

![](images/integration_1.png)

Search for **Coralogix** from the **Alert Source** drop down menu and copy the webhook URL shown.

![](images/coralogix_1.png)

### In Coralogix: Create a Squadcast Webhook

Login to Coralogix and click on the **Settings** present under your user icon.

![](images/coralogix_2.png)

Click on the **Webhooks** tab and click on the **+** button to add a new Webhook.

![](images/coralogix_3.png)

(a) Give the Webhook a name in the Alias field.

(b) Choose WebHook as the option from the drop down.

(c) Paste the copied Webhook URL from Squadcast in the URL field.

(d) Choose Method as Post.

(e) Click on Test Configuration. Go back to Squadcast and verify if the test alert from Coralogix triggered an incident. If it did, the integration is working successfully.

(f) Click on Save.

![](images/coralogix_4.png)

Now, go to the **Alerts** tab and click on **New Alert**.

![](images/coralogix_5.png)

Fill up the alerting specs as per your requirement. In the **Conditions** section, enable the **Notify When Resolved** toggle.

![](images/coralogix_6.png)

In the **Recipients** section, under **Webhook Recipients**, select the Squadcast Webhook URL you just created and click on **Create Alert**.

![](images/coralogix_7.png)

That’s it! Your Coralogix integration is complete, you are good to go.

Now, whenever Coralogix sends an alert with `alert_action` **trigger** on the Squadcast webhook, an Incident gets created in Squadcast.

Similarly, when Coralogix sends an alert with `alert_action` **resolve** on the Squadcast webhook, the corresponding triggered incident in Squadcast gets **automatically resolved**.