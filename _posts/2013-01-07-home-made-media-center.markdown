---
author: milocasagrande
comments: true
date: 2013-01-07 12:30:32+00:00
layout: post
link: https://www.milo.name/2013/01/07/home-made-media-center/
slug: home-made-media-center
title: Home Made Media Center with Ubuntu
wordpress_id: 425
categories:
- Media
- Ubuntu
tags:
- media
- tv
- ubuntu
---

During the Christmas holidays I spent some time "refurbishing" a netbook me and my girlfriend have, but is not used, into an home-made media center, running (at the moment) plain Ubuntu 12.10.

We watch some TV, during and after dinner, mostly for TV series and movies, and we used to do that loading everything on a USB key attached to the TV. A boring, and repetitive task. So why not giving some new life to that small netbook?

#### Ingredients

All the ingredients for this recipe are:

  * A netbook (this one has an Atom N570 CPU, 1GB RAM, 500GB disk)
  * Copy of Ubuntu 12.10 32-bit
  * VGA cable
  * 2 USB hard-disks
  * A [Hi-Fi system](http://store.sony.com/p/2.1-channel,-surround-sound,-40-inch,-home-theater-system,-speaker,-wireless,-Bluetooth/en/p/HTCT260#overview) (optional)

Installing the operating system, the necessaries codecs and all the updates is an easy-peasy experience nowadays. Nothing special to report, everything works flawlessly. After connecting all the cables, safely hidden from the eye (the back of the TV is turning into a jungle), the netbook-turned-media-center is now stored in a shady place in the living room, connected to the TV via its VGA cable (unfortunately the only video output), linked to the Hi-Fi via Bluetooth (hurray! one cable less!), with close to 2TB of USB-connected disk space, sharing videos and music on the internal network.

At the moment I'm piloting the media center via a VNC connection from a Nexus 7, but I'm planning to find a (or write my own) keyboard and mouse app for the tablet to pair up via Bluetooth with the netbook. Or a special Ubuntu oriented Android app to control an Ubuntu machine in an easy way.

I tried installing Rygel to serve media files, but had no luck in making it work. I will have to dig deeper and give it another try. The other solution I was pondering was to install XMBC. Time permitting, I'll probably try it out.

Of course everything is not perfect: I have some high quality videos, [Matroska](http://en.wikipedia.org/wiki/Matroska) files weighing from 2 to 8 GB, that the system is not handling in a good way. The smallest ones are not reproduced correctly, audio and video are out of sync, the biggest ones are not reproduced at all: or you get video, or you get audio. Guess the decoding is not that fast to handle everything is a smooth way. Listening to music via the Bluetooth connection to the Hi-Fi, is not as bad as I would have thought: it actually provides a really enjoyable experience.
