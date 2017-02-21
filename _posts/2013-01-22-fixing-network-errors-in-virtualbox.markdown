---
author: milocasagrande
comments: true
date: 2013-01-22 10:57:33+00:00
layout: post
link: https://www.milo.name/2013/01/22/fixing-network-errors-in-virtualbox/
slug: fixing-network-errors-in-virtualbox
title: Fixing Network Errors in VirtualBox
wordpress_id: 515
categories:
- News
---

This is that kind of post that are more necessary to me for remembering than anything else. Lots of digital ink has already been spent on this topic, but, as others I guess, I find that writing down things helps me remembering them (and mind-maps are precious on that front).

#### VirtualBox Clone Operation

I have a couple of local virtual machines installation for Ubuntu desktop and Ubuntu server, usually the latest LTS ones, and I clone them as I needed: I need to test some scripts, or the installation of a program, like it was being performed on a real installation.

VirtualBox has this nice little feature of creating clones of your virtual machines, and in no time you are up an running with a clean environment (as long as you remembered to take a snapshots at a good point in time).

#### The Error

When you clone a virtual machine, you are cloning everything of it, configurations included. And that's where the problem is. The network will not work at all, and ifconfig will tell you that there is no interface configured.

#### The Solution

The solutions lies in one file:

    /etc/udev/rules.d/70-persistent-net.rules

Open that file with your editor, remove the offending line and reboot.

In this case the offending line is an erroneous "_eth*_" interface, that will results in multiple network entries in that file when just one is needed. Pay attention to the MAC address of the network interface though.
