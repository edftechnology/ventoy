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

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando:
    ```bash
    sudo apt clean
    ```

    2.2 Remover pacotes `.deb` antigos ou duplicados do `cache` local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando:
    ```bash
    sudo apt autoclean
    ```

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando:
    ```bash
    sudo apt autoremove -y
    ```

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt update
    ```

    2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes:
    ```bash
    sudo apt --fix-broken install
    ```

    2.6 Limpar o `cache` do gerenciador de pacotes `apt` novamente:
    ```bash
    sudo apt clean
    ```

    2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt list --upgradable
    ```

    2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt full-upgrade -y
    ```

Para instalar o `Ventoy` no `Linux Ubuntu` pelo `Terminal Emulator`, você pode seguir os passos abaixo. O `Ventoy` é uma ferramenta de código aberto que permite criar um drive USB bootável contendo várias imagens `.iso`, permitindo que você escolha qual sistema operacional inicializar durante a partida do computador.

1. **Baixe o pacote `Ventoy`:** Primeiro, você precisa baixar o pacote mais recente do `Ventoy` do site oficial. Você pode fazer isso visitando `https://www.ventoy.net` e navegando até a seção de _download_ para baixar a versão para `Linux`.

2. **Extraia o arquivo baixado:** Após o _download_, você precisará extrair o arquivo. Você pode fazer isso com o comando `tar` no `Terminal Emulator`. Supondo que o arquivo baixado esteja no diretório `~/Downloads`, o comando seria algo como:

    ```bash
    sudo tar -xvzf ~/Downloads/ventoy-x.y.z-linux.tar.gz
    ```

    Substitua `ventoy-x.y.z-linux.tar.gz` pelo nome do arquivo que você baixou.

2. **Navegue até o diretório extraído:** Uma vez extraído, navegue até o diretório do `Ventoy` usando o comando `cd`:

    ```bash
    cd ventoy-x.y.z
    ```

    **NÃO** se esqueça de colocar a pasta do `Ventoy` em `~/Downloads`, se não, você terá dificuldades em instalá-lo.

3. **Instale o `Ventoy` no seu drive USB:** Primeiro, você precisa identificar o dispositivo USB em que deseja instalar o `Ventoy`. Use o comando `lsblk` para listar todos os dispositivos de bloco e identificar seu drive USB. Tenha cuidado para selecionar o dispositivo correto, pois o processo irá formatar o drive e todos os dados existentes serão perdidos:

    ```bash
    lsblk
    ```

4. Identifique seu drive USB (por exemplo, `/dev/sdc`) e prossiga com a instalação do `Ventoy` nesse _drive_. Substitua `/dev/sdx` pelo caminho correto do seu drive USB:

    ```bash
    sudo ./Ventoy2Disk.sh -i /dev/sdx
    ```

    - **`-i`:** significa instalar o `Ventoy` no dispositivo especificado.

    **Nota:** Tenha certeza de substituir `/dev/sdx` pelo identificador correto do seu drive USB. Você não quer acidentalmente formatar o dispositivo errado.

    Esses passos devem instalar o `Ventoy` no seu drive USB, permitindo que você copie imagens ISO para o drive e as inicialize diretamente através do menu de _boot_ do `Ventoy`.

5. Copie os arquivos `.iso` para a _pendrive_ que foi formatado pelo `Ventoy`, pronto, agora você possui um _pendrive multiboot_ com um ou vários sistemas operacionais.

**Importante:** Antes de executar comandos, especialmente aqueles que modificam partições ou dispositivos, como a instalação do Ventoy, certifique-se de ter backups de seus dados e de ter lido e entendido cada passo. Comandos como `sudo ./Ventoy2Disk.sh -i /dev/sdx` podem causar a perda de dados se direcionados ao dispositivo errado.



### 1.1 Código completo para configurar/instalar/usar

Para configurar/instalar/usar o `ventoy` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abra o `Terminal Emulator`. Você pode fazer isso pressionando: `Ctrl + Alt + T`

2. Digite o seguinte comando e pressione `Enter`:

    ```
    NÂO há.
    ```


## 2. Criar boot persistente com o `ventoy`

O **boot persistente** permite salvar mudanças (arquivos, pacotes, configurações) em um sistema 
*live*. Abaixo está um exemplo no **Linux Ubuntu**, usando as ISOs do **Xubuntu** e do **Kali**.

### 2.1 Criar arquivos de persistência

1. No diretório onde você extraiu o `ventoy`, use o _script_ `CreatePersistentImg.sh` para criar os 
arquivos de persistência (ex.: 4 GB cada):

  **NOTA(S)**: Lei as **OBSERVAÇÃO(ÕES)** antes de executar o(s) comando(s) abaixo:

  ```bash
  cd /media/edenedfsls/Ventoy/ventoy-1.0.97
  sudo ./CreatePersistentImg.sh -s 4096 -l casper-rw -o /media/edenedfsls/Ventoy/persistence/
  xubuntu.dat
  sudo ./CreatePersistentImg.sh -s 4096 -l persistence -c persistence.conf -o /media/edenedfsls/Ventoy/
  persistence/kali.dat

  ls -lh /media/edenedfsls/Ventoy/persistence
  ```

  **OBSERVAÇÃO(ÕES)**:
  
  - **NÃO** esqueça de alterar o nome do usuário `edenedfsls` para o nome do usuário em questão.

  - Demoram alguns minutos para criar os arquivos, tenha paciência. No final da criação de cada
  arquivo será gerada uma saída, por exemplo:

  ```bash
  sudo ./CreatePersistentImg.sh -s 4096 -l casper-rw -o /media/edenedfsls/Ventoy/persistence/xubuntu.dat
  [sudo] password for edenedfsls: 
  4096+0 records in
  4096+0 records out
  4294967296 bytes (4,3 GB, 4,0 GiB) copied, 353,26 s, 12,2 MB/s
  mke2fs 1.46.5 (30-Dec-2021)
  Creating filesystem with 1048576 4k blocks and 262144 inodes
  Filesystem UUID: dc86edf5-8758-4163-ab88-186ff81ff2cb
  Superblock backups stored on blocks: 
    32768, 98304, 163840, 229376, 294912, 819200, 884736

  Allocating group tables: done                            
  Writing inode tables: done                            
  Creating journal (16384 blocks): done
  Writing superblocks and filesystem accounting information: done 
  ```

  - `Kali` precisa do arquivo `persistence.conf` dentro do _backend_ de persistência. O Comando
  `sudo ./CreatePersistentImg.sh -s 4096 -l persistence -c persistence.conf -o /media/edenedfsls/Ventoy/
  persistence/kali.dat` já cria o arquivo com o conteúdo `/ union`.



### 2.3 Associar cada ISO ao seu arquivo de persistência

O Ventoy aceita o `ventoy.json` na raiz e também em `/ventoy/ventoy.json`
 (depende da versão/configuração). Por isso deixei nos dois lugares — é 
 o jeito mais seguro de garantir que ele leia.

1. Crie o arquivo `ventoy.json` em `/media/edenedfsls/Ventoy/` (se a pasta não existir, crie-a):

    ```bash
    mkdir -p /media/edenedfsls/Ventoy/ventoy
    touch ventoy.json
    ```

2. Conteúdo sugerido do `ventoy.json`:

    ```bash
    {
    "persistence": [
        {
        "image": "/xubuntu-22.04.5-desktop-amd64.iso",
        "backend": "/persistence/xubuntu.dat",
        "timeout": 10,
        "autosel": 1
        },
        {
        "image": "/kali-linux-2024.3-live-amd64.iso",
        "backend": "/persistence/kali.dat",
        "timeout": 10,
        "autosel": 1
        }
    ]
    }
    ```

### 2.4 Como iniciar o _boot_ de persistÊncia

1. Selecione o ISO.

2. Vá em Boot in normal mode.

3. Deve aparecer o prompt de persistência com contagem de 10s.


### 2.5 Observações importantes

- Ao inicializar pelo `Ventoy`, selecione a opção Persistence (quando aparecer) para usar o armazenamento persistente.
- Se o `Linux Ubuntu` não reconhecer a persistência, recrie o arquivo com o _label_ adequado (em versões antigas, `casper-rw`; em versões mais novas, writable). Exemplo:

    ```bash
    sudo /media/edenedfsls/Ventoy/ventoy-1.0.97/CreatePersistentImg.sh -s 8192 -t ext4 -l writable $USB/persistence/xubuntu.dat
    ```

- Para o `Kali`, geralmente o _label_ recomendado é persistence. Se necessário, recrie assim:

    ```bash
    sudo /media/edenedfsls/Ventoy/ventoy-1.0.97/CreatePersistentImg.sh -s 8192 -t ext4 -l persistence $USB/persistence/kali.dat
    ```

## Referências

[1] OPENAI. ***Instalar `Ventoy` no Ubuntu.*** Disponível em: <https://chat.openai.com/c/f274e863-9214-4f34-9adf-b8b1fdf17029> (texto adaptado). Acessado em: 03/04/2023 17:11.

[2] OPENAI. ***Vs code: editor popular.*** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). Acessado em: 03/04/2024 17:10.


