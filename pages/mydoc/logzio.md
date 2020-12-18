---
title: Logz.io
tags: [Logstash, ManageEngine-Opmanager]
keywords: 
last_updated: 
summary: "Send log alerts to Squadcast from Logz.io (ELK stack)"
sidebar: mydoc_sidebar
permalink: docs/logz.io.html
folder: mydoc
---

Follow the steps below to configure a Service so as to receive log alert data from Logz.io.

Squadcast will then process this information to create incidents for this Service as per your preferences.

### In Squadcast: Configuring Logz.io as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service-1.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1-3.png)

Select **Logz.io** from **Alert Source** drop down and copy the Webhook URL shown.

![](images/logzio_1.png)

### In Logz.io: Create a Squadcast Webhook alert

In the app, go to Alerts & Events > Notification endpoints to create the webhook.

![](images/logzio_2.png)

Click on Add endpoint.

![](images/logzio_3.png)

Fill in the form as shown below:

- Type: Custom
- Name: Squadcast Webhook
- Description (optional)
- URL: Paste the URL endpoint that was copied from Squadcast Service for Logz.io
- Method: POST
- Run the test to see if you received a test alert in Squadcast
- Click on Save

Find more details on how each of these parameters can be configured [here](https://docs.logz.io/user-guide/integrations/custom-endpoints.html).

![](images/logzio_4.png)

Next, to create the alert itself, you can either:

- Go to Alerts & Events > New Alert or,
- Click on Create Alert from the Kibana dashboard

![](images/logzio_5.png)

Find more details on how each of these parameters can be configured [here](https://docs.logz.io/user-guide/alerts/configure-an-alert.html).

Give the alert a title.

Now, you will have to fill out the 3 sections:

(a) Search for... section:

- Either enter your Search query or verify that the query present is correct
- Choose to Group By certain fields
- Select Accounts to be searched
- Choose to repeat this (by adding another query), join the queries, etc.

![](images/logzio_6.png)

(b) Trigger if... section:

- Add trigger condition for the alert and add one or more thresholds for the trigger

![](images/logzio_7.png)

(c) Notify section: 

- Add a Description for the alert (which will be visible for these incidents in Squadcast) 
- Associate Tags (if any) 
- Who to send it to -> choose Squadcast Webhook 
- Choose a wait time between notifications as needed 
- Output format -> choose JSON 
- You can choose to either send all log fields or custom fields

![](images/logzio_8.png)

Click on Save.

![](images/logzio_9.png)

That is it, you are now good to go! Whenever a log alert is triggered in Logz.io, an incident will be created automatically in Squadcast.

{{site.data.alerts.blue-note}}
<b>Note:</b>
<br/><br/><p>This integration does not support alert auto-resolve.</p>
{{site.data.alerts.end}}