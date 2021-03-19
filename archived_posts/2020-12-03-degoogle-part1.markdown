---
layout: post
title:  "My de-Googling journey - Part 1"
date:   2020-12-03 11:35:00 -0700
categories: blog
author: Nicholas Danes
tags: [privacy, android, linux, technology]
---
*Edited: 01-14-2021*

As many more folks in the world seem to feel, many of the services/features provided by "the big 5", GAFAM (Google, Apple, Facebook, Amazon, Microsoft) have given us a tremedous amount of convenience, at the cost of our privacy. Among the big 5, I think Google products have always made me feel the most conflicted due to my enjoyment of their services. However, as [Chris Wiegman](https://chriswiegman.com) as stated in his blog, I agree that [privacy is not a zero-sum game](https://chriswiegman.com/2020/06/privacy-empathy-and-the-zero-sum-game/); there are always trade-offs that need to be made between our ability to be productive or improve our lives versus the freedoms we lose. Furthermore, I think incremental improvements are better than no improvements at all and we should not treat changes in our privacy as black and white issues. In this post, I will summarize what I have and haven't replaced, and my reasoning for those choices. The remainder of this post, will loosely follow the format done by [Cassidy James Blaede's blog.](https://cassidyjames.com/blog/de-googling/)
### Complete

#### Search: Google to DuckDuckGo + Startpage

I have been on/off user of [DuckDuckGo](https://duckduckgo.com/) for years, but also switched to Bing on/off, simply due to the fact they give you points toward gift cards for using their search engine. However, recently there has been some [privacy concerns](https://lemmy.ml/post/31321) with DuckDuckGo circulating in some circles, but I haven't fully investigated it myself.  

I am currently using [Startpage](https://startpage.com) as my daily search engine, which also has had its criticisms with privacy due to their [recent acquisition by System1](https://support.startpage.com/index.php?/Knowledgebase/Article/View/1275/0/what-is-startpages-relationship-with-privacy-onesystem1-and-what-does-this-mean-for-my-privacy-protections). For me, it's about "harm reduction" so I'm fine with using either over Google. 

#### Browers: Chrome to Firefox + Ungoogled Chromium/Bromite

I was an on/off chrome user for years, but I've mostly settled into using Firefox on my desktop, with [Ungoogled-chromium](https://github.com/Eloston/ungoogled-chromium) as a secondary browser and [Bromite](https://www.bromite.org/fdroid) on my Android phone. I tried Firefox for Android on the past, and just didn't like the user experience.

#### Email/Contacts/Calendar: Gmail to Fastmail

I have switched away from my Gmail account in the past, but for some reason returned. I think at the time, I didn't let the data-mining practices of Google bother me for a period of time, especially when I was using a Pixel 3 as a daily driver. 

Back in October, I decided it was time move away again. I owned the domain nicholasdanes.com in the past, but thought the domain name was too long for me to be practical. This time, I purchased ndanes.com through NameCheap and ultimately decided on [Fastmail](https://fastmail.com) as my email provider. I know there are more privacy friendly options such as Protonmail or Tutanota, but having a transition period with some of my accounts to Gmail makes email management without IMAP conveniently available on Linux was a dealbreaker for me. Additionally, as [@celia](https://fosstodon.org/@celia/105304537350668024) on Fosstodon pointed out, encryption at rest with our emails only solves part of the problem; if people are still using large providers for email and we are still emailing these folks, then little has changed. 

Fastmail also has provided many quality of life features that other providers wouldn't have given me. First, I can send/receive emails from my Gmail account as I slowly transition things over. Second, I have unlimited aliases through my domain, so I can use example@ndanes.com for example.com, for example, to organize my emails, as well as mitigate issues if there's a data breach with my account. Third, they provide DAV support for contacts, calendar, and storage. With this, I can sync my contacts & calendar using the app [DavX5](https://f-droid.org/en/packages/at.bitfire.davdroid/) on my Android phone. My website here, is also hosted on Fastmail, due to their static html webpage support. 

Overall, I'm very happy, and will likely stick to the service at least for a few years and then re-evaluate once my accounts tied to my Gmail are completely switched over. 

#### Notes: Google Keep to Standard Notes

I wasn't a heavy user of Google Keep; I mostly used it for quick notes, grocery lists, and so forth. I decided to switch back to [Standard Notes](https://standardnotes.org), which I have used in the past. It is a free and open source note-taking app with end-to-end encryption support of the box. The free version only supports plaintext (with paid features adding a lot of extensions). I tried the paid version and quickly realized I didn't really need any of the features it provided. They also have an (outdated) [F-Droid build](https://f-droid.org/en/packages/com.standardnotes/), which I hope will eventually be updated. In the meantime, you can either get the [apk](https://standardnotes.org/download) directly from their website, or use the Google Play version (which I'm doing for now). 

#### YouTube: Newpipe (Android) + FreeTube (Desktop)

I absolutely love YouTube as a content platform. However, when I used to use the YouTube app and website directly, I would waste a lot of time falling into the rabbit hole that is the YouTube algorithm. Thankfully, I found a solution that would allow me to track my subscriptions on both mobile and desktop without relying on my Youtube account.

For mobile, I use [NewPipe](https://f-droid.org/en/packages/org.schabi.newpipe/) to manage my subscriptions, and watch videos. Before deleting on my subscriptions on my YouTube account, NewPipe provides a link with instructions on importing your YouTube subscriptions in a JSON file via Google Takeout. For your convenience, here is [instructions](https://newpipe.schabi.org/FAQ/tutorials/import-export-data/) on their website! 

For the desktop, I try to use the app [FreeTube](https://freetubeapp.io/). It provides support of import/export the same JSON file from NewPipe, which I can then sync between my devices via [Syncthing](https://syncthing.net/). It also has support for [Indivious](https://github.com/iv-org/invidious/wiki/Invidious-Instances), a privacy-respecting front-end for YouTube. However, the app can be buggy and sometimes I have to copy of the video link over to the browser. But overall, I'm okay with the tradeoff.   

#### Google Photos: Syncthing + Backups

For Google Photos, my solution is a little simple but works for now. Like mentioned above for my YouTube subcriptions, I use [Syncthing](https://syncthing.net/)
to setup a photo sync between my phone's DCIM folder and my laptop + desktop. To manage the photos on my desktop, I currently use [Gnome Shotwell](https://wiki.gnome.org/Apps/Shotwell). For backups, I currently make encrypted backup of my entire home directory (which includes these photos) to an external drive. I also make an encrypted copy of my photos/videos into a [Cryptomator](https://cryptomator.org/) container on my Google Drive account using rsync manually with my Google Drive folder on my local machine, provided by [Insync](https://www.insynchq.com/), which unfortunately is not a FOSS solution.
  
### Incomplete

#### Android

Unfortunately, I am currently using a Samsung Galaxy S10e (US Snapdragon) as my daily phone, which has its bootloader locked; this means I have no options for custom roms such as LineageOS. To mitigate Google tracking, I have tried to minimize the number of Google Play apps, turn on [NetGuard](https://f-droid.org/en/packages/eu.faircode.netguard/) with host blocking, and favor apps in the [F-Droid](https://f-droid.org) store. If you also have a phone that can't install a custom ROM, I also recommend using this [Universal Android Debloater](https://gitlab.com/W1nst0n/universal-android-debloater) script (use at your own risk/I am not responsible if you brick your phone) to remove bloated apps from OEM's such as Samsung. I won't go into all the android apps I use here, but I plan to do so in a future blog post.

My eventual goal is to sign out of my Google account and use the [Aurora Store](https://f-droid.org/en/packages/com.aurora.store/) once I can let go some of the few Google services I'm still using. 
  
#### Google Drive

Due to its price and currently only needing less than 100 GB of cloud storage for my personal data, I am still using Google Drive to backup crucial data. As mentioned above, I am currently using Cryptomator to encrypt my data at rest to mitigate this fact. For daily syncing, I still use Syncthing for files I need between devices. Additionally, since I don't use it for daily syncing, Google Drive does not need to be installed as an app on my phone.

#### Google Sheets/Docs

For my [bands](/music), I unfortunately still use Sheets/Docs (and Google Drive) for collaboration with bandmates, as I haven't quite made the jump to approach them toward alternatives. Hopefully, this can happen in the future!

#### Google Maps

Many folks have recommended [OSMAnd~](https://f-droid.org/en/packages/net.osmand.plus/) as an alternative to Google Maps, but unfortunately I haven't been able to rely on it completely. One major issue is the lack of street numbers/addresses that have not been provided by users. I try to contribute street numbers/addreses when I can, but there is an occasional case where I have to use Google Maps for Navigation. I try to mitigate this by using it as a web app on my phone, relying only on Navigation Go from the Google Play store. 


#### Google Voice

I mostly use this for voicemail forwarding for visual voicemail on my cell phone, and text/voice for instances where I don't want the other party to have my main phone number, such as buying/selling on Craigslist. I'm not sure how to entirely replace this yet, nor if I want to completely.


#### Google Wifi

Last year, I bought a Google Wifi puck for my house and eventually had to buy a second one when I moved, due to the walls in my new place having poor wifi reach. Replacing this has mostly been a financial constraint, as I'm still waiting for Wifi-6 mesh router prices to go down. Recommendations here are welcome! 


### Conclusion

If you made it this far, thanks for reading my de-Googling journey so far. Next time, I think I will dive a little deeper on my Android app setup, which will hopefully have more progress by the time I write the post. Of course, if you have any suggestions for some of my choices, I'd appreciate it! Thanks for reading!


