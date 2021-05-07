---
layout: post
title:  "I switched [back] to iPhone from Android: Pros & Cons after 4 weeks"
date:   2021-05-07 11:10:00 -0700
categories: blog
author: Nicholas Danes
tags: [technology, privacy, android]
---

## Background

For my daily mobile device, I was using [Samsung Galaxy S10e](https://www.apple.com/iphone-se/) up until recently, when I traded in for a [2020 iPhone SE](https://www.apple.com/iphone-se/). As a FOSS advocate, this may be a bit suprising, but I feel like the trade offs between privacy, usability, and convenience were a major factor for my switch. In this post, I will overview what I felt was missing with Android, why I switched to iPhone and what the pros/cons of switching has been so far. 


## What caused me to switch away from my Galaxy S10e

Overall, I was pretty happy with my Galaxy S10 and was able to customize what I wanted and enjoy mostly timely updates. However, there were many constraints that I did not like about the device:

* *Rom Support:* Even though the device was carrier unlocked, there is no way to unlock the bootloader and hence no ability to run third-party custom roms. 
	+ Even if I had a phone with this ability, it seems like custom roms like Lineage OS have many [security vulnerabilities](https://madaidans-insecurities.github.io/android.html) due to its unlocked nature and root access. 
	+ Android Phones like the Google Pixel devices support roms like [Graphene OS](https://grapheneos.org/) which overcome these security issues, with a significant increase in privacy. However, due to the lack of Google Play Services, many apps from the Google Play Store don't work, which I'm currently not in a place to give up certain apps. In particular, apps related to my day job. 

* *More research on Android vs iOS privacy*: In the past, there has been research on how Android [phone home](https://www.bleepingcomputer.com/news/google/idle-android-phones-send-data-to-google-ten-times-more-often-than-ios-devices-to-apple/) significantly more than iOS. More recently, there has been a newer study further [confirming that iOS also collects data](https://www.tomsguide.com/news/android-ios-data-collection), although the data size is smaller compared to stock Android. This is a problem from both platforms which hopefully can be changed in the future.    

* *Messaging apps in the United States*: In my immediate friend/family circle, I would say ~90% of them own iPhones. This means that most people I know use iMessage as their primary instant messaging platform. Because of this, many people are highly resistant to installing third-party chat apps at all. Common third-party apps that people were willing to use were a downgrade in privacy: Discord, Facebook Messenger, and WhatsApp. I was thankfully fortunate to have a subset of my friends use [Signal](https://signal.org/), but there were still some people unwilling to switch. This means that people that weren't on Signal or XMPP (my other chat platform I primarily use) were messaging me with SMS/MMS, which is worse, both from a usability and security/privacy perspective. Even being able to use iMessage with ~90% of my contacts would be a significant upgrade in privacy due to iMessage's [end-to-end encryption](https://www.apple.com/privacy/features/). However, I do recognize that iCloud backups are [end-to-end encrypted but Apple has the keys](https://support.apple.com/en-us/HT202303), but I don't believe Apple is data mining these backups, at least according to their [privacy policy](https://www.apple.com/legal/privacy/en-ww/). I know it's not a perfect solution, but it is an improvement overall in privacy by making this decision to consider an iPhone.

* *Signal Crypto Announcement*: The cataylst to switch away from Android was Signal's [announcement to integrate cryptopayments](https://signal.org/blog/help-us-test-payments-in-signal/) into the app. This raised red flags with folks in the [security community](https://www.schneier.com/blog/archives/2021/04/wtf-signal-adds-cryptocurrency-support.html) and I felt that I needed a backup option in case someting went wrong with Signal in the next few years. I still don't like the decision that Signal made, but I am still using the app as a backup chat platform. That said, this announcement was really the catalyst to want me to switch away from Android.

## My experience with iPhone

### Previous Experience

Back in 2017, I bought the original [iPhone SE](https://en.wikipedia.org/wiki/IPhone_SE_(1st_generation)) for similar reasons mentioned above for iMessage. However, back during these times, I felt iOS was a lot more locked down due to no ability to set default web browser or email apps, and requiring iTunes for local backups and music syncing. I eventually switched back to Android by buying a [Google Pixel 3](https://www.gsmarena.com/google_pixel_3-9256.php) in 2019, which I loved for its camera, but hated for its hardware issues. Even after an RMA, I still had software issues with the Pixel 3. Those hardware issues led me to trade-in for a Galaxy S10e which I was using up until switching to the 2020 iPhone SE 2020.

### Pros 

#### 1st Party Apps are great

Most of the 1st party apps on iOS are great. In particular, Apple Music, Maps, Files, iMessage, Facetime and Camera apps I use on a regular basis and thoroughly enjoy the UI/UX experience.

#### 3rd Party Apps are (also) great

iOS apps, compared to Android, generally feel more polished and less buggy. Even for the Google apps I still have to use, I find them more polished compared to Android. I recognize this is due to its walled garden approach, and only having to support few devices compared to the Android ecosystem. Some of my favorite FOSS apps on iOS include:

* Tofu Authenticator
* Bitwarden 
* Cryptomator
* Firefox

#### Long-term updates

iOS has historically been shown to have [longer software support](https://www.androidpolice.com/2017/11/02/android-versus-ios-software-updates-revisited-two-years-later/) than their Android counterparts. This means the device is generally more secure for a longer period of time, increases its long term value, and theoretically means less upgrades. Though I generally am bad about keeping devices and I need to work on this.  


### Cons

#### Syncthing Support is Limited

In a previous post, I gushed about how much [I Love Syncthing](/blog/2021/03/11/i-love-syncthing/). While I still love it, I unfortunately had to stop using it when I switched to iPhone. There is a third-party app called [https://mobiussync.com](Möbius Sync) which uses syncthing, but currently doesn't support photo syncing due to how the iOS filesystem works. Because of this, I am temporarily using Google Drive with [Cryptomator](https://cryptomator.org/) and Google Photos until I find a good alternative for photo backup and file sync.  

#### No Headphone Jack or USB-C

My previous Android phone still had a headphone jack, which feels like a losing battle these days. I also have to carry a lightning cable for charging, but this is more an inconvenience than a deal breaker. I hope that Apple decides to switch to an open standard in the future.

#### Background Photo Sync

Photo sync in general on iOS seems to be severely hamstringed in any third-party apps. All this means is that one has to remember to open those apps reguarly to sync photos, but again this is also an inconvenience than a deal breaker.

#### XMPP Clients are awful

I was a huge fan of the [Conversations](https://conversations.im/) XMPP app on Android. Everything worked and it had clean, simple UI. However, iOS XMPP clients are another story. All the clients I've tried (SiskinIM, Monal, ChatSecure) all have their issues. I've found SiskinIM to be the most stable, but I still have issues with push notifications in group chats. I hope this improves in the future, and I will be trying to financially contribute to some of these XMPP client projects. 

## Conclusions

Overall I am happy with my switch to iPhone. I miss certain things about Android, but it's nice having something that mostly *just works* and I am able to talk to most people in my day-to-day life with a *more* private chat platform. I will hopefully give another update in the future, but we'll see how this journey goes. I'm sorry if I've disappointed any FOSS friends who are reading this, but I think we all have to figure out what we're willing to put up with for privacy and unfortunately there's no perfect solution. 

