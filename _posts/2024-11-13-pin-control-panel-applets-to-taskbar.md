---
title: How to pin Control Panel applets to the Windows taskbar
tags:
  - control panel
  - taskbar
  - shortcuts
excerpt: Create shortcuts to system applets and special folders by using the item's class ID from the registry. 
---

A CLSID (Class Identifier) is a globally unique identifier (GUID) used in Microsoft Windows to identify a specific class of objects, typically associated with COM (Component Object Model) components, ActiveX controls, or other system components. These identifiers are registered in the Windows registry and can be used to locate and interact with software components, services, or objects.

# Find the CLSID
- Search the registry for the item by name
- Copy the key name (CLSID)
- Optionally, copy the icon location
  
![Search the registry for the item](/assets/images/2024-11-13-windows-clsid-key-guid-1.png)

# Create the shortcut
- Create shortcut in `%APPDATA%\Microsoft\Internet Explorer\Quick Launch\User Pinned\TaskBar`
- Set the Target to `C:\Windows\explorer.exe Shell:::{CLSID}`
- Change the shortcut icon
- Drag shorcut onto the taskbar
  
![Create a shortcut using the CLSID](/assets/images/2024-11-13-windows-clsid-key-guid-2.png)


# CLSID cheatsheet

| **Item** | **CLSID** |
| --- |  --- |
| 3D Objects  | ::{0DB7E03F-FC29-4DC6-9020-FF41B59E513A} |
| Action Center / Security and Maintenance  | ::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6} |
| Add Network Place  | ::{D4480A50-BA28-11D1-8E75-00C04FA31A86} |
| Administrative Tools / Windows Tools  | ::{D20EA4E1-3957-11D2-A40B-0C5020524153} |
| All Tasks (God Mode)  | ::{ED7BA470-8E54-465E-825C-99712043E01C} |
| Applications  | ::{4234D49B-0245-4DF3-B780-3893943456E1} |
| AutoPlay  | ::{9C60DE1E-E5FC-40F4-A487-460851A8D915} |
| BitLocker Drive Encryption | ::{D9EF8727-CAC2-4E60-809E-86F80A666C91} |
| Bluetooth Devices  | ::{28803F59-3A75-4058-995F-4EE5503B023C} |
| Color Management  | ::{B2C761C6-29BC-4F19-9251-E6195265BAF1} |
| Command Folder  | ::{437FF9C0-A07F-4FA0-AF80-84B6C6440A16} |
| Common Places FS Folder  | ::{D34A6CA6-62C2-4C34-8A7C-14709C1AD938} |
| Control Panel  | ::{5399E694-6CE5-4D6C-8FCE-1D8870FDCBA0} |
| Control Panel (Category view)  | ::{26EE0668-A00A-44D7-9371-BEB064C98683} |
| Control Panel ➞ All Control Panel Items  | ::{21EC2020-3AEA-1069-A2DD-08002B30309D} |
| Credential Manager  | ::{1206F5F1-0569-412C-8FEC-3204630DFB70} |
| Date and Time  | ::{E2E7934B-DCE5-43C4-9576-7FE4F75E7480} |
| Default Programs / Default Apps  | ::{17CD9488-1228-4B2F-88CE-4298E93E0966} |
| Default Programs / Default Apps  | ::{E44E5D18-0652-4508-A4E2-8A090067BCB0} |
| Delegate folder / Computer | ::{B155BDF8-02F0-451E-9A26-AE317CFD7779} |
| Desktop  | ::{B4BFCC3A-DB2C-424C-B029-7FE99A87C641} |
| Desktop in Favorites  | ::{04731B67-D933-450A-90E6-4ACD2E9408FE} |
| Device Manager  | ::{74246BFC-4C96-11D0-ABEF-0020AF6B0B7A} |
| Devices and Printers  | ::{A8A91A66-3A7D-4424-8D24-04E180695C7A} |
| Documents  | ::{D3162B92-9365-467A-956B-92703ACA08AF} |
| Documents  | ::{A8CDFF1C-4878-43BE-B5FD-F8091C1C60D0} |
| Downloads  | ::{088E3905-0323-4B02-9826-5D99428E115F} |
| Downloads  | ::{374DE290-123F-4565-9164-39C4925E467B} |
| Email  | ::{2559A1F5-21D7-11D4-BDAF-00C04F60B9F0} |
| Ease of Access Center  | ::{D555645E-D4F8-4C29-A827-D93C859C4F2A} |
| Favorites  | ::{323CA680-C24D-4099-B94D-446DD2D7249E} |
| File History | ::{F6B6E965-E9B2-444B-9286-10C9152EDBC5} |
| Folder Options  | ::{6DFD7C5C-2451-11D3-A299-00C04F8EF6AF} |
| Font Settings  | ::{93412589-74D4-4E4E-AD0E-E0CB621440FD} |
| Fonts  | ::{BD84B380-8CA2-1069-AB1D-08000948F534} |
| Frequent Folders  | ::{3936E9E4-D92C-4EEE-A85A-BC16D5EA0819} |
| Games Explorer | ::{ED228FDF-9EA8-4870-83B1-96B02CFE0D52} |
| Get Programs  | ::{15EAE92E-F17A-4431-9F28-805E482DAFD4} |
| HomeGroup  | ::{67CA7650-96E6-4FDD-BB43-A8E774F73A57} |
| Hyper-V Remote File Browsing  | ::{0907616E-F5E6-48D8-9D61-A91C3D28106D} |
| Inbox (Outlook)  | ::{00020D75-0000-0000-C000-000000000046} |
| Indexing Options  | ::{87D66A43-7B11-4A28-9811-C86EE395ACF7} |
| Infrared | ::{A0275511-0E86-4ECA-97C2-ECD8F1221D08} |
| Installed Updates  | ::{D450A8A1-9568-45C7-9C0E-B4F9FB4537BD} |
| Internet Options  | ::{A3DD4F92-658A-410F-84FD-6FBBBEF2FFFE} |
| iSCCI Initiator  | ::{A304259D-52B8-4526-8B1A-A1D6CECC8243} |
| Keyboard Properties  | ::{725BE8F7-668E-4C7B-8F90-46BDB0936430} |
| Libraries  | ::{031E4825-7B94-4DC3-B131-E946B44C8DD5} |
| Location and Other Sensors / Location Settings | ::{E9950154-C418-419E-A90A-20C5287AE24B} |
| Media Servers  | ::{289AF617-1CC3-42A6-926C-E6A863F0E3BA} |
| Mobility Center  | ::{5EA4F148-308C-46D7-98A9-49041B1DD468} |
| Mouse Properties  | ::{6C8EEC18-8D75-41B2-A177-8831D59D2D50} |
| Music  | ::{3DFDF296-DBEC-4FB4-81D1-6A3438BCF4DE} |
| Music  | ::{1CF1260C-4DD0-4EBB-811F-33C572699FDE} |
| My Computer / Computer / This PC  | ::{20D04FE0-3AEA-1069-A2D8-08002B30309D} |
| My Documents  | ::{450D8FBA-AD25-11D0-98A8-0800361B1103} |
| My Network Places  | ::{208D2C60-3AEA-1069-A2D7-08002B30309D} |
| Network  | ::{F02C1A0D-BE21-4350-88B0-7367FC96EF3C} |
| Network and Sharing Center  | ::{8E908FC9-BECC-40F6-915B-F4CA0E70D03D} |
| Network Connections  | ::{7007ACC7-3202-11D1-AAD2-00805FC1270E} |
| Network Connections  | ::{992CFFA0-F557-101A-88EC-00DD010CCC48} |
| Notification Area Icons (append \\SystemIcons for System Icons) | ::{05D7B0F4-2121-4EFF-BF6B-ED3F69B894D9} |
| Offline Files Folder | ::{AFDB1F70-2A4C-11D2-9039-00C04F8EEB3E} |
| OneDrive  | ::{018D5C66-4533-4307-9B53-224DE2ED1FE6} |
| Other Users Folder / Media Streaming Options  | ::{B4FB3F98-C1EA-428D-A78A-D1F5659CBA93} |
| Pen and Touch | ::{F82DF8F7-8B9F-442E-A48C-818EA735FF9B} |
| Personalization | ::{ED834ED6-4B5A-4BFE-8F11-A626DCB6A921} |
| Phone and Modem  | ::{40419485-C444-4567-851A-2DD7BFA1684D} |
| Pictures  | ::{24AD3AD4-A569-4530-98E1-AB02F9417AA8} |
| Pictures  | ::{3ADD1653-EB32-4CB0-BBD7-DFA0ABB5ACCA} |
| Portable Devices  | ::{35786D3C-B075-49B9-88DD-029876E11C01} |
| Power Options  | ::{025A5937-A6BE-4686-A844-36FE4BEC8B6D} |
| Previous Versions Results Folder  | ::{F8C2AB3B-17BC-41DA-9758-339D7DBF2D88} |
| Printers  | ::{863AA9FD-42DF-457B-8E4D-0DE1B8015C60} |
| Printers and Faxes  | ::{2227A280-3AEA-1069-A2DE-08002B30309D} |
| printhood delegate folder | ::{ED50FC29-B964-48A9-AFB3-15EBB9B97F36} |
| Programs and Features  | ::{7B81BE6A-CE2B-4676-A29E-EB907A5126C5} |
| Public Folder  | ::{4336A54D-038B-4685-AB02-99BB52D3FB8B} |
| Quick access  | ::{679F85CB-0220-4080-B29B-5540CC05AAB6} |
| Recent Places / Recent Folders  | ::{22877A6D-37A1-461A-91B0-DBDA5AAEBC99} |
| Recovery | ::{9FE63AFD-59CF-4419-9775-ABCC3849F861} |
| Recycle Bin  | ::{645FF040-5081-101B-9F08-00AA002F954E} |
| Region and Language  | ::{62D8ED13-C9D0-4CE8-A914-47DD628FB1B0} |
| RemoteApp and Desktop Connections  | ::{241D7C96-F8BF-4F85-B01F-E2B043341A4B} |
| Removable Storage Devices  | ::{A6482830-08EB-41E2-84C1-73920C2BADB9} |
| Results Folder  | ::{2965E715-EB66-4719-B53F-1672673BBEFA} |
| Run  | ::{2559A1F3-21D7-11D4-BDAF-00C04F60B9F0} |
| Search | ::{2559A1F0-21D7-11D4-BDAF-00C04F60B9F0} |
| Search (Modern)  | ::{2559A1F8-21D7-11D4-BDAF-00C04F60B9F0} |
| Search Results | ::{9343812E-1C37-4A49-A12E-4B2D810D956B} |
| Set Program Access and Defaults  | ::{2559A1F7-21D7-11D4-BDAF-00C04F60B9F0} |
| Show Desktop  | ::{3080F90D-D7AD-11D9-BD98-0000947B0257} |
| Sound  | ::{F2DDFC82-8F12-4CDD-B7DC-D4FE1425AA4D} |
| Speech Recognition  | ::{58E3C745-D971-4081-9034-86E34B30836A} |
| Storage Spaces | ::{F942C606-0914-47AB-BE56-1321B8035096} |
| Sync Center  | ::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF} |
| Sync Setup Folder  | ::{2E9E59C0-B437-4981-A647-9C34B9B90891} |
| System  | ::{BB06C0E4-D293-4F75-8A90-CB05B6477EEE} |
| System Restore | ::{3F6BC534-DFA1-4AB4-AE54-EF25A74E0107} |
| Tablet PC Settings | ::{80F3F1D5-FECA-45F3-BC32-752C152E456E} |
| Taskbar Settings  | ::{0DF44EAA-FF21-4412-828E-260A8728E7F1} |
| Text to Speech  | ::{D17D1D6D-CC3F-4815-8FE3-607E7D5D10B3} |
| Troubleshooting | ::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651} |
| User Accounts  | ::{60632754-C523-4B62-B45C-4172DA012619} |
| User Accounts (netplwiz)  | ::{7A9D77BD-5403-11D2-8785-2E0420524153} |
| User Folder  | ::{59031A47-3F72-44A7-89C5-5595FE6B30EE} |
| User Pinned  | ::{1F3427C8-5C10-4210-AA03-2EE45287D668} |
| Videos  | ::{F86FA3AB-70D2-4FC7-9C99-FCBF05467F3A} |
| Videos  | ::{A0953C92-50DC-43BF-BE83-3742FED03C9C} |
| Window Switcher  | ::{3080F90E-D7AD-11D9-BD98-0000947B0257} |
| Windows Features | ::{67718415-C450-4F3C-BF8A-B487642DC39B} |
| Windows Firewall | ::{4026492F-2F69-46B8-B9BF-5654FC07E423} |
| Work Folders | ::{ECDB0924-4208-451E-8EE0-373C0956DE16} |

# References

[List of Windows 11 CLSID Key (GUID) Shortcuts](https://www.elevenforum.com/t/list-of-windows-11-clsid-key-guid-shortcuts.1075/)

[Shells, Shortcuts, and CLSID Listing](https://www.sysnative.com/forums/threads/shells-shortcuts-and-clsid-listing-windows-10-8-1-8-7.12156/#anchor0)

[How-to: A list of common ClassIDs](https://ss64.com/nt/syntax-clsid.html)
