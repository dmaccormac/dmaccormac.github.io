---
title: Play audio using VBScript and the Windows Media Player ActiveX control
date: 2024-11-10
tags: vbscript, activex, audio
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
	Do While player.playState <> 1 ' 1 means Stopped
		WScript.Sleep 100
	Loop

Else
    MsgBox "No audio file path provided!", vbExclamation
End If
```

### Explanation
- `CreateObject("WMPlayer.OCX")`: This creates an instance of the Windows Media Player ActiveX control.
- `player.URL = audioFile`: This loads the audio file into the player. You need to specify the full path to your audio file.
- `player.Controls.play`: This starts playback of the audio.
- `Do While player.playState <> 1`: This loop waits until the audio stops playing (i.e., the play state becomes "Stopped", which is represented by the value 1).
- `WScript.Sleep 100`: This makes the script pause briefly (100 milliseconds) so it doesn't consume too much CPU while waiting for the audio to finish.
- `Set player = Nothing`: This cleans up the object after the script finishes.

## Run the script
From Windows GUI: `wscript.exe play.vbs c:\file.mp3`

From the command line: `cscript.exe play.vbs c:\file.mp3`