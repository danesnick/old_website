---
layout: post
title:  "What's on my phone? - January 2020"
date:   2021-01-15 11:44:00 -0700
categories: blog
author: Nicholas Danes
tags: [android, linux, technology, minimalism]
---

I've seen a lot YouTube videos showing off their phone setups, so I figured why not write a blog post on what my phone setup looks like currently as a means to "snapshot" my technological life. I plan to do one for my desktop as well soon! As with other facets of my life, I try to be digitally minimal as possible, where each app on my phone stays on it due to its utility. If I find myself not using something for a while, or it starts becoming a major distraction, I will uninstall it. A clear example of this is [Tusky](https://tusky.app/), a Mastodon client. I uninstalled the app due to it becoming a major distraction for me. I still access [Fosstodon](https://fosstodon.org) on my web browser to make it a little more inconvenient for me to browse unintentionally.

## The Phone 
<div align="center">
<img loading="lazy" src="/images/phone-Jan2021/s10e.jpg">
<div><i>Back of my Galaxy S10e with the <a href="https://dbrand.com/shop/samsung-galaxy-s10e-skins">DBrand "Swarm" Skin</a> (<a target="_blank" href="/images/phone-Jan2021/big/s10e.jpg">Large Photo</a>)</i></div>
</div>


My current daily driver is a US Unlocked Samsung Galaxy S10e (G970U1) running Android 10 with One UI 2.5. Unfortunately the US Snapdragon variants of Samsung phones have their [bootloaders locked](https://www.xda-developers.com/snapdragon-samsung-galaxy-note-10-galaxy-s10-galaxy-tab-s6-twrp-support/), so currently there is no way to flash roms on these phones, leading to [planned obsolesence](https://en.wikipedia.org/wiki/Planned_obsolescence). I bought this back in March 2020 and have been extremely happy with the hardware, since it includes basic things like SD card expansion, a headphone jack, great camera with unofficial [GCam support](https://www.thetechverts.com/what-is-google-camera-gcam-and-how-to-install-it-on-android-devices/), and guaranteed updates to [Android 11 & 12](https://www.phonearena.com/news/samsung-galaxy-s20-note-android-11-update_id126654). Hopefully with a battery swap, I *should* be able to keep this phone for a few years, assuming I can resist my brain being preconditioned to [perceived obsolesence](https://en.wikipedia.org/wiki/Planned_obsolescence#Perceived_obsolescence). 

## The Apps

For my apps, I try my best to use as few Google apps as possible, as I've been trying to [de-Google](/blog/2020/12/03/degoogle-part1.html) my life whenever I feasibly can. Although I do install some apps from the Play Store, I try to use apps from the [F-Droid](f-droid.org/), a free & open source (FOSS) alternative app store, whenever possible. Some alternatives lack features or just aren't very usable sometimes, unfortunately. If you see a category that isn't FOSS app and you know a good alternative, please let me know by [contacting me](/about/#contact)!

### My Home Screen
<div align="center">
<img loading="lazy" src="/images/phone-Jan2021/homescreen.jpg">
<div><i>My current home screen setup (<a target="_blank" href="/images/phone-Jan2021/big/homescreen.jpg">Large Photo</a>). Wallpaper by <a href="https://unsplash.com/photos/d4feocYfzAM">Damiano Baschiera</a> </i></div>
</div>


Below is a table summary of the apps I currently use on my home screen!

| Type |   App  | Source |
| :--- | :--- | :--- |
| Launcher | Lawnchair  | Google Play |
| Dialer | Google Phone  | Google Play |
| Email | Fastmail  | Google Play |
| Web Browsers | Privacy Browser (Web surfing)  | F-Droid |
| | Firefox Nightly (Accounts)  | Google Play |
| Maps  | OsmAnd~ (Main)  | F-Droid |
|   | Google Maps Go (Backup)  | Google Play |
| Messaging | Signal (Main)  | Google Play |
| | Conversations (XMPP & SMS/MMS via [JMP.chat](https://jmp.chat))  | F-Droid |
| | Google Messages (RCS & SMS/MMS)  | Google Play |
| Notes  | Standard Notes  | F-Droid |
| Music  | Metro Music Player  | F-Droid |
| Podcasts  | AntennaPod  | F-Droid |
| Camera  | Google Camera  | APK |
| Money  | Ally (Banking)  | Google Play |
|   | Chase (Credit Card)  | Google Play |
|   | YNAB (Budgeting)  | Google Play |
|   | Venmo (Send/Receive Money)  | Google Play |
|   | Splitwise (Bill Splitting)  | Google Play |
| One-time Passwords (OTP) | Aegis Authenticator  | F-Droid |
| Weather | Geometric Weather  | F-Droid |

#### FOSS Apps I recommend  (even for non-FOSS advocates)

Even though I think my home screen is fairly organized and minimal, a lot of these apps (like banking) are specific to me only and not things I would recommend to everyone. Many of the Google apps I use, there are just not good FOSS alternatives, at least to me. For example, I used to use [Simple Dialer](https://f-droid.org/en/packages/com.simplemobiletools.dialer/) as my dialing app, but I regularly receive spam calls and Google phone is much better at managing/warning me about those types of calls. Furthermore, the UX on the Google phone app is much better than the Simple dialer, in my opinion. For cameras, there is also [Open Camera](https://f-droid.org/en/packages/net.sourceforge.opencamera/), but the picture quality is poor and requires much more adjustments compared to the Google Camera app, *especially* in low light. I think if we want folks to switch to more FOSS apps, we need them to be *as* usable as the non-FOSS ones, or else widespread adoption will *not* happen. Anyways, of the apps on my homescreen, here are the ones I strongly recommend:

* [Antenna Pod](https://f-droid.org/en/packages/de.danoeh.antennapod/) - I used to be a heavy [PocketCasts](https://www.pocketcasts.com/) user until the 2.0 upgrade of AntennaPod came out, and the app received a major UI overhaul. The app is great, and provides [gpodder](https://gpodder.github.io/) support and local backups which I sync to my desktop using [Syncthing](https://f-droid.org/en/packages/com.nutomic.syncthingandroid/). Just a great FOSS podcasting app!

* [Conversations](https://f-droid.org/en/packages/eu.siacs.conversations/) - A great XMPP client that works extremely well with [JMP.chat](https://jmp.chat), an XMPP-powered VOIP service. If you don't know what XMPP (formerly known as Jabber) is, it is a chatting protocol that has been around for years, and even powers many [chat services](https://xmpp.org/uses/instant-messaging.html) that people use everyday! This included Facebook Messenger and Google Chat before both services discontinued that federation ([Source: Zoom](https://support.zoom.us/hc/en-us/articles/204927135-Facebook-and-Google-To-Discontinue-XMPP-Chat-Protocol)). I would love to get more people using XMPP! 

* [Privacy Browser](https://signal.org/android/apk/) - An Android WebView powder web browser with privacy in mind by default. Lots of great features, including disabled JavaScript by default, built-in adblocking, per domain settings to toggle JavaScript, Cookies, etc and [more](https://www.stoutner.com/privacy-browser/)! The developer is also on [Fosstodon](https://fosstodon.org/web/accounts/235548)!

* [Signal](https://signal.org/android/apk/)/[Molly](https://github.com/mollyim/mollyim-android) - A centralized end-to-end encrypted (E2EE) messaging app for the masses. Sure it has its problems, but its ease-of-use and barrier to entry are extremely user-friendly. I use this to talk to family and close friends mainly since it requires a phone number. If you don't want to use the Google Play version, the [APK](https://signal.org/android/apk/) is available on their website, which is usually is not as up-to-date as the Google Play one, in my experience. There is also a hardened, completely FOSS fork of Signal (Signal is bundled with Google dependencies) called [Molly](https://github.com/mollyim/mollyim-android/releases) but I have no direct experience with it and would like to test it in the future.

* [Standard Notes](https://f-droid.org/en/packages/com.standardnotes/) - A nice, simple E2EE note-taking app. It supports dark mode, and the premium version ads lots of cool [extensions](https://standardnotes.org/extensions). Personally, the free version is enough for what I use it for since i just need to take plaintext notes on the go. There is also an option to [self-host](https://standardnotes.org/help/47/can-i-self-host-standard-notes).

* [Aegis Authenticator](https://f-droid.org/en/packages/com.beemdevelopment.aegis/) - A one-time password (OTP) alternative to Google Authenticator with a lot more features. My favorite feature has to be the ability to create encrypted local backups (which I can sync to my desktop using Syncthing). The UI is very nice too!

### Other FOSS apps I recommend

There also a number of apps in my app drawer that I regularly use, but don't want this blog post to get longer than it already is. I will mention some noteworthy ones below: 

* [Markor](https://f-droid.org/en/packages/net.gsantner.markor/) - A simple Markdown/todo list editor. I mostly use this if I need to update my [Theme Journal](/themejournal/) on the go. 

* [NetGuard](https://f-droid.org/en/packages/eu.faircode.netguard/) - An internet firewall to block network access to apps installed on your phone on a per app level using Android's VPN service. The F-Droid version also allows you to add a hosts file for additional system-wide ad/tracker blocking. This, combined with my [NextDNS](https://nextdns.io) private [DNS over TLS](https://www.androidsage.com/2018/12/25/how-to-block-ads-using-private-dns-dns-over-tls-feature/) setup gives me fairly good tracking protection regardless of my internet connection.

* [Syncthing](https://f-droid.org/en/packages/com.nutomic.syncthingandroid/) - I have already mentioned it a few times above, but *I love Syncthing*. It is not a cloud service, but a decentralized syncing service that allows you to sync files between devices without the use of cloud storage. I mainly use it to sync photos, documents and android configuration files to my desktop so I can properly back them up. I plan on making a short tutorial on how I do this in the future!


## Conclusions

This has been a non-exhaustive look at my phone setup, which is constantly changing. I plan I trying to do these every few months to see how much they change at all. If you have any other recommendations, feel free to [reach out](/about/#contact)! 
