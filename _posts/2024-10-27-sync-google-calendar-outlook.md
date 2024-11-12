---
title: Sync Google Calendar in Outlook
date: 2024-10-27
tags: 
  - google
  - outlook
  - calendar
  - sync
---

You can sync your Google Calendar with Outlook, but it requires some additional steps as there's no built-in feature in Outlook to automatically sync Google Calendar. 

You can see your Google Calendar in Outlook following the steps [here](https://support.microsoft.com/en-us/office/see-your-google-calendar-in-outlook-c1dab514-0ad4-4811-824a-7d02c5e77126). While this method allows you to view your Google Calendar inside Outlook, it does not enable full two-way sync (i.e., you can't modify the Google Calendar directly in Outlook).

For full two-way sync (where you can add and edit events in either Google Calendar or Outlook), you need to use a third-party tool. Outlook Google Calendar Sync is a free tool that can sync your Google calendar with Outlook. Here's how you can set it up. 

### Download and install the app
Downoad Outlook Google Calendar Sync app [here](https://www.outlookgooglecalendarsync.com/).

### Configure Google Settings
Click on the **Settings** tab and then click on the **Google** tab. Enter your Gmail address under the **Connected Account** field and then click on the **Retrieve Calendars** button.

![Google Settings]({{ site.url }}{{ site.baseurl }}/assets/images/2024-10-27-outlook-google-calendar-sync-1.png){: .align-center}

When authenticating with Google, make sure to check the box to allow the app to make changes to your calendar. 

![Google Permission]({{ site.url }}{{ site.baseurl }}/assets/images/2024-10-27-outlook-google-calendar-sync-2.png){: .align-center}

If you need to remove your Google account from the app and reconnect it, you will need to delete the Outlook Google Calendar Sync folder from `AppData`.

### Configure Outlook Settings
Click on the **Settings** tab and then click on the **Outlook** tab. Select the calendar you wish you synchronize and then set sync options as needed.

![test2]({{ site.url }}{{ site.baseurl }}/assets/images/2024-10-27-outlook-google-calendar-sync-3.png){: .align-center}

### Configure Sync Options
Click on the **Settings** tab and then click on the **Sync Options** tab. From the **Direction** drop-down, select the two-way sync option. 

Expand the **When** and **What** sections to configue the sync schedule and behaviour. 

![test2]({{ site.url }}{{ site.baseurl }}/assets/images/2024-10-27-outlook-google-calendar-sync-4.png){: .align-center}

### Configure Application Behaviour
Click on the **Settings** tab and then click on the **Application Behaviour** tab. Configure startup and logging properties.

![test2]({{ site.url }}{{ site.baseurl }}/assets/images/2024-10-27-outlook-google-calendar-sync-5.png){: .align-center}

### Start the Sync
Click on the **Sync** tab and then click on **Start Sync** button to initiate the sync. You should now see your Google Calendar events appear in Outlook, and vice versa.

<!-- [![lightbox]({{ site.url }}{{ site.baseurl }}/assets/images/2024-10-27-outlook-google-calendar-sync-1.png)]({{ site.url }}{{ site.baseurl }}/assets/images/2024-10-27-outlook-google-calendar-sync-1.png) -->


