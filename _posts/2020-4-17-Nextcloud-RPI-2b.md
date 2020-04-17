---
layout: post
title: Will it run - Nextcloud on Raspberry Pi 2b
categories: [raspberrypi, nextcloud, software, hardware, project]
tags: [raspberrypi, nextcloud, easy]
---
<!--more-->
Kano - Powered by the Raspberry Pi 2B. Probably the worst $150 that can be spent. In hindsight, a 512mb computer that runs at a *700 MHz* base clock probably wasn't such a good idea for any sort of GUI application. I had no idea how to overclock at the time, so I was left with a bulky case and a "computer" that is only useful as a paperweight. However, I'll save that rant for another day. It looks as if I finally have found a use for this excuse for a computer. Today, I am going to be sharing my experience with using the Raspberry Pi 2B for a Nextcloud server.
<!--more-->

The disclaimer bit: I just want to say that your mileage may vary (with any section of this) due to special conditions that I try to put my Raspberry Pi 2 in to optimize performance (such as *stone cooling* my Pi).

OK, now to using the Pi. I have a bunch of Micro SD cards laying around, so I flashed one with the [OwnYourBits Nextcloud](https://ownyourbits.com/nextcloudpi/), which is a prebuilt image of Nextcloud equipped with special tools and its own web dashboard to make installing Nextcloud insanely easy....until you try and modify it (which we will be doing because the vanilla image takes a crazy amount of time to load anything). I'm on Windows, so I used WinRAR to extract the file, then [balenaEtcher](https://www.balena.io/etcher/) to flash NextcloudPi onto the SD card. After removing the SD card then reinserting it, the "boot" partition showed up. Since SSH is disabled by default because of a security issue with default passwords, you now need to make a file called "ssh" at the root of the boot partition. The makers of the Raspberry Pi made this so you can't get hacked if you use the default password when you boot the Pi. This is not a problem for us since we will be changing the password when we boot. To enable SSH, I made a file called ssh.txt with Notepad in "boot" with no content in it. I clicked File --> Save As, then switched the .txt to "All Files", then removed the .txt ending, making it just "ssh".

I inserted the SD card into the Pi (with an adapter), and it booted right up. You can use any power supply that has a Micro USB ending on it, but later we will need a more powerful supply for overclocking. I connected an HDMI cable from the Raspberry PI to my TV, logged in with the default username `pi` and default password `raspberry`. The first thing that needs to be changed is the default password. To change this, type `passwd`, enter your current password (`raspberry`), then type your new password, which should be strong, but rememberable since you will need this when you remotely connect. 

### Time to completion: ~10 hours
### Difficulty: 3/10
