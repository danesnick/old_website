---
layout: post
title:  "Thoughts on macOS and why I'm going back to Windows/Linux for personal use"
date:   2021-11-20 08:49:00 -0700
categories: blog
author: Nicholas Danes
tags: [technology]
---

## Introduction

In my [last post](/blog/2021/08/16/chronological-timeline-computing-devices/), I talked about my adventure with various computing devices in 2021. I wish it was over, but unfortunately I am me. I tend to be a tech minimalist and try to own as few devices as possible. My fiance got a 2020 13" M1 Macbook Pro from me as a gift after she finished school back in July. However, this machine was largely collecting dust and I decided to start using it and ended up selling my Thinkcentre that was described in my last post. However, with the holidays coming up and other personal factors, it came time for my fiance to start using her Mac again so I had to start factoring in whether I wanted to stay on macOS by buying another Macbook, or going back to PC.

I have primarily been a Windows and Linux user for most of my computing life. However, as a tech geek I've always liked trying new things and see what is across the virtual pond that is macOS. Although I own other Apple devices, such as my iPhone and iPad, there's something about macOS that always hasn't rubbed right for me. 


In this post, I will go over my history using macOS, what I don't like and like about it and why I'm going back to Windows/Linux.


## My History with macOS Machines


### My First Macbook Pro

My first exposure to owning a macOS machine was purchasing a 2009 15.4" Macbook Pro back in 2009, which I believe was running Mac OS X Snow Leopard. At this time, no PC could match the hardware/build quality of the Macbook Pro lineup and it was incredibly well built machine. Despite this, even back then I ran into frustrations with the OS. I ended up selling this machine and picked my first ever Linux machine, a [System 76 Sterling Netbook](https://janehadley.net/Starling_Review/starling_review.html) running Ubuntu 9.04 Jaunty Jackalope. 

### A Second Try in Graduate School

Around 2017, I was loaned a 15" Macbook Pro for an internship working as a graduate student researcher. I don't remember model specifics, but I remember getting frustrated with window management (more on this below) and constantly hearing the fans spin up when doing basic tasks. On my personal machines at this time, I was running Ubuntu or PopOS regularly for all my graduate student research. Having to shift to a MBP for work definitely felt like it was getting in my way a lot.

### My macOS usage in the present

Over the years since 2017, I've tried various macOS products, including, but not limited to:

* 2019 13" Macbook Air - returned
* 2020 13" Intel Macbook Pro - my current work laptop I've used since late 2020
* 2020 M1 Mac Mini - returned
* 2020 13" M1 Macbook Air - returned
* 2020 13" M1 Macbook Pro - My fiance's device and I'm typing this blog post on it now!

Despite all these attempts to the use macOS as my daily driver, I have constantly ran into frustrations with the OS. However, before I go into my frustrations with macOS, I wanted to highlight what I enjoy that Windows / Linux do not provide.

## What I like about macOS

### Apple Apps and Ecosystem

I've blogged about the [Apple ecosystem](/blog/2021/06/16/mostly-avoiding-apple-ecosystem/) in the past,  but since that post, I've come to learn that you really get the best experience when you dive in completely and use the applications / integrations that Apple provides. The tight integration of macOS with other Apple devices, such as an iPhone or iPad, is unmatched on any other ecosystem. Some of these tight integrations include, but are not limited to:

* iMessage, Phone Calls, and FaceTime across devices
* Copy+Paste syncing between devices
* GarageBand is unmatched as a free audio recording software suite
* Handoff is very convenient to continue looking at a browser tab from one device to another
* AirDrop to send photos from my phone to the Macbook for a quick post

All these things are great, but unfortunately they don't outweigh my annoyances with macOS. Let's dive in!

## What I dislike about macOS


### Quick disclaimer

I know a lot of the issues I listed below are either niche or have workarounds. For most folks, they will not run into these issues and will have a good experience with macOS. However, **for me**, for an OS from a company that claims "it just works", I haven't had that experience for my use case with macOS. I started driving to daily drive macOS because I was getting grumpy with configuring tech, and macOS ironically was making me do that more. 


### Display Scaling Headaches

The first thing that frustrates the most about macOS is display scaling support on external displays. Without going to a bunch of scenarios with external monitors, here are the main points:

1. macOS was designed to look good around [110 PPI](https://blog.leiy.me/post/mac-external-display/) for low DPI and looks best around 220 PPI for high DPI, also known as "Retina". Most, if not all modern Apple Mac devices have Retina displays.

2. For monitors less than 110 PPI, the UI will look appropriately scaled, but fonts will look poor due to sub-pixel anti-aliasing disabled by default, starting with [macOS Mojave](https://www.howtogeek.com/358596/how-to-fix-blurry-fonts-on-macos-mojave-with-subpixel-antialiasing/) and [completely removed](https://www.archyde.com/macos-big-sur-removes-system-preferences-option-to-smooth-fonts/) starting with macOS Big Sur. This makes fonts look quite terrible in the OS on displays that are under 110 PPI if you are too close to the screen.

3. For monitors between 110 and 220 PPI, you may run into issues with small UI elements. However, display scaling issues get worse depending on what monitor you have:  
	1. If you own a [4K monitor](https://apple.stackexchange.com/questions/342682/how-to-properly-use-scaling-on-an-external-display-from-macbook-pro-2016), macOS does expose the display options to scale the display. However, this still makes fonts look semi-blurry from my experience, especially compared to scaling on a Windows 10 computer.  
	2. If you own a monitor that is **not** 4K, say a 23.8" 1440p panel (~122 PPI) in my case, you will get no options for display scaling at all by default. You can lower the resolution, but that defeats the purpose of using a higher resolution monitor. In contrast, Windows looks beautiful at 150% scaling on my 23.8" 1440p monitor. This seems to be a conscious choice by Apple since all their devices have Retina displays, and hence they have no financial incentive to support odd display situations.
	3. The situation gets more complicated whether you own a Intel or Apple Silicon machine. With my point in 3.2, if you own a Intel machine with a non-4K display between 110 and 220 PPI, there are workarounds by adjusting system files to trick macOS into thinking your monitor is Retina. The one I've tried successfully is the [one-key-hidpi](https://github.com/xzhih/one-key-hidpi) I found on GitHub. If you own a Apple Silicon machine, this workaround isn't supported. Instead, you have to create a dummy 4K display that your monitor can mirror in order to show the HiDPI scaling options. If you are in this situation, the application [BetterDummy](https://github.com/waydabber/BetterDummy) makes this much easier to manage.

Hence, monitors in macOS are largely a headache unless you own a 4K panel. Even with a 4K monitor and/or the workarounds, I still find the font and UI scaling looks poor compared to using the same monitor with Windows or Linux. 

### Weird Audio Issues

I've had a number of weird audio issues with macOS, especially recently. For my computer "speakers", I use a Anker Soundcore 2 bluetooth speaker. However, when connected via bluetooth, I started noticing YouTube videos would hang and not play until I disconnected the device. Still not sure why this is happening.

The other annoyance I've had is with how macOS handles volume control on sound devices. If your audio device is *not* bluetooth or the system speakers, macOS does not let you adjust the volume of the device. So situations such as HDMI/DisplayPort audio and my Scarlett Focusrite USB audio interface do not allow for audio adjustment through the volume shortcuts on my keyboard. This is a small quality of life thing, but this is never a problem with Linux or Windows.


### Window Management

I know a lot of people love how macOS handles windows through trackpad gestures and spotlight search, but I've personally never fully gotten used to it. I've tried tools such as [Rectangle](https://rectangleapp.com/) and [Alfred](https://www.alfredapp.com/) to improve the window management experience, but I still find the OS gets in my way a lot, despite using for over a year on my work machine.


### Multi-Monitor Quirks

I recently started trying to use the Macbook Pro 13" display as my main display, with my 23.8" monitor as my secondary monitor for quick glance items. Unfortunately, there has been weird quirks with this setup as well. 

First, if you put a full-screen YouTube video a secondary display, [the top menu bar](https://apple.stackexchange.com/questions/336066/two-displays-menu-bar-disappears-in-fullscreen) vanishes on the primary display. Although this doesn't break functionality, it feels like an afterthough from a UI/UX perspective.  

Second, has to do with virtual workspaces. One suggestion to handle open windows in macOS is to take advantage of virtual workspaces. You can cycle through them by either opening Mission Control (F4 or CTRL + Up arrow key), cycling through workspaces with CTRL + Left/Right arrow key, or 3-finger left/right swipe gestures on the trackpad. However, on the secondary display, only Mission Control works on changing virtual workspaces. I haven't figured out why this isn't working my situation, as searching around for this suggests I shouldn't be having this issue. 


## Conclusions

Overall, macOS is very polished and good looking operating system and I can see the appeal both for developers and creatives. However, my use case for computing doesn't necessarily require macOS and my particular set of hardware/computer accessories have made it more frustrating to use. I will miss some of the tight integrations with my iPhone/iPad, but these are more nice to haves than must haves. 

I have a [Lenovo Ideapad Slim Pro 7i](https://www.costco.com/lenovo-ideapad-slim-7i-pro-14%22-touchscreen-intel-evo-platform-laptop---11th-gen-intel-core-i7-11370h---2880-x-1800---windows-11.product.100794401.html) coming in the mail hopefully next week and am very excited to go back to Windows/Linux (my work device is still macOS so I'm stuck there for now). I will likely document my experience in a future blog post so stay tuned! 



