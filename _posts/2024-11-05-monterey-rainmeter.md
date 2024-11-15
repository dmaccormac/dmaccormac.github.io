---
title: Overview of updates in Monterey Rainmeter v1.0.4
date: 2024-11-05
last_modified_at: 2024-11-05
excerpt:  A new release of the skin with additional monitor widgets and interface updates. Source code available [here](https://github.com/dmaccormac/MontereyRainmeter).
tags: 
  - rainmeter
  - customization
  - skins
---

This is an overview of updates in Monterey Rainmeter v1.0.4. I've added some additional monitor items and made some small UI changes. 

Below is a screenshot of the new CPU temperature monitor and network monitor items.

![Monitor widgets](/assets/images/2024-11-05-monterey-rainmeter-1.png){: .align-center}

# Add CPU temperature monitors
Rainmeter supports integration with [Core Temp](https://www.alcpu.com/CoreTemp/) which we need to install first to support CPU temperature monitoring. 

To add the new temperatue monitor widgets, we need to add the new items to the drop down menu and then create new functions for these monitors. 

## Add drop down items
Edit `@Resources\Scripts\Contexts\Monitor.inc` to add entries for the new items. Add entries for each CPU core under the `[Variables]` and `[SetTickMark]` sections.

```
[Variables]
MonitorContextTitle10=Core0
MonitorContextAction10=[!WriteKeyValue Variables [#Meter] "Core0" "#@#Variables\Monitor.inc"][!Refresh]

[SetTickMark]
IfMatch8=Core0
IfMatchAction8=[!SetOption Rainmeter ContextTitle10 "Core0  [\x2714]"]
```

![Add drop down menu items](/assets/images/2024-11-05-monterey-rainmeter-2.png){: .align-center}

## Add functions for new items
Edit `@Resources\Scripts\Widgets\Monitor.inc` to add functions for the new items. Copy the existing CPU functions and use them as templates for new functions for each CPU core. Replace all new instances of 'CPU' with core name, for example Core0.

To update the widget to show CPU temperature we can edit the `Core0Monitor` function to read Core0 temperature from CoreTemp application:

```
[Core0Monitor]
Measure=Plugin
Plugin=CoreTemp
CoreTempType=Temperature
CoreTempIndex=0
Alias=Temp
UpdateDivider=(#BatterySaverMode# = 0 ? 10 : 20)
MinValue=0
MaxValue=100
OnChangeAction=[!UpdateMeasure Core0Rounded]
```

## Update monitor icons
Add icon images for the new monitors in `@Resources\Images\Monitor`


# Add IP monitors
I added two new network monitor items to show public and private IP address. As before, add the drop down entries to `@Resources\Scripts\Contexts\Monitor.inc` and add the supporting functions to `@Resources\Scripts\Widgets\Monitor.inc`.

Update `LANRounded` to show private IP address
```
[LANRounded]
Measure=Plugin
Plugin=SysInfo
SysInfoType=IP_ADDRESS
SysInfodata=Best
```


Update `WANRounded` to show public IP address
```
[WANRounded]
Measure=Plugin
Plugin=WebParser
URL=https://checkip.amazonaws.com/
UpdateRate=14400
RegExp=(?s)^(.*)$
StringIndex=1
Substitute="":"N/A"
```

# UI changes
Made some small changes to UI to accommodate the new widgets.

## Widget Output
-  Update `Widgets\Monitor\Large.ini` and edit `[MeterValue5]` and `[MeterValue6]` sections to remove percent character from slots 5 and 6 (to accomodate IP output).
    `Text=[&[#Meter5]Rounded]`

Adjust other widget output as needed in `Widgets/Monitor` files.

## Refresh on double click
- Add the following to the widget inc file:
`LeftMouseDoubleClickAction=[!Refresh]`

## Fix Settings Display Brightness
- Edit `Settings.ini` and set `#BackgroundColor#10` in `[RightHalfMeter]` section.
  
## Add custom context menu actions 
- Add menu item in `@Resources\Scripts\Contexts\Widget.inc`
- Set menu item text variables in `@Resources\Languages\en\Widget.inc`

# Links
[GitHub Repo](https://github.com/dmaccormac/MontereyRainmeter)
[Release - v1.0.4](https://github.com/dmaccormac/MontereyRainmeter/releases/tag/v1.0.4)