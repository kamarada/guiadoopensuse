---
layout: default
title: 12. Integração com o Windows - Usando o openSUSE em uma rede Windows, abrindo documentos do Office e executando aplicativos para Windows
permalink: windows
---

# 12. Integração com o Windows

O mundo do PC é dominado pela Microsoft, e ela não é exatamente conhecida por facilitar a integração entre diversos sistemas. Apesar disso, é possível integrar Linux e Windows de forma bastante transparente na maioria dos casos. Esse capítulo aborda os problemas mais comuns.

## 12.1 Documentos do Office

O LibreOffice usa por padrão o Open Document Format (\*.odt, \*.ods, \*.odp, etc.), que é um padrão aberto. Esse formato é parcialmente suportado pelo Microsoft Office a partir da versão 2007 Service Pack 2. Você pode sugerir aos seus contatos que usam Windows e Mac OS X instalar o LibreOffice, uma vez que ele também é disponibilizado gratuitamente para esses sistemas.

O LibreOffice também pode ler e escrever nos formatos do Microsoft Office (\*.doc, \*.xls, \*.ppt, \*.docx, \*.xlsx, \*.pptx, etc.) muito bem — assim como em uma ampla variedade de formatos.

{% include tip.html tip="Se você se deparar com documentos do Microsoft Office que o LibreOffice não renderiza bem, considere tentar se tem mais sorte com a suíte Calligra." %}

## 12.2 Redes Windows

For sharing resources on a local network with MS Windows machines the Samba service is used.

### 12.2.1 Accessing Shares

No configuration is needed to access files shared by others. Simply:

<div class="path">Launch the Dolphin file manager => Click the location bar or press Ctrl+L for an editable location bar => Enter 'smb://[ip-address]'</div><p></p>

{% include screenshot.html image="smb-dolphin" %}

If you don't know the IP-address of the share you want to access, you can *browse* the local network by simply entering *smb:/* in the Dolphin location bar. However, this will only work if you configure or (temporarily) disable the firewall first. More instructions coming soon...

### 12.2.2 Sharing Your Files

To share *your* files with MS Windows users, Mac OSX users or other GNU/Linux users on the local network you must configure the Samba Server (make sure the packages *yast2-samba-server* and *samba* are installed). You only need to perform the first three steps the first time you want share a folder.

1) Open the YaST Samba Server module.

<div class="path">YaST =&gt; Network Services  =&gt; Samba Server</div><p></p>

{% include screenshot.html image="samba-server" %}

2) In the tab *Start-Up* select whether to autostart the Samba service during boot and whether to open the firewall ports required.

3) Go to the *Shares* tab, check the options *Allow Users to Share Their Directories* and *Allow Guest Access*. In the *Identity* tab you can configure your workgroup and share name.

4) Add shares by clicking the "Add" button and specifying the directories you want to share.

## 12.3 Running MS Windows Applications

High quality, native GNU/Linux applications exist for almost any purpose, but it's possible that you're dependent on a MS Windows-only application for some job. These are your options in such a case.

{% include note.html note="You should only run non-native applications as a last resort. Apps work better in their native environment." %}

### 12.3.1 Wine

Wine (Wine Is Not an Emulator) is an application that enables you to run many MS Windows applications, you can install wine with YaST or zypper. Wine is a command line application, the syntax is:

<div class="cl">wine /path/to/setup.exe</div><p></p>

{% include tip.html tip="The package [q4wine](http://sourceforge.net/projects/q4wine/) provides a graphical interface for some features of Wine." %}

The Wine project keeps a database for sharing experiences of running applications, see:

[http://appdb.winehq.org/appbrowse.php](http://appdb.winehq.org/appbrowse.php)

### 12.3.2 CrossOver

CrossOver is not gratis. It's specialised in running a select few of the major MS Windows applications - mostly office related.

[https://www.codeweavers.com/products/cxlinux/](https://www.codeweavers.com/products/cxlinux/)

### 12.3.3 Dual Boot

As mentioned in the *Installation* chapter, it's relatively simple to run GNU/Linux and MS Windows on the same computer. If your only need a few applications that you rarely use, maybe it's worth it to reboot into MS Windows now and then, when you need to use these particular apps.

When you install a dual boot system, your MS Windows disks/partitions should be mounted under */windows/C/*, */windows/D/* etc. If not, you can assign mountpoints (folders in which the drives should be mounted) with YaST => System => Partitioner. By default partitions formatted with the NTFS file system will be read-only. To make them writable for the normal user you have to edit the respective entries in */etc/fstab* and replace *fmask=113,dmask=002* with *umask=0002*.

### 12.3.4 Virtualisation

It's possible to run MS Windows on top of GNU/Linux inside a *virtual machine*, using software such as VirtualBox, KVM, Xen or VMware. This is somewhat advanced, and requires some computer power.
