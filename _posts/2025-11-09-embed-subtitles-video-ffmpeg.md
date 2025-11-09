---
title: Embedding subtitles into video files using FFmpeg
date: 2025-11-09
excerpt: How to use tools like VLSub and FFmpeg to download and embed subtitles into your video files.
tags: 
- vlsub
- yt-dlp
- ffmpeg
- subtitles
- mkv
- srt
---

# Introduction 

Embedding subtitles into a video file - especially in a container like MKV - has several advantages over keeping subtitles as separate .srt files or using containers like MP4, which do not support embedded .srt subtitles.

Embedding subtitles directly into an MKV file improves portability by keeping everything in a single package, eliminating the need to manage separate .srt files. It also enhances compatibility with media players, allowing users to toggle subtitles on or off during playback. Additionally, MKV supports multiple subtitle tracks, making it easy to include and switch between different languages within the same file.

In this post, we'll walk through how to use tools like VLSub [[1]](#references) and yt-dlp [[2]](#references) to download subtitles and then use ffmpeg [[3]](#references) to embed these subtitles into an MKV container.


# Download subtitles
An `srt` file is a plain-text file that contains subtitle data, including the start and end timecodes and the text to be displayed. It's one of the most widely supported subtitle formats and is compatible with media players, video editors, and containers like MKV. 

You can obtain SRT files from subtitle databases such as [OpenSubtitles.org](https://www.opensubtitles.org/), or by using tools like VLSub (for VLC) or yt-dlp (for YouTube videos). To create your own, you can manually write subtitles in a text editor following the SRT format, or use subtitle editing software like SubtitleEdit [[4]](#references).


## Using yt-dlp
You can use the following options with `yt-dlp` to dowload both `srt` and `mp4` files:

```batch
yt-dlp --write-subs --write-auto-subs --convert-subs srt --sub-lang en -f "bestvideo[ext=mp4]+bestaudio[ext=m4a]/mp4" --merge-output-format mp4 https://www.youtube.com/watch?v=VIDEO_ID
```


## Using VLSub

VLSub is an extension for VLC Media Player that lets you search and download subtitles directly from OpenSubtitles.org. 


1. Open VLC and start playing your video.
2. Go to **View > VLSub**.
3. Enter the movie title and select the language.
4. Click **Search by name** or **Search by hash** (hash works best).
5. Select a subtitle and click **Download selection**.

Once downloaded, you’ll have an `.srt` file ready to be merged.

# Merge video and subtitles

FFmpeg is a powerful, open-source command-line tool used for processing audio and video files. It can record, convert, stream, and manipulate multimedia content in a wide variety of formats.

We can use the following options with ffmpeg to merge video and subtitles files:

```bash
ffmpeg -i input.mp4 -i subtitles.srt  -c:v copy -c:a copy -c:s copy output.mkv
```

Command breakdown:

- `-i input.mp4`: Input video.
- `-i subtitles.srt`: Subtitle file.
- `-c:v copy`: Copies video without re-encoding.
- `-c:a copy`: Copies audio without re-encoding.
- `-c:s copy`: Copies subtitles without re-encoding.
- `output.mkv`: Output file with embedded subtitles.


Since we are just copying all three streams here, we could shorten the above command as follows:

```bash
ffmpeg -i input.mp4 -i subtitles.srt -c copy output.mkv
```


Additionally, we can tag the subtitle stream as English, helping media players display it correctly.

```bash
ffmpeg -i input.mp4 -i subtitles.srt -c copy -metadata:s:s:0 language=eng output.mkv
```

Command breakdown:

- `-i input.mp4`: Input video.
- `-i subtitles.srt`: Subtitle file.
- `-c:copy`: Copies all streams (video, audio, subs) without re-encoding.
- `metadata:s:s:0 language=eng`: Tag subtitle stream 0 as english.
- `output.mkv`: Specify output file.

## Batch file solution
I've created the following batch file which to easily create MKV files with embedded subtitles. 

Select both your `mp4` and `srt` files, then drag and drop them onto this batch file. The output file will be saved to the same directory with the file extension `.sub.mkv`.

```batch
for %%a in (%1) do set vid=%%~na
for %%b in (%2) do set sub=%%~na
set outdir=%~dp1

ffmpeg -i %1 -i %2 -c copy -metadata:s:s:0 language=eng "%outdir%%vid%.sub.mkv"

timeout 30
```

# Conclusion

Using tools like VLSub and ffmpeg, you can quickly grab subtitles files and embed them into an MKV file that’s portable and player-friendly. Putting this workflow together in a batch file provides a robust and easy to use solution for merging video and subtitle files into a single output file.

# References 
[[1] VLSub GitHub](https://github.com/exebetche/vlsub)

[[2] yt-dlp GitHub](https://github.com/yt-dlp/yt-dlp)

[[3] FFmpeg Download](https://ffmpeg.org/download.html)

[[4] SubtitleEdit](https://github.com/SubtitleEdit/subtitleedit/releases)

# Appendix

Use yt-dlp to download subtitles and embed subtitles into MKV container:

```batch
yt-dlp --write-subs --write-auto-subs --embed-subs --convert-subs srt --sub-lang en --merge-output-format mkv https://www.youtube.com/watch?v=VIDEO_ID
```