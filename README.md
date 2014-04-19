YouTube 1080p Downloader
========================

The Problem
-----------

It used to be you could directly download any YouTube video in any quality you wanted, as a single `.mp4` file. However, around a year ago, YouTube switched from the "single file stream", to "DASH" streaming, which streams the video and the audio to you as two separate streams, which are played in sync with each other in the YouTube player.

It's still possible to download YouTube videos as a single file, but YouTube only offers that for qualities up to 720p. So you can't download "single file stream" videos in 1080p or higher (at least not directly from YouTube).


The Solution
------------

This script downloads the audio and video as separate streams, then uses FFMPEG to re-combine them into a single video file.


Requirements
------------

- `youtube-dl (pip install youtube-dl)`
	- I recommend installing this through `pip` instead of through `apt-get` because the `youtube-dl` in the official repositories seems to be outdated. `pip` will ensure you have the most up to date version of `youtube-dl`
- `ffmpeg`
	- WILL NOT WORK if you use the `ffmpeg` found in the Ubuntu repository. That one is old and weird, and will not work with this script. I ended up compiling my own `ffmpeg` ([as described here for Ubuntu](https://trac.ffmpeg.org/wiki/UbuntuCompilationGuide)), a process which only took about 10 minutes.


Usage 
-----

	{scriptname} {youtube video url}


Assuming the script is called `yt1080download.sh` and is located in your current directory, here's an example invocation:
	
	./yt1080download.sh https://www.youtube.com/watch?v=XSGBVzeBUbk

Upon completion of the script, you'll have a 1080p copy of [this YouTube video](https://www.youtube.com/watch?v=XSGBVzeBUbk) in your current directory called `Big Buck Bunny animation (1080p HD)-1080p.mp4`.


Notes
-----

- This script will only work on videos that are available in 1080p. It will fail if you attempt to run it on a YouTube video that is, for example, only in 720p.
- This script does not re-encode the audio or the video that is downloaded from YouTube. They are combined as-is into a single file. This preserves the video quality, and greatly improves the speed of combining the streams.
- Run time of this script is largely dependant on your internet speed and how fast you can download the media from YouTube. For a 10 minute YouTube clip on a machine that has a 100mbps internet connection, this script will produce a video in about 30 seconds.