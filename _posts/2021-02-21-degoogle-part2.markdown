---
layout: post
title:  "My de-Googling journey - Part 2"
date:   2021-02-21 11:58:00 -0700
categories: blog
author: Nicholas Danes
tags: [privacy, android, linux, technology]
---

Back in December  2020, I [wrote a blog post](/blog/2020/12/03/degoogle-part1.html) documenting my de-Googling journey. Since then, I've made enough significant changes to justify an update. Most of these updates are good; however I do want to point out some regressions as I'm trying to find a balance between privacy, usability and mental bandwidth to make changes in my life. This post will focus only what I've changed since my last post, so if you need more context, feel free to read it first!

## Positive Changes

In this section, I will highlight what changes I consider to be a net positive for moving away from Google.

### Google Drive: Syncthing + Backblaze B2

I have officially stopped paying for Google Drive as my sync and backup solution for *personal* use (more on this below). As alternative, I now sync my important files via Syncthing to a Mac Mini I have at home that acts as the central server to sync files to my phone and laptop. A subset of these files (photos, sensitive documents, etc) are now encrypted and backed up using a [Backblaze B2](https://www.backblaze.com/b2/cloud-storage.html) bucket. I personally use [Duplicati](https://www.duplicati.com/) to manage the encryption and scheduling these backups. I also have a second B2 bucket for backing up my home directory on my Thinkpad X390 in case my system borks randomly using [duplicity](https://gitlab.com/duplicity/duplicity) with my GPG key. Although it's not a completely FOSS solution, I don't mind since I'm able to encrypt locally and automate the process.  

I should note that I still have my Google Drive account, as I do manage some band stuff through my personal Google account. I don't see this going away in the foreseeable future. 

### Google Voice: JMP.chat 

I have ported my Google Voice number to [JMP.chat](https://jmp.chat), an XMPP-powered VOIP and SMS/MMS service. I started using the service via their free-trial and was extremely impressed on the service, as well as the customer support. I am now paying $2.99/month to continue using the service. I mostly use it for visual voicemail, voicemail forwarding and for giving my number out to strangers. For this use case, it works perfectly and I am extremely happy. To send/receive calls, I use [Linphone](https://www.linphone.org/). To manage SMS/MMS (as well as my XMPP account messages), I use [Conversations](https://conversations.im).

### Google Wifi: Linksys Velop

I swapped my Google mesh wifi system to a [Linksys Velop](https://www.linksys.com/us/velop/) Wifi-5 mesh system for my home networking needs. I was able to pick up a 3-pack used locally and have had no major issues with it. It is nice being able to access my router settings on the web browser again. 

### Gmail: More Accounts Moved!

I am continuing to transition old accounts from my Gmail into my Fastmail account, deleting unused ones in the process. I believe I have moved most of the important ones, but I'm sure there are others I need to sort through. In particular, any Bitwarden login/password that has my Gmail account has the login. I am taking my time with this, as it is not a fun process. 

## Neutral Changes

Although I have made some positive changes, there are some where I am away from Google, but haven't found something that completely makes me happy as an alternative. 
### Search Engine "Hopping"

I have mostly stopped using Google search, but I have found myself hopping between the following search engines:

* Bing - Owned by Microsoft, but gives you rewards that you can donate to charities
* [DuckDuckGo (DDG)](https://duckduckgo.com) - Mixed success with search results
* [Ecosia](https://www.ecosia.org/) - Uses Bing
* [Startpage](https://startpage.com) - Contextual searches (e.g. weather, conversions) are not as good as Google or DDG
* [Okeno](https://okeano.com/) - Similar to Ecosia, but not sure how they fetch results

As of now, I'm mostly using DDG and Bing, depending on the search. I'm not sure what to settle on at this point. I still use Google for work as these other search engines unfortunately just aren't as good.

### Switching from Standard Notes to Markdown Files via Syncthing
I think [Standard Notes](https://standardnotes.org) is a great application, but my mental bandwidth just didn't want to have to login to another account whenever I setup a new system. To fix this, I moved all my notes to my Syncthing "Sync" folder using Markdown files. I can then edit the notes on my computer using vim/nvim or [Mark Text](https://github.com/marktext/marktext), and use [Markor](https://github.com/gsantner/markor) on my Android phone. So far, this has worked well for me. 

### Web Browsers: Firefox everywhere!

Despite Mozilla's [questionable](https://arstechnica.com/information-technology/2020/08/firefox-maker-mozilla-lays-off-250-workers-says-covid-19-lowered-revenue) [practices](https://blog.mozilla.org/blog/2020/10/20/mozilla-reaction-to-u-s-v-google/) in recent years, there is no good browser alternative that meets the combination of usability and privacy, while also not being Chromium based. Thankfully, Firefox has a great add-on/extension library and many the default privacy settings can be disabled. I am now using Firefox with Sync on all my devices.  

## Regressions

Unfortunately, I did have a few regressions on my de-Googling journey, which I will note here!

### Google Play Store

Once I was able to switch away from Google Voice and Wifi, I tried signing out of my Google account and only using [Aurora Store](https://github.com/whyorean/AuroraStore) to keep my Play store apps up to date. However, the user experience was a little frustrating with auto-updates. Additionally, I still had a couple paid applications I wasn't able to access without being logged in. I eventually caved and switched back to using it. As long as I'm using my Galaxy S10e, I don't see myself switching away from it for the time being.

### Google Maps

In my last update, I was trying to use a combination of [OSMAnd~](https://osmand.net/) and Google Maps Go for my navigation needs. However, I found the UX for both of these still poor, so I ended up switching back to the regular Google Maps navigation app on my phone. Hopefully, this will improve over time as more people contribute to OSM.

### Google Chrome

Recently, [Firefox decided to remove installing web apps](https://bugzilla.mozilla.org/show_bug.cgi?id=1682593) on their browsers. Although chromium-based browsers on Android have the ability to create Progressive Web Apps (PWA's), they are not able to be integrated into my app drawer, unlike standard Google Chrome. Hence, I do use Google Chrome on my phone, but only for PWA's. I also use Google Chrome on my laptop to stay logged into my Google account whenever I need to access it.   

## Conclusions

I feel like I have made a lot of progress on my de-Googling journey, removing my explicit dependence on them for my data. The elephant in the room are the other big companies: Amazon, Apple and Microsoft. I will hopefully try to address my dependence on those companies in the future, although they are not as bad as Google's. Hopefully this provides some options for folks who are also on their own de-Googling journeys!
