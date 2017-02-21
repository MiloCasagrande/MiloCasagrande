---
author: milocasagrande
comments: true
date: 2012-05-20 09:57:04+00:00
layout: post
link: https://www.milo.name/2012/05/20/kindle-4-pc-under-linux/
slug: kindle-4-pc-under-linux
title: Kindle 4 PC Under Linux
wordpress_id: 167
categories:
- Ubuntu
tags:
- drm
- kindle
- ubuntu
---

If you are trying to install or use Kindle for PC under Linux, I had a problem with the version of Wine shipped by default in Ubuntu 12.04 (that is Wine version 1.4).

After installing [Wine PPA](https://launchpad.net/~ubuntu-wine/+archive/ppa) and upgrading to version 1.5, I had another problem, but this one is easily solvable: it is necessary ro rename or remove one file from the Wine installation directory. The file is:

    drive_c/windows/winsxs/manifests/x86_microsoft.vc90.crt_1fc8b3b9a1e18e3b_9.0.30729.4148_none_deadbeef.manifest

and Kindle 4 PC will work in all its glory. Just saying it here since I found different results on the Internet, with different solutions, none of which were really working. Somebody is also reporting the necessity to have ttf-mscorefonts installed to have it work, I didn't install them, or they have been installed by default.

Why using Kindle for PC? I'm trying to export books bought via the Kindle Store, but without the DRM. Looks like [Calibre](http://calibre-ebook.com/) is able to do it, but I had no luck. There are [plugins that should help you](http://www.wired.com/gadgetlab/2011/01/how-to-strip-drm-from-kindle-e-books-and-others/) with that, but I still have errors while trying to import a DRMed book.

What should be necessary is a Kindle PID, not the serial number, that can be found out easily, plus your Kindle serial number. With both of them, nothing will change. I do not know if with the latest Kindle generation Amazon changed something in their encryption mechanism...

If anybody out there had more luck, fancy sharing your experience?
