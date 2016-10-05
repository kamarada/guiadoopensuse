---
layout: default
title: 5. KDE Workspace - Use and Configure KDE on Desktop or Netbook
permalink: /kde/
---

# 5. KDE Plasma Workspace

The KDE Plasma workspace is one of the first things you'll see when you boot openSUSE Leap for the first time. The desktop workspace consists of the desktop itself, menus, panels, file management and window management.

## 5.1 The Desktop

The desktop is not very different from other desktop environments you may be familiar with - you have a panel on the bottom, a launch menu which is opened in the lower left corner.

However, a few things differ significantly from most other desktop environments:

- KDE uses *single click* to open and launch things by default
- The content of the * ~/Desktop/* folder is not scattered all over the desktop itself, but is instead organized inside a widget called Folder View
- By default the applications you have running when you shutdown will be started again in the next session

{% include screenshot.html image="desktop" %}

### 5.1.1 The Launch Menu

The launch menu is opened by clicking the icon in the bottom left corner of the screen or pressing Alt+F1. On the bottom there's a search box and at the top left are your favourite applications. You can add and remove applications from favourites by right clicking them.

{% include screenshot.html image="launchmenu" %}

You can edit menu entries or add new ones like this:

<div class="sti">Right click the menu icon =&gt; Menu Editor</div>

To add a shortcut for an application on the desktop or in the panel you can do this (requires widgets to be unlocked):

<div class="sti">Find the application in the menu => Right click the entry => Click "Add to panel" or "Add to desktop"</div>

### 5.1.2 Widgets

The KDE Plasma Desktop is centered around widgets and containments. The desktop and the panel are containments in which widgets can be placed. The menu, the system tray, the folderview on the desktop are simply widgets. Lots and lots of other widgets are available.

To manipulate widgets the widgets need to be unlocked.

<div class="sti">Right click the desktop => Either "Lock Widgets" or "Unlock Widgets".</div>

It's very useful to keep the widgets locked when you are not configuring your desktop, this way you don't get things popping up when you hover over them and you don't risk accidentally moving or removing widgets.

To add widgets:

<div class="sti">Right click the desktop => Add widgets</div><p></p>

{% include screenshot.html image="widgets" %}

To add widgets to the panel, drag them from widget browser to the panel.

When your widgets are covered by windows you can view them by pressing <i>Ctrl+F12</i> to open the widget dashboard.

### 5.1.3 Virtual Desktops

To avoid your desktop getting cluttered with windows you can use virtual desktops to organize your applications and be more productive. In the panel you'll find a small grid, this is the desktop pager, use it to switch between your virtual desktops.

<center><img src="{{ site.baseurl | append: '/images/screenshots/pager.png' | replace: '//', '/' }}" alt="pager" class="pic" /></center>

You can also use the desktop grid effect to get a big overview of your virtual desktops, try pressing *Ctrl+F8* (requires desktop effects support, see the paragraph on this topic below).

<!--
### 5.1.4 Activities

Next to the virtual desktop pager is a cube with three little circles, clicking here opens the Activity Manager. Activities are different desktops which can be configured for specific tasks/activities with different widgets, different wallpapers and automatically starting certain applications.

This enables you to quickly and easily switch between desktops (activities) configured for different situations, for example you might set up one activity for when you're at work, a different one for when you're at home, a third one for when you're doing photo editing and a fourth one for when you're doing public presentations and so forth, and you can switch between these completely different desktops with just a click or two. The toolbox in the top right corner of the screen displays the name of the currently used activity.

The Activity Manager lets you create activities and switch between them. Additionally you can perform various tasks by clicking the little overlay icons on each activity to start or stop the activities, delete them or configure them.

<center><a href="{{ site.baseurl | append: '/images/screenshots/activities.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/screenshots/activitiesb.png' | replace: '//', '/' }}" alt="widgets" class="pic" /></a></center>
-->

## 5.2 File Management

The default file manager is Dolphin.You can find it as one of the favourites in the launch menu or in the "System" category. It should be very intuitive. USB sticks and other removable media will automatically appear in the left pane of Dolphin.

{% include screenshot.html image="dolphin" %}

## 5.3 KDE Systemsettings

The global KDE settings are gathered conveniently in one place. Here you can configure almost anything related to the KDE workspace including mouse behaviour, default applications, file associations etc. You can also find Systemsettings as one of the favourites in the launch menu.

{% include screenshot.html image="systemsettings" %}<p></p>

{% include tip.html tip="Don't confuse the KDE control center used for personal configuration of the KDE Workspace and KDE applications with the YaST control center used for administrator settings on a deeper level of the system (See later chapter about YaST)." %}

## 5.4 System Activity / Task List

Naturally KDE also has a tool to watch running processes and usage of system ressources. Simply press *Ctrl+Esc* to bring up the system activity window.

{% include screenshot.html image="systemactivity" %}

For an advanced and customizable system monitor, including network graphs etc. run the program *ksysguard*

## 5.5 Desktop Effects

The KDE window manager has built-in support for 3D desktop effects. A basic, unobtrusive selection of effects will be enabled out of the box if you have the proper hardware and driver support in place. Try pressing *Ctrl+F8* or *Ctrl+F9* for example.

You can disable or enable other/more effects in Systemsettings.

{% include screenshot.html image="effects" %}

The keyboard shortcut to temporarily toggle desktop effects on/off is *Alt+Shift+F12*.
