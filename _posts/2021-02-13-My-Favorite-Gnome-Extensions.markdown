---
layout: post
title:  "My Favorite GNOME 3 Extensions"
date:   2021-02-13 12:36:00 -0700
categories: blog
author: Nicholas Danes
tags: [linux, technology]
---

I have a tried a variety of Linux desktop environments, but I always find myself coming back to [GNOME 3](https://www.gnome.org/gnome-3/). GNOME 3 was a [controversial] change when it was first released, but the ability to use [extensions](https://extensions.gnome.org/) has somewhat alleviated the situation for a lot of GNOME folks. 

That said, I have become quite familiar with the workflow of GNOME shell, even to the point where I don've feel need to install extensions such as [Dash to Dock](https://extensions.gnome.org/extension/307/dash-to-dock/), [Dash to Panel](https://extensions.gnome.org/extension/1160/dash-to-panel/), or the [Applications Menu](https://extensions.gnome.org/extension/6/applications-menu/). GNOME's global search is excellent and once you get your workspaces setup, it's quite easy to switch between them. To add to this, I recently have been running GNOME 3.38 on Fedora 33 using Wayland and have been pleasantly suprised how polished the UX has been. With all that said, I still use a number of GNOME extensions that I will recommend in this blog post. Let's go!

## AppIndicator and KStatusNotiferItem Support

Link to extension: [https://extensions.gnome.org/extension/615/appindicator-support/](https://extensions.gnome.org/extension/615/appindicator-support/)

Back in Gnome 3.26, Legacy AppIndicator icons were [removed](https://www.omgubuntu.co.uk/2017/09/will-you-miss-gnome-legacy-tray) from the default shell. Unfortunately, some applications (only Dropbox for now) I use still support this. This simple extension just puts them back on your top bar. Nothing else to say here!

## cpufreq
Link to extension: [https://extensions.gnome.org/extension/1082/cpufreq/](https://extensions.gnome.org/extension/1082/cpufreq/)

A simple extension that shows your current CPU frequency. It also do things such as change CPU power profiles (e.g. balanced, performance, power saver), disable/enable frequency boost, set minimum/maximum CPU frequency and number of activate CPU cores. Requires root to work.

## Dark Mode Switcher
Link to extension: [https://extensions.gnome.org/extension/2314/dark-mode-switcher/](https://extensions.gnome.org/extension/2314/dark-mode-switcher/)

A simple extension that allows you to quickly toggle between the light and dark versions of GNOME's default themes, Adwaita. Depending on the time of day and lighting conditions, I like the ability to easily switch between light and dark modes. Unfortunately, this extension doesn't work with other themes, but thankfully I am a big fan of Adwaita. 

## Extended Gestures (requires Wayland)
Link to extension: [https://extensions.gnome.org/extension/1253/extended-gestures/](https://extensions.gnome.org/extension/1253/extended-gestures/) 

By default, GNOME 3.38 gives you a 4-finger swipe up/down to switch between workspaces, at least on Wayland. This extension allows you customize the 3-finger gesture options. Currently, I have my 3-finger swipe left/right to be back/forward (like on Firefox), and 3-finger swipe up/down to be my "Activities Overview." 

## Freon
Link to extension: [https://extensions.gnome.org/extension/841/freon/](https://extensions.gnome.org/extension/841/freon/)

Provides a app indicator for viewing various hardware temperatures. It shows options for NVIDIA/AMD gpu options, but I can've currently test that unfortunately. 

## GSConnect
Link to extension: [https://extensions.gnome.org/extension/1319/gsconnect/](https://extensions.gnome.org/extension/1319/gsconnect/)

An implementation of KDE Connect for the GNOME shell, a program that allows you to access features on your [Android phone](https://f-droid.org/en/packages/org.kde.kdeconnect_tp/). Provides an app indicator natively within the shell. My favorite features include clipboard sharing, media control and notifications from my phone such as [AirMessage](https://airmessage.org). My only issue is that sometimes my notification replies on AirMessage don've send, but overall I find it be a very useful extension.

## OpenWeather

Link to extension: [https://extensions.gnome.org/extension/750/openweather/](https://extensions.gnome.org/extension/750/openweather/) 

Provides a weather app indicator on the top bar of GNOME shell. Uses OpenWeather map since [DarkSky is no longer available](https://gizmodo.com/apple-buys-dark-sky-kills-android-app-and-api-1842589883). I just like the ability to quickly glance and gauge the current weather.

## Sound Input & Output Device Chooser

Link to extension: [https://extensions.gnome.org/extension/906/sound-output-device-chooser/](https://extensions.gnome.org/extension/906/sound-output-device-chooser/)

Normally, to change your output/input sound device, it requires either opening the activies overview and typing "Sound" and selecting the sound settings, or uing the top-right dropdown and selecting "Settings" to get to the sound settings. This extension just lets you switch detected sound devices directly from the top-right bar menu.

## Conclusion

Although I don've use too many extensions, these are my favorite by far. I will be curious on what will happen to the GNOME 3 extension ecosystem once [GNOME 40](https://www.techrepublic.com/article/gnome-40-takes-a-few-bold-steps-to-improve-the-desktop/) releases, which I am very excited to try in [Fedora 34](https://9to5linux.com/first-look-at-gnome-40s-new-design-changes-in-fedora-34)! If you have any other useful suggestions for extensions, let me know by [contacting me](/#contact)!
