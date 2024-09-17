## **_Deploy Aplicação Vite no Linux_**

Aqui está um tutorial passo a passo para configurar um serviço `systemd` no Linux que inicia automaticamente um servidor Vite usando o comando `serve -s dist -l 8080` sempre que o servidor Linux é iniciado.

## **Tutorial: Configurando um Serviço `systemd` para Servir uma Aplicação Vite**

### **Passo 1: Instalar Node.js e NPM (se necessário)**

Se você ainda não tem o Node.js e o NPM instalados, instale-os usando o gerenciador de pacotes do seu sistema. Por exemplo, no Ubuntu, você pode fazer isso com:

```bash
sudo apt update
sudo apt install nodejs npm
```

Verifique a instalação executando:

```bash
node -v
npm -v
```

### **Passo 2: Instalar o Servidor `serve`**

O `serve` é uma ferramenta simples para servir arquivos estáticos. Você pode instalá-lo globalmente usando o NPM:

```bash
sudo npm install -g serve
```

Verifique a instalação executando:

```bash
which serve
```

Isso deve retornar o caminho para o comando `serve` (por exemplo, `/usr/local/node/bin/serve`).

### **Passo 3: Preparar a Aplicação Vite**

Certifique-se de que sua aplicação Vite foi construída e está pronta para ser servida. Isso normalmente envolve rodar o comando de build do Vite:

```bash
npm run build
```

Isso criará um diretório `dist` que contém os arquivos estáticos da sua aplicação.

### **Passo 4: Criar um Link Simbólico (opcional)**

Se o caminho para o diretório de sua aplicação contém espaços ou caracteres especiais, considere criar um link simbólico para simplificar o caminho:

```bash
ln -s "/home/usuario/Área de trabalho/frontend" /home/usuario/frontend
```

### **Passo 5: Criar o Arquivo de Serviço `systemd`**

Crie um arquivo de serviço em `/etc/systemd/system/`. Nomeie o arquivo como `vite-serve.service`:

```bash
sudo nano /etc/systemd/system/vite-serve.service
```

### **Passo 6: Configurar o Serviço**

No editor de texto, adicione a seguinte configuração ao arquivo de serviço. Substitua os caminhos conforme necessário:

```ini
[Unit]
Description=Vite Serve Application
After=network.target

[Service]
WorkingDirectory=/home/usuario/frontend
ExecStart=/usr/local/node/bin/serve -s dist -l 8080
Restart=always
User=usuario
Group=usuario
Environment=PATH=/usr/local/node/bin:/usr/local/bin:/usr/bin:/bin
Environment=NODE_ENV=production
KillMode=process
TimeoutSec=10

[Install]
WantedBy=multi-user.target
```

- **WorkingDirectory**: O diretório onde a aplicação está localizada.
- **ExecStart**: O comando para iniciar o servidor Vite.
- **User e Group**: O usuário e o grupo sob os quais o serviço será executado.
- **Environment**: Variáveis de ambiente necessárias para a execução do comando.

### **Passo 7: Recarregar `systemd` e Iniciar o Serviço**

Após salvar o arquivo de configuração, recarregue o `systemd` para que ele reconheça o novo serviço:

```bash
sudo systemctl daemon-reload
```

Inicie o serviço manualmente para verificar se está funcionando corretamente:

```bash
sudo systemctl start vite-serve.service
```

### **Passo 8: Verificar o Status do Serviço**

Verifique o status do serviço para garantir que ele foi iniciado corretamente:

```bash
sudo systemctl status vite-serve.service
```

Se tudo estiver funcionando, o serviço deve estar ativo e servindo sua aplicação na porta 8080.

### **Passo 9: Habilitar o Serviço para Iniciar Automaticamente**

Para garantir que o serviço inicie automaticamente sempre que o servidor for reiniciado, habilite-o com o seguinte comando:

```bash
sudo systemctl enable vite-serve.service
```

### **Passo 10: Verificar o Serviço Após Reiniciar o Servidor**

Reinicie o servidor e verifique se o serviço foi iniciado automaticamente:

```bash
sudo reboot
```

Após o reinício, você pode verificar o status do serviço:

```bash
sudo systemctl status vite-serve.service
```

Se o serviço estiver ativo, sua aplicação Vite estará disponível na porta 8080.

### **Conclusão**

Você configurou com sucesso um serviço `systemd` que serve sua aplicação Vite automaticamente sempre que o servidor é iniciado. Este processo garante que sua aplicação esteja sempre disponível sem a necessidade de iniciar manualmente o servidor após cada reinicialização.
