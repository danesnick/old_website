---
layout: post
title:  "Trying Nextcloud by Self-Hosting: Initial Impressions"
date:   2021-06-11 17:30:00 -0700
categories: blog
author: Nicholas Danes
tags: [technology, privacy, foss]
---

## Introduction

Last month, I wrote about [switching to iPhone](/blog/2021/05/07/switched-to-iphone/) from Android and overall I've been really happy with the switch. I've been generally been getting grumpy with technology and may have greatly regressed on many of my old privacy goals, for the sake of convenience and features. Some of the pitfalls include:

* Switching to macOS as my desktop OS
	+ iMessage and Phone calls through the OS are unimaginably convenient due to iMessage's commonality in the United States
	+ Audio latency and music recording is extremely cumbersome on Linux and I really just need a low-latency recording solution to track my metronome practices on drums. Hence, Garage Band was a perfect fit. 
* Using more Google services:
	+ Maps - Apple Maps is fine, but there's no offline map support 
	+ Photos - As explained in my switching to iPhone post
	+ Voice - I didn't use my [JMP.chat](https://jmp.chat) account enough to justify the monthly cost, but I rarely use the Google Voice acccount even now.
	+ Drive/Sheets - using a [Cryptomator](https://cryptomator.org) container for sensitive files

Despite all this, I decided it was time to take some action on some of these services, in particular with Google. I have a i3-8100B, 8 GB RAM, 128 GB 2018 Mac Mini that I wasn't fully utilizing, and was also a bit to slow to use as a daily desktop. Hence, I decided to spin up a Ubuntu Server 20.04 virtual machine using [Virtual Box](https://www.virtualbox.org/) to explore self-hosting my own stuff. 

Of all the Google services listed above that I still use, my primary focus was moving away from Photos, since it is a lot of personal data and trust to be put under one provider.

## Self-Hosting Background
I've only dabbled with self-hosting, all of which occured on the Mac Mini mentioned above. In particular, I was able to spin up and set up [Jellyfin](https://jellyfin.org/) behind a [Nginx](https://nginx.org/en/) reverse proxy to access it remotely for the first time for a few months back, but at the time I didn't find a use for it. Because of this experience, I felt a bit more confident in setting things up.

## Going with Nextcloud

I've previously [spoke negatively](/blog/2021/03/11/i-love-syncthing/) about NextCloud, given that it has so many features and managing it locally seemed difficult. Furthermore, I tried [Cloudamo](https://cloudamo.com/), a Nextcloud provider, and found the user experience through the web UI incredibly slow. Despite all this, I heard good things about the Ubuntu [snap package](https://github.com/nextcloud/nextcloud-snap) of Nextcloud, so I decided to give it a try. By going with Nextcloud, I would be able to drop two Google services at once: Drive and Photos. 

## Overview of How I Self-Hosted Nextcloud
This isn't meant to be a guide for self-hosting Nextcloud, but I thought I'd give an overview of the steps I did to get it up and running:

* Setup Ubuntu 20.04 Server Virtual Machine using Virtual Box with 2 cores, 32 GB storage and 2 GB RAM
	+ The snap package for Nextcloud is an option during the installer
	+ Setup [Virtual Box Guest addition](https://www.pragmaticlinux.com/2021/04/install-virtualbox-guest-additions-in-ubuntu-20-04/) so I can add external folders on the host machine
* Open ports 80 and 443 on my router for the local IP address of the VM
* Point an A record of `mynextcloudsubdomain.ndanes.com` to my public ip address in my DNS settings on Fastmail 
* Configure Nextcloud following this [Digital Ocean guide](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-nextcloud-on-ubuntu-20-04), stopping before Step 4.
* Modify Nextcloud's `config.php` file to use a folder on my external drive following [this guide](https://github.com/nextcloud/nextcloud-snap/wiki/Change-data-directory-to-use-another-disk-partition)
* Change Nextcloud's default ports of 80 and 443 to not those
* Setup a nginx reverse proxy for Nextcloud by partially following [this guide](https://damienoh.com/set-up-nextcloud-docker-nginx-reverse-proxy/), skipping the Docker steps
* Setup Nextcloud user account, and start syncing files!
* Once everything is working, setup backups. I loosely followed [Kev Quirk's Nextcloud guide]() for using Duplicati with Backblaze. 

## Impressions so Far

I will breakdown my initial impressions so far in different categories: performance/stability and features.
### Performance/Stability

Performance on my self-hosted VM is noticeably better than Cloudamo's free option. The web UI is noticeable smooth and changing pages loads quickly. The iOS app also navigates smoothly, especially in the photo gallery. So far, it's been an incredibly good user experience. I should note that I initially had the VM installed on a [WD easystire 8TB external drive](https://www.bestbuy.com/site/wd-easystore-8tb-external-usb-3-0-hard-drive-black/6425302.p?skuId=6425302) and obviously saw a noticeable improvement when I moved the VM image to the internal SSD. The bulk of files are still on the external drive and still  

### Features

The amount of [apps](https://apps.nextcloud.com/) that you can install on Nextcloud is sort of overwhelming. For now, I've mostly enabled apps that enhance security, such as 2FA using TOTP and U2F and also the mail app just to see if it worked. Some of the apps in the snap package yet, but I'm honestly fine with waiting. 

I mainly needed Nextcloud to replace two main requirements: file and photo sync. So far, it has served these purposes beautifully. Since I'm self-hosting, a major perk is not having to use client-side encrypted solutions like Cryptomator, making the files easily accessible by just logging in.

## Conclusions

So far, I'm pretty happy with using Nextcloud. Setting it up was fairly low maintenance, and I'm hoping that by using the snap package that updates will also be seamless. I will try to give an update in a few months to see if I end up sticking with it. If I do stick with it, I will finally delete my files off Google Drive and Photos.

### What's missing?
There are a few things that I still need to replace from Google:

* Sheets - The mobile app experience is hard to beat, which is my primary use case for it for tracking my budget on the go. I may try to use Nextcloud's integration with [Collabora Office](https://nextcloud.com/collaboraonline) or [ONLY OFFICE](https://www.onlyoffice.com/en/office-for-nextcloud.aspx) as a potential solution. 
* Maps - [OpenStreetMaps](https://www.openstreetmap.org/) is a common recommendation, but I still find the experience extremely lacking. I may just reinstall it on my phone and try to be better about contributing to the project
* Photos - Although Nextcloud photos gives me the ability to get my photos off my phone and onto a hard drive easily, there are no editing tools, no machine-learning based face/object recognition and the gallery application is a bit lacking. There are many self-hosted alternatives outthere, but all of them seem to be missing a feature or two that Google Photos provides. The best potential candidate I've found so far is [Photo Prism](https://photoprism.app/) which I'll be closely watching.  


If you have any other recommendations, please [let me know](/#contact).




	

