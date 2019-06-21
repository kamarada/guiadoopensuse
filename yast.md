---
layout: default
title: 9. Configurações de Administrador (YaST) - Introdução ao Centro de controle do YaST
permalink: yast
---

# 9. Configurações de Administrador (YaST)

YaST (do inglês *Yet another Setup Tool*, "apenas mais uma ferramenta de configuração") é a ferramenta central para administrar o sistema. Você encontra o YaST no lançador de aplicativos, na categoria "Sistema".

{% include screenshot.html image="yast-controlcenter" %}

**Módulos padrão do YaST**

No YaST você pode fazer praticamente qualquer tarefa de sistema com poderosos módulos gráficos, por exemplo:

- Instalar e remover *softwares* (veja o próximo capítulo)
- Configurar sua impressora
- Configurar o *firewall*
- Habilitar e desabilitar serviços do sistema
- Configurar compartilhamentos de rede (Samba)
- Particionar e formatar suas unidades de disco
- Habilitar o daemon NTP
- E muito, muito mais...

**Módulos adicionais do YaST**

Há vários outros módulos do YaST disponíveis além dos incluídos na instalação padrão (leia sobre como instalar pacotes no próximo capítulo). Alguns módulos notáveis não instalados por padrão são:

- Servidor *web* Apache (pacote: yast2-http-server)
- Daemon SSH (pacote: yast2-sshd)
- Servidor FTP (pacote: yast2-ftp-server)
- Servidor NFS (pacote: yast2-nfs-server)
- E muitos mais...

{% include tip.html tip="Se não deseja, você não precisa usar o YaST. As mesmas ações administrativas que você faz com o YaST e mais podem ser feitas usando ferramenas de linha de comando e editando manualmente arquivos de configuração." %}

## 9.1 YaST no terminal

Os módulos do YaST também podem ser usados no terminal (modo ncurses) - isso é muito útil em servidores sem ambiente gráfico, em acessos remotos via SSH ou caso você esteja enfrentando algum problema para usar seu ambiente gráfico.

Simplesmente execute *yast* como *root* no terminal.

<div class="clroot">yast</div><p></p>

{% include screenshot.html image="yast-ncurses" %}

Navegue pelas opções usando as teclas de setas, a tecla Enter e as combinações de teclas Alt + [letra destacada] (por exemplo, Alt + S para sair).
