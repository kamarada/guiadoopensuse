---
layout: default
title: 14. Browser Plugins - Install Plugins For Your Web Browser Such As Flash and Java
permalink: /browserplugins/
---

# 14. Browser Plugins

Many websites require various browser plugins to be installed to function as expected. Here are some plugins that you may want to install.

{% include tip.html tip="If the concepts of *package manager* and *repositories* are foreign to you, revisit the chapters [Installing Software](../installpackage/) and [Software Repositories](../repositories/)." %}

## 14.1 Adobe Flash

Install the package **flash-plugin**, if you need Flash support for some online videos, games and other things (*Adobe Flash Plugin Repository* is required).

Installing Flash in the terminal:

<div class="clroot">zypper addrepo -f http://linuxdownload.adobe.com/linux/x86_64/ adobe-flash-plugin</div>

<div class="clroot">zypper install flash-plugin</div>

You will get a warning about a missing GPG-key.

## 14.2 Java

Java web applets are used for games, home banking in some countries, and various other things.

Install the package **java-1_8_0-openjdk-plugin** with the package manager if it isn't already installed.

Installing Java browser plugin in the terminal:

<div class="clroot">zypper install java-1_8_0-openjdk-plugin</div>

## 14.3 Video and Audio Streaming

To get support for various multimedia streams in Firefox and other browsers, install the package **xine-browser-plugin** (*Packman Repository* required).

Installing multimedia plugin in the terminal:

<div class="clroot">zypper install xine-browser-plugin</div>

## 14.4 Microsoft Silverlight

Microsoft have created something called Silverlight to compete with Adobe Flash in making the web require proprietary extensions.

As you'd expect Microsoft do *not* provide an official plugin for GNU/Linux, but there is something called [Pipelight](http://fds-team.de/cms/articles/2013-08/pipelight-using-silverlight-in-linux-browsers.html) bringing Microsoft Silverlight to the GNU/Linux platform. You can find Pipelight packages for openSUSE [here](http://software.opensuse.org/package/pipelight).

Netflix will play in the latest Google Chrome Browser, without any need for Microsoft Silverlight.

## 14.5 Google Voice and Video Chat

Google provide voice and video chat with Google services on GNU/Linux with a browser plugin. Download the RPM files for openSUSE here:

[http://www.google.com/chat/video](http://www.google.com/chat/video)
