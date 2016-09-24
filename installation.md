---
layout: default
title: 4. Installation - Howto Install openSUSE on Your Computer
permalink: /installation/
---

# 4. Installation

This is just a brief description of openSUSE installation. For more thorough help see the official documentation.

## 4.1 Before Installation

Before starting there are a few things you should be aware of.

### 4.1.1 System Minimum Requirements

<ul>
    <li><b>CPU:</b> AMD64 or Intel64 processor</li>
    <li><b>RAM:</b> 1 GB physical RAM (2 GB recommended)</li>
    <li><b>Disk Space:</b> 5,0 GB for a normal installation (more recommended)</li>
    <li><b>Sound and Graphics Card:</b> Most modern cards are supported</li>
    </ul>
    
### 4.1.2a Burning the ISOs to a DVD

When you burn the downloaded ISO files to a DVD it's important to remember to burn them as ISOs/images with your CD/DVD writer software, or the media won't be bootable.

### 4.1.2b Creating a USB stick

The ISO can also be put on an USB stick, see instructions for this on these pages depending on which operating systems you have available:

<ul>
<li> openSUSE or other Linux: <a href="http://en.opensuse.org/SDB:Live_USB_stick" target="_blank">http://en.opensuse.org/SDB:Live_USB_stick</a></li>
<li> Microsoft Windows: <a href="https://en.opensuse.org/SDB:Create_a_Live_USB_stick_using_Windows" target="_blank">https://en.opensuse.org/SDB:Create_a_Live_USB_stick_using_Windows</a></li>
<li> Mac OSX: <a href="https://en.opensuse.org/SDB:Create_a_Live_USB_stick_using_Mac_OS_x" target="_blank">https://en.opensuse.org/SDB:Create_a_Live_USB_stick_using_Mac_OS_x</a></li>
</ul>

### 4.1.3 BIOS Setup

If your computer won't boot from the DVD or USB media, check that the computer BIOS is configured to boot from CD/DVD or USB.

### 4.1.4 Dual Boot (openSUSE and MS Windows on the same computer)

Having openSUSE and MS Windows installed on the same computer is usually fairly simple if MS Windows was installed first. During installation openSUSE will detect MS Windows and the bootloader will display a menu on each startup letting you choose whether to boot openSUSE or MS Windows.

openSUSE needs to be installed on a separate partition/disk. It's recommended to free up space beforehand using a partitioning tool that you're familiar with. But you can also let the openSUSE installer resize your MS Windows partitions - it's strongly recommended to defragment the MS Windows partition before doing so.

### 4.1.5 Connect Network Cable and Turn on Peripherals

If you connect your network cable and turn on your printer and other peripherals before commencing the installation, there's a good chance of them being autodetected and configured.

## 4.2 The Installation Process

When you're ready, insert the DVD or USB stick and (re)start the computer.

This describes the installation of the 4.7 GB DVD ISO, as mentioned in the previous chapter there's also a live medium available that is not as well-tested, that installation is not described here, but it's quite similar.

### Welcome

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/welcome.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/welcomeb.png' | replace: '//', '/' }}" alt="welcome" class="pic" /></a></td>
		<td valign="top">The first thing you'll see is this welcome screen.</td>
	</tr>
</table>

### Start Installation

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/grub.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/grubb.png' | replace: '//', '/' }}" alt="grub" class="pic" /></a></td>
		<td valign="top">Then you're presented with a menu.<br /><br />

		Here you can select your desired language and a few other options, afterwards begin installation.</td>
	</tr>
</table>

### Language, Keyboard and Licence

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-welcome.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-welcomeb.png' | replace: '//', '/' }}" alt="welcome" class="pic" /></a></td>
		<td valign="top">The licence agreement is only to inform you of your rights. It doesn't require your acceptance, since it doesn't limit your use.<br /><br />
 
		Check that language and keyboard layout are as desired.</td>
	</tr>
</table>

### Installation Options

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-mode.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-modeb.png' | replace: '//', '/' }}" alt="inst-mode" class="pic" /></a></td>
		<td valign="top">Here you choose to add online repositories or include add-on products, usually will just click "Next". Online repositories can be added in the installed system later.</td>
	</tr>
</table>

### Partitioning

<table>
	<tr>
	  <td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-disk.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-diskb.png' | replace: '//', '/' }}" alt="inst-disk" class="pic" /></a></td>
	  <td valign="top">By default openSUSE will propose to create three new partitions / (root) for system files, /home/ for personal files of users and swap which is used as a supplement for RAM, similar to the page file in MS Windows.<br /><br />

	  Don't worry about all the subvolumes created, these are just technicalities of the Btrfs filesystem, and not "real" partitions, that normal users should need to worry about.<br /><br />

	  If you're performing a dual boot installation, pay extra attention, to make sure everything is as desired.<br /><br />

	  Note that Linux labels disks/partitions using the following scheme - <i>sda1</i> is first partition on the first disk, <i>sdb3</i> is the third partition on the second disk, and so forth. Partitions that will be formatted are written in red text.</td>
	</tr>
</table>

### Clock and Time Zone

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-time.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-timeb.png' | replace: '//', '/' }}" alt="inst-time" class="pic" /></a></td>
		<td valign="top">Set the timezone here.<br /><br />

If you have only GNU/Linux it's recommended to set the hardware clock to UTC, if you dual boot with MS Windows set it to local time.</td>
	</tr>
</table>

### Desktop Selection

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-desktop.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-desktopb.png' | replace: '//', '/' }}" alt="inst-desktop" class="pic" /></a></td>
		<td valign="top">Various different graphical user interfaces (desktop environments) exist for GNU/Linux. KDE is preselected and is preferred by about 70% of openSUSE users and is also the focus of this guide.<br /><br />

		Under "Other" you can select LXDE, Xfce, minimal graphical environment (IceWM) and even a text based system which is useful for servers.</td>
	</tr>
</table>

### Create New User

<table>
	<tr>
	<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-user.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-userb.png' | replace: '//', '/' }}" alt="inst-user" class="pic" /></a></td>
	<td valign="top">Now it's time to create your user. Note that by default the root user (administrator) password will be the same as the password for the normal user.<br /><br />

	If you want the added security of a separate root password, consider unchecking that checkbox. You may also want to consider disabling autologin to prevent people from easily accessing your system and data.</td>
	</tr>
</table>

### Installation Settings

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-overview.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-overviewb.png' | replace: '//', '/' }}" alt="inst-overview" class="pic" /></a></td>
		<td valign="top">Double check that everything is as desired - this is the point of no return!</td>
	</tr>
</table>

### Actual Installation

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-inst.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-instb.png' | replace: '//', '/' }}" alt="inst-inst" class="pic" /></a></td>
		<td valign="top">Now the actual installation is performed. When it's done the system will reboot and be ready to use.<br /><br />

Have a lot of fun with openSUSE!

		</td>
	</tr>
</table>


<!--
### Automatic Configuration

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/dvd/inst-autoconfig.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/dvd/inst-autoconfigb.png' | replace: '//', '/' }}" alt="inst-inst" class="pic" /></a></td>
		<td valign="top">After installation is performed, the system will restart and perform autoconfiguration.

		And finally your brand new openSUSE system will start. Congratulations, and have a lot of fun with openSUSE!

		</td>
	</tr>
</table>

-->

<!--

## 4.3 Live DVD/USB Installation

When you're ready to install, insert the DVD/USB and (re)boot the computer.

The Live DVD/USB provides two different installation modes, you can install directly from the boot menu, or you can boot the system and install from the desktop while the system is running, by clicking on the install icon on the desktop. There is only a visual difference between the two modes of installation. It's recommended to try booting the live system  before installing to see if your hardware components are supported.

### Language and License

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/live/live-welcome.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/live/live-welcomeb.png' | replace: '//', '/' }}" alt="live-welcome" class="pic" /></a></td>
		<td valign="top">The licence agreement is only to inform you of your rights. It doesn't require your acceptance, since it doesn't limit your use.
 
		Check that language and keyboard layout are as desired.</td>
	</tr>
	</table>

### Clock and Time Zone

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/live/live-time.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/live/live-timeb.png' | replace: '//', '/' }}" alt="live-time" class="pic" /></a></td>
		<td valign="top">Set the timezone here.

If you have only GNU/Linux it's recommended to set the hardware clock to UTC, if you dual boot with MS Windows set it to local time.</td>
	</tr>
</table>

### Partitioning

	<table>
	<tr>
	<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/live/live-partition.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/live/live-partitionb.png' | replace: '//', '/' }}" alt="live-partition" class="pic" /></a></td>
	<td valign="top">By default openSUSE will propose to create three new partitions / (root) for system files, /home/ for personal files of users and swap which is used as a supplement for RAM, similar to the page file in MS Windows.

	  If you're performing a dual boot installation, be extra careful here.

	  Note that Linux labels disks/partitions using the following scheme - <i>sda1</i> is first partition on the first disk, <i>sdb3</i> is the third partition on the second disk, and so forth. Partitions that will be formatted are written in red text.</td>
	</tr>
</table>

### Create New User

<table>
	<tr>
	    <td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/live/live-user.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/live/live-userb.png' | replace: '//', '/' }}" alt="live-user" class="pic" /></a></td>
	    <td valign="top">Now it's time to create your user. Note that by default the root user (administrator) password will be the same as the password for the normal user.

	If you want the added security of a separate root password, consider unchecking that checkbox. You may also want to consider disabling autologin to prevent people from easily accessing your system and data.</td>
	</tr>
</table>

### Installation Settings

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/live/live-settings.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/live/live-settingsb.png' | replace: '//', '/' }}" alt="live-settings" class="pic" /></a></td>
		<td valign="top">Double check that everything is as desired - this is the point of no return!</td>
	</tr>
</table>

### Actual Installation

<table>
	<tr>
		<td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/live/live-installation.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/live/live-installationb.png' | replace: '//', '/' }}" alt="live-installation" class="pic" /></a></td>
		<td valign="top">Now the actual installation is performed.</td>
	</tr>
</table>

### Automatic Configuration

<table>
	<tr>
	    <td width="205" valign="top"><a href="{{ site.baseurl | append: '/images/installation/live/live-done.png' | replace: '//', '/' }}" rel="thumbnail"><img src="{{ site.baseurl | append: '/images/installation/live/live-doneb.png' | replace: '//', '/' }}" alt="live-done" class="pic" /></a></td>
	    <td valign="top">When all packages are installed, the system needs to reboot from the harddrive.

		You can either remove the DVD/USB during the reboot process or leave it in and select <i>Boot from harddisk</i> at the boot menu.

	    After the reboot, the system will perform automatic configuration.

	    Afterwards your brand new openSUSE system will start. Congratulations, and have a lot of fun with openSUSE!</td>
	</tr>
</table>
-->
