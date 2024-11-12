---
title: Shell folder shortcuts
date: 2024-10-34
tags:
  - shell
  - folder
  - shortcuts
---
Windows Shell Folder shortcuts are special shortcuts in Windows that point to predefined system locations or folders. These shortcuts provide quick access to commonly used directories without needing to know the exact file path or the user's settings.

The idea behind Shell Folders is to offer a standardized way for applications and users to access specific directories, even when their locations may change due to system configuration. Each shell folder has a special folder ID (also known as a CSIDL, for constant shell folder identifier) and can be accessed programmatically via Windows API calls.

Below is a list of Windows shell folder shortcuts.

## Shell folder shortcuts

| **Description** | **Shortcut** | **Alternative** |
| --- | --- | --- |
| Access shortcuts pinned to the Start menu or Taskbar | shell:User Pinned | %AppData%\\Microsoft\\Internet Explorer\\Quick Launch\\User Pinned\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Internet Explorer\\Quick Launch\\User Pinned |
| Account Pictures | Shell:AccountPictures | %AppData%\\Microsoft\\Windows\\Account Pictures\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Account Pictures |
| Apps folder | shell:appsFolder |     |
| Display 32-bit programs stored on 64-bit Windows,  <br>or the \\Program Files folder on 32-bit Windows | shell:ProgramFilesX86 | %ProgramFiles(x86)% = C:\\ProgramFiles (x86) |
| Display Sync Center | shell:SyncCenterFolder | Control Panel \> Sync Center |
| Display Sync Center Conflicts | shell:ConflictFolder | Control Panel \> Sync Conflicts |
| Display Sync Center Results | shell:SyncResultsFolder | Control Panel \> Sync Results |
| Display further user tiles | shell:Roaming Tiles | %LocalAppData%\\Microsoft\\Windows\\Roaming Tiles\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\RoamingTiles |
| Display installed Windows Updates | shell:AppUpdatesFolder | Control Panel \> Programs and Features \> Installed updates |
| Display links provided by your PC manufacturer (if any) | shell:OEM Links |     |
| Display public libraries, if any | shell:PublicLibraries | %Public%\\Libraries\\ = C:\\Users\\Public\\Libraries |
| Display the Control Panel | shell:ControlPanelFolder | Control Panel |
| Display the user\'s Ringtones folder | shell:Ringtones | %LocalAppData%\\Microsoft\\Windows\\Ringtones\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\Ringtones |
| Display your Music library | shell:MusicLibrary | Libraries\\Music |
| Display your Pictures library | shell:PicturesLibrary | Libraries\\Pictures (previously My Pictures)  <br>\= C:\\Users\\<username>\\Pictures |
| Display your Videos library | shell:VideosLibrary | Libraries\\Videos |
| Display your user tiles (the images you can use for your account) | shell:UserTiles | %UserProfile%\\AppData\\Roaming\\Microsoft\\Windows\\AccountPictures\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\AccountPictures |
| Launches Internet Explorer Applets and applications | shell:InternetFolder |     |
| Open All Users Start Menu\\Administrative Tools folder | shell:Common Administrative Tools | %ProgramData%\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\  <br>\=C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools |
| Open the Client Side Cache Offline Files folder, if supported | shell:CSCFolder | Client Side Cache, if enabled |
| Open the Common Files for 32-bit programs stored on 64-bit Windows,  <br>Or the Program Files\\Common Files folder on 32-bit Windows | shell:ProgramFiles**Common**X86 | %ProgramFiles(x86)%\\Common Files\\  <br>\= C:\\ProgramFiles (x86)\\Common Files |
| Open the Computer folder | shell:MyComputerFolder | "This PC" |
| Open the Control Panel "Install a program from the network" applet | shell:AddNewProgramsFolder | Control Panel \> Get Programs from the network |
| Open the Control Panel "Uninstall or change a program" applet | shell:ChangeRemoveProgramsFolder | Control Panel \> Uninstall or change a program |
| Open the Documents library | shell:DocumentsLibrary | Libraries\\Documents |
| Open the Fonts folder | shell:Fonts | %SystemRoot%\\Fonts  <br>\= C:\\Windows\\Fonts |
| Open the Games folder | shell:Games |     |
| Open the HomeGroup folder | shell:HomeGroupFolder |     |
| Open the HomeGroup folder for the currently logged-on user (if any) | shell:HomeGroupCurrentUserFolder |     |
| Open the Internet Explorer Cookies folder | shell:Cookies | %LocalAppData%\\Microsoft\\Windows\\iNetCookies\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\iNetCookies |
| Open the Internet Explorer Favorites folder | shell:Favorites | %UserProfile%\\Favorites\\  <br>\= C:\\Users\\<username>\\Favorites |
| Open the Libraries folder | shell:Libraries | Libraries |
| Open the Network Places folder | shell:NetworkPlacesFolder | "Network" |
| Open the Printers folder | shell:PrintersFolder | Control Panel \> Printers |
| Open the Program Files folder | shell:ProgramFiles | [%ProgramFiles%](https://ss64.com/nt/syntax-variables.html)  <br>\= C:\\Program Files |
| Open the Program Files\\Common Files folder | shell:ProgramFilesCommon | %ProgramFiles%\\Common Files\\  <br>\= C:\\Program Files\\Common Files |
| Open the Public Application Data folder | shell:Common AppData | [%ProgramData%](https://ss64.com/nt/syntax-variables.html)  <br>\= C:\\ProgramData |
| Open the Public Desktop | shell:Common Desktop | %Public%\\Desktop\\  <br>\= C:\\Users\\Public\\Desktop |
| Open the Public Documents folder | shell:Common Documents | %Public%\\Documents\\  <br>\= C:\\Users\\Public\\Documents |
| Open the Public Downloads folder | shell:CommonDownloads | %Public%\\Downloads\\  <br>\= C:\\Users\\Public\\Downloads |
| Open the Public Game Explorer folder | shell:PublicGameTasks | %ProgramData%\\Microsoft\\Windows\\GameExplorer\\  <br>\=C:\\ProgramData\\Microsoft\\Windows\\GameExplorer |
| Open the Public Music folder | shell:CommonMusic | %Public%\\Music\\ = C:\\Users\\Public\\Music |
| Open the Public Pictures folder | shell:CommonPictures | %Public%\\Pictures\\ = C:\\Users\\Public\\Pictures |
| Open the Public Start Menu Programs folder | shell:Common Programs | %ProgramData%\\Microsoft\\Windows\\Start Menu\\Programs\\  <br>\=C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs |
| Open the Public Start Menu folder | shell:Common [Start Menu](https://ss64.com/nt/syntax-folders.html) | %ProgramData%\\Microsoft\\Windows\\Start Menu\\  <br>\=C:\\ProgramData\\Microsoft\\Windows\\Start Menu |
| Open the Public Startup folder | shell:Common Startup | %ProgramData%\\Microsoft\\Windows\\Start Menu\\Programs\\Startup\\  <br>\=C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Startup |
| Open the Public Templates folder | shell:Common Templates | %ProgramData%\\Microsoft\\Windows\\Templates\\  <br>\=C:\\ProgramData\\Microsoft\\Windows\\Templates |
| Open the Public Video folder | shell:CommonVideo | %Public%\\Videos\\ = C:\\Users\\Public\\Videos |
| Open the Public ringtones folder | shell:CommonRingtones | %ProgramData%\\Microsoft\\Windows\\Ringtones\\  <br>\=C:\\ProgramData\\Microsoft\\Windows\\Ringtones |
| Open the Public user tiles folder | shell:PublicUserTiles | %ProgramData%\\Microsoft\\User Account Pictures\\  <br>\= C:\\ProgramData\\Microsoft\\User Account Pictures\\ |
| Open the Quick Launch folder (disabled by default) | shell:Quick Launch | %AppData%\\Microsoft\\Internet Explorer\\Quick Launch\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Internet Explorer\\Quick Launch |
| Open the Recycle Bin | shell:RecycleBinFolder | "Recycle Bin" |
| Open the Sample Music folder | shell:SampleMusic | %Public%\\Music\\Sample Music\\ = C:\\Users\\Public\\Music\\SampleMusic |
| Open the Sample Pictures folder | shell:SamplePictures | %Public%\\Pictures\\Sample Pictures\\ = C:\\Users\\Public\\Pictures\\Sample Pictures |
| Open the Sample Videos folder | shell:SampleVideos | %Public%\\Videos\\Sample Videos\\ = C:\\Users\\Public\\Videos\\Sample videos |
| Open the Saved Games folder | shell:SavedGames | %UserProfile%\\Saved Games\\ = C:\\Users\\<username>\\Saved Games |
| Open the Sync Center\'setup options | shell:SyncSetupFolder | Control Panel \> Setup new Sync Partnerships |
| Open the Temporary Internet Files folder | shell:Cache | %LocalAppData%\\Microsoft\\Windows\\iNetCache\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\iNetCache |
| Open the Users\\Public folder (Shared files) | shell:Public | [%Public%](https://ss64.com/nt/syntax-variables.html) = C:\\Users\\Public |
| Open the Windows Photo Gallery Original Images folder, if installed | shell:Original Images |     |
| Open the Windows Resources folder (themes are stored here) | shell:ResourceDir | %SystemRoot%\\Resources\\ = C:\\Windows\\Resources |
| Open the Windows Search tool | shell:SearchHomeFolder | Windows Explorer\'search box |
| Open the Windows System folder | shell:System | %SystemRoot%\\System32\\ = C:\\Windows\\System32 |
| Open the Windows System folder for 32-bit files on 64-bit Windows,  <br>Or \\Windows\\System32 on 32-bit Windows | shell:Systemx86 | %SystemRoot%\\SysWOW64\\ = C:\\Windows\\SysWOW64 |
| Open the Windows installation folder (usually \\Windows) | shell:Windows | [%SystemRoot%](https://ss64.com/nt/syntax-variables.html) = C:\\Windows |
| Open the default Sidebar Gadgets folder | shell:Default Gadgets |     |
| Open the folder holding all user profiles | shell:UserProfiles | C:\\Users |
| Open the folder where files are stored before being burned to disc | shell:CD Burning | %LocalAppData%\\Microsoft\\Windows\\Burn\\Burn\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\Burn\\Burn |
| Open the hidden ImplicitAppShortcuts folder | shell:ImplicitAppShortcuts | %AppData%\\Microsoft\\InternetExplorer\\ImplicitAppShortcuts\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Internet Explorer\\ImplicitAppShortcuts |
| Open the list of Network Connections | shell:ConnectionsFolder | Control Panel \> Network Connections |
| Open the saved searches folder | shell:Searches | %UserProfile%\\Searches\\ = C:\\Users\\<username>\\Searches |
| Open the user folder of downloaded Sidebar Gadgets | shell:Gadgets |     |
| Open the user\'s Application Data folder | shell:AppData | [%AppData%](https://ss64.com/nt/syntax-variables.html) = C:\\Users\\<username>\\AppData\\Roaming\\ |
| Open the user\'s Application Data folder | shell:Local AppData | [%LocalAppData%](https://ss64.com/nt/syntax-variables.html) = C:\\Users\\<username>\\AppData\\Local\\ |
| Open the user\'s Credentials folder | shell:CredentialManager | %AppData%\\Microsoft\\Credentials\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Credentials |
| Open the user\'s Documents folder | shell:Personal | %UserProfile%\\Documents\\ = C:\\Users\\<username>\\Documents |
| Open the user\'s Game Explorer folder | shell:GameTasks | %LocalAppData%\\Microsoft\\Windows\\GameExplorer\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\GameExplorer |
| Open the user\'s History folder | shell:History | %LocalAppData%\\Microsoft\\Windows\\History\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\History |
| Open the user\'s Links folder | shell:Links | %UserProfile%\\Links\\ = C:\\Users\\<username>\\Links |
| Open the user\'s Music folder | shell:My Music | %UserProfile%\\Music\\ = C:\\Users\\<username>\\Music |
| Open the user\'s Network Places folder | shell:NetHood | %AppData%\\Microsoft\\Windows\\Network Shortcuts\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Network Shortcuts |
| Open the user\'s Pictures\\Slide Shows folder (if present) | shell:PhotoAlbums |     |
| Open the user\'s Recent Documents folder | shell:Recent | %AppData%\\Microsoft\\Windows\\Recent\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Recent |
| Open the user\'s Send To folder | shell:SendTo | %AppData%\\Microsoft\\Windows\\SendTo\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\SendTo |
| Open the user\'s Start Menu Programs folder | shell:Programs | %AppData%\\Microsoft\\Windows\\Start Menu\\Programs\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs |
| Open the user\'s Start Menu folder | shell:[Start Menu](https://ss64.com/nt/syntax-folders.html) | %AppData%\\Microsoft\\Windows\\Start Menu\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu |
| Open the user\'s Start Menu\\Administrative Tools folder (if any) | shell:Administrative Tools | %LocalAppData%\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\  <br>\= C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools |
| Open the user\'s Startup folder | shell:Startup | %AppData%\\Microsoft\\Windows\\Start Menu\\Programs\\Startup\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Startup |
| Open the user\'s Templates folder | shell:Templates | %AppData%\\Microsoft\\Windows\\Templates\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Templates |
| Open the user\'s Videos folder | shell:My Video | %UserProfile%\\Videos\\ = C:\\Users\\<username>\\Videos |
| Open the user\'s Windows Contacts folder | shell:Contacts | %UserProfile%\\Contacts\\ = C:\\Users\\<username>\\Contacts |
| Open the user\'s \\Music\\Playlists folder | shell:Playlists |     |
| Open the user\'s certificates folder | shell:SystemCertificates | %AppData%\\Microsoft\\System Certificates\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\System Certificates |
| Open the user\'s desktop folder | shell:Desktop | Desktop merged from %UserProfile%\\Desktop + %Public%\\Desktop\\ |
| Open the user\'s downloads folder | shell:Downloads | %UserProfile%\\Downloads\\ = C:\\Users\\<username>\\Downloads |
| Open the user\'s encryption keys folder | shell:Cryptokeys | %AppData%\\Microsoft\\Crypto\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Crypto |
| Open the user\'s printer\'shortcuts folder | shell:PrintHood | %AppData%\\Microsoft\\Windows\\Printer\'shortcuts\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Windows\\Printer\'shortcuts |
| Open the user\'s profile folder | shell:Profile | [%UserProfile%](https://ss64.com/nt/syntax-variables.html) = C:\\Users\\<username> |
| Opens the user\'s AppData\\Roaming\\Microsoft\\Protect folder | shell:DpAPIKeys | %AppData%\\Microsoft\\Protect\\  <br>\= C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Protect |

#### References
[Shell: folder\'shortcuts](https://ss64.com/nt/shell.html)