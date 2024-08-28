## **_OpenSSH Liberação do FTP_**

Para habilitar a porta 22 para SFTP (Secure File Transfer Protocol) no Ubuntu, você precisará garantir que o serviço SSH (Secure Shell) esteja instalado e configurado corretamente, pois o SFTP é um subsistema do SSH. Aqui estão os passos para habilitar a porta 22 para SFTP:

### Passo 1: Instalar o OpenSSH Server

Se o OpenSSH Server não estiver instalado, você pode instalá-lo com o seguinte comando:

```bash
sudo apt update
sudo apt install openssh-server -y
```

### Passo 2: Verificar se o SSH está em Execução

Depois de instalar o OpenSSH Server, verifique se o serviço está em execução com:

```bash
sudo systemctl status ssh
```

Se o serviço não estiver em execução, você pode iniciá-lo com:

```bash
sudo systemctl start ssh
```

E habilitá-lo para iniciar automaticamente na inicialização com:

```bash
sudo systemctl enable ssh
```

### Passo 3: Configurar o SSH para SFTP

Edite o arquivo de configuração do SSH para garantir que o SFTP esteja habilitado. Abra o arquivo de configuração do SSH com o editor de texto de sua preferência:

```bash
sudo nano /etc/ssh/sshd_config
```

Localize as seguintes linhas no arquivo de configuração:

```text
#Subsystem sftp /usr/lib/openssh/sftp-server
```

Certifique-se de que a linha não está comentada (remova o `#` se necessário) e que o caminho para o `sftp-server` está correto. A linha deve ficar assim:

```text
Subsystem sftp /usr/lib/openssh/sftp-server
```

### Passo 4: Reiniciar o Serviço SSH

Após fazer as alterações, reinicie o serviço SSH para aplicar as mudanças:

```bash
sudo systemctl restart ssh
```

### Passo 5: Verificar se a Porta 22 Está Aberta

Verifique se a porta 22 está aberta e escutando conexões. Execute:

```bash
sudo ufw allow 22
sudo ufw enable
sudo ufw status
```

Isso permitirá conexões na porta 22 através do firewall UFW (Uncomplicated Firewall), se ele estiver habilitado.

### Passo 6: Testar Conexão SFTP

Agora você pode testar a conexão SFTP usando um cliente SFTP, como o `sftp` no terminal, ou um cliente gráfico como FileZilla.

```bash
sftp user@server_address
```

Substitua `user` pelo seu nome de usuário e `server_address` pelo endereço IP ou nome do servidor.

Depois desses passos, a porta 22 deve estar habilitada para conexões SFTP no seu servidor Ubuntu.
