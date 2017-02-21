---
author: milocasagrande
comments: true
date: 2012-04-27 14:14:16+00:00
layout: post
link: https://www.milo.name/2012/04/27/javamail-session-to-the-rescue/
slug: javamail-session-to-the-rescue
title: JavaMail Session to the Rescue
wordpress_id: 103
categories:
- Development
tags:
- development
- glassfish
- java
- mail
---

There might comes the time when you need to send emails to your users base within your Java application, deployed in Glassfish. So you start to code some simple Java mail classes, and you find yourself hardcoding host names, user names, passwords and all the other good sensible information in your code, that is open source.

This is the situation I found myself in while doing some maintenance on our code base: subscription emails, or any other emails for the matter, were sent out using one simple Mail Java class, that had everything hardcoded in it. Not good.

But we are using Glassfish, and this is good (well, it depends who you are asking, but in this case it is good as probably any other app-server out there). We can use Glassfish to handle our "mail session", and inject the necessary values inside our class when needed, leaving us free from storing sensible data in our Java code.

Obviously this is all good in theory, in practice this works if your Java code is managed directly by your app-server, and our is not, since we do not need that. But do not despair, all is possible.

With non-managed code, you need to access the "context" of your Java application, where you have objects bound to an exclusive name.

So, lets make this work.

Creating a new JavaMail Session in Glassfish is very simple either through the admin interface, or via the command line. There are  two important aspects to keep in mind: whatever you need SSL enabled or not, and your JNDI name. Since we are using Gmail, and we want to use its SMTP server, we are going to use SSL for this. The other piece of information that has to be kept in mind, is the last value in the command line: that is the JNDI name, the one you will use in your code to retrieve the JavaMail session. The command line is very simple, you can find it on [github](https://gist.github.com/2509214).

Now you need to retrieve the JavaMail session from Glassfish, so that it is possible to use it in a [MimeMessage](http://docs.oracle.com/javaee/6/api/javax/mail/internet/MimeMessage.html) Java object. Code to do that is again very simple, and you can find an example here on [github](https://gist.github.com/2509400).

So, all in all, the situation is now better: we do not store values in the code, and the code is a little bit more flexible and can handle different JavaMail sessions in order to send emails with different accounts. We started with one Java class that handled everything, now we have four classes and one interface, and all the values that need to be retrieved (JNDI names) are stored in a separate Java properties file. Since I was at that, I added attachments support to the email creation, you never know when it might comes handy. ;)

Last step in this work: create HTML templates for sending nice email instead of boring black character emails, and handle internationalization and localization of the templates. Another funny task ahead. :)
