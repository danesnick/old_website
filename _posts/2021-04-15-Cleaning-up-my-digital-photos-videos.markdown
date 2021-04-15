---
layout: post
title:  "How I Cleaned up my Digital Photo & Video Collection"
date:   2021-04-15 08:21:00 -0700
categories: blog
author: Nicholas Danes
tags: [technology, privacy, minimalism]
---
Back in October 2020, I was using Google Photos for my digital photo & video management and sharing platform. I still believe Google Photos is probably the best photo management application out there, in terms of features, UX and pricing. However, the privacy implications of using the service are unfortunately hard to ignore.

One criticism of the Google Photos app is how to delete old photos/videos. I think the application feels sluggish in the regard. Also, I felt like Google Photos was enabling my digitally hoarding a lot of photos/videos over the past decade or so due to their unlimited storage option (up until [recently](https://www.androidauthority.com/google-photos-free-storage-1176862/)). and felt like it was finally time to sort through and clean up my collection. This post will **outline** the general guidelines on how I did this and is not intended to be a guide. As a end result, I went from *approximately __50 gb to 9 gb__ of photos/videos* by going through this process.

## Step 0: Google Takeout

Of course the first step is getting my photos/videos out of Google using their takeout service. The process is fairly straight forward; they provide a checklist of all their services that provide a data export. Once you request the export, you wait until you receive a email link to download the collection as a compressed file.

When you download the compressed file, you will find the photos are organized with a particular hierachy based on EXIF data by date. Additionally, you also see JSON files for each photo that provide EXIF metadata. I personally ended up deleting the JSON files by recursively finding them and deleting them. I don't have the exact script/command I used to do this, but you can do something similar in bash by using something like [this](https://unix.stackexchange.com/questions/116389/recursively-delete-all-files-with-a-given-extension).

## Step 1: Import to Photo Manager

Next, I started looking for a photo management application and ended up going with [GNOME Shotwell](https://wiki.gnome.org/Apps/Shotwell) since I am on a Linux operating system, and found the app to suit all my basic needs of managing photos/videos. 

## Step 2: Go through all photos/videos (the hardest step!)

This step took me several months to complete. Over the past few months (approximately October 2020 to present), I would randomly open Shotwell and go through my photos to delete. My criteria for deleting was loosely based on the following:

* Is the photo too blurry?
* Do I have multiple "similiar" photos?
	+ Dog photos! Of course I kept some of them :D
	+ Photos of landscapes, parks, and museum exhibits 
* Will I ever reference or share this photo again?
	+ Sold used items
	+ Receipts outside warranty/return policy
	+ Referencing photos from chats with friends/family
* Does this photo bring up a "bad memory"?

A similar process was also applied to my videos as well. A **majority** of my photo/video size was reduced during this step.

## Step 3: Optimize those files!

> **WARNING**: Make a copy or backup of your photos/videos before attempting anything in this section. If you don't like the end result (like overcompressing) or you change one of the commands incorrectly, you won't be able to recover the original photo/video.

### JPEG

Since most of these photos were taken from smartphones and were usually JPEG files, I decided to optimize how much space they were taking up. There are a few different CLI tools to do this, but I decided to use [jpegoptim](https://github.com/tjko/jpegoptim), which allows for easy batch processing. By default, `jpegoptim` uses a lossless optimization algorithm to optimize files, and will skip files that results in a larger file size. Optionally, you can add lossy compression which is what I did. I ended up finding a bash script on the [Arch Forums](https://bbs.archlinux.org/viewtopic.php?id=178748) that allows you to run jpegoptim recursively to apply to every subdirectory of photos you want to optimize. I made the following modification for 90% quality and [progressive jpegs](https://www.liquidweb.com/kb/what-is-a-progressive-jpeg/) only:

	jpegoptim --max=90 --all-progressive *.jpg 

If you have PNG files too, there's a similar tool called [optipng](https://optipng.sourceforge.net/). I ended up converting the few PNG files I had to JPEG using [imagemagick](https://imagemagick.org/index.php) instead. 

### MP4

For my video files, I decided to use [ffmpeg](https://ffmpeg.org/) to optimize the files by converting them to [H.265]. I found a reference on [Stack Exchange](https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg) to convert an mp4 using H.265 using ffmpeg.

Prior to running this, I ended up moving all my videos to their own folder using a `find` ([reference here](https://unix.stackexchange.com/questions/67503/move-all-files-with-a-certain-extension-from-multiple-subdirectories-into-one-di):

	find . -name \*.mp4 -exec mv "{}" /path/to/Videos \;

Then, batch converting can be done using the following script:

	#!/bin/bash -x
	for i in *.mp4;
	  do name=`echo "$i" | cut -d'.' -f1`
	  echo "$name"
	  ffmpeg -i "$i" -vcodec libx265 -crf 28 "ffmpeg_converted/${name}.mp4"
	done

where the original form of this bash script was found [here](https://stackoverflow.com/questions/5784661/how-do-you-convert-an-entire-directory-with-ffmpeg). I got roughly a 50% reduction in file size with not much loss in quality by doing this!

## Conclusions

I am extremely happy with how many photos/videos I was able to get rid of by going through this process. I am still trying to figure out where to host my photos for syncing and sharing in the future, but hopefully I can find a good option soon. If you have any recommendations, feel free to [contact me](/#contact) and let me know! 
