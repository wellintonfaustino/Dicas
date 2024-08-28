## **_Liberação de Portas com o UFW_**

O UFW (Uncomplicated Firewall) é uma ferramenta de firewall para sistemas Linux que simplifica a configuração de regras de firewall com IPTables. Abaixo está um tutorial detalhado de como usar o UFW para listar, liberar, bloquear portas, e explorar outras funcionalidades.

### 1. **Instalar o UFW**

Na maioria das distribuições Ubuntu, o UFW já está instalado por padrão. Caso contrário, você pode instalá-lo com o comando:

```bash
sudo apt install ufw
```

### 2. **Verificar o Status do UFW**

Para verificar o status atual do UFW (se está ativo ou inativo), utilize:

```bash
sudo ufw status
```

Se o UFW estiver ativo, o comando mostrará as regras de firewall atualmente aplicadas.

### 3. **Ativar o UFW**

Para ativar o UFW e começar a proteger seu sistema:

```bash
sudo ufw enable
```

### 4. **Desativar o UFW**

Se precisar desativar o firewall temporariamente, você pode usar:

```bash
sudo ufw disable
```

### 5. **Listar Regras do UFW**

Para listar todas as regras de firewall atualmente configuradas:

```bash
sudo ufw status numbered
```

A opção `numbered` é útil para gerenciar regras específicas mais facilmente.

### 6. **Permitir uma Porta**

Para permitir o tráfego em uma porta específica, use o comando `allow` seguido pela porta:

```bash
sudo ufw allow 80
```

Isto permitirá tráfego HTTP na porta 80. Para liberar tráfego em uma porta específica utilizando um protocolo, como TCP ou UDP:

```bash
sudo ufw allow 443/tcp
sudo ufw allow 53/udp
```

### 7. **Bloquear uma Porta**

Para bloquear o tráfego em uma porta específica, use o comando `deny` seguido pela porta:

```bash
sudo ufw deny 21
```

Este comando irá bloquear a porta 21 (FTP).

### 8. **Permitir ou Bloquear um Intervalo de Portas**

Para permitir um intervalo de portas, especifique o intervalo e o protocolo:

```bash
sudo ufw allow 1000:2000/tcp
```

Para bloquear um intervalo de portas:

```bash
sudo ufw deny 1000:2000/udp
```

### 9. **Permitir ou Bloquear IPs Específicos**

Para permitir um endereço IP específico:

```bash
sudo ufw allow from 192.168.1.100
```

Para bloquear um endereço IP específico:

```bash
sudo ufw deny from 192.168.1.100
```

Para permitir um IP específico em uma porta específica:

```bash
sudo ufw allow from 192.168.1.100 to any port 22
```

### 10. **Remover Regras do UFW**

Para remover uma regra específica, primeiro liste as regras com números:

```bash
sudo ufw status numbered
```

Em seguida, remova a regra pelo seu número. Por exemplo, para remover a regra número 2:

```bash
sudo ufw delete 2
```

### 11. **Definir Políticas Padrão**

As políticas padrão determinam o comportamento padrão do firewall. Para definir a política padrão para negar todas as conexões de entrada e permitir todas as conexões de saída:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

Você também pode configurar para permitir todas as conexões de entrada e negar todas as conexões de saída, conforme necessário.

### 12. **Ver Logs do UFW**

Para ativar o registro de eventos do UFW, use:

```bash
sudo ufw logging on
```

Para desativar o registro de eventos:

```bash
sudo ufw logging off
```

Os logs do UFW podem ser encontrados no arquivo `/var/log/ufw.log`.

### 13. **Recarregar o UFW**

Se você alterar a configuração manualmente no arquivo de configuração (`/etc/default/ufw`), recarregue o UFW com:

```bash
sudo ufw reload
```

### 14. **Resetar o UFW**

Para restaurar o UFW para o seu estado padrão (removendo todas as regras):

```bash
sudo ufw reset
```

### 15. **Verificar Aplicações com Perfil UFW**

Alguns serviços e aplicações têm perfis UFW predefinidos. Para listar todos os perfis disponíveis:

```bash
sudo ufw app list
```

Para permitir ou bloquear um aplicativo específico, use:

```bash
sudo ufw allow 'NomeAplicativo'
sudo ufw deny 'NomeAplicativo'
```

### Resumo dos Comandos Básicos:

- **Ativar o UFW:** `sudo ufw enable`
- **Desativar o UFW:** `sudo ufw disable`
- **Verificar o status do UFW:** `sudo ufw status`
- **Permitir uma porta:** `sudo ufw allow [porta]`
- **Bloquear uma porta:** `sudo ufw deny [porta]`
- **Remover uma regra:** `sudo ufw delete [número_da_regra]`

Esse tutorial deve cobrir a maioria das funcionalidades básicas para gerenciar o firewall usando o UFW no Ubuntu.
