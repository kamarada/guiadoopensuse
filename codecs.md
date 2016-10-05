---
layout: default
title: 13. Multimedia Codecs - Install Support For MP3, DVD, WMA, WMV, MOV etc.
permalink: /codecs/
---

# 13. Multimedia Codecs

This chapter describes three different methods for installing the packages needed to playback most multimedia formats - including MP3, DVDs etc., with Dragon (video) and Amarok (audio). You can use manual installation with graphical software or use the command line - whichever method you prefer.

By default only free, open, non-patent encumbered formats such as Ogg Theora, Ogg Vorbis and Flac are supported for legal reasons (US software patents and Digital Millennium Copyright Act (DMCA)).

## 13.1 Codec Installation with YaST Software Management

1) First add/enable the repositories with YaST Software Repositories:

- **Packman Repository**
- **libdvdcss repository** (skip if you don't need DVD playback)

{% include tip.html tip="If the concepts of *package manager* and *repositories* are foreign to you, revisit the chapters [Installing Software](../installpackage/) and [Software Repositories](../repositories/)." %}

2) Then install the following packages with YaST Software Management:

- **k3b-codecs**
- **ffmpeg**
- **lame**
- **phonon-backend-vlc**
- **phonon4qt5-backend-vlc**
- **vlc-codecs**
- **flash-player**
- **libdvdcss2** (skip if you don't need DVD playback)

3) Finally remove/uninstall the following packages with YaST Software Management:

- **phonon-backend-gstreamer**
- **phonon4qt5-backend-gstreamer**

## 13.2 Codec Installation in the Terminal

To install codecs using the terminal instead, do these steps:

{% include tip.html tip="Use Copy/Paste to avoid typos. To paste in Konsole right click mouse => Paste - or use **Ctrl+Shift+V**." %}

1) Add the needed repositories (skip the dvd repo if you don't need DVD playback):

<div class="clroot">zypper addrepo -f http://packman.inode.at/suse/openSUSE_Leap_42.1/ packman</div>
<div class="clroot">zypper addrepo -f http://opensuse-guide.org/repo/openSUSE_Leap_42.1/ dvd</div>

2) Then install the necessary packages (skip libdvdcss2 if you don't need DVD playback):

<div class="clroot">zypper install k3b-codecs ffmpeg lame phonon-backend-vlc phonon4qt5-backend-vlc vlc-codecs flash-player libdvdcss2</div>

3) Now remove these packages:

<div class="clroot">zypper remove phonon-backend-gstreamer phonon4qt5-backend-gstreamer</div>
