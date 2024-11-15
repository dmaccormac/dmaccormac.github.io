---
title: Overview of updates in Monterey Rainmeter v1.0.4
date: 2024-11-05
last_modified_at: 2024-11-05
excerpt:  A new release of the rainmeter skin with additional system monitor widgets and interface updates. 
tags: 
  - rainmeter
  - customization
  - skins
---

This is an overview of updates in Monterey Rainmeter v1.0.4. I've added some additional monitor items and made some small UI changes. 

Below is a screenshot of the new CPU temperature monitor and network monitor items.

![Monitor widgets](/assets/images/2024-11-05-monterey-rainmeter-1.png){: .align-center}

# Add CPU temperature monitors
Rainmeter supports integration with [Core Temp](https://www.alcpu.com/CoreTemp/) to provide CPU temperature monitoring data.  

To add the new temperatue monitor widgets, we need to add the new items to the drop down menu and then create new functions for these items.

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

The Core Temp application must be open in order for the widget to receive temperate data.

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
I made some small changes to UI to accommodate the new widgets.

## Widget Output
- Open `Widgets\Monitor\Large.ini` 
- Edit `[MeterValue5]` and `[MeterValue6]` sections 
- Remove percent character from the value of `Text` (to accomodate IP address output).

`Text=[&[#Meter5]Rounded]`

Adjust other widget text output as needed.

## Refresh on double click
- Add the following to the widget .ini file:
  
`LeftMouseDoubleClickAction=[!Refresh]`

## Fix Settings display
- Edit `Settings.ini` and set `#BackgroundColor#10` in `[RightHalfMeter]` section.
  
## Add custom context menu actions 
- Add menu item in `@Resources\Scripts\Contexts\Widget.inc`
- Set menu item text variables in `@Resources\Languages\en\Widget.inc`

# References
[[1] GitHub Repo](https://github.com/dmaccormac/MontereyRainmeter)

[[2] Download Monterey_1.0.4.rmskin](https://github.com/dmaccormac/MontereyRainmeter/releases/download/v1.0.4/Monterey_1.0.4.rmskin)

[[3] Core Temp](https://www.alcpu.com/CoreTemp/)

[[4] Rainmeter: CoreTemp plugin](https://docs.rainmeter.net/manual/plugins/coretemp/)
