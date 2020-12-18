---
title: Bugsnag
tags: [Azure-Monitor, Buildkite]
keywords: 
last_updated: 
summary: "Send error alerts to Squadcast from Bugsnag"
sidebar: mydoc_sidebar
permalink: docs/bugsnag.html
folder: mydoc
---

Follow the steps below to configure a Service so as to receive error alerts from Bugsnag.

Squadcast will then process this information to create incidents for this Service as per your preferences.

### In Squadcast: Configuring Bugsnag as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service-1.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1-3.png)

Select **Bugsnag** from **Alert Source** drop down and copy the Webhook URL shown.

![](images/bugsnag_1.png)

### In Bugsnag: Create a Squadcast Webhook for error alerts

In the app, within your Project, click on the Settings icon on the top right and select Project Settings.

![](images/bugsnag_2.png)

Scroll down a little to the Integrations and email section and select Data forwarding.

![](images/bugsnag_3.png)

Select Webhook to configure custom webhook.

![](images/bugsnag_4.png)

Paste the Webhook URL copied from Squadcast under Webhook URL. Test the configuration by clicking on Test. This would generate test error alert which would create a test incident in Squadcast.

![](images/bugsnag_5.png)

Once the integration is verified, click on Save. Verify that the newly configured Webhook is listed under Configured integrations.

![](images/bugsnag_6.png)

Click on the Webhook to configure when you should be notified for errors by enabling different options in the **Notify me when** section. Here is [Bugsnag's documentation](https://docs.bugsnag.com/product/integrations/data-forwarding/webhook/) to understand what each of these settings mean and when you would be notified.

![](images/bugsnag_7.png)

{{site.data.alerts.blue-note}}
<b>Note:</b>
<br/><br/><p>Except for "This project has a spike in errors" and "This project has a new release", every other "Notify me when" type is supported.</p>
{{site.data.alerts.end}}

That is it, you are now good to go! Whenever an error alert is triggered in Bugsnag, an incident will be automatically created in Squadcast based on your Notification rules in Bugsnag. Whenever, **an error is resolved in Bugsnag, the corresponding incident is auto-resolved in Squadcast as well**.