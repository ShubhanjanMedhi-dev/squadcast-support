---
title: Coralogix
tags: [integration, coralogix]
last_updated:
keywords:
summary: "Get alerts from Coralogix into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/coralogix.html
folder: mydoc
---

## Pre-requisites
1.  A valid Squadcast cloud subscription 
2. A user account in Coralogix

Follow the steps below to configure a service so as to push related alert data from Coralogix into Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Coralogix as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Coralogix** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/coralogix_1.png)

## Create a Squadcast Webhook in Coralogix

1.Login to Coralogix and click on the **Settings** button as shown below.

![](images/coralogix_2.png)

2.Click on the **Integrations** tab.

![](images/coralogix_3.png)

3.Click on the **+** button to add a new integration.

![](images/coralogix_4.png)

4.Select WebHook from the dropdown. Paste the Webhook URL copied from Squadcast dashboard in the **URL** field. Select the **Method** as *Post*. Click on Save.

![](images/coralogix_5.png)

5.Now, go to the **Alerts** tab.

![](images/coralogix_6.png)

6.Click on **New Alert**.

![](images/coralogix_7.png)

7.Fill up the alerting specs as per your requirement. In the **Conditions** section, enable the **Notify When Resolved**.

![](images/coralogix_8.png)

8.In the **Recipients** section, under **Webhook Recipients**, select the Squadcast Webhook URL you just created. Finally save the alert.

![](images/coralogix_9.png)

Now, whenever Coralogix sends an alert with `alert_action` **trigger** on the Squadcast webhook, an Incident gets created in Squadcast.
Similarly, when Coralogix sends an alert with `alert_action` **resolve** on the Squadcast webhook, the corresponding triggered incident in Squadcast gets resolved.