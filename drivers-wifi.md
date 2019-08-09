---
layout: default
title: 16. Drivers para redes sem fio - Faça sua placa de rede sem fio Broadcom, Ralink, etc. funcionar
permalink: drivers-wifi
---

# 16. Drivers para redes sem fio

A maior parte das placas de rede sem fio deve simplesmente funcionar, sem precisar instalar *drivers* adicionais. Nesses casos, você pode configurar o acesso à rede Wi-Fi usando o *widget* do NetworkManager, que fica na área de notificação:

{% include screenshot.html image="plasmoid-network-management" %}

Ainda que sua placa de rede sem fio não seja suportada pela instalação padrão, provavelmente é fácil fazê-la funcionar.

## 16.1 Descubra qual é o chipset

O primeiro passo é executar o comando a seguir para descobrir qual é o *chipset* da placa. O *chipset* é o que faz a diferença, o fabricante e o modelo da placa não importam realmente.

<div class="clroot">hwinfo --wlan --short</div><p></p>

{% include screenshot.html image="hwinfo" %}

Agora que você sabe qual é o *chipset* da placa, pode pesquisar o que precisa fazer para que ele funcione no openSUSE — normalmente você só precisará instalar algum *driver* ou *firmware*.

## 16.2 Chipsets mais novos da Broadcom

O *kernel* Linux vem com o [*driver* brcm80211](http://linuxwireless.org/en/users/Drivers/brcm80211) por padrão. Esse *driver* suporta os *chipsets* **bcm4313, bcm43224, bcm43224, bcm43225, bcm4329, bcm4330, bcm4334, bcm43241, bcm43235 (>= rev 3), bcm43236 (>= rev 3), bcm43238 (>= rev 3), bcm43143, bcm43242**.

Se você tiver problemas com o *driver* acima e tem um dos seguintes *chipsets*: **bcm4312, bcm4313, bcm4321, bcm4322, bcm43224, bcm43225, bcm43227, bcm43228**, tente instalar o [*driver* proprietário broadcom-wl](https://www.broadcom.com/support/802.11) (pacote: *broadcom-wl*) disponível no repositório Packman.

## 16.3 Chipsets mais antigos da Broadcom

Se você tem um *chipset* mais antigo da Broadcom [suportado pelo *driver* livre b43, feito por engenharia reversa](http://linuxwireless.org/en/users/Drivers/b43#Supported_chip_types), por exemplo: **bcm4303, bcm4306, bcm4309, bcm4311, bcm4318**, você só precisa instalar o *firmware*. Isso foi automatizado pela criação de um *script*, você só precisa executar o comando a seguir e reiniciar quando terminar (certifique-se de que o pacote *b43-fwcutter* esteja instalado e que você esteja conectado à Internet quando executar o comando):

<div class="clroot">install_bcm43xx_firmware</div>

## 16.4 Chipsets da Atheros

A Atheros trabalha com os desenvolvedores do *kernel* Linux para fornecer suporte para todos os seus *chipsets* sem fio na linha principal de desenvolvimento do *kernel* Linux, por meio dos *drivers* [ath5k](http://linuxwireless.org/en/users/Drivers/ath5k#supported_chips) e [ath9k](http://linuxwireless.org/en/users/Drivers/ath9k#supported_chipsets). Com isso, a maioria dos *chipsets* da Atheros deve simplesmente funcionar.

## 16.5 Chipsets da Intel

A Intel coopera bastante com os desenvolvedores do *kernel* Linux e todos os *chipsets* sem fio da Intel devem simplesmente funcionar.
