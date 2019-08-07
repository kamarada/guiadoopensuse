---
layout: default
title: 14. Plugins para navegadores - Instale plugins para seu navegador, como Flash e Java
permalink: plugins-para-navegadores
---

# 14. Plugins para navegadores

Muitos *sites* precisam que *plugins* estejam instalados nos navegadores para que funcionem como esperado. Aqui estão alguns *plugins* que talvez você queira instalar. Só instale esses *plugins* se realmente precisar deles: eles podem afetar a performance e a segurança da navegação na Internet.

{% include tip.html tip="Se você desconhece os conceitos de *gerenciador de pacotes* e *repositórios*, revisite os capítulos [Instalando *softwares*](instalando-softwares) e [Repositórios de *software*](repositorios)." %}

## 14.1 Adobe Flash

Instale o pacote **freshplayerplugin**, se você precisa do Flash para alguns vídeos, jogos, *games* e outros aplicativos *online* (é necessário adicionar o *repositório Packman*).

Para instalar o Flash pelo terminal:

<div class="clroot">zypper addrepo -f http://packman.inode.at/suse/openSUSE_Leap_15.1/ packman</div>

<div class="clroot">zypper install freshplayerplugin</div>

## 14.2 Java

*Applets* do Java são usados para jogos, *netbanking* em alguns países e várias outras coisas.

Instale o pacote **java-1_8_0-openjdk-plugin** usando o gerenciador de pacotes, caso não já esteja instalado.

Para instalar o *plugin* do Java pelo terminal:

<div class="clroot">zypper install java-1_8_0-openjdk-plugin</div>

## 14.3 Streaming de áudio e vídeo

Para obter suporte para várias transmissões multimídia (*streamings*) no Firefox e em outros navegadores, instale o pacote **xine-browser-plugin** (é necessário adicionar o *repositório Packman*).

Para instalar o *plugin* multimídia pelo terminal:

<div class="clroot">zypper install xine-browser-plugin</div>

## 14.4 Microsoft Silverlight

A Microsoft criou algo chamado Silverlight pra disputar com o Adobe Flash quem mais faz os internautas instalarem extensões proprietárias...

Como você pode imaginar, a Microsoft *não* fornece um *plugin* oficial para GNU/Linux, mas há um projeto chamado [Pipelight](http://fds-team.de/cms/articles/2013-08/pipelight-using-silverlight-in-linux-browsers.html) que traz o Microsoft Silverlight para a plataforma GNU/Linux. Você pode encontrar pacotes do Pipelight para openSUSE [aqui](http://software.opensuse.org/package/pipelight).

A Netflix deve funcionar na versão mais recente do navegador Google Chrome sem precisar do Microsoft Silverlight.

## 14.5 Google Hangouts

O bate-papo por voz e vídeo do Google funciona no GNU/Linux com a adição de um *plugin*. Baixe os pacotes RPM para openSUSE aqui:

[http://www.google.com/chat/video](http://www.google.com/chat/video)
