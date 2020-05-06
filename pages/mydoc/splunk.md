---
title: Splunk
tags: [integration, splunk]
keywords: 
last_updated: 
summary: "Get Splunk alerts into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/splunk.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Splunk. Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Splunk as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Splunk** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/splunk_1.png)

## Create a Squadcast webhook alert in Splunk

In your Splunk dashboard, click on **Search & Reporting** under **Apps**.

![](images/splunk_2.png){: style="max-width: 30%" }

Do the required search and then click on **Save As** and select **Alert**.

![](images/splunk_3.png)

In the **Save As Alert** box, enter the title, description and other Trigger Conditions and under **Trigger Actions**, click on the **Add Actions** button and select **Webhook** and enter the webhook url from the previous step under **URL** and click the **Save** button.

![](images/splunk_4.png)

That's it! The Splunk Integration is completed and whenever an alert is fired for your search query, an alert will get created in Squadcast as well.