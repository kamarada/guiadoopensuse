---
layout: default
title: 8. Terminal - Executando comandos e usando a interface de linha de comando no openSUSE
permalink: terminal
---

# 8. Terminal

Quase qualquer tarefa pode ser feita graficamente em uma distribuição GNU/Linux moderna como o openSUSE. Mas para realmente se tornar um usuário auto-suficiente e verdadeiramente tirar proveito do poder do seu sistema operacional GNU/Linux, você deveria pelo menos conhecer alguns conceitos básicos do terminal — não é nada difícil!

Há milhares de comandos que você pode executar, cada um com um número diferente de opções. Desse modo, este capítulo é apenas um pequeno *teaser* descrevendo os comandos mais comuns.

Você encontrará o **Konsole** na categoria **Sistema**, no menu lançador de aplicativos.

{% include video.html video="konsole" screenshot="konsole" size="4.3 MB" %}

Usar a linha de comando é muito fácil. Simplesmente digite um comando e possivelmente uma ou mais opções e um ou mais argumentos e então pressione Enter. Por exemplo:

<div class="cl">ls -l /home/[nomedeusuario]/ </div>

O **comando** `ls` exibe uma lista de arquivos, a **opção** `-l` significa que a lista deve ser exibida em um formato de lista longa (um arquivo por linha), e o **argumento** `/home/[nomedeusuario]/` define a pasta cujos arquivos devem ser listados.

## 8.1 Atalhos úteis

### Tecla Tab

A tecla Tab é incrivelmente útil: se possível, ela autocompleta comandos e argumentos, o que te ajuda a trabalhar mais rápido e evitar erros de digitação.

### Ctrl + Shift + V

Cola da área de transferência.

### Ctrl + C

Esse atalho interrompe qualquer operação que você tenha iniciado.

## 8.2 Exemplos de comandos básicos

Esta é apenas uma seleção bem pequena de comandos para te dar uma ideia de como as coisas funcionam.

{% include tip.html tip="Comandos escritos em **vermelho** precisam ser executados como *root*." %}

### 8.2.1 Gerenciamento de arquivos

Para mudar a pasta, execute:

<div class="cl">cd /home/nomedousuario/nomedapasta/</div>

Listar arquivos em uma pasta:

<div class="cl">ls</div>

Copiar um arquivo:

<div class="cl">cp nomedoarquivo /home/nomedousuario/nomedapasta/nomedoarquivo</div>

Deletar um arquivo:

<div class="cl">rm nomedoarquivo</div>

Deletar uma pasta junto com seu conteúdo:

<div class="cl">rm -rf /home/nomedousuario/nomedapasta</div>

Mover ou renomear um arquivo:

<div class="cl">mv /home/nomedousuario/nomedoarquivo /home/nomedousuario/novonomedoarquivo</div>

### 8.2.2 Monitoramento do sistema

Exibir processos em execução e consumo de recursos do sistema (pressione a tecla **Q** para sair):

<div class="cl">top</div>

Verificar o uso do espaço em disco:

<div class="cl">df</div>

Verificar o consumo de memória:

<div class="cl">free</div>

### 8.2.3 Rede

Descobrir seu endereço IP:

<div class="cl">ip -c a</div>

Descobrir seu roteador (*gateway*):

<div class="cl">ip route</div>

Descobrir seus servidores DNS:

<div class="cl">cat /etc/resolv.conf</div>

### 8.2.4 Páginas de manual e ajuda

Quase todos os comandos vem acompanhados de uma página de manual descrevendo como usá-los e as opções que disponibilizam. Por exemplo, execute:

<div class="cl">man cp</div>

Para sair da página de manual, pressione **Q**.

Se um comando não tem uma página de manual, tente usar `--help` no lugar, por exemplo:

<div class="cl">cp --help</div>

### 8.2.5 Tornando-se root

Para alternar para o usuário *root* e executar comandos como administrador do sistema, execute:

<div class="cl">su -</div>

Então digite a senha do usuário *root* e tecle Enter. Nada aparecerá na tela enquanto você digita a senha do usuário *root*, isso é intencional.

Para parar de trabalhar como *root* e voltar a trabalhar com sua conta de usuário normal, execute:

<div class="clroot">exit</div>

Para executar apenas um único comando como *root*, use:

<div class="cl">su -c "[comando]"</div><p></p>

{% include note.html note="Apenas trabalhe como *root* quando for absolutamente necessário." %}

### 8.2.6 Ações de sistema

Para desligar, execute:

<div class="clroot">systemctl shutdown</div>

Reiniciar:

<div class="clroot">reboot</div>

Iniciar (*start*), parar (*stop*), reiniciar (*restart*) ou verificar o estado (*status*) de serviços do sistema, exemplos:

<div class="clroot">systemctl start apache2</div>
<div class="clroot">systemctl stop firewalld</div>
<div class="clroot">systemctl restart network</div>
<div class="clroot">systemctl status smb</div>

Habilitar (*enable*) ou desabilitar (*disable*) a inicialização de um serviço durante a inicialização do sistema, exemplos:

<div class="clroot">systemctl enable sshd</div>
<div class="clroot">systemctl disable cups</div>

### 8.2.7 O kernel

Para descobrir a versão e variação do seu *kernel*:

<div class="cl">uname -r</div>

Ler mensagens do *kernel* (útil para solucionar problemas de *hardware*):

<div class="clroot">dmesg</div>

Listar módulos do *kernel* carregados:

<div class="clroot">lsmod</div>

Carregar um módulo do *kernel*:

<div class="clroot">modprobe [nomedomodulo]</div>

Descarregar um módulo do *kernel*:

<div class="clroot">rmmod [nomedomodulo]</div>

### 8.2.8 Informações sobre o hardware

O comando **hwinfo** pode fornecer informações sobre quase todos os dispositivos de *hardware*, alguns exemplos:

<div class="clroot">hwinfo --short --wlan</div>
<div class="clroot">hwinfo --short --gfxcard</div>

Listar dispositivos PCI:

<div class="clroot">lspci</div>

Listar dispositivos USB:

<div class="cl">lsusb</div>

## 8.3 Editando arquivos de texto

Editar arquivos de configuração ou outros arquivos de texto pode ser feito usando o editor **vim**, que é instalado por padrão.

Abra um arquivo com o comando `vim /caminho/para/arquivo`. Exemplo:

<div class="clroot">vim /etc/sysconfig/yast2</div><p></p>

{% include note.html note="Permissões de *root* são usadas nesse exemplo porque o arquivo `yast2` é um arquivo de configuração do sistema — geralmente isso não é necessário para editar arquivos com o Vim." %}

Pressione **i** para entrar no modo de inserção (você verá `-- INSERT --` na parte inferior). Agora você pode editar o texto no arquivo. Quando terminar de editar, pressione **Esc** para deixar o modo de inserção e retornar ao modo de comando. Agora digite **:x**, que é o comando para salvar e sair, e tecle Enter. Para sair sem salvar as modificações, use **:q!**.

O Vim é um editor de texto bastante avançado, talvez você queira instalar um editor de texto mais simples. Experimente, por exemplo, o **nano**.

## 8.4 Mais informações

Se você quer aprender mais sobre como usar o terminal, há muitos recursos disponíveis na Internet, aqui estão alguns *links*:

[http://linuxcommand.org/](http://linuxcommand.org/)

[http://tldp.org/LDP/GNU-Linux-Tools-Summary/html/index.html](http://tldp.org/LDP/GNU-Linux-Tools-Summary/html/index.html)
