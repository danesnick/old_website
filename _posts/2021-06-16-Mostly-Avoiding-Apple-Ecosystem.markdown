---
layout: post
title:  "How I [mostly] avoid the Apple 'Ecosystem' when using Apple Products"
date:   2021-06-16 09:49:00 -0700
categories: blog
author: Nicholas Danes
tags: [technology, privacy, foss]
---

## Introduction

In recent months, I've recently kind of stumbled into using more Apple products, all of which are in the 'budget' category:

* **Phone:** iPhone SE 2020 64 GB 
	+ I switched to iPhone back in [April](/blog/2021/05/07/switched-to-iphone/). In summary, I moved mostly because of iMessage's massive adoption [here in the United States](https://www.imore.com/what-can-apple-do-make-imessage-more-popular-outside-united-states), and for folks unwilling to switch chat services like Signal or XMPP, I rather message them with something that is end-to-end encrypted compare to plaintext SMS/MMS. 
* **Desktop:** Late 2020 M1 Mac Mini (256 GB SSD, 8GB Unified Memory)
	+ Costco had this on sale for $70 off their normal price. On top of that, [Slickdeals](https://slickdeals.net/f/15017929-costco-members-apple-mac-mini-late-2020-m1-cpu-w-8gb-ram-256gb-ssd-600-free-shipping?page=31#commentsBox) forum members found out there was a $50 off $500 coupon circulating online that Costco members could ask for in the chat support. Because of this, I decided to pick one up to see what all the hype was. Hence, with all discounts, I was able to pick up the Mac Mini for $550 ($150 off MSRP) before tax. It's incredibly snappy and fast computer, despite only having 8 GB RAM. I'm honestly shocked how performant it is given the price I paid. 
* **Tablet:** My fiance had a 7th Gen iPad that wasn't in use, so I decided to start use it for lounging around the house and [eventually] for travel. It doesn't get too much use right now. It also acts as a second monitor using [Sidecar](https://support.apple.com/en-us/HT210380) when needed.  
* **Bluetooth Earbuds:** Airpods
	+ This was another hand me down from my fiance, which I don't think I would have bought. I will admit they're incredibly convenient. They don't sound too great, and I hate the fact they're effectively consumables that might end up the landfill. Thankfully, there's some programs like [Podswap](https://www.thepodswap.com/) trying to create a way to keep them out of the landfill. 


The biggest draw for Apple products is their great design, hardware and integration between their products, often called the Apple 'Ecosystem.' In this post, I will describe what that is, and how I try to avoid it, despite using so many Apple products now. 

## The Apple 'Ecosystem': What is it and Trying to Avoid it

If you haven't heard of the term before, [YouTuber MKBHD](https://www.youtube.com/watch?v=KB4_WIPE7vo) has a great video summarizing what it is. He defines a tech ecosystem as:

>> "...So in tech you know an ecosystem is just a community of interacting objects." - MKBHD, "The 🍎 Ecosystem: Explained!"

In particular with Apple, the ecosystem is defined as:

>> "So Apple makes a ton of devices: you know, the iPhone, the iPad, the Mac, the Apple watch, the Apple TV, the HomePod, AirPods...but they also make software and proprietary technology that ties them all together: AirPlay, AirDrop, Continuity, iCloud." - MKBHD, "The 🍎 Ecosystem: Explained!"

He goes on to explain that once they can get you to buy one of their products (he gives the example of the iPhone), then that causes one to buy other Apple products/services since they work so well together. 
	
### Why avoid the ecosystem?

Despite the convenience of this tight integration, there are reasons to avoid getting too tied into this ecosystem:

* **The "Walled" Garden**: Let's say you need/want to use products with different software (e.g. Windows, Android, Linux); you may not be able to access the technologies you need  without having that Apple product on hand. Some examples of this include: iCloud Drive, iMessage and up until [recently](https://www.theverge.com/2021/6/7/22522889/apple-facetime-android-windows-web-ios-15-wwdc), Facetime. Furthermore, if you decide to switch away from Apple products in the future, it will be much more difficult to make the transition.
* **Privacy**: Despite Apple marketing itself has a "Privacy-first" company and being quite better than say Google or Facebook, they are far from perfect. If you look at their [privacy policy](https://www.apple.com/legal/privacy/), you will see they still collect of a lot of data on you, especially if you rely too much on their integrated services.  
* **Centralized service risk:** There have been random stories of people getting locked out of their [Google accounts](https://www.polygon.com/2021/2/8/22272284/terraria-google-stadia-canceled-developer-locked-out), and the truth is no different here with [Apple](https://dcurt.is/apple-card-can-disable-your-icloud-account). Relying on any cloud service to hold your data is in practice a bad idea, especially if you don't have a backup somewhere else.  

Because of these reasons, I want to explain how I am currently avoiding most Apple services, while still using their products.

## Apple Ecosystem Services Breakdown
I will breakdown by subsection of the various major Apple services that I currently do and don't have alternatives for. In my previous [blog post](/2021/06/11/trying-nextcloud/), I was also looking too avoid other Big Tech alternatives (Amazon, Google, Microsoft) for similiar reasons that I listed above for Apple's ecosystem.

### iCloud

iCloud is the biggest mountain to overcome since it is the most tightly integrated product across all Apple devices. I haven't completely disabled iCloud, as some services are actually [end-to-end encrypted](https://support.apple.com/en-us/HT202303) between your devices. iCloud also deals with syncing contacts, calendar, messages and files if you completely use it. Because of the many moving parts of iCloud, I will have to address components of it individually.

#### iMessage

In particular, iMessage is one to be particularly mindful of, since messages are involved both with iCloud *sync* and *backups*. I will try to summarize the possibilities here:

* **iCloud Sync off, iCloud Backup off**: Encryption keys only stored on device
* **iCloud Sync on, iCloud Backup off**: Encyption keys only stored on device, but Messages can sync across devices. Apple notes this on their iCloud security page:
>> "If you have iCloud Backup turned on, your backup includes a copy of the key protecting your Messages. This ensures you can recover your Messages if you lose access to iCloud Keychain and your trusted devices. When you turn off iCloud Backup, a new key is generated on your device to protect future messages and isn't stored by Apple" - [iCloud Security Overview](https://support.apple.com/en-us/HT202303), End-to-end encrypted data
* **iCloud Sync on, iCloud Backup on**: As shown in the quote above, a copy of your key is uploaded to iCloud for recovery purposes. Hence, *Apple has a copy of your keys if you leave iCloud Backup on*. 

Keeping this all in mind, I still use some of the iCloud sync services. In summary, I have the following still enabled:

* Reminders
* Notes
* Messages (with Backups off)
* Home
* Health
* Wallet
* App data


Reminders and Notes will eventually be transitioned once I find a good alternative. Notes suprisingly integrates natively with [Fastmail](https://www.fastmail.com/help/notes/usage.html), my email provider.

#### Phone Backup

Since I'm not using iCloud backup, I simply use the 'iTunes'/MacOS finder integrated backup solution, which gives me a local backup of my iPhone. They also provide the ability to encrypt the backup, which I also use. That backup is then backed up to an external drive using [Time Machine](https://support.apple.com/en-us/HT201250)


#### Email, Contacts & Calendar

Suprisingly, Apple still supports the IMAP, CalDav, and CardDAV standards for email, calendar, and contacts, respectively. On my devices though, I only really use Fastmail for contacts and calendar, while using the web client and their apps for my email. 


#### Files

As mentioned in my [last post](/2021/06/11/trying-nextcloud/), I was recently testing my own Nextcloud instance, hosting on my old 2018 Mac mini. I ended up selling this device so I could eventually use a dedicated Linux workstation instead for self-hosting. For now, I am using the 100 GB 'Basic' Cloud from [Cloudamo](https://cloudamo.com/) and have been extremely happy with the experience, while only costing $4/mo. I prepaid for a few months and will likely revisit self-hosting once that time comes. For backups from the cloud, I am using [Duplicati](https://www.duplicati.com/) to backup my important files to my 10 GB Fastmail file manager via WebDAV, and also [Backblaze B2](https://backblaze.com), encrypted with PGP.

#### Photos

I was using a combination of iCloud and Google photos for a couple months after switching to iPhone. After being happy with Nextcloud, I ended up deleting my photos from both services completely. I am now using the iOS Nextcloud app for photo syncing from my own. These photos are then able to sync from Nextcloud to my Mac Mini, which I then backup using [Backblaze B2](https://www.backblaze.com/) with [Duplicati](https://www.duplicati.com/), also encrypted with PGP.

For photo management, I initially tried [Photo Prism](https://photoprism.app/), which is *almost* a replacement for Google Photo's AI facial/object recognition for photo organization, but I will likely revisit when I decide to start self-hosting again. In the meantime, I am using a combination of [GNU Image Manipulation Program](https://www.gimp.org/) and [Darktable](https://www.darktable.org/), both FOSS applications, on my Mac mini for photo editing and management.

### Facetime

I honestly rarely use Facetime other than with my Fiance. Since it's becoming cross platform and is end-to-end encrypted, I don't really mind using it with people I know. Otherwise, I do have Signal and [Jitsi Meet](https://meet.jit.si/) as alternatives depending on the person I want to chat with.


### Pages/Numbers/Keynote (Apple Office Apps)

Since I only really use spreadsheets (for budgeting), I don't have much of a need (or an opinion) for a full-fledged office suite for personal use. That said, Apples' Numbers application feels like abandonware, as their mobile, desktop and web apps all feel incredibly half-baked. I was using Google Sheets instead up until recently. Instead, I am using the FOSS alernatives [LibreOffice Vanilla](https://apps.apple.com/us/app/libreoffice-vanilla/id921923693?mt=12) for desktop and [Collabora Office](https://apps.apple.com/us/app/collabora-office/id1440482071) for mobile when I need to edit on budget on the go.


### Safari Web Browser

For web browsing, I use Firefox on desktop, but Safari on my iOS devices, since ad/content blockers are only available on Safari mobile. [Handoff](https://support.apple.com/en-us/HT209455) lets me access tabs that are active on my iPhone/iPad, but will open them on Firefox desktop application. 

### Maps

There is really no good alternative to Google Maps, and that includes Apples' own Map application. Despite that, I still decided to continue using Apple Maps, with [OSMand](https://apps.apple.com/us/app/osmand-maps-travel-navigate/id934850257) also installed with preinstalled mapdata in case I run out of data, since Apple Maps still doesn't support offline map downloads.

## Conclusions

In this blog post, I have overviewed the Apple ecosystem and how I try to avoid it, despite using a lot of Apple hardware. I think my setup is quite doable, especially when using Nextcloud and Fastmail with the backends. Sure it takes a few extra steps to setup, but it's nice knowing that if my Apple account is suddenly closed/locked out, I will be able to access most of my data. Furthermore, I can move and use other platforms with quite ease. If you're also a person still using Apple products and wanted to reduce your dependency to the ecosystem, I hope this setup helps you figure out your own solution!
