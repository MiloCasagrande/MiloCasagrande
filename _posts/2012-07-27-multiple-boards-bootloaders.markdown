---
author: milocasagrande
comments: true
date: 2012-07-27 16:38:06+00:00
layout: post
link: https://www.milo.name/2012/07/27/multiple-boards-bootloaders/
slug: multiple-boards-bootloaders
title: 'Multiple Boards and Bootloaders on a Single Hardware Pack  '
wordpress_id: 209
categories:
- Development
tags:
- arm
- linaro
- ubuntu
---

#### Multiple Boards and Bootloaders

Finally, [Linaro Image Tools](https://launchpad.net/linaro-image-tools) has support for multiple boards and multiple bootloaders on single configuration file and hardware pack.

#### Linaro Image Tools

Linaro Image Tools is a set of command line utilities that help in the creation and installation of Linaro built operating system images so they can be run on [ARM](http://www.arm.com/) based computers.

With Linaro Image Tools you can take a generic ARM [Ubuntu](http://www.ubuntu.com) or [Android](http://www.android.com/) operating system image and customise it with the hardware specific packages needed to make it run on a specific board. These hardware specific packages are found in a hardware pack, which itself is generated using a tool, linaro-hwpack-create and a configuration file.

#### The old days

[caption id="" align="aligncenter" width="430"]![Old days computer](http://u1.ipernity.com/10/05/29/3670529.a9875504.1024.jpg) The Old Days of Computer[/caption]

In the "old days", this configuration file (an [INI-style](http://en.wikipedia.org/wiki/INI_file) configuration file) and hardware pack held information for just one ARM board: it was not possible to define a single configuration file for multiple boards that shared most, if not all, of the same configuration and as a consequence, the resulting hardware pack could only be used with a single device too.

Starting with the new [2012.07 Linaro Image Tools release](https://launchpad.net/linaro-image-tools/trunk/2012.07), it is now possible to support multiple boards/devices and multiple bootloaders with a single hardware pack. This should speed up development because one hardware pack can be used for several boards running similar hardware, reducing the number of hardware packs that need to be created to test new code on multiple devices.

A [new configuration file format](https://wiki.linaro.org/HardwarePacksV3) has been created: now based on [YAML](http://yaml.org/), it enables engineers to express more complex scenarios, and Linaro Image Tools has been expanded to support this new format.

Backward compatibility is maintained: the old version 2 format is still supported, but it will be deprecated in the [Linaro Image Tools 2012.08 release](https://launchpad.net/linaro-image-tools/+milestone/2012.08), when the new version 3 format will have had enough use to have any bugs found and fixed.

The very old version 1 format is now completely unsupported and the ability to read these files will be dropped from Linaro Image Tools with the 2012.08 release.

With these changes, a new command line tool has been written to help engineers convert an old version 2 configuration file format into a version 3 one: running linaro-hwpack-convert <config-file> will create a version 3 configuration file called <config-file>.yaml (after that you can remove the suffix, it is not necessary, but we keep the old file for you). This file is then used by linaro-hwpack-create to create a new style hardware pack. The procedure for creating a hardware pack has not changed and Linaro Image Tools will automatically detect and use the new format.

The only thing that changes when you use linaro-media-create is you can now specify a bootloader for a hardware pack that can provide more than one. Predictably, this option is --bootloader <bootloader name> and if you want to know what your options are, you can query a hardware pack by using the --read-hwpack option:

    linaro-media-create --hwpack hwpack_linaro-lt-panda_1_armhf_v3.tar.gz --read-hwpack
    +--------------------------------------+--------------------------------------+
    Supported boards                       | Supported bootloaders
    +--------------------------------------+--------------------------------------+
    linaro-lt-panda                        | uefi,u_boot
    +--------------------------------------+--------------------------------------+

linaro-media-create --hwpack hwpack_linaro-lt-panda_1_armhf_v3.tar.gz --bootloader u_boot …

Unfortunately, not all of the features described here are already available in the 2012.07 release of Linaro Image Tools. What is available at the moment is:

  * Converter from old configuration file to new one.
  * Support for the new YAML syntax.

The code with all the features was merged after the release, but is already in for the 2012.08 one. And if you feel adventurous, you can [get the development version](https://code.launchpad.net/~linaro-image-tools/linaro-image-tools/trunk) and test it out.

If you find any bugs, or want to suggest improvements, please do so in the [Linaro Image Tools Launchpad page](https://bugs.launchpad.net/linaro-image-tools).

_This post was written by [James Tunnicliffe](https://launchpad.net/~dooferlad) and [me](http://launchpad.net/~milo)_
