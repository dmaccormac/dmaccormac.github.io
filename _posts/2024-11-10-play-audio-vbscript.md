---
title: How to play audio files in Windows using VBScript
date: 2024-11-10
last_modified_at: 2024-11-13
excerpt: Play audio without showing any GUI using VBScript and the Windows Media Player ActiveX control.
tags: 
  - activex
  - audio
  - vbscript
---

You can use VBScript to play audio using the Windows Media Player ActiveX control (WMPlayer.ocx). To do this, you need to instantiate the WMPlayer.OCX ActiveX control, load the media file, and call the play method.

## Create the script

Here's an example of a VBScript that takes the path to an audio file as an argument and uses the Windows Media Player ActiveX control to play the audio file.

```
If WScript.Arguments.Count > 0 Then
    audioFile = WScript.Arguments(0)
	Set Player = CreateObject("WMPlayer.OCX.7")
	Player.URL = audioFile
	Player.Controls.play
	Do While Player.playState <> 1 ' 1 means Stopped
		WScript.Sleep 100
	Loop
	Set Player = Nothing
	
Else
    MsgBox "No audio file path provided!", vbExclamation
End If
```

## Explanation

- `CreateObject("WMPlayer.OCX")`: Creates an instance of the Windows Media Player ActiveX control.
- `Player.URL = audioFile`: Loads the audio file into the player. Specify the full path to your audio file.
- `Player.Controls.play`: Starts playback of the audio.
- `Do While Player.playState <> 1`: This loop waits until the audio stops playing (i.e., the play state becomes "Stopped", which is represented by the value 1).
- `WScript.Sleep 100`: This makes the script pause briefly (100 milliseconds) so it doesn't consume too much CPU while waiting for the audio to finish.
- `Set Player = Nothing`: Clean up after the script finishes.

## Run the script

From the GUI

`wscript.exe play.vbs c:\file.mp3`

From the command line 

`cscript.exe play.vbs c:\file.mp3`