---
layout: post
title:  "My 30+ Days using Gentoo Linux: A Newbie's Perspective"
date:   2021-01-28 13:51:00 -0700
categories: blog
author: Nicholas Danes
tags: [linux, technology]
---

I've been using Linux on/off since about 2009. However, primarily I've been a Ubuntu/Debian user, only occassionally trying other distributions such as Fedora. During the 2020 Christmas break, I decided to install Gentoo on my personal desktop as a learning experience. When I was originally planning to write this blog post, I had no plans of moving away from Gentoo Linux as my daily driver. Unfortunately, I was trying to switch from my kernel build from [genkernel](https://wiki.gentoo.org/wiki/Genkernel) to a [distribution kernel](https://www.gentoo.org/news/2020/09/15/distribution-kernel.html) and I ended up breaking my install, unable to get my LUKS partition to decrypt. I really didn't want to spend time fixing it, so I decided to install Elementary OS 5.1 Hera, as I had it on a flash drive lying around.

Regardless, I would like to talk about my experience, both the positives and negatives. I will preemptively say there is more positives than negatives. Let's begin!

## Installing Gentoo

In this section, I will give an overview of my process when I decided to install Gentoo. Of course, before doing any of this, I made sure to backup my important files both locally and in the cloud. From my perspective, this is the *hardest* part of the Gentoo experience.

### Installing a VM using QEMU+KVM

Before I decided to install Gentoo on baremetal, I setup an installation using [QEMU+KVM](https://www.qemu.org/) on my at the time Ubuntu 20.04 install. I followed the [AMD64 Guide](https://wiki.gentoo.org/wiki/Handbook:AMD64) as closely I could for the installation. Ultimately, I was able to setup the virtual machine with [XFCE](https://xfce.org). 

### Baremetal Installation

After completing the QEMU+KVM install, I decided I was ready to install it on my actual hardware. Thankfully, I had a spare SSD on hand, so I was able to install Gentoo while keeping my Ubuntu 20.04 install setup in case anything went wrong.

#### Setting up LUKS+LVM

For my second run through of the installation, I decided I wanted disk encryption for the drive. Thankfully, Gentoo has good documentation on how to set up [LUKS encryption with LVM](https://wiki.gentoo.org/wiki/Full_Disk_Encryption_From_Scratch_Simplified). However, through my experience on running through the documentation, I did find myself having to cross reference the [AMD64 Manual](https://wiki.gentoo.org/wiki/Handbook:AMD64) as well. Nevertheless, I was able to setup LUKS and boot using GRUB by pointing to the appropriate UUID in my <code>/etc/fstab</code> file.

#### Deciding on Kernel setup

Most people think you have to customize and setup your own kernel on Gentoo. Of course, in principle this is a good learning experience, but for my first install, I decided to go with the [genkernel](https
://wiki.gentoo.org/wiki/Genkernel) option. Gentoo also provides [distribution kernels](https://wiki.gentoo.org/wiki/Handbook:AMD64/Installation/Kernel#Alternative:_Using_distribution_kernels) (with a binary option) now as well if you really don't want to deal with updating your kernel yourself and apparently will also update with Gentoo's package manager Portage. In retrospect, I wish I went with the distribution kernel during my first setup.

#### Installing GNOME

For my desktop environment, I initially decided to try [GNOME using OpenRC](https://wiki.gentoo.org/wiki/GNOME/GNOME_Without_systemd/Gentoo). This took hours, despite having 6 threads on my i5-8400. After all said and done, I was able to enter my desktop environment! The experience with Gnome was largely the same for me without systemd, except I didn't experience those random shutdown hangtimes you can sometimes experience with a hanging systemd process.

## Learning Gentoo

### Portage

The best part about Gentoo is through its package manager Portage. Portage is a source-based package manager where packages are installed through the command <code>emerge</code> You can think of <code>emerge</code> as functionally similar to <code>apt</code> or <code>dnf</code>, but the packages and its dependencies in most cases are built from source. Because most packages are built from source, this allows you to customize compiler flags and dependencies on a package-by-package basis; Portage makes managing how you want to setup dependencies and compiler flags incredibly user-friendly. I'm not going to go into detail about Portage, but I will highlight the parts I used and enjoyed the most about it.

#### Package USE Flags

One of the most powerful features of Portage was USE flags. USE flags allow you to enable/disable dependencies on all the packages available through Portage. For example, as seen in the [XFCE guide](https://wiki.gentoo.org/wiki/Xfce), you can build a package without any QT 5 dependencies by passing the parameter to <code>emerge</code>:

{% highlight bash %}
$ emerge --ask package-name -qt5
{% endhighlight %}

You can even apply this globally by adding the following to the <code>/etc/portage/make.conf</code> file:
{% highlight bash %}
.
.
.
USE="-qt5"
.
.
.
{% endhighlight %}

#### Package Keywords

Gentoo is considered to be a rolling release distro, but does not keep bleeding edge packages in the main repository like Arch Linux, for example. By default, it will use the latest LTS kernel and will keep packages held back until they have been sufficiently tested. However, if you'd like to use a package version that is no in the main/stable repositories, these are accessible through the use of <code>ARCH</code> keywords. For example, if you're using a 64-bit x86 system, <code>ARCH=amd64</code> and accessing unstable packages can be obtained by setting <code>~amd64</code> for the desired package under <code>/etc/portage/package.accept_keywords</code>. For example, if  I wanted to install Dino, I would create the file <code>/etc/portage/package.accept_keywords/dino-im</code> with:

{% highlight bash %}
net-im/dino-im ~amd64
{% endhighlight %}

If you know what you are doing (or stupid, like me). You can also set this keyword globally in your <code>/etc/portage/make.conf</code> file:
{% highlight bash %}
.
.
.
ACCEPT_KEYWORDS="~amd64"
.
.
{% endhighlight %}

More on this below...


#### Portage will *try* to keep you from breaking things

When you emerge packages, Portage will check to see what dependencies you need for a package, as well if there is any conficts due to masked packages/dependencies. Similarly, if you want to remove a package, Portage will also not depenencies that other installed packages may need.

However, if you decide to use unstable packages via <code>~amd64</code> keyword, things will probably break. I did this shortly after setting up GNOME, and ended up having to re-emerge a lot of packages after breaking my GNOME desktop environment. At the time of this happening, I thought there was just something wrong with GNOME, so I switched to XFCE. 

### Gentoo Overlays

If you're familiar with Ubuntu PPA's, package overlays are analogous on a Gentoo system. Overlays are often unofficial, user maintained set of [ebuilds](https://wiki.gentoo.org/wiki/Ebuild) that are publically available to other users, typically on GitHub. There are a variety tools that make accessing these overlays easy, such as [layman](https://wiki.gentoo.org/wiki/Layman). With these overlays, I was able to access things such as the megasync client, which is normally only available in deb or rpm packages. 

## Conclusions

Overall, I really enjoyed my time with Gentoo. It was a good learning experience to know how to setup a Linux system only using a tty for setting up drive partitions (with LUKS), kernel install, bootloader configuration, etc.  

What I really enjoyed the most about Gentoo is how powerful Portage is as a package manager. It really gives you more control than any other package manager I've ever used. This alone is a reason to use Gentoo.

I also really enjoyed Gentoo's official documentation. For example, compared to other distros I've heavily used like Ubuntu, I find Ubuntu's official documentation extremely lacking, and often find solutions for problems either through StackExchange, StackOverflow and/or the Ubuntu forums. 

What I disliked the most about Gentoo was compile times for certain packages. For example, I decided to use an overlay for ungoogled-chromium that required building from source, which would take hours to recompile and update. Of course, binaries for packages like LibreOffice or web browsers are usually available to avoid this. 

Another thing I didn't enjoy was sometimes package availability. Sure, there was often an overlay that would provide the package, but there was often some trial and error getting certain packages to emerge properly given dependencies and USE flags currently used on my system.

Although Gentoo's official documentation was very good, when I ran into very specific problems, sometimes determining solutions was a bit difficult through web searches. I'm fairly stubborn when I have issues and I don't usually like asking for help (which often could have fixed my problems more quickly, I'd imagine). On the flip side, since Debian/Ubuntu-based distributions are very popular, you can typically find solutions for problems fairly quickly. 

### Would I use Gentoo in the future?

If I didn't bork my installation earlier this week, I'd probably be typing this post on my Gentoo installation. However, fixing things issues like this are just not in my mental energy to do so nowadays, especially because my day job I do stuff like this as a daily occurence. Maybe when I have a bigger gap of free time, or if I get a new Linux-friendly machine, I would consider installing Gentoo again.

### Would I recommend it to others?

I've heard somewhere on the internet that "Gentoo is a hobby", and I think for me, that rings *partially* true. I took the opportunity to install and learn the basics of Gentoo during a holiday break. If I had tried using Gentoo during my graduate school days, I would hate having to take away research time to fix my OS (which would likely not happen if you stay on the stable repositories) or having to wait for important updates to compile. Regardless, I think if you have some free time to get through the initial installation and are able to *carefully* read documentation, you will really enjoy a Gentoo system. Also, I've come to learn more and more that some folks [do use Gentoo in a production environment](https://www.youtube.com/watch?v=C0xpWHNdBv4), so I wouldn't be opposed to recommending it in some situations.

That's all I have to say for Gentoo for now. As mentioned above, I am currently running Elementary OS 5.1 on my desktop and have really enjoyed the Pantheon desktop environment from a UI/UX perspective, so I will likely stay here for now. Thanks for reading about my experience with Gentoo!

For more insight on Gentoo, I highly recommend you read [Hund's blog post](https://hunden.linuxkompis.se/2020/05/25/why-i-like-gentoo.html) on why they like Gentoo. 
