YouTube_1080p_Downloader
========================

The Problem
-----------

It used to be you could directly download any YouTube video in any quality you wanted, as a single `.mp4` file. However, around a year ago, YouTube switched from the "single file stream", to "DASH" streaming, which streams the video and the audio to you as two separate streams, which are played in sync with each other in the YouTube player.

It's still possible to download YouTube videos as a single file, but YouTube only offers that for qualities up to 720p. So you can't download "single file stream" videos in 1080p or higher.


The Solution
------------

This script downloads the audio and video as separate streams, then uses FFMPEG to re-combine them into a single video file.


Requirements
------------

- `youtube-dl (pip install youtube-dl)`
	- I recommend installing this through `pip` instead of through `apt-get` because the one in the official repositories seems to be outdated. `pip` will ensure you have the most up to date version of `youtube-dl`
- `ffmpeg`
	- WILL NOT WORK if you use the `ffmpeg` found in the Ubuntu repository. That one is old and weird, and will not work with this script. I ended up compiling my own `ffmpeg` ([as described here for Ubuntu](https://trac.ffmpeg.org/wiki/UbuntuCompilationGuide)) which only took about 10 minutes.



