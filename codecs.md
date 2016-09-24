---
layout: default
title: 13. Multimedia Codecs - Install Support For MP3, DVD, WMA, WMV, MOV etc.
permalink: /codecs/
---

# 13. Multimedia Codecs

This chapter describes three different methods for installing the packages needed to playback most multimedia formats - including MP3, DVDs etc., with Dragon (video) and Amarok (audio). You can use manual installation with graphical software or use the command line - whichever method you prefer.

By default only free, open, non-patent encumbered formats such as Ogg Theora, Ogg Vorbis and Flac are supported for legal reasons (US software patents and Digital Millennium Copyright Act (DMCA)).

<!--
## 13.1 Codec Installation with 1-Click

Temporarily not available for technical reasons.

Click on the button below to install multmedia codecs with 1-click install.

<center><a href="http://opensuse-community.org/codecs-kde.ymp"><img src="{{ site.baseurl | append: '/images/oneclick/codecs.png' | replace: '//', '/' }}" alt="ymp" class="pic" /></a></center>

-->


<!--
<center><a href="data:text/x-suse-ymu,http://opensuse-guide.org/ymp/codecs.ymp"><img src="{{ site.baseurl | append: '/images/oneclick/codecs.png' | replace: '//', '/' }}" alt="codecs ymp" class="pic" /></a></center>

-->

<!--
Note, if you get a warning dialog like this don't panic! Simply select the proper option, to either allow changing the vendor for some packages from <i>openSUSE</i> to <i>Packman</i>, or possibly to downgrade a package (usually the same package version, only with a lower build number) then click <i>OK -- Try Again</i>.

-->

<!--
<center><a href="{{ site.baseurl | append: '/images/screenshots/conflict.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/screenshots/conflictb.png' | replace: '//', '/' }}" alt="conflict" class="pic" /></a></center>

-->

## 13.1 Codec Installation with YaST Software Management

1) First add/enable the repositories with YaST Software Repositories:

<ul>
<li><b>Packman Repository</b></li>
<!-- <li><b>Non-OSS Respository</b></li> -->
<li><b>libdvdcss repository</b> (skip if you don't need DVD playback)</li>
</ul>

<div class="tip">
<table>
<tbody>
<tr>
<td><img src="{{ site.baseurl | append: '/images/pics/tip.png' | replace: '//', '/' }}" alt="tip" /></td>
<td>If the concepts of <i>package manager</i> and <i>repositories</i> are foreign to you, revisit the chapters <a href="installpackage.php">Installing Software</a> and <a href="repositories.php">Software Repositories</a>.</td>
</tr>
</tbody>
</table>
</div>

2) Then install the following packages with YaST Software Management:

<ul>
<li><b>k3b-codecs</b></li>
<li><b>ffmpeg</b></li>
<li><b>lame</b></li>
<li><b>phonon-backend-vlc</b></li>
<li><b>phonon4qt5-backend-vlc</b></li>
<li><b>vlc-codecs</b></li>
<li><b>flash-player</b></li>
<li><b>libdvdcss2</b> (skip if you don't need DVD playback)</li>
</ul>

3) Finally remove/uninstall the following packages with YaST Software Management:

<ul>
<li><b>phonon-backend-gstreamer</b></li>
<li><b>phonon4qt5-backend-gstreamer</li>
</ul>

<!--
You can install the packages manually instead if you prefer.

First add/enable the repositories with YaST Software Repositories:

<ul>
<li><b>Packman Repository</b></li>
<li><b>Non-OSS Respository</b></li>
<li><b>libdvdcss repository</b> (skip if you don't need DVD playback)</li>
</ul>

<div class="tip">
<table>
<tbody>
<tr>
<td><img src="{{ site.baseurl | append: '/images/pics/tip.png' | replace: '//', '/' }}" alt="tip" /></td>
<td>If the concepts of <i>package manager</i> and <i>repositories</i> are foreign to you, revisit the chapters <a href="installpackage.php">Installing Software</a> and <a href="repositories.php">Software Repositories</a>.</td>
</tr>
</tbody>
</table>
</div>

Then install the following packages with YaST Software Management:

<ul>
<li><b>k3b-codecs</b></li>
<li><b>ffmpeg</b></li>
<li><b>lame</b></li>
<li><b>gstreamer-plugins-bad</b></li>
<li><b>gstreamer-plugins-ugly</b></li>
<li><b>gstreamer-plugins-ugly-orig-addon</b></li>
<li><b>gstreamer-plugins-libav</b></li>
<li><b>gstreamer-fluendo-mp3</b></li>
<li><b>libdvdcss2</b> (skip if you don't need DVD playback)</li>
</ul>
-->

## 13.2 Codec Installation in the Terminal

To install codecs using the terminal instead, do these steps:

<div class="tip">
<table>
<tbody>
<tr>
<td><img src="{{ site.baseurl | append: '/images/pics/tip.png' | replace: '//', '/' }}" alt="tip" /></td>
<td>Use Copy/Paste to avoid typos. To paste in Konsole right click mouse => Paste - or use <b>Ctrl+Shift+V</b>.</td>
</tr>
</tbody>
</table>
</div>

1) Add the needed repositories (skip the dvd repo if you don't need DVD playback):

<div class="clroot">zypper addrepo -f http://packman.inode.at/suse/openSUSE_Leap_42.1/ packman</div>
<div class="clroot">zypper addrepo -f http://opensuse-guide.org/repo/openSUSE_Leap_42.1/ dvd</div>

2) Then install the necessary packages (skip libdvdcss2 if you don't need DVD playback):

<div class="clroot">zypper install k3b-codecs ffmpeg lame phonon-backend-vlc phonon4qt5-backend-vlc vlc-codecs flash-player libdvdcss2</div>

3) Now remove these packages:

<div class="clroot">zypper remove phonon-backend-gstreamer phonon4qt5-backend-gstreamer</div>

<!--
Add the needed repositories (skip the dvd repo if you don't need DVD playback):
<div class="clroot">zypper addrepo -f http://packman.inode.at/suse/openSUSE_Leap_42.1/Essentials/ packman</div>
<div class="clroot">zypper addrepo -f http://opensuse-guide.org/repo/openSUSE_Leap_42.1/ dvd</div>

Then install the necessary packages (skip libdvdcss2 if you don't need DVD playback):
<div class="clroot">zypper install k3b-codecs ffmpeg lame gstreamer-plugins-bad gstreamer-plugins-ugly gstreamer-plugins-ugly-orig-addon gstreamer-plugins-libav libdvdcss2</div>

You will be asked if you want to allow vendor change for some packages - allow it.

Finally ensure that you have a consistent set of packages from the Packman Repository:
<div class="clroot">zypper dup --from http://packman.inode.at/suse/openSUSE_Leap_42.1/Essentials/</div>

You will be asked if you want to allow vendor change for some packages - allow it.

If you still experience problems try removing the GStreamer cache and reboot your system:
<div class="cl">rm -rf ~/.cache/gstreamer-1.0/</div>
-->
