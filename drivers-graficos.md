---
layout: default
title: 15. Drivers gráficos - Instale os drivers das placas de vídeo 3D NVIDIA ou ATI/AMD
permalink: drivers-graficos
---

# 15. Drivers gráficos

Observe que não há necessidade de instalar os *drivers* não livres abaixo se os *drivers* livres usados por padrão atendem as suas necessidades.

## 15.1 NVIDIA

Esta seção descreve duas formas de instalar o *driver* gráfico proprietário da NVIDIA: usando a instalação com 1 clique ou o terminal.

### 15.1.1 Instalar o driver da NVIDIA usando a instalação com 1 clique

Clique no botão correspondente à sua placa de vídeo NVIDIA para instalar o *driver* apropriado usando a instalação com 1 clique:

- **GeForce série 600 e mais recente** ([veja os produtos suportados](https://www.nvidia.com/Download/driverResults.aspx/145182/en-us))

{% include ymp.html icon="nvidia" link="http://opensuse-community.org/nvidia_G05.ymp" %}

- **GeForce série 400 e mais recente** ([veja os produtos suportados](https://www.nvidia.com/Download/driverResults.aspx/142567/en-us))

{% include ymp.html icon="nvidia" link="http://opensuse-community.org/nvidia_G04.ymp" %}

- **GeForce 8xxx e mais recente** ([veja os produtos suportados](https://www.nvidia.com/Download/driverResults.aspx/135161/en-us))

{% include ymp.html icon="nvidia" link="http://opensuse-community.org/nvidia_G03.ymp" %}

Depois da instalação, reinicie o computador.

### 15.1.2 Instalar o driver da NVIDIA usando o terminal

Você pode instalar o driver da NVIDIA pelo terminal. **Usando esse método, você não precisa saber o modelo da sua placa de vídeo**.

Primeiro, adicione o repositório da NVIDIA:

<div class="clroot">zypper addrepo -f http://download.nvidia.com/opensuse/leap/15.1 nvidia</div>

Depois, execute o comando a seguir, que deve instalar automaticamente o *driver* correto para a sua placa de vídeo:

<div class="clroot">zypper install-new-recommends --repo https://download.nvidia.com/opensuse/leap/15.1</div>

Quando a instalação acabar, reinicie o computador.

## 15.2 ATI/AMD

Os *drivers* livres instalados por padrão devem funcionar bem para a maioria das placas.

## 15.3 Intel

Os *drivers* para as placas de vídeo 3D da Intel são *softwares* livres e são incluídos no openSUSE por padrão. Não são necessárias instalação ou configuração adicionais.
