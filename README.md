# Prototype for audio normalization

## Introduction

The goal of this prototype is to implement the audio normalization process using FFMPEG and the loudnorm filter.
FFmpeg is the leading multimedia framework, able to decode, encode, transcode, mux, demux, stream, filter and 
play pretty much anything that humans and machines have created. It supports the most obscure ancient formats up 
to the cutting edge. No matter if they were designed by some standards committee, the community or a corporation. 
It is also highly portable and for this reason represents a valid alternative to perform the normalization process.
 
## What exactly audio normalization means?

With audio normalization we identify the process of GAIN alteration on a given track. The goal of this track is to 
force all the tracks in input to be on the same "loudness" so that the human hear perception will be the same 
across all of them.

## Setup

In order to run the Script you need to:

1. Install python 3.x - http://docs.python-guide.org/en/latest/starting/install/linux/
2. Configure FLASK - following the guide here: http://flask.pocoo.org/docs/0.11/installation/
3. Download FFMpeg - https://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz

## Track Processor configuration

The track-processor.py script uses the following paths to retrieve tracks so that it is mandatory to keep it up 
to date with your local environment settings. To do so, open the script and update the following entries:

songs_folder = '/home/<your-name>/<path-where-the-songs-are-stored>/songs/'
songs_normalized_folder = '/home/<your-name>/<path-where-the-songs-will-be-stored-after-normalization>/normalized/'
ffmpeg_executer = '/home/<your-name>/<path-where-ffmpeg-is-placed>/'

## Run flask

It's very easy to run the track-processor.py on flask. What you need to do is just to run in your terminal:

python /home/<your-name>/<path-to-the-project>/track-processor.py

And you're done.

## How to use the app

Open the FFMPEG_demo.html page in your browser and in the text input "Loudness value", insert a value ina  range of
-70.0 to 0.0. Then pick all the tracks you want to normalize using the "Another Track" button and the input file.

Once you're done click on "Track Information and Normalization!" link. You can check what's happening on your terminal 
(the one that currently hosts flask - track-processor.py). Once everything is done, a new page will be prompted and you
will be able to check what is changed from the original track to the new one that will be placed in the 
"songs_normalized_folder". To listen for them it is recommended to use the final_page.html file. In it there's also an
explanation of the normalization filter and how it works.
