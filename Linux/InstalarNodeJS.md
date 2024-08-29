## **_Instalar NodeJS a partir de um .tar.xz_**

Para instalar o Node.js usando um arquivo `.tar.xz` que você baixou, siga estas instruções:

### Passo 1: Extraia o Arquivo

Abra o terminal e navegue até o diretório onde o arquivo `.tar.xz` foi baixado. Use o comando `tar` para extrair o arquivo:

```bash
tar -xf nome-do-arquivo.tar.xz
```

Substitua `nome-do-arquivo.tar.xz` pelo nome real do arquivo que você baixou.

### Passo 2: Mova os Arquivos para o Diretório de Sistema

Depois de extrair o arquivo, você terá uma nova pasta com o Node.js. Para instalar o Node.js globalmente, mova essa pasta para o diretório `/usr/local`:

```bash
sudo mv nome-da-pasta-extraída /usr/local/node
```

Substitua `nome-da-pasta-extraída` pelo nome da pasta que foi criada após a extração.

### Passo 3: Configurar Variáveis de Ambiente

Para tornar o Node.js acessível a partir de qualquer lugar, você precisa adicionar o diretório `bin` do Node.js ao `PATH`. Abra o arquivo de configuração de shell (`.bashrc` ou `.zshrc`, dependendo do shell que você usa):

```bash
nano ~/.bashrc
```

No final do arquivo, adicione a seguinte linha:

```bash
export PATH=/usr/local/node/bin:$PATH
```

Salve o arquivo (`Ctrl + O`, depois `Enter`) e saia do editor (`Ctrl + X`).

### Passo 4: Atualizar as Variáveis de Ambiente

Execute o seguinte comando para carregar as novas configurações do arquivo de configuração:

```bash
source ~/.bashrc
```

### Passo 5: Verificar a Instalação

Verifique se o Node.js e o npm estão instalados corretamente:

```bash
node -v
npm -v
```

Se você vir as versões corretas, a instalação foi concluída com sucesso.

### Passo 6: (Opcional) Remover a Instalação Antiga

Se houver uma versão antiga do Node.js instalada, você pode removê-la:

```bash
sudo apt remove nodejs npm
```

Agora, você terá o Node.js instalado a partir do arquivo `.tar.xz`!

Caso dê erro no terminal zsh, execute o comando:

Parece que o problema está relacionado à configuração do `PATH`. Vamos corrigir isso adicionando o caminho correto ao arquivo de configuração do seu shell.

### Passo 1: Verifique o Shell que Está Usando

Como você está usando o `zsh`, é provável que precise adicionar o `PATH` ao arquivo de configuração do `zsh` (`.zshrc`) em vez do `.bashrc`.

Abra o arquivo `.zshrc` para edição:

```bash
nano ~/.zshrc
```

### Passo 2: Adicione o Diretório `bin` do Node.js ao `PATH`

No final do arquivo `.zshrc`, adicione a seguinte linha:

```bash
export PATH=/usr/local/node/bin:$PATH
```

Salve o arquivo (`Ctrl + O`, depois `Enter`) e saia do editor (`Ctrl + X`).

### Passo 3: Recarregue as Configurações do Shell

Recarregue o arquivo de configuração para que as mudanças entrem em vigor:

```bash
source ~/.zshrc
```

### Passo 4: Verifique a Instalação Novamente

Agora, verifique novamente as versões do Node.js e npm:

```bash
node -v
npm -v
```

Isso deve corrigir o problema de comando não encontrado.
