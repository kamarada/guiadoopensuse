---
layout: default
title: 13. Codecs multimídia - Instale suporte para codecs restritos como MP3, DVD, WMA, WMV, MOV, etc.
permalink: codecs
---

# 13. Codecs multimídia

Este capítulo descreve dois métodos diferentes para instalar os pacotes necessários para reproduzir a maioria dos formatos multimídia — incluindo MP3, DVDs, etc. — com o reprodutor multimídia padrão VLC, assim como reproduzir vídeos *online* no Firefox. Você pode usar a instalação com 1 clique ou o terminal — o método que preferir.

Por padrão, apenas formatos livres, abertos, não protegidos por patentes — como Ogg Theora, Ogg Vorbis e Flac — são suportados pelo openSUSE, devido a questões legais, como patentes de *software* registradas nos Estados Unidos e Digital Millennium Copyright Act (DMCA).

## 13.1 Instalação dos codecs com 1 clique

1) Clique no botão abaixo para adicionar os repositórios necessários e instalar os pacotes requeridos usando a instalação com 1 clique:

{% include ymp.html icon="codecs" link="http://opensuse-community.org/codecs-kde.ymp" %}

{% include tip.html tip="Se uma caixa de diálogo de conflito aparecer, escolha instalar os pacotes *com* alteração de fornecedor." %}

2) Depois disso, certifique-se de que todos os seus pacotes multimídia estão vindo do repositório Packman:

<div class="path">Inicie o Gerenciamento de software do YaST => Clique em Ver => Clique em Repositórios => Selecione o repositório Packman => Clique em Comutar pacotes do sistema para as versões neste repositório => Clique em Aceitar</div><p></p>

{% include screenshot.html image="packman-vendorchange" %}

## 13.2 Instalação dos codecs pelo terminal

Se você prefere instalar os *codecs* usando o terminal, execute estes passos:

{% include tip.html tip="Use Copiar/Colar para evitar erros de digitação. Para colar no Konsole, clique com o botão direito do *mouse* => Colar — ou pressione **Ctrl + Shift + V**." %}

1) Adicione os repositórios necessários:

<div class="clroot">zypper addrepo -f http://packman.inode.at/suse/openSUSE_Leap_15.1/ packman</div>
<div class="clroot">zypper addrepo -f http://opensuse-guide.org/repo/openSUSE_Leap_15.1/ dvd</div>

2) Instale os pacotes necessários:

<div class="clroot">zypper install --allow-vendor-change ffmpeg lame gstreamer-plugins-bad gstreamer-plugins-ugly gstreamer-plugins-ugly-orig-addon gstreamer-plugins-libav libavdevice56 libavdevice58 libdvdcss2 vlc-codecs</div>

3) Certifique-se de que todos os seus pacotes multimídia estão vindo do repositório Packman:

<div class="clroot">zypper dup --allow-vendor-change --from http://packman.inode.at/suse/openSUSE_Leap_15.1/</div>
