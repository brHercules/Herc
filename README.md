brHercules
========

Build Status:  
[![Build Status](https://travis-ci.org/brHercules/Herc.svg?branch=master)](https://travis-ci.org/brHercules/Herc)

Issues and pull requests:  
[![Open Issues](https://img.shields.io/github/issues-raw/brHercules/Herc.svg?label=Open%20Issues)](https://github.com/brHercules/Herc/issues)
[![Issues in progress](https://badge.waffle.io/brHercules/Herc.svg?label=status%3Aconfirmed&title=In%20Progress)](https://waffle.io/brHercules/Herc)
[![Ready PRs](https://badge.waffle.io/brHercules/Herc.svg?label=status%3Aready&title=Ready%20PRs)](https://waffle.io/brHercules/Herc)

Project Info:  
![Language](https://img.shields.io/badge/language-C-yellow.svg)
[![License](https://img.shields.io/badge/license-GPLv3-663399.svg)](https://github.com/HerculesWS/Hercules/blob/master/LICENSE)

Índice
---------
* 1 O que é brHercules?
* 2 Pré-requisitos
* 3 Instalação
* 4 Solução de problemas
* 5 Ligações úteis
* 6 Mais Documentação

O que é brHercules?
-----------------
Hercules é um projeto de desenvolvimento de software colaborativo que gira em torno do
criação de um jogo multiplayer (MMORPG).
Escrito em C, o programa é muito versátil e fornece NPCs e varias modificações.
O projecto é gerido conjuntamente por um grupo de
voluntários localizados em todo o mundo, bem como uma comunidade enorme fornecendo
QA e suporte. brHercules é uma continuação do projeto Athena originais.

Pré-requisitos
-------------
Antes de instalar o brHercules há certas ferramentas e aplicações que você vai
necessidade. Isso difere entre os sistemas operacionais variados disponíveis, de modo a
a seguir é dividido em Windows e Unix (incl. Linux) pré-requisitos.

Para obter uma lista de plataformas suportadas, consulte o [Apoiado
Plataformas] (https://github.com/HerculesWS/Hercules/wiki/Supported-Platforms) página wiki.

#### Janelas
  - Cliente Git
  - Servidor MySQL compatível ([MySQL Community Edition] (https://www.mysql.com/products/community/) ou
    [MariaDB] (https://mariadb.org/))
  - Microsoft Visual Studio ([Versão 2012 a 2015] (https://www.visualstudio.com/))

#### Unix / Linux / BSD (nomes de pacotes podem exigir números de versão específicas sobre determinadas distribuições)
  - git
  - Gcc ou clang (versão 4.5 ou mais recente, recomendado 5.0 ou mais recente)
  - GNU make
  - MySQL (mysql-server`) ou MariaDB
  - libmysqlclient ( `mysql-devel`)
  - Zlib ( `zlib-devel`)
  - libpcre ( `pcre-devel`)
  - * Dependências opcionais para o desenvolvimento só *
    - Perl (necessário para reconstruir os Hooks HPM e HPMDataCheck)
    - Doxygen (necessário para reconstruir os Hooks HPM e HPMDataCheck)

#### Mac OS X
  - Xcode ou as ferramentas de linha de comando do Xcode.
  - Servidor MySQL compatível (instalação de `mysql` ou` mariadb` através [Homebrew] (http://brew.sh/) é recomendado)
  - Biblioteca PCRE (instalação de `pcre` através [Homebrew] (http://brew.sh) é recomendado)
  - * Dependências opcionais para o desenvolvimento só *
    - Doxygen (necessário para reconstruir os Hooks HPM e HPMDataCheck)

#### opcionais, ferramentas úteis
  - clientes MySQL GUI
    - [MySQL Workbench] (http://www.mysql.com/downloads/workbench/) (cross-platform)
    - [HeidiSQL] (http://www.heidisql.com/) (Windows)
    - [Sequel Pro] (http://www.sequelpro.com/) (Mac OS X)
  - clientes GUI Git
    - [Atlassian SourceTree] (https://www.sourcetreeapp.com/) (Windows, Mac OS X)
    - [TortoiseGit] (https://tortoisegit.org/) (Windows)


Instalação
------------

Esta seção é um breve conjunto de instruções de instalação. Para mais concisa
guias relevantes para o seu sistema de operação, consulte o Wiki (links na
o fim do ficheiro).

#### Janelas
  1. Instalar os pré-requisitos.
  2. Clone o repositório Hercules (ver [GitHub] (https://github.com/HerculesWS/Hercules)) usando um cliente git, em um novo
     pasta.
  3. Conecte-se ao servidor MySQL como root:
    - Criar um banco de dados (Hercules): CREATE Hercules banco de dados; `
    - Crie um usuário (Hercules): CREATE 'Hercules' user @ 'localhost' identificado por 'password'; `.
    - Dê permissões (GRANT SELECT, INSERT, UPDATE, DELETE) para o usuário: GRANT SELECT, INSERT, UPDATE, DELETE ON
      \ `Hércules \` * TO 'Hercules' @ 'localhost';. '
  4. Conecte-se ao servidor MySQL como o novo usuário:
    - Importe os arquivos .sql em / SQL-files / para o novo banco de dados.
  5. Inicie o Visual Studio e carregar a solução fornecida:
    - Compilar e executar os três projetos, login-servidor, char-servidor, mapa-servidor.

#### Unix
  1. Instalar os pré-requisitos, através do gerenciador de pacotes da sua distribuição
    - (Red Hat compatível / CentOS) `yum install make gcc mysql mysql-devel mysql-server pcre-devel git` zlib-devel
    - (Debian compatível) `apt-get install gcc make git` libmysqlclient-dev zlib1g-dev libpcre3-dev mysql-server
    - (FreeBSD) `pkg instalar clang35 gmake mysql56-server mysql-connector-c pcre git`
    - (Mac OS X):
      - Instale Xcode através da Mac App Store
      - Inicializar as ferramentas de compilação através do Terminal `--help` xcode-select
      - Instale Homebrew como descrito na página do projeto
      - Instale os outros pré-requisitos: `bebida instalar mysql pcre`
  2. Clone o repositório Hercules `git clone https://github.com/HerculesWS/Hercules.git ~ / Hercules`
  3. Configure o servidor MySQL e iniciá-lo.
  4. Conecte-se ao servidor MySQL como root:
    - Criar um banco de dados (Hercules): CREATE Hercules banco de dados; `
    - Crie um usuário (Hercules): CREATE 'Hercules' user @ 'localhost' identificado por 'password'; `.
    - Dê permissões (GRANT SELECT, INSERT, UPDATE, DELETE) para o usuário: GRANT SELECT, INSERT, UPDATE, DELETE ON
      \ `Hércules \` * TO 'Hercules' @ 'localhost';. '
  5. Conecte-se ao servidor MySQL como o novo usuário:
    - Importe os arquivos .sql em / SQL-files / para o novo banco de dados.
  6. Introduza o diretório Hercules e configurar / construir Hercules
    -. `/ Configure`
    - `Make clean && make sql` (no FreeBSD, substitua` make` com `gmake`)
  7. Inicie os três servidores login-servidor, char-servidor, mapa-servidor.

Solução de problemas
---------------

Se você está tendo problemas com o início de seu servidor, a primeira coisa que você deve
fazer é verificar o que está acontecendo em seus consoles. Mais frequentemente do que não, todo o apoio
problemas podem ser resolvidos simplesmente por olhar para as mensagens de erro dadas.

Exemplos:

* Você recebe um erro no seu mapa-server_sql que é algo como isto:

`` `
[Erro]: npc_parsesrcfile: Não é possível analisar, provavelmente um TAB ausente ou extra no arquivo 'NPC / custom / jobmaster.txt', linha '17'. Ignorando linha ...
        * W1 = prontera, 153,193,6 roteiro
        * W2 = Mestre Job
        * W3 = 123, {
        * W4 =
`` `

  Se você olhar para o erro, ele está dizendo que você está perdendo (ou ter um
  adicional) TAB. Isto é facilmente corrigido por olhar para esta parte do erro:
  `* W1 = prontera, 153,193,6 script`.
  Se houvesse um guia onde é suposto ser, essa linha teria
  `Prontera, 153,193,6` em script` w1 e` a w2. Como há um espaço em vez de um
  TAB, as duas secções são lidos como um único parâmetro.

* Você tem um aviso semelhante ao seguinte usuário / senha padrão:

`` `
[Warning]: Usando o usuário padrão / S1 senha / p1 não é recomendado.
[Nota]: Por favor edite sua mesa 'login' para criar um verdadeiro usuário inter-servidor / password (gênero 'S')
[Nota]: e, em seguida, editar o seu usuário / senha no conf / map-server.conf (ou conf / importação / map_conf.txt)
`` `

  Relaxe. Este é apenas o que indica que você está usando o nome de usuário e senha padrão. Para
  corrigir isso, verifique sobre a parte nas instruções de instalação relevantes para a tabela `login`.

* O servidor Mapa diz o seguinte:

`` `
[Erro]: make_connection: conectar falhou (socket # 2, erro 10061:. Nenhuma conexão pôde ser feita porque a máquina de destino recusou ativamente)!
`` `

  Se este mostra-se no servidor de mapas, que geralmente significa que não há Char
  Servidor disponível para aceitar a conexão.

Links úteis
-------------

A lista de links a seguir apontam para vários arquivos de ajuda dentro do repositório,
artigos ou páginas da Wiki ou tópicos dentro do fórum Hercules.

* Hercules Fórum:
  http://herc.ws/board/

* Hercules Wiki:
  http://herc.ws/wiki/Main_Page

* Repositório Git URL:
  https://github.com/HerculesWS/Hercules

* Hercules IRC Canal:
  Rede: `irc.rizon.net`
  Canal: `# Hercules`

mais Documentação
------------------

Hercules tem uma grande coleção de arquivos de ajuda e scripts NPC amostras localizados em
/ Doc /

### Scripting
Recomenda-se a olhar o arquivo /doc/script_commands.txt Para obter ajuda ou até
mesmo para ideias de seu próximo script NPC. A maioria dos comandos de script tem um uso
exemplo.

### `@ Commands`
No jogo, os Game Masters tem a capacidade de usar Atcommands ( `` @) para controlar
jogadores, criar itens, mobs spawn, recarregar os arquivos de configuração e até mesmo controle
do clima. Para obter uma explicação detalhada, consulte /doc/atcommands.txt

### Permissão
O emulador Hercules tem um sistema de permissão que permite que certos grupos de
jogadores podem executar determinadas ações, ou ter acesso a certas melhorias visuais
ou atividades dentro do jogo. Para ver quais permissões estão disponíveis, elas
estão detalhados na /doc/permissions.txt

### Outras
Há mais arquivos no diretório /doc/ que irá ajudá-lo a criar scripts
ou atualizar o MapCache, ou até mesmo explicar como funciona o sistema de classes e bônus de itens.
Antes de postar um tópico pedindo ajuda nos fóruns, recomendamos que
todos os usuários leiam este conteúdo.
