## **_Instalar o Dbeaver_**

Para baixar e instalar o DBeaver no Ubuntu, você pode seguir os seguintes passos:

### 1. Instalação via Snap (Método mais fácil)

A maneira mais simples de instalar o DBeaver no Ubuntu é utilizando o Snap:

1. Abra o terminal no Ubuntu.
2. Execute o seguinte comando para instalar o DBeaver Community:

   ```bash
   sudo snap install dbeaver-ce
   ```

Este comando instalará a versão mais recente do DBeaver Community.

### 2. Instalação via Repositório DEB (Método Tradicional)

Se você preferir instalar a versão DEB diretamente do repositório oficial do DBeaver:

1. Abra o terminal no Ubuntu.
2. Adicione o repositório oficial e a chave GPG:

   ```bash
   wget -O - https://dbeaver.io/debs/dbeaver.gpg.key | sudo apt-key add -
   echo "deb https://dbeaver.io/debs/dbeaver-ce /" | sudo tee /etc/apt/sources.list.d/dbeaver.list
   ```

3. Atualize o cache dos pacotes e instale o DBeaver:

   ```bash
   sudo apt update
   sudo apt install dbeaver-ce
   ```

### 3. Instalação via Pacote DEB (Método Manual)

Você também pode baixar o pacote `.deb` diretamente do site do DBeaver e instalar manualmente:

1. Baixe o arquivo `.deb` [neste link](https://dbeaver.io/download/).
2. Após o download, execute o seguinte comando para instalar:

   ```bash
   sudo dpkg -i /caminho/para/o/arquivo/dbeaver-ce_x.x.x_amd64.deb
   sudo apt-get install -f  # Para corrigir possíveis dependências
   ```

### 4. Executando o DBeaver

Após a instalação, você pode encontrar o DBeaver no menu de aplicativos ou executá-lo pelo terminal com o comando:

```bash
dbeaver
```

Esses métodos devem permitir que você instale e comece a usar o DBeaver no seu Ubuntu.
