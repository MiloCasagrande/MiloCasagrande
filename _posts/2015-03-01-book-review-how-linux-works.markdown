---
author: milocasagrande
comments: true
date: 2015-03-01 14:47:13+00:00
layout: post
link: https://www.milo.name/2015/03/01/book-review-how-linux-works/
slug: book-review-how-linux-works
title: 'Book Review: How Linux Works'
wordpress_id: 579
categories:
- Books
tags:
- book
- linux
- nostarch
- review
---

_Disclaimer: I received a free a copy of "[How Linux Works 2nd Edition](http://www.nostarch.com/howlinuxworks2)" to review from [NoStarch Press](http://www.nostarch.com)._

[caption id="attachment_594" align="aligncenter" width="660"][![How Linux Works Cover](http://www.milo.name/wp-content/uploads/2015/03/how-linux-works-1024x683.jpg)](http://www.milo.name/wp-content/uploads/2015/03/how-linux-works.jpg) How Linux Works 2n Edition book cover.[/caption]

I enjoy doing these occasional [reviews](http://www.milo.name/2013/01/17/book-review-think-like-a-programmer/): it's a good excuse to read a new book, learn something new (there's always something to learn, every day) and to move my eyes aways from a light emitting digital device (yeah, apart from when I actually write the review…). And since I fully read the books, that's why usually it takes some time to review them all.

I have to admit I love NoStarch books: lovely cover arts, a nice book form factor, well written and edited content, multiple formats to choose from (paper, digital DRM-free versions). And "How Linux Works" is no less.

## The Review: How Linux Works by Brian Ward

17 chapters strong, the book opens with a general overview of a Linux system providing the reader with a really clean explanation of the differences between the kernel space and the user space, moving to a quick overview of the shell system.

From Chapter 3, the pace changes, and it's here where the author starts diving into into the real Linux system. Devices, device types, sysfs and how they are implemented at the kernel level are an introduction to concepts that will be taken further in Chapter 4, where file systems, a generic overview on how they fit into the kernel, and the most used and common commands to work with partitions, are introduced.

I consider Chapter 5 and Chapter 6 to be the strength of the book: how the Linux boot process works, what GRUB is, does and how to configure it, all clearly explained with detailed steps of the overall boot process. And then, as a natural consequence after the boot phase, the init systems are introduced and the reader is taken further into the user space land.

Chapter 6 covers basically everything that is needed nowadays to understand the init process: systemd, upstart and sys-v are all explained in their glory details (although the latter is the less detailed): how they are configured, where their configurations are located and the different terminologies each adopts are easy to understand.

From here on, the book covers all that is necessary: logging, users, /etc and login methods with a focus on PAM (Chapter 7); processes, resources, CPU & I/O and all the commands to help you in performance diagnosis (Chapter 8); network, network configuration, a concise but exhaustive introduction to the network layers, the kernel routing table and internet/network user space applications (Chapter 9, 10).

Chapter 11 takes us back to the shell with an extensive coverage of its most useful and used commands, that will lead as to know all the file sharing programs available at our fingertips (Chapter 12).

The remaining chapters cover the user space environment: startup files, desktop environment and window manager, D-Bus, CUPS; development tools (compilers, debuggers) and how to compile software.

Of all the book, I found these last chapters (counting also Chapter 12) to be the less interesting: probably because most of the concepts described were already known, or they were covering not (that) much interesting subjects to me.

### In the End…

The book is really well organized, technically accurate and up-to-date with the recent modern Linux technologies. A really great Linux power-user book that doesn't spend too much time in a graphical environment, but concentrates on command line tools and the depths of how a Linux system is glued together. Read it if you want to expand and deepen your Linux knowledge.
