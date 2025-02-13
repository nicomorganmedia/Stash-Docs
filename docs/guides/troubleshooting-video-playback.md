---
title: Troubleshooting video playback
---

## Inspecting files

You can use the ffprobe command to gather useful information about a video file:

```shell
ffprobe -show_format -show_streams big_buck_bunny.mkv
```

This can be useful for example, when filing bug reports, or discussing in chat.

## Remuxing files

Another good test, is to see if remuxing the file into a new video file helps:

```shell
ffmpeg -i big_buck_bunny.mkv -c:v copy -c:a copy remuxed_file.mkv
```

## Extracting a sample of a video

If you are asked for a sample of a video (e.g. for developers to analyse), you can use 

```shell
ffmpeg -ss 120 -i big_buck_bunny.mkv  -t 30 -c:v copy -c:a copy 30_second_sample.mkv
```

The above command starts at the 120-second marker, and takes a 30-second sample of the video file.

## Check the path to the file hasn't changed

If you don't rescan your library very often and use another app, like Whisparr, which to manage your library, files can move without your local stask knowing.

Check the path in file info and if it has changed you can do a selective rescan to update the file path to the correct one.
