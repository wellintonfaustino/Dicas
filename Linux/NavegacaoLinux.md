Esses comandos são essenciais para usuários que desejam utilizar a linha de comando (CLI) do Ubuntu de forma eficiente.

### **Comandos de Navegação no Ubuntu**

1. **`pwd` (Print Working Directory)**

   - Exibe o diretório atual em que você está.

   ```bash
   pwd
   ```

2. **`cd` (Change Directory)**

   - Muda para outro diretório.

   ```bash
   cd /caminho/do/diretorio
   ```

   - **`cd ~`**: Vai para o diretório home do usuário.
   - **`cd ..`**: Sobe um nível na hierarquia de diretórios.
   - **`cd -`**: Retorna ao diretório anterior.

3. **`ls` (List)**
   - Lista o conteúdo do diretório atual.
   ```bash
   ls
   ```
   - **`ls -l`**: Lista com detalhes (permissões, proprietário, tamanho, etc.).
   - **`ls -a`**: Lista todos os arquivos, incluindo os ocultos.
   - **`ls -lh`**: Exibe o tamanho dos arquivos de forma legível (em KB, MB, etc.).

### **Comandos de Manipulação de Arquivos e Diretórios**

4. **`touch`**

   - Cria um novo arquivo vazio.

   ```bash
   touch nome_do_arquivo.txt
   ```

5. **`mkdir` (Make Directory)**

   - Cria um novo diretório.

   ```bash
   mkdir nome_do_diretorio
   ```

   - **`mkdir -p`**: Cria um diretório e seus subdiretórios.

   ```bash
   mkdir -p pasta/subpasta
   ```

6. **`cp` (Copy)**

   - Copia arquivos ou diretórios.

   ```bash
   cp arquivo_origem.txt arquivo_destino.txt
   ```

   - **`cp -r`**: Copia diretórios recursivamente.

   ```bash
   cp -r diretorio_origem diretorio_destino
   ```

7. **`mv` (Move)**

   - Move ou renomeia arquivos ou diretórios.

   ```bash
   mv nome_antigo.txt nome_novo.txt
   ```

   - Também pode ser usado para mover arquivos para outro diretório.

   ```bash
   mv arquivo.txt /caminho/do/diretorio
   ```

8. **`rm` (Remove)**

   - Remove arquivos.

   ```bash
   rm arquivo.txt
   ```

   - **`rm -r`**: Remove diretórios recursivamente.

   ```bash
   rm -r diretorio
   ```

   - **`rm -i`**: Remove arquivos ou diretórios com confirmação do usuário.
   - **`rm -f`**: Força a remoção sem confirmação.

9. **`rmdir` (Remove Directory)**
   - Remove diretórios vazios.
   ```bash
   rmdir nome_do_diretorio
   ```

### **Comandos de Visualização e Edição de Arquivos**

10. **`cat`**

    - Exibe o conteúdo de um arquivo.

    ```bash
    cat arquivo.txt
    ```

11. **`more` e `less`**

    - Exibe o conteúdo de um arquivo página por página.

    ```bash
    more arquivo.txt
    less arquivo.txt
    ```

12. **`head`**

    - Exibe as primeiras linhas de um arquivo.

    ```bash
    head -n 10 arquivo.txt
    ```

13. **`tail`**

    - Exibe as últimas linhas de um arquivo.

    ```bash
    tail -n 10 arquivo.txt
    ```

14. **`nano`**

    - Editor de texto no terminal.

    ```bash
    nano arquivo.txt
    ```

    - Comandos comuns no `nano`:
      - **Ctrl + O**: Salvar arquivo.
      - **Ctrl + X**: Sair do editor.
      - **Ctrl + K**: Cortar linha.
      - **Ctrl + U**: Colar linha.

15. **`vi` ou `vim`**
    - Editores de texto mais avançados no terminal.
    ```bash
    vi arquivo.txt
    vim arquivo.txt
    ```
    - Modo de comando:
      - **i**: Entra no modo de inserção (edição).
      - **Esc**: Sai do modo de inserção para o modo de comando.
      - **:w**: Salva o arquivo.
      - **:q**: Sai do editor.
      - **:wq**: Salva e sai.
      - **:q!**: Sai sem salvar.

### **Comandos de Pesquisa e Manipulação de Texto**

16. **`grep`**

    - Procura por padrões em arquivos.

    ```bash
    grep 'palavra' arquivo.txt
    ```

    - **`grep -i`**: Pesquisa sem diferenciar maiúsculas de minúsculas.
    - **`grep -r`**: Pesquisa recursivamente em diretórios.

17. **`find`**

    - Localiza arquivos e diretórios.

    ```bash
    find /caminho -name 'nome_do_arquivo'
    ```

18. **`wc` (Word Count)**
    - Conta linhas, palavras e caracteres em arquivos.
    ```bash
    wc arquivo.txt
    ```
    - **`wc -l`**: Conta apenas as linhas.
    - **`wc -w`**: Conta apenas as palavras.
    - **`wc -c`**: Conta apenas os caracteres.

### **Comandos de Permissões e Propriedades de Arquivos**

19. **`chmod` (Change Mode)**

    - Altera as permissões de arquivos ou diretórios.

    ```bash
    chmod 755 arquivo.txt
    ```

    - Exemplos de permissões:
      - **`chmod +x`**: Adiciona permissão de execução.
      - **`chmod -r`**: Remove permissão de leitura.

20. **`chown` (Change Owner)**
    - Altera o proprietário de arquivos ou diretórios.
    ```bash
    sudo chown usuario:grupo arquivo.txt
    ```

### **Comandos de Compressão e Arquivamento**

21. **`tar`**

    - Cria ou extrai arquivos `.tar`.

    ```bash
    tar -cvf arquivo.tar /caminho/do/diretorio
    tar -xvf arquivo.tar
    ```

    - **`tar -czvf`**: Cria um arquivo `.tar.gz` comprimido.
    - **`tar -xzvf`**: Extrai um arquivo `.tar.gz`.

22. **`gzip` e `gunzip`**
    - Comprime e descomprime arquivos.
    ```bash
    gzip arquivo.txt
    gunzip arquivo.txt.gz
    ```

### **Comandos de Rede e Sistema**

23. **`ifconfig` ou `ip`**

    - Exibe informações de rede.

    ```bash
    ifconfig
    ip addr
    ```

24. **`ping`**

    - Testa a conectividade de rede.

    ```bash
    ping google.com
    ```

25. **`ssh`**

    - Conecta-se a um servidor remoto via SSH.

    ```bash
    ssh usuario@servidor
    ```

26. **`top`**

    - Monitora processos em execução e uso de recursos.

    ```bash
    top
    ```

27. **`ps`**

    - Exibe processos em execução.

    ```bash
    ps aux
    ```

28. **`kill` e `killall`**

    - Termina processos em execução.

    ```bash
    kill PID
    killall nome_do_processo
    ```

29. **`df`**

    - Exibe o uso de espaço em disco.

    ```bash
    df -h
    ```

30. **`du`**
    - Exibe o uso de espaço em diretórios.
    ```bash
    du -sh /caminho/do/diretorio
    ```

### **Outros Comandos Úteis**

31. **`history`**

    - Exibe o histórico de comandos digitados.

    ```bash
    history
    ```

32. **`alias`**

    - Cria atalhos para comandos.

    ```bash
    alias ll='ls -la'
    ```

33. **`man`**

    - Mostra o manual de um comando.

    ```bash
    man comando
    ```

34. **`echo`**

    - Exibe uma linha de texto.

    ```bash
    echo "Olá, Mundo!"
    ```

35. **`clear`**
    - Limpa a tela do terminal.
    ```bash
    clear
    ```

Este guia cobre uma ampla gama de comandos básicos e avançados que você pode usar para gerenciar arquivos, diretórios, permissões, processos e muito mais no Ubuntu. Esses comandos são fundamentais para operar e administrar sistemas baseados em Linux.
