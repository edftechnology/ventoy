# Como configurar/instalar/usar o `ventoy` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para configurar/instalar/usar o `ventoy` no `Linux Ubuntu`.

## _Abstract_

_This document contains the main commands and settings for configuring/installing/using the `ventoy` on `Linux Ubuntu`._


## Descrição [2]

### `ventoy`

O `Ventoy` é uma ferramenta de código aberto que permite criar um pendrive bootável multifuncional. Com o `Ventoy`, é possível copiar várias imagens ISO para o pendrive e inicializá-las diretamente sem precisar gravar o pendrive novamente. Isso oferece flexibilidade para usuários que precisam manter diversas ferramentas de inicialização, como sistemas operacionais e utilitários de diagnóstico, em um único dispositivo.


## 1. Como configurar/instalar/usar o `ventoy` no `Linux Ubuntu` [1][3]

Para configurar/instalar/usar o `ventoy` no `Linux Ubuntu`, você pode seguir estes passos:

1. Abra o `Terminal Emulator`. Você pode fazer isso pressionando: `Ctrl + Alt + T`

2. Certifique-se de que seu sistema esteja limpo e atualizado.

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando: `sudo apt clean` 
    
    2.2 Remover pacotes `.deb` antigos ou duplicados do cache local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando: `sudo apt autoclean`

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando: `sudo apt autoremove -y`

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`: `sudo apt update`

    2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes: `sudo apt --fix-broken install`

    2.6 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando: `sudo apt clean` 
    
    2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:  `sudo apt list --upgradable`

    2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`: `sudo apt full-upgrade -y`
   

Para instalar o `Ventoy` no `Linux Ubuntu` pelo `Terminal Emulator`, você pode seguir os passos abaixo. O `Ventoy` é uma ferramenta de código aberto que permite criar um drive USB bootável contendo várias imagens `.iso`, permitindo que você escolha qual sistema operacional inicializar durante a partida do computador.

1. **Baixe o pacote `Ventoy`:** Primeiro, você precisa baixar o pacote mais recente do Ventoy do site oficial. Você pode fazer isso visitando `https://www.ventoy.net` e navegando até a seção de _download_ para baixar a versão para `Linux`.

2. **Extraia o arquivo baixado:** Após o _download_, você precisará extrair o arquivo. Você pode fazer isso com o comando `tar` no `Terminal Emulator`. Supondo que o arquivo baixado esteja no diretório `~/Downloads`, o comando seria algo como: `sudo tar -xvzf ~/Downloads/ventoy-x.x.x-linux.tar.gz`

    Substitua `ventoy-x.x.x-linux.tar.gz` pelo nome do arquivo que você baixou.

2. **Navegue até o diretório extraído:** Uma vez extraído, navegue até o diretório do `Ventoy` usando o comando `cd`: `cd ventoy-1.0.97`

    **NÃO** se esqueça de colocar a pasta do Ventoy em `~/Downloads`, se não, você terá dificuldades em instalá-lo.

3. **Instale o `Ventoy` no seu drive USB:** Primeiro, você precisa identificar o dispositivo USB em que deseja instalar o `Ventoy`. Use o comando `lsblk` para listar todos os dispositivos de bloco e identificar seu drive USB. Tenha cuidado para selecionar o dispositivo correto, pois o processo irá formatar o drive e todos os dados existentes serão perdidos: `lsblk`

4. Identifique seu drive USB (por exemplo, `/dev/sdc`) e prossiga com a instalação do `Ventoy` nesse _drive_. Substitua `/dev/sdx` pelo caminho correto do seu drive USB. `sudo ./Ventoy2Disk.sh -i /dev/sdx`

    - **`-i`:** significa instalar o `Ventoy` no dispositivo especificado.

    **Nota:** Tenha certeza de substituir `/dev/sdx` pelo identificador correto do seu drive USB. Você não quer acidentalmente formatar o dispositivo errado.

    Esses passos devem instalar o `Ventoy` no seu drive USB, permitindo que você copie imagens ISO para o drive e as inicialize diretamente através do menu de boot do Ventoy.

5. Copie os arquivos `.iso` para a pendrive que foi formatado pelo `Ventoy`, pronto, agora você possui um _pendrive multiboot_ com um ou vários sistemas operacionais.

**Importante:** Antes de executar comandos, especialmente aqueles que modificam partições ou dispositivos, como a instalação do Ventoy, certifique-se de ter backups de seus dados e de ter lido e entendido cada passo. Comandos como `sudo ./Ventoy2Disk.sh -i /dev/sdx` podem causar a perda de dados se direcionados ao dispositivo errado.

### 1.1 Código completo para configurar/instalar/usar

Para configurar/instalar/usar o `ventoy` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abra o `Terminal Emulator`. Você pode fazer isso pressionando: `Ctrl + Alt + T`

2. Digite o seguinte comando e pressione `Enter`:

    ```
    NÂO há.
    ```


## Referências

[1] OPENAI. ***Instalar Ventoy no Ubuntu.*** Disponível em: <https://chat.openai.com/c/f274e863-9214-4f34-9adf-b8b1fdf17029> (texto adaptado). Acessado em: 03/04/2023 17:11.

[2] OPENAI. ***Vs code: editor popular.*** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). Acessado em: 03/04/2024 17:10.

