---
title: ManageEngine Opmanager
tags: [integration, manage engine, opmanager]
keywords: 
last_updated: 
summary: "Get alerts from ManageEngine OpManager into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/manageengine-opmanager.html
folder: mydoc
---

Follow the steps below to configure a service so as to push related alert data from ManageEngine OpManager onto Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using ManageEngine OpManager as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **ManageEngine OpManager** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/opmanager_1.png)

## Create a Squadcast Webhook in ManageEngine OpManager

- Go to you /Opmanager/bin folder and run the following command 

```
sudo wget https://raw.githubusercontent.com/squadcastHub/squadcast-opmanager-script/master/sq-opmanager-script.py
```

Once the file is downloaded please make sure that the file has execute permissions for your ManageEngine OpManager user. 

If not, then please provide the same using the following command

```
sudo chmod +x sq-opmanager-script.py
```

- Login to ManageEngine OpManager. 
- Go to Inventory->Devices and select the device whose alerts you want to send to Squadcast. 
- Click the **Envelope Icon** on the top right corner to configure notifications and click **Add**

![](images/opmanager_2.png)

Select Run Program. 
In Command Name paste the following:

```
./sq-opmanager-script.py
```

In Program Arguments paste the following (make sure to replace the url with the Webhook URL you copied from the Squadcast dashboard):

```
"https://api.squadcast.com/v1/incidents/opmanager/85b5aa611b99d9c4c6a70fed0a16c2cc16ceec8c" "$alarmid" "$message" "$displayName" "$category" "$stringseverity" "IP Address:$DeviceField(ipAddress)" "$strModTime" "$eventType"  "Entity: $entity"
```

Click **Next**. 
Check all the severities you want to receive notifications for.

![](images/opmanager_3.png)

Select appropriate time window and trigger options. 
Click **Next**.

![](images/opmanager_4.png)

Give a name to the notification profile and click **Save**.

![](images/opmanager_5.png)

Now whenever an event is triggered in ManageEngine OpManager, an incident will be automatically created in Squadcast.