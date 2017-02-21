---
author: milocasagrande
comments: true
date: 2013-01-08 11:18:46+00:00
layout: post
link: https://www.milo.name/2013/01/08/convert-a-bazaar-repository-into-a-git-one/
slug: convert-a-bazaar-repository-into-a-git-one
title: Convert a bazaar repository into a git one
wordpress_id: 472
categories:
- Development
tags:
- development
- linaro
---

Yesterday, for a work task, I needed to convert a [bazaar](http://bazaar.canonical.com/) repository into a [git](http://git-scm.com/) one, to store code for other teams (that mostly use git) to work on. The bazaar repo was very simple actually, small history and it didn't contain any merges.

#### Read The Docs™

Or almost... The first thing I did was heading other bazaar extensive documentation, in particular to its [wiki sections on plugins](http://wiki.bazaar.canonical.com/BzrPlugins). And there you have it, just an install-command away, ready to work: [bzr-fastimport](http://doc.bazaar.canonical.com/plugins/en/fastimport-plugin.html). Yeah, it says import, but it works also on the export part.

The steps I took:

    bzr branch repo git-repo
    cd git-repo && git init
    bzr fast-export `pwd` | git fast-import
    rm -rf .bzr

It should work also for fairly complex projects, though I didn't try it on one.
