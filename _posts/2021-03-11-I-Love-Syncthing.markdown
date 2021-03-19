---
layout: post
title:  "I Love Syncthing"
date:   2021-03-11 12:53:00 -0700
categories: blog
author: Nicholas Danes
tags: [linux, technology]
---

There are variety of file syncing options out there, with the most popular ones being Dropbox, Google Drive, iCloud, and Microsoft OneDrive. Although the pricing for all these services have very affordable prices (per GB), there is one thing they all have in common; they presume trust on the provider to keep your data safe and respect your privacy. Whether it be a distgruntled employee, poor privacy policies, and/or a data breach, your data's destiny isn't just yours. 

Although there are client-side encryption solutions like [Cryptomator](https://cryptomator.org/) (which I do use for some use-cases) and [Veracrypt](https://www.veracrypt.fr/code/VeraCrypt/) that can be used with any of the cloud services above, I find these solutions quite tedious to use on a daily basis. Alternatively, there are end-to-end encrypted cloud services like [pCloud](https://www.pcloud.com/), [Mega](https://mega.io/sync), and [Tresorit](https://tresorit.com/), there is still an issue of trust regarding governance (especially with Mega), and the trust of client-side encryption (with the exception of [Mega](https://github.com/meganz/MEGAsync)). I'm also incredibly cheap and will only pay for services if absolutely necessary (e.g. privacy). 

As a final alternative, there is the well-regarded open source alternative [NextCloud](https://nextcloud.com/). But on the outside, the service seems like it offers way more features than I would ever need. Furthermore, running one in a VPS can get very expensive for higher storage capacities, and I don't want to deal with managing one locally. 

I've tried various combinations of cloud service and client-side encryption software but I ultimately settled on a very simple, powerful piece of FOSS software: [Syncthing](https://syncthing.net/). Next, I will talk about why I love Syncthing and how I use it on a daily basis.

## What is Syncthing?

To start things, let's start with the description from the official website:

> Syncthing is a continuous file synchronization program. It synchronizes files between two or more computers in real time, safely protected from prying eyes. Your data is your data alone and you deserve to choose where it is stored, whether it is shared with some third party, and how it's transmitted over the internet. Source: <a href="https://syncthing.net">Syncthing</a>

Basically, Syncthing is a *decentralized* filesyncing service without the dependence of a cloud server. It gives you granular control on how, when and which files are synced.

## Why do I love it?

I love Syncthing simply due to its simplicity, ease of use and trust model. As a overview, here is how you generally use it:

* Install Syncthing on your local machine (e.g. desktop)
* Install Syncthing on another local machine (e.g. laptop)
* Add the device ID to each device
* Choose a folder to share on one of the machines (e.g. desktop). 
	+ The syncthing client will detect the folder and ask you to add it to your machine
* Files start syncthing!

Some other notable features include:

* File versioning on a device-by-device basis
	+ Various versioning options, including number of versions, how long to keep, etc.
* Syncing prioritiziation options (random, small files or large files first, etc)
* Syncing can go one-way (receive or send only) or two-way
* User-friendly Web UI
* (Optional) Local and Global Discovery
	+ Allows you to sync your files anywhere!
	+ Discovery can be dynamic or through a static IP
* Encrypted file transfers using TLS
* *Very* Cross-Platofrm
	* Supports Linux, MacOS, Windows, Android, and more!
	* iOS support is [limited](https://forum.syncthing.net/t/syncthing-for-ios/16045)

Since Syncthing is decentralized, you can decide where you can put the files, controlling the trust completely since you can choose to use it only on computers you have access to.

## How I use Syncthing
I don't claim to be an expert with Syncthing and/or networking, and that is not my goal here. I would describe myself as an intermediate-to-advanced Linux user who doesn't mind tinkering with things to get them to work. There are some great advanced guides on Syncthing, one of which I can recommend created by [Lawrence Systems](https://www.youtube.com/watch?v=O5O4ajGWZz8). For now, I will describe my very basic setup on how I use Syncthing. For a basic guide, you can take a look at their [Getting Started](https://docs.syncthing.net/intro/getting-started.html) guide.

### My "home" server: 2018 Mac Mini

There are various ways to setup Syncthing, but for me it made the most since to have one centralized "home server" for which all other devices synchronize with. In my use case, I chose use to my 2018 Mac Mini, since it is always on for me to use [AirMessage](https://airmessage.org) on my Android Phone. Setting up Syncthing on a Mac is as simple as downloading and installing the DMG file from their [GitHub](https://github.com/syncthing/syncthing-macos/releases/). From there, you can access the GUI client by typing <code>http://127.0.0.1:8384/</code> and start setting up your other devices. 

With all my files synced to a centralized "server", I do need to manage some sort of backup solution. To do this, I use [Duplicati](https://www.duplicati.com/) with with [Backblaze B2](https://www.backblaze.com/b2/cloud-storage.html), which uses GPG for encryption, to backup my important files and photos.

### Syncing to my Android Phone

Since I ditched Google Photos, I needed an alternative way to manage my photos. It turns out, that Syncthing's [Android app](https://f-droid.org/en/packages/com.nutomic.syncthingandroid/) is treated as a first-class citizen. You gain access to the very familiar Web GUI, as well as its own native interface. On my Android phone, I pointed a few important directories to sync to my Mac Mini:

* Android Backup - Stores configuration and backup files for things such as NewPipe, Aegis OTP, Signal, etc.
* Docs_Sheets - Stores spreadsheets (Collabora Office) and markdown files (Markor) that I want to be able to edit on the go
* DCIM - My phone's default location for photo storage

I allow syncing to go both ways, so if I delete a photo on my Mac Mini, it will delete on my phone (which is why I have a backup solution!). Additionally, the following folder from my Mac Mini is synced *to* my Android phone:

* Music - My MP3 collection (mostly from Bandcamp and Google Music purchases)

## Syncing to my primary laptop

The last piece of the syncing setup is my laptop. My laptop *only* communicates with the Mac mini, using a originally named folder called <code>Sync</code> which holds my photos, documents, music and other important daily files. On the Mac mini, it also has a folder called <code>Sync</code>, where the items from my Android phone are also synced. This effectively lets me only have to sync one folder between my laptop and Mac mini.

# Conclusions

I am very happy with my file syncing setup. It is very managable, and easy to setup, as well as maintain. Although there are more feature-rich privacy-respecting options, I like the simplicity Syncthing provides for my file syncing needs. I highly recommend it if you're looking for a way to sync your files without depending on a third party. 
