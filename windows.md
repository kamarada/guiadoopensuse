---
layout: default
title: 12. Integração com o Windows - Usando o openSUSE em uma rede Windows, abrindo documentos do Office e executando aplicativos para Windows
permalink: windows
---

# 12. Integração com o Windows

O mundo do PC é dominado pela Microsoft, e ela não é exatamente conhecida por facilitar a integração entre diversos sistemas. Apesar disso, é possível integrar Linux e Windows de forma bastante transparente na maioria dos casos. Esse capítulo aborda os problemas mais comuns.

## 12.1 Documentos do Office

O LibreOffice usa por padrão o Open Document Format (\*.odt, \*.ods, \*.odp, etc.), que é um padrão aberto. Seus contatos que usam Windows e Mac OS X podem abrir documentos criados por você usando o Microsoft Office, que suporta parcialmente esse formato desde a versão 2007 Service Pack 2. Ou você pode sugerir-lhes instalar o LibreOffice, que é disponibilizado gratuitamente também para esses sistemas.

O LibreOffice também pode ler e escrever nos formatos do Microsoft Office (\*.doc, \*.xls, \*.ppt, \*.docx, \*.xlsx, \*.pptx, etc.) muito bem — assim como em uma ampla variedade de formatos.

{% include tip.html tip="Se você se deparar com documentos do Microsoft Office que o LibreOffice não renderiza bem, considere tentar se tem mais sorte com a suíte Calligra." %}

## 12.2 Redes Windows

Para compartilhar recursos em uma rede local com computadores com Windows, é usado o serviço Samba.

### 12.2.1 Acessando compartilhamentos

Não é necessária configuração adicional para acessar arquivos compartilhados por outros. Simplesmente:

<div class="path">Abra o gerenciador de arquivos Dolphin => Clique na barra de endereços ou pressione Ctrl + L para editar a localização => Digite <code>smb://[nome-ou-endereco-ip-do-computador]</code></div><p></p>

{% include screenshot.html image="smb-dolphin" %}

Se não souber o nome ou endereço IP do computador que deseja acessar, você pode *navegar* pela rede local simplesmente digitando `smb:/` na barra de endereços do Dolphin. No entanto, isso só vai funcionar se você configurar ou (temporariamente) desabilitar o *firewall* antes. Mais informações em breve...

### 12.2.2 Compartilhando seus arquivos

Para compartilhar *seus* arquivos com usuários de Windows, de Mac OS X ou de outros GNU/Linux na rede local, você precisa configurar o Servidor Samba (certifique-se de que os pacotes *yast2-samba-server* e *samba* estão instalados). Você só precisa executar os passos 2 e 3 a seguir na primeira vez que compartilhar uma pasta.

1) Abra o módulo Servidor Samba do YaST.

<div class="path">YaST =&gt; Serviços de rede =&gt; Servidor Samba</div><p></p>

{% include screenshot.html image="samba-server" %}

2) Na guia **Inicialização**, selecione iniciar o serviço do Samba tanto após salvar configuração quanto após reinicializar e também abrir as portas necessárias no *firewall*.

3) Na guia **Compartilhamentos**, marque as opções **Permitir aos Usuários Compartilhar seus Diretórios** e **Permitir Acesso de Convidado**. Na guia **Identidade**, você pode configurar seu grupo de trabalho (ou domínio) e nome de computador (como aparecerá para outros computadores com Windows).

4) Na guia **Compartilhamentos**, adicione compartilhamentos clicando em **Adicionar** e especificando as pastas que você quer compartilhar.

## 12.3 Executando aplicativos para Windows

Existem aplicativos de alta qualidade nativos para GNU/Linux para quase todos os propósitos, mas pode ser que você dependa de um aplicativo disponível apenas para Windows para fazer algum trabalho. Estas são suas opções em casos assim:

{% include note.html note="Você só deve executar aplicativos não-nativos como último recurso. Aplicativos funcionam melhor nos sistemas operacionais para os quais foram desenvolvidos." %}

### 12.3.1 Wine

Wine (do inglês *Wine Is Not an Emulator*, "Wine não é um emulador") é um aplicativo que possibilita a você executar vários aplicativos para Windows. Você pode instalar o Wine usando YaST ou zypper. O Wine é um aplicativo de linha de comando, sua sintaxe é:

<div class="cl">wine /caminho/para/o/aplicativo.exe</div><p></p>

{% include tip.html tip="O pacote [q4wine](http://sourceforge.net/projects/q4wine/) fornece uma interface gráfica para algumas funcionalidades do Wine." %}

O projeto Wine mantém um banco de dados onde usuários compartilham suas experiências usando aplicativos:

[http://appdb.winehq.org/appbrowse.php](http://appdb.winehq.org/appbrowse.php)

### 12.3.2 CrossOver

O CrossOver não é grátis. É especializado em executar alguns dos aplicativos para Windows mais usados — em sua maioria, relacionados a escritório.

[https://www.codeweavers.com/products/cxlinux/](https://www.codeweavers.com/products/cxlinux/)

### 12.3.3 Dual boot

Como foi dito no capítulo *Instalação*, é relativamente simples ter GNU/Linux e Windows instalados no mesmo computador. Se você precisa de apenas alguns aplicativos que raramente usa, talvez valha a pena reiniciar para o Windows vez por outra, quando você precisar usar esses aplicativos específicos.

Quando você instala um sistema em *dual boot*, suas partições do Windows provavelmente são montadas em */windows/C/*, */windows/D/*, etc. Se não, você pode atribuir pontos de montagem (pastas nas quais as partições devem ser montadas) em YaST => Sistema => Particionador. Por padrão, partições formatadas com o sistema de arquivos NTFS serão montadas somente leitura. Para habilitar a escrita para usuários normais, você deve editar as entradas correspondentes no arquivo */etc/fstab* e substituir *fmask=113,dmask=002* por *umask=0002*.

### 12.3.4 Virtualização

É possível executar o Windows sobre o GNU/Linux dentro de uma *máquina virtual*, usando *softwares* como VirtualBox, KVM, Xen ou VMware. Isso é um pouco avançado e requer algum poder computacional.
