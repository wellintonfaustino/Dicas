Para instalar o Google Chrome no Ubuntu, você pode seguir os passos abaixo:

### 1. Baixar o Google Chrome

Primeiro, baixe o pacote `.deb` do Google Chrome diretamente do site oficial:

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

### 2. Instalar o Google Chrome

Depois de baixar o arquivo, você pode instalar o Google Chrome usando o `dpkg`:

```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

### 3. Resolver Dependências (se necessário)

Se houver problemas de dependências durante a instalação, você pode corrigi-los com o seguinte comando:

```bash
sudo apt-get install -f
```

### 4. Iniciar o Google Chrome

Após a instalação, você pode iniciar o Google Chrome a partir do terminal:

```bash
google-chrome
```

Ou pode encontrá-lo no menu de aplicativos do Ubuntu.

### 5. Verificar a Instalação

Para verificar se o Chrome foi instalado corretamente e sua versão:

```bash
google-chrome --version
```

Agora você deve ter o Google Chrome instalado no seu Ubuntu e pode usá-lo como o navegador para seu projeto.
