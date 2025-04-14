---
title: How to Prevent Automatic Restarts After Windows Updates
date: 2025-04-13
last_modified_at: 2025-04-13
excerpt: Windows updates are essential for maintaining system security and performance, but automatic restarts can disrupt your workflow.
tags: 
    - Windows updates
    - Troubleshooting
    - Tips
---

# Introduction
Windows updates are essential for maintaining system security and performance, but unexpected automatic restarts can be problematic. Fortunately, there are several ways to prevent these interruptions and take control of when your system restarts.


# Methods to prevent automatic restarts
There are several methods to prevent automatic restarts after Windows updates. Here are some effective ways to manage this issue:

## Windows Settings
You can adjust settings related to update notifications and restarts. You can also set active hours to avoid restarts during your working hours.

Got to **Settings** > **Windows Update** > **Advanced Options**.  

- Go to **Settings** > **Windows Update** > **Advanced Options** > **Notify me when a restart is required**.
- Go to **Settings** > **Windows Update** > **Change Active Hours**.

## Use Group Policy Editor
For Windows Pro and Enterprise users, the Group Policy Editor provides a way to disable automatic restarts:
- Press **Win + R**, type `gpedit.msc`, and hit Enter.
- Navigate to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Windows Update** > **Manage end user experience**.
- Enable the policy **Configure Automatic Updates**.
- Choose the option **2 - Notify for download and notify for install**. This setting will notify you about updates but won't install them automatically.

## Modify the Registry
If you're using Windows Home, you can achieve similar results by editing the registry:
- Press **Win + R**, type `regedit`, and hit Enter.
- Navigate to `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`.
- Create a new DWORD (32-bit) value named `AUOptions` and set its value to  decimal `3`.

## Pause Updates
You can temporarily pause updates to prevent automatic restarts:
- Go to **Settings** > **Windows Update** > **Pause Updates**.
- Select the duration for which you want to pause updates (up to 5 weeks).

## Disable Update Services
For advanced users, disabling the Windows Update service can prevent automatic restarts:
- Press **Win + R**, type `services.msc`, and hit Enter.
- Locate **Windows Update**, right-click, and select **Stop**.
- Set the startup type to **Disabled** to prevent the service from running.

## Third-Party Tools
There are tools like StopUpdates10 [3] or Windows Update Blocker [4] that can help manage updates and prevent automatic restarts.

# Conclusion
You can prevent automatic restarts using various methods including built-in settings, group policies, registry edits, or third-party tools. By implementing these methods, you can ensure that Windows updates don't interrupt your work. 

# References
[[1] Windows Update: FAQ](https://support.microsoft.com/en-us/windows/windows-update-faq-8a903416-6f45-0718-f5c7-375e92dddeb2)

[[2] GP Search](https://gpsearch.azurewebsites.net/)

[[3] StopUpdates10](https://greatis.com/stopupdates10/)

[[4] Windows Update Blocker](https://www.sordum.org/9410/windows-update-blocker-v1-8/)

