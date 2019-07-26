---
layout: default
title: 10. Instalando softwares - Instale programas com o gerenciador de pacotes
permalink: instalando-softwares
---

# 10. Instalando softwares

A instalação de *softwares* geralmente é incrivelmente fácil no openSUSE. Há um gerenciador de pacotes, que permite a você instalar e remover pacotes com muita facilidade — pode ser comparado com as lojas de aplicativos presentes em vários *smartphones* atualmente.

## 10.1 Usando o gerenciador de pacotes

Abra o YaST e clique em **Gerenciamento de software**.

{% include video.html video="installpackage114" screenshot="sw-single" size="0.99 MB" %}

Pesquise pelo pacote que deseja, marque-o para instalação e clique em **Aceitar**. O gerenciador de pacotes então baixará o pacote RPM dos repositórios de *software* configurados e o instalará junto com quaisquer dependências. Quando a instalação terminar, o aplicativo deve aparecer no menu lançador de aplicativos (a menos que seja um programa de linha de comando).

{% include tip.html tip="A disponibilidade de pacotes de *software* no gerenciador de pacotes depende dos repositórios de *software* configurados. Leia sobre repositórios de *software* no próximo capítulo." %}

### 10.1.1 Usando a instalação com 1 clique (1-Click Install)

Ao visitar *sites* relacionados ao openSUSE, você pode se deparar com botões como este:

<center><img class="pic" alt="oneclick" src="{{ site.baseurl | append: '/images/pics/oneclick.png' | replace: '//', '/' }}" /></center>

A instalação com 1 clique (em inglês, *1-Click Install*), também chamada da "instalação direta" (*Direct Install*), automatiza o processo de adicionar um ou mais repositórios de *software* ao gerenciador de pacotes e instalar um ou mais pacotes RPM. Por isso, a instalação com 1 clique *deve ser usada com o mesmo cuidado* que a adição manual de repositórios não oficiais (leia o próximo capítulo para mais sobre repositórios de *software*).

## 10.2 Outros métodos de instalação

A maioria dos usuários encontrará tudo que precisa e mais no gerenciador de pacotes — especialmente se alguns repositórios de *software* forem adicionados (veja o próximo capítulo). Mas nem todos os *softwares* são empacotados e disponibilizados nos repositórios, e *softwares* não-livres (também chamados de proprietários) legalmente não podem ser distribuídos pelo gerenciador de pacotes devido a restrições de suas licenças.

Nesses casos, você terá que ir até o *site* do desenvolvedor/vendedor, baixar e instalar o *software* manualmente — mas **sempre** procure antes por um pacote para o openSUSE nos repositórios — e certifique-se de somente baixar e instalar *software* de fontes confiáveis.

### 10.2.1 Arquivo RPM

Com um pouco de sorte, o *site* do desenvolvedor/vendedor terá um arquivo RPM para o openSUSE. Para instalar um arquivo RPM baixado manualmente:

<div class="path">Abra o gerenciador de arquivos Dolphin =&gt; Abra a pasta do arquivo RPM =&gt; Clique com o botão direito do <em>mouse</em> nele =&gt; Abrir com... => Instalar/Remover Software</div><p></p>

{% include note.html note="Apenas instale arquivos RPM feitos especificamente para (a sua versão do) openSUSE." %}

### 10.2.2 Tarball

Se o *site* não tiver um RPM para openSUSE, muito provavelmente terá um arquivo chamado *tarball*. *Tarballs* (\*.tar.gz, \*.tar.bz2) são simplesmente arquivos comprimidos, semelhantes aos arquivos ZIP e RAR. Para descompactar um _tarball_:

<div class="path">Abra o gerenciador de arquivos Dolphin =&gt; Abra a pasta do <em>tarball</em> =&gt; Clique com o botão direito do <em>mouse</em> nele =&gt; Extrair Arquivo</div>

O *tarball* pode conter binários que apenas precisam ser executados, ou pode conter código-fonte que precisa ser compilado para executar em seu computador — isso pode ser muito complicado, e requer que antes você instale várias ferramentas de desenvolvimento. Não há uma forma padrão de instalar o conteúdo de arquivos *tarball*, mas normalmente são fornecidas instruções dentro de arquivos chamados INSTALL (instalar), README (leia-me) ou parecidos dentro dos arquivos *tarball*, ou você deve ser capaz de encontrar instruções de instalação no *site* onde baixou o *tarball*.

## 10.3 Gerenciamento de pacotes no terminal

Se você quiser, também pode instalar e remover pacotes pelo terminal.

Para pesquisar por um pacote, execute *zypper search [termo de pesquisa]*. Por exemplo:

<div class="cl">zypper search thunder</div>

Para instalar um pacote, execute *zypper install [nome do pacote]*. Exemplo:

<div class="clroot">zypper install MozillaThunderbird</div>

Para desinstalar um pacote, execute *zypper remove [nome do pacote]*. Exemplo:

<div class="clroot">zypper remove PackageKit</div>

Veja *man zypper* para mais informações:

<div class="cl">man zypper</div>

Ou, para ajuda com comandos individuais, use, por exemplo:

<div class="cl">zypper install --help</div>

### 10.3.1 Usando a instalação com 1 clique (1-Click Install) no terminal

Você também pode usar a instalação com 1 clique no terminal, a sintaxe é *OCICLI [link]*. Por exemplo:

<div class="clroot">OCICLI http://opensuse-community.org/nvidia.ymp</div>

### 10.3.2 Arquivo RPM baixado manualmente

Para instalar um arquivo RPM baixado manualmente, execute:

<div class="clroot">zypper install /caminho/para/o/arquivo/baixado/manualmente.rpm</div>

### 10.3.3 Consultas de RPM

Você pode obter muitas informações úteis sobre pacotes instalados do banco de dados do RPM de forma fácil.

Verifique qual versão de um pacote está instalada. Por exemplo:

<div class="cl">rpm -q MozillaFirefox</div>

Liste os arquivos que são instalados por um pacote e onde estão. Exemplo:

<div class="cl">rpm -ql amarok</div>

Descubra a qual pacote um determinado arquivo pertence. Exemplo:

<div class="cl">rpm -qf /usr/bin/firefox</div>

Obtenha várias informações sobre um pacote, incluindo histórico de mudanças (*changelog*). Exemplo:

<div class="cl">rpm -qi --changelog MozillaFirefox</div>
