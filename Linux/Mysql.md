## **_Re-instalação do mysql_**

Reinstalar o MySQL do zero no Ubuntu, siga os passos abaixo:

### 1. Remover o MySQL existente

Primeiro, você precisa remover completamente o MySQL do seu sistema. Isso inclui pacotes e dados associados.

1. **Parar o serviço MySQL**:

   ```bash
   sudo systemctl stop mysql
   ```

2. **Desinstalar os pacotes MySQL**:

   ```bash
   sudo apt-get remove --purge mysql-server mysql-client mysql-common
   ```

3. **Remover diretórios e arquivos de configuração MySQL**:

   ```bash
   sudo rm -rf /etc/mysql /var/lib/mysql
   sudo rm -rf /var/log/mysql*
   sudo rm -rf /usr/lib/mysql /usr/share/mysql
   ```

4. **Atualizar o sistema**:
   ```bash
   sudo apt-get autoremove
   sudo apt-get autoclean
   sudo apt-get update
   ```

### 2. Reinstalar o MySQL

1. **Instalar o MySQL Server**:

   ```bash
   sudo apt-get install mysql-server
   ```

2. **Configurar o MySQL**:
   Após a instalação, o MySQL pode solicitar a configuração de uma senha para o usuário root.

3. **Verificar o status do MySQL**:

   ```bash
   sudo systemctl status mysql
   ```

4. **Acessar o MySQL**:
   ```bash
   sudo mysql -u root -p
   ```

Agora, você deve ter uma instalação limpa do MySQL em seu sistema Ubuntu.

Para configurar o usuário `root` no MySQL após a reinstalação, siga os passos abaixo:

### 1. Acesse o MySQL como usuário `root`

Primeiro, você precisa acessar o MySQL como o usuário `root`. Como a autenticação padrão para o usuário `root` pode ser feita via `auth_socket` (ou seja, sem senha, apenas pelo usuário do sistema), use o seguinte comando:

```bash
sudo mysql -u root
```

### 2. Configurar a senha para o usuário `root`

Após acessar o MySQL, você pode configurar uma nova senha para o usuário `root`:

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'NovaSenha';
```

Substitua `'NovaSenha'` pela senha desejada.

### 3. Aplicar as mudanças

Para garantir que as mudanças sejam aplicadas, execute o comando:

```sql
FLUSH PRIVILEGES;
```

### 4. Sair do MySQL

Depois de configurar a senha, você pode sair do MySQL:

```sql
EXIT;
```

### 5. Testar o acesso com a nova senha

Agora você pode testar o acesso ao MySQL usando a nova senha configurada para o usuário `root`:

```bash
mysql -u root -p
```

Será solicitado que você insira a nova senha. Se tudo estiver configurado corretamente, você deve conseguir acessar o MySQL como `root` usando a senha que configurou.
