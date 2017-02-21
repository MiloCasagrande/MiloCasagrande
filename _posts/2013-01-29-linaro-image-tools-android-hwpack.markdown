---
author: milocasagrande
comments: true
date: 2013-01-29 08:30:36+00:00
layout: post
link: https://www.milo.name/2013/01/29/linaro-image-tools-android-hwpack/
slug: linaro-image-tools-android-hwpack
title: 'New Feature for Linaro Image Tools: Android Hwpack'
wordpress_id: 447
categories:
- Development
tags:
- android
- development
- hwpack
- linaro
---

Finally, after some delays, [Linaro Image Tools](https://launchpad.net/linaro-image-tools) now has support for [Android hardware pack](https://wiki.linaro.org/AndroidHardwarePacksV3) (or Android _hwpack_).

#### What is an Android hwpack

Let's start with with clearing out the confusion the term "_hwpack_" has in this context.

Generally speaking, for Linaro Image Tools an hwpack is a tar-ball that contains Debian packages, some configuration and metadata files, and some directory structures, needed to create and install bootable operating system images.

Linaro Image Tools has had support for this kind _hwpack_ since the beginning of time, but they are not necessary to create Android bootable images. The process to create an Android image is slightly different.

This new hwpack, the **_Android hwpack_**, is just a configuration file, based on the same [syntax of previous Linaro Image Tools hwpack](https://wiki.linaro.org/HardwarePacksV3), that stores information necessary to correctly create Android images. An Android hwpack does not contain any Debian packages nor binary blob or anything else, it is just a text file (a YAML file for instance).

It's probably better to call is "_Android configuration file_".

#### Why an Android hwpack

The necessity for this came out during last Linaro Connect Europe, from the Android team. The needs were an easy way to add support for new boards (without having to hack into Linaro Image Tools code), the possibility to change board parameters (almost) "_on-the-fly_" for testing (without having to touch code), and the possibility to maintain backward compatibility by providing some kind of "_versioned_" hwpack, guaranteed to work for specific Linaro releases.

#### How to use it

In order to use it, you need to have at least Linaro Image Tools version 2013.01. At the time of this writing, Android hwpack support [is also being built into the Android boot tarball](https://blueprints.launchpad.net/linaro-android/+spec/hwpack-config-support-in-android-build), so it should be totally transparent for the user: no need to add command line arguments and to pass file paths.

Still, it is possible to pass an Android hwpack to Linaro Android Media Create, the command line tools that creates Android bootable images. The command line argument is the same as Linaro Media Create one: --hwpack

So, if you want to use the new feature, arm yourself with an Android hwpack file (examples can be [found on GitHub](https://github.com/MiloCasagrande/android-hwpacks)), and run:

    linaro-android-media-create --mmc /dev/sdc --dev panda --boot boot.tar.bz2 --system system.tar.bz2 --userdata userdata.tar.bz2 --hwpack panda-hwpack

Backward compatibility has been maintained: the old hard-coded values have been kept, so it is still possible to use everything in the old way.

If you find bugs, of other possible improvements, feel free to leave them in the comments below, or better on [Launchpad](https://bugs.launchpad.net/linaro-image-tools).
