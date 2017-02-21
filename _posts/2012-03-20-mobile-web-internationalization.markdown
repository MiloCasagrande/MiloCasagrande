---
author: milocasagrande
comments: true
date: 2012-03-20 18:41:22+00:00
layout: post
link: https://www.milo.name/2012/03/20/mobile-web-internationalization/
slug: mobile-web-internationalization
title: Mobile Web & Internationalization
wordpress_id: 90
categories:
- Development
tags:
- development
- internationalization
- web
---

For my work, we are building the trending-trend for the mobile world: mobile web applications. Web applications, or whatever you prefer to call them, thought and optimized for being used through a mobile device. This is all great and cool, you can exploit your HTML5-CSS-JavaScript-fu, and you do not have to learn to program natively on the various mobile platform out there. It is more or less a win-win situation: write once, use on every device. There are drawbacks of course: no real power from your device, you are doomed by the Lord of the Internet Connections and offline access to the data is not really good, and you loose a little bit of that native feeling. Even with all of these, you are still able to create great mobile experiences: the available tool-kits are really well done and are actively developed ([jQuery Mobile](http://jquerymobile.com/), [Sencha](http://www.sencha.com/), [KendoUI](http://www.kendoui.com/)), there are tools to help you building a "native" app converting your HTML5 code, and you are even able to access (with some tricks) some of the hardware resources. But there is always one problem that sometimes people forget to think about: provide users with content in their own language (or at least try to get close to that very language).

The problem we are facing now is exactly this: how to do it? How to provide users with localized content? How to better handle the localization process?

Since we are on the web, we can get language information from different sources, which one to trust is open to debate: should we trust the web browser? Should we get the language via the geolocation of the user or should we get, in some way or another, the information from the underlying operating system?

I usually consider my case: I'm Italian, I live in France, my desktop environment is in Italian, but I prefer, where possible, to read websites in English (that is because websites tend to be better in English if not properly translated).

OK, deciding that is a little bit tricky, you can get into nasty discussions about how to render time and dates, monetary currency, the direction of the text, plural forms, left aside cultural changes if you embrace a broader users base (colors, icons...).

But, if we know which source to trust, how can we "easily" extract the text to be localized, translate it, and reconstruct everything after? Our software stack is composed of HTML + PHP, JavaScript (that comes from jQuery Mobile and Sencha), and Java.

Java provides us our backend, and some messages comes from it too: error messages if something goes kaput, email messages for authenticating a user, plus other small things. But with Java we are more or less safe: there is support for [gettext in Java](http://code.google.com/p/gettext-commons/) or we can use the Java built-in features (message bundles and properties file, that I do not like much). PHP has gettext support, so even here we are safe.
JavaScript seems a little bit more problematic. Around the web the are a lot of different approaches one can take, even if they all share a small common idea. jQuery Mobile seems to have some sort of internationalization support, Sencha I wasn't able to find any, but there is a [JavaScript implementation of the gettext](http://jsgettext.berlios.de/) library (it is not clear if it supports MO file loading).

All these JavaScript approaches looks like they are made with the idea to load the translations dynamically (a-la-gettext), but what if we want to create the final translated page on the server, and send it already translated to the user? Caching the pages directly on server side and serving content a little bit faster? These, and probably others, are questions that I will have to find an answer in the coming months, and they look interesting.
