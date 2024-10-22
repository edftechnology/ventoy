# Como instalar/configurar/usar o `speedtest-cli` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para instalar/configurar/usar o `speedtest-cli` no `Linux Ubuntu`.

## _Abstract_

_This document contains the main commands and settings to install/configure/use the `speedtes-cli` on `Linux Ubuntu`._

## Descrição [2]

### `speedtest-cli`

O `speedtest-cli` é uma ferramenta de linha de comando amplamente utilizada para medir a velocidade da conexão à internet de um sistema `Linux`. Baseado no serviço `Speedtest.net`, ele permite aos usuários verificar a largura de banda de download e upload de sua conexão, bem como a latência da rede, tudo a partir da linha de comando. O `speedtest-cli` é uma opção conveniente para administradores de rede, usuários avançados e aqueles que desejam monitorar a qualidade de sua conexão à internet de forma rápida e direta, sem a necessidade de uma interface gráfica. Ele fornece informações valiosas para avaliar o desempenho da rede e solucionar problemas de conectividade.

## 1. Configurar/Instalar/Usar o `speedtest-cli` no `Linux Ubuntu` [1]

Para configurar/instalar/usar o `speedtest-cli` no Ubuntu, você pode usar o gerenciador de pacotes apt. Siga os passos abaixo:

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
    

3. **Instale o `speedtest-cli`:** Utilize o comando apt para instalar o pacote. `sudo apt install speedtest-cli -y`

4. **Confirme a Instalação:** Após a instalação ser concluída, você pode verificar se o `speedtest-cli` foi instalado com sucesso executando o seguinte comando: `speedtest-cli --version`

Isso deverá mostrar a versão do `speedtest-cli` instalada.

5. **Execute um Teste:** Para fazer um teste de velocidade, simplesmente execute o comando: `speedtest-cli --share`

Pronto! Agora você deve ter o `speedtest-cli` instalado e funcionando em seu sistema Ubuntu.

## 1.1 Código completo para configurar/instalar/usar

Para configurar/instalar/usar o `speedtest` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abra o `Terminal Emulator. Você pode fazer isso pressionando: `Ctrl + Alt + T`

2. Digite o seguinte comando e pressione `Enter`:

    ```
    sudo apt clean
    sudo apt autoclean
    sudo apt autoremove
    sudo apt update -y
    sudo apt autoremove
    sudo apt autoclean
    sudo apt list --upgradable
    sudo apt full-upgrade -y
    sudo apt install speedtest-cli -y
    speedtest-cli --version
    speedtest-cli --share
    ```

## Referências

[1] OPENAI. ***Instalar speedtest-cli no ubuntu.*** Disponível em: <https://chat.openai.com/c/09b3a046-d1c5-42ce-b924-ab66e10a2e43> (texto adaptado). ChatGPT. Acessado em: 25/10/2023 10:24.

[2] OPENAI. ***Vs code: editor popular.*** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). ChatGPT. Acessado em: 16/11/2023 10:06.
