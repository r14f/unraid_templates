# Automatic Ripping Machine (ARM)

## Overview

Insert an optical disc (Blu-ray, DVD, CD) and checks to see if it's audio, video (Movie or TV), or data, then rips it.

See: https://b3n.org/automatic-ripping-machine

use         lsscsi -g 
on root of unraid to get info for --device for cd/dvd/blurat drive

for handbrake presets 
https://handbrake.fr/docs/en/latest/technical/official-presets.html


## Features

- Detects insertion of disc using udev
- Determines disc type...
  - If video (Blu-ray or DVD)
    - Retrieve title from disc or [OMDb API](http://www.omdbapi.com/) to name the folder "Movie Title (Year)" so that Plex or Emby can pick it up
    - Determine if video is Movie or TV using [OMDb API](http://www.omdbapi.com/)
    - Rip using MakeMKV or HandBrake (can rip all features or main feature)
    - Eject disc and queue up Handbrake transcoding when done
    - Transcoding jobs are asynchronously batched from ripping
    - Send notifications via IFTTT, Pushbullet, Slack, Discord, and many more!
  - If audio (CD) - rip using abcde (get disc-data and album art from [musicbrainz](https://musicbrainz.org/))
  - If data (Blu-ray, DVD, or CD) - make an ISO backup
- Headless, designed to be run from a server
- Can rip from multiple-optical drives in parallel
- Python Flask UI to interact with ripping jobs, view logs, update jobs, etc



## Usage

- Insert disc
- Wait for disc to eject
- Repeat


