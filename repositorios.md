---
layout: default
title: 11. Repositórios de software - Adicionando e gerenciando repositórios de pacotes
permalink: repositorios
---

# 11. Repositórios de software

Como mencionado no capítulo anterior, o gerenciador de pacotes instala *softwares* obtendo pacotes de repositórios de *software*. Portanto, os *softwares* disponíveis para fácil instalação via gerenciador de pacotes dependem dos repositórios configurados.

Um repositório de *software* é uma coleção de pacotes RPM (o formato de empacotamento usado pelo openSUSE) e metadados sobre os pacotes disponibilizados. Normalmente, repositórios ficam em servidores *online*, mas também podem estar em CDs, DVDs ou em outras mídias.

## 11.1 Gerenciando repositórios

Repositórios podem ser adicionados, removidos e configurados pelo YaST, no módulo chamado **Repositórios de software**.

{% include screenshot.html image="yast-repos" %}

### 11.1.1 Adicionando repositórios

Os repositórios oficiais já vêm pré-configurados, mas muitos repositórios não-oficiais existem e podem ser adicionados também.

{% capture repositories_obs %}
Adicione repositórios com cuidado.

- Repositórios não-oficiais podem incluir pacotes experimentais
- Nem todos os repositórios são mutualmente compatíveis
- O nível de risco de um repositório pode mudar com o tempo
- Ter muitos repositórios torna o gerenciador de pacotes mais lento
{% endcapture %}
{% include note.html note=repositories_obs %}

O jeito mais fácil e seguro de adicionar repositórios é usando a lista de repositórios comunitários *online* no YaST, que oferece uma seleção de repositórios populares e seguros.

<div class="path">YaST => Software => Repositórios de software => Clique em "Adicionar" => Selecione "Repositórios da comunidade" e clique em "Próximo"</div><p></p>

{% include video.html video="repos114" screenshot="community-repos" size="1.2 MB" %}

Note que o *openSUSE Build Service* é um serviço para a comunidade criar e compartilhar pacotes. *Repositórios do openSUSE Build Service não são oficiais e não são suportados*. Use por sua conta e risco.

### 11.1.2 Repositórios recomendados

Você sempre deve ter os quatro repositórios *oficiais* (que já vêm configurados por padrão):

- **Main Repository** ou **Repositório principal**: contém apenas *softwares* de código aberto (*open source software*, OSS)
- **Non-OSS Repository** ou **Repositório Non-OSS**: contém apenas *softwares* proprietários (código fechado)
- **Main Update Repository** ou **Repositório principal de atualização**: atualizações (*updates*) para os pacotes do repositório principal
- **Update Repository (Non-OSS)** ou **Repositório de atualização (Non-OSS)**: atualizações (*updates*) para os pacotes do repositório de *softwares* proprietários

Além disso, eu recomendo adicionar o seguinte repositório *não-oficial* da lista de repositórios comunitários, por ter um bom equilíbrio entre *softwares* disponibilizados e estabilidade para a maioria dos usuários:

- **Packman Repository**

{% capture repositories_tip %}
Não consegue encontrar um pacote?

Você pode procurar por pacotes e repositórios no openSUSE Build Service aqui:

[http://software.opensuse.org/search](http://software.opensuse.org/search)

Esta busca de pacotes também inclui o repositório Packman:

[http://webpinstant.com](http://webpinstant.com)

Lembre-se de tomar cuidado ao adicionar repositórios não-oficiais!
{% endcapture %}
{% include tip.html tip=repositories_tip %}

### 11.1.3 Atualizações com alteração de fornecedor

Atualizar pacotes instalados a partir de um repositório para versões de um repositório diferente com um *fornecedor* diferente pode ser um pouco complicado. Leia mais sobre isso aqui:

[http://pt.opensuse.org/SDB:Atualização_e_alteração_de_fornecedor](http://pt.opensuse.org/SDB:Atualização_e_alteração_de_fornecedor)

## 11.2 Gerenciamento de repositórios no terminal

Se quiser, você pode gerenciar seus repositórios pelo terminal também.

Adicione um repositório habilitando a atualização automática (*auto-refresh*) com `zypper addrepo -f [URL] [Alias]`. Exemplo:

<div class="clroot">zypper addrepo -f http://packman.inode.at/suse/openSUSE_Leap_15.1/ packman</div>

Desabilite um repositório com `zypper modifyrepo -d [URL|Alias]`. Exemplo:

<div class="clroot">zypper modifyrepo -d Packman</div>

Remova um repositório com `zypper removerepo [URL|Alias]`. Exemplo:

<div class="clroot">zypper removerepo http://packman.inode.at/suse/openSUSE_Leap_15.1/</div>

Liste os repositórios configurados, mostrando informações detalhadas (como prioridade, URL, etc.):

<div class="cl">zypper repos -d</div>

Consulte `man zypper` para mais informações:

<div class="cl">man zypper</div>

Ou, para ajuda com comandos individuais, use, por exemplo:

<div class="cl">zypper addrepo --help</div>
