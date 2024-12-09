---
title: Windows Terminal tips and tricks
date: 2024-12-08
last_modified_at: 2024-12-08
tags: windows terminal settings json
excerpt: Configure various settings, including appearance, behavior, key bindings, and profiles.
---

# Introduction
In Windows Terminal, the `settings.json` file is used to configure various settings, including appearance, behavior, key bindings, and profiles. Modifying this file allows you to fine-tune your terminal experience and tailor it to your preferences [1, 2]. 

# Configuration

## Opening settings.json
Open Windows Terminal and click on the down arrow ▼ in the top bar next to the tabs. You can also access settings using the keyboard shortcut combination `Ctrl + , (comma)`. Once in settings, click on the option for `Open JSON file` in the lower-left corner. This will open the settings.json file in your default text editor.

You can also access the `settings.json` file directly at the following path:

`C:\Users\<YourUsername>\AppData\Local\Packages\Microsoft.WindowsTerminal_<random_string>\LocalState
`

## Configuring settings.json
When you open the settings.json file, configuration is categorized in several different sections. 

### profiles
This section contains configurations for individual terminal profiles.
```
"profiles": {
    "list": [
        {
            "guid": "{<GUID>}",
            "name": "Windows PowerShell",
            "commandline": "powershell.exe",
            "hidden": false,
            "colorScheme": "Campbell",
            "fontFace": "Consolas",
            "fontSize": 12
        }
    ]
}
```

### schemes
This section contains color schemes that you can apply to your profiles.
```
"schemes": [
{
    "name": "CustomScheme",
    "background": "#1d1f21",
    "foreground": "#c5c8c6",
    "black": "#282a2e",
    "red": "#a54242",
    "green": "#8c9440",
    "yellow": "#de935f",
    "blue": "#5f819d",
    "purple": "#85678f",
    "cyan": "#5e8d87",
    "white": "#707880"
}
]
```

### actions
This section is where you can define custom keyboard shortcuts.
```
"actions": [
    {
        "command": {
            "action": "newTab",
            "profile": "Windows PowerShell"
        },
        "keys": ["ctrl+shift+t"]
    }
]
```

### startupAction
This controls actions to run when Windows Terminal starts. 

### defaults
This section defines default settings for all profiles, such as font size, cursor shape, or starting directory.


Below is an example of a skeleton `settings.json` file:


```
{
    "defaultProfile": "{<GUID>}",
    "profiles": {
        "defaults": {
            "fontSize": 12,
            "fontFace": "Cascadia Code"
        },
        "list": [
            {
                "guid": "{<GUID>}",
                "name": "Windows PowerShell",
                "commandline": "powershell.exe",
                "colorScheme": "Campbell",
                "fontFace": "Consolas",
                "fontSize": 14
            },
            {
                "guid": "{<GUID>}",
                "name": "Ubuntu",
                "commandline": "wsl.exe",
                "colorScheme": "Tango",
                "fontSize": 12
            }
        ]
    },
    "schemes": [
        {
            "name": "Tango",
            "background": "#2e3436",
            "foreground": "#d3d7cf",
            "black": "#000000",
            "red": "#cc0000",
            "green": "#4e9a06",
            "yellow": "#c4a000",
            "blue": "#3465a4",
            "purple": "#75507b",
            "cyan": "#06989a",
            "white": "#d3d7cf"
        }
    ],
    "actions": [
        {
            "command": {
                "action": "newTab",
                "profile": "Windows PowerShell"
            },
            "keys": ["ctrl+shift+t"]
        }
    ],
    "startupAction": "newTab"
}
```
  
## Customizations 
Common customizations that can be made to the `settings.json` file include customizing profiles, binding hot key actions and modifying window appearance.

### Profiles
Windows Terminal allows you to configure different profiles for different shells (e.g., Command Prompt, PowerShell, WSL). By modifying the settings.json file, you can adjust appearance settings for each profile by setting attributes such as the color scheme, font, background color and startup settings.

To add a new profile called `Terminal Admin` which starts Windows Terminal in elevated mode, we can add the code below to the `profiles` section.

```
{
    "commandline": "wt.exe",
    "elevate": true,
    "guid": "{guid}",
    "hidden": false,
    "name": "Terminal Admin",
    "startingDirectory": "%USERPROFILE%"
}
```

## Hot keys
Common hot keykey actions include opening new tabs, splitting panes, navigating between tabs. 

In the example code below, the `Alt+Shift+Home` key combination is assigned to change path to the user's home directory.

```
{
    "command": 
    {
        "action": "sendInput",
        "input": "cd $HOME\r"
    },
    "id": "User.sendInput.A65B7E58",
    "keys": "alt+shift+home"
}
```

To add a hotkey to always keep the terminal window on top of other windows, add the following code to the `actions` section:

```
{
    "command": "toggleAlwaysOnTop",
    "id": "User.ToggleAlwaysOnTop",
    "keys": "alt+shift+pgup"
}
```

# Conclusion
Working with the settings.json file in Windows Terminal provides granular level control of many terminal settings such as appearance, behaviour and key bindings. Using a combination scripts and actions allows for development of highly customized work flows.

# References
[[1] Windows Terminal](https://apps.microsoft.com/detail/9n0dx20hk701?rtc=1&hl=en-us&gl=US)

[[2] General profile settings in Windows Terminal](https://learn.microsoft.com/en-us/windows/terminal/customize-settings/profile-general)

# Appendix

Table 1 - List of Windows Terminal Keyboard Shortcuts

|   **Description**  |  **Shortcut**   |
| --- | --- |
| Open a new Windows Terminal instance. | Ctrl + Shift + N |
| Open a new default profile tab | Ctrl + Shift + T |
| Open a new tab, profile index: 1 to 9 | Ctrl + Shift + Number(1-9) |
| Switch to tab 1 to 9 | Ctrl + Alt + Number(1-9) |
| Switch to the Next tab | Ctrl + Tab |
| Switch to the Previous tab | Ctrl + Shift + Tab |
| Open the profile selection dropdown menu | Ctrl + Shift + Space |
| Open another instance of the current tab. | Ctrl + Shift + D |
| Open another instance of the current pane. | Alt + Shift + D |
| Close the current tab | Ctrl + Shift + W |
| Open Windows Terminal Settings UI | Ctrl \+ , |
| Open default settings file | Ctrl + Alt \+ , |
| Open settings file | Ctrl + Shift \+ , |
| Find | Ctrl + Shift + F |
| Create/Split a Vertical pane | Alt + Shift + + |
| Create/Split a Horizontal pane | Alt + Shift + - |
| Resize the current pane up | Alt + Shift + ↑ |
| Resize the current pane down | Alt + Shift + ↓ |
| Resize the current pane left | Alt + Shift + ← |
| Resize the current pane right | Alt + Shift + → |
| Open command palette | Ctrl + Shift + P |
| Increase the font size | Ctrl + = |
| Decrease the font size | Ctrl + - |
| Reset the font size to the default | Ctrl + 0 |
| Scroll up in the Windows Terminal. | Ctrl + Shift + ↑ |
| Scroll down in the Windows Terminal. | Ctrl + Shift + ↓ |
| Scroll up one page | Ctrl + Shift + PgUp |
| Scroll down one page | Ctrl + Shift + PgDn |
| Scroll to the top of history | Ctrl + Shift + Home |
| Scroll to the bottom of history | Ctrl + Shift + End |
| Move focus to one pane up | Alt + ↑ |
| Move focus to one pane down | Alt + ↓ |
| Move focus to one pane left | Alt + ← |
| Move focus to one pane right | Alt + → |
| Move focus to the last used pane | Ctrl + Alt + ← |
| Toggle on/off High Visibility screen mode. | Left Alt + Left Shift + PrtScn |
| Summon Quake mode | Win + \` |
| Toggle on/off fullscreen mode | F11 |
| Close the Windows Terminal (entire program) | Alt + F4 |