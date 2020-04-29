---
title: Create and Manage On-call Schedules & Rotations
tags: [schedules, rotations]
summary: "Rotations for your customer support engineers or on-call teams"
sidebar: mydoc_sidebar
permalink: schedules.html
folder: mydoc
---

Schedules allow you to create time-based rotations/repetitions for on-call schedules. You can see who is on-call on which day with monthly, weekly, daily and agenda views.

In this documentation, we'll be going through the following :-
- Creating a Schedule
- Creating on-call person/squad for a schedule
- Updating an existing on-call
- Deleting an on-call
- Updating/Deleting a Schedule

{{site.data.alerts.note}}
<br/><br/><p>If you have configured routing rules for a service, they will override the schedule and will be given priority.</p>
{{site.data.alerts.end}}

{{site.data.alerts.blue-note}}
<b>Adding Schedules to Escalation Policies</b>
<br/><br/><p>Note that you will need to add a created schedule to a service for them to be notified when an incident.</p>
{{site.data.alerts.end}}

![](images/schedules_1.png)

## Creating a Schedule

You can create a schedule under **Schedules** → **+** button at the right hand side of the screen.

![](images/schedules_2.png)

**Schedule Name**: Give the schedule a name which you can use while adding the on-call schedule to the calendar.

**Schedule Description**: This is a short description of the schedule explaining what it is and why it exists. 

**Schedule Color**: You can also set a color for a specific schedule, which will be used while rendering the on-call on the calendar.

## Creating on-call person/squad for a schedule

You can click on any day of the calendar to create an on-call starting from that day. You can also drag from a day to another to automatically set the *Start date* and *End date*

![](images/schedules_3.png)

*Start date*, *Start time*, *End date* and *End time* determine when the event begins and when it ends respectively. 
Every on-call must be a part of some pre-defined schedule. You need to choose which *schedule* you want to create an on-call for.

{{site.data.alerts.green-note-check}}
<b>Localized Timezones:</b>
<br/><br/><p>The selected timezone will default to the local machine timezone. This is especially beneficial for geography-based on-call rotations. <br/><br/>The teams will be able to view any created on-call schedule in their local time.</p>
{{site.data.alerts.end}}

Repetitions can be daily, weekly or monthly. You can customize the number of days/weeks/months you want the on-call to repeat for. You can also restrict the schedules to specific times of the day or during specific days of the week, based on your need.
In case of weekly on-call, you can also customize on which day of the week it will repeat.

![](images/schedules_4.png)

You can set an end date to the repetitions or you may choose to repeat it forever till you delete it.

![](images/schedules_5.png)

If you want the on-call to rotate between some users or squads, you can do it by clicking **Add New Rotation**.

![](images/schedules_6.png)

And it will create and show the on-call users on the calendar as per the configuration you have made.

![](images/schedules_7.png)

## Updating an existing on-call

You can update an already existing on-call by clicking over any assigned user/squad on the calendar.

![](images/schedules_8.png)

You can update the on-call configuration as per your need and you can select **Update method** as:
-  **This Event Only**: to update that particular event.
-  **This and proceeding events**: to update the selected event and all the events that comes afterwards.
- **All events in this series**: to update all the events of that series irrespective of which event you clicked on.

![](images/schedules_9.png)

## Deleting an on-call

You can delete an existing on-call by clicking the **Delete** button at the bottom right corner of the **Update on-call** dialog box.
You have to choose between:
- **This event only**: It will delete only the selected event of the series.
- **This and proceeding events**: It will delete the event selected as well as all the future events belonging to that series.
- **All events**: It will delete all the events belonging to that series.

![](images/schedules_10.png)

## Updating/Deleting a Schedule

You can update/delete a schedule by clicking the the Schedule name you want to delete at the right hand side of the page. You can update the schedule details as per your needs or you may delete it by clicking the *bin* icon at the bottom right corner of the dialog box. 

![](images/schedules_11.png)

### Creating a Recurring Schedule

**Recurring Schedules**

Typically, organizations ensure that their on-calls schedules are repetitive so teams can get used to them and the on-call shifts can be more predictable to avoid any surprises. 

These types of schedules have a list of users who will be rotated one after the other in a repetitive cycle. 

To setup a recurring schedule on Squadcast, you can just untick the `Does not repeat` box in the pop-up and complete the rest of the schedule configuration as per your need.

![](images/schedules_12.png)

**Creating a One-off Schedule / Irregular Schedule**

One-off or non-recurring schedules are used to cover on-call for a short period of time but are not a part of the usual recurring rotations. 

In some one-off cases where one member of your team is asked to step in for another, cases where there's an unavoidable emergency or even in the case of planned vacations, you can create one-off  schedules. 

To setup a one-off schedule on Squadcast, you can just untick the `Does not repeat` box in the pop-up and complete the rest of the schedule configuration as per your need.

![](images/schedules_13.png)