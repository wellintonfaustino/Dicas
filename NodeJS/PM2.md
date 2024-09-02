## **\_PM2**

O PM2 é um gerenciador de processos para aplicações Node.js, que facilita o gerenciamento e monitoramento de suas aplicações em produção.

### 1. Instalação do PM2

Primeiro, você precisa ter o Node.js e o npm (Node Package Manager) instalados em seu sistema. Para instalar o PM2, você pode usar o npm com o seguinte comando:

```bash
npm install pm2 -g
```

O `-g` indica que o PM2 será instalado globalmente em seu sistema.

### 2. Iniciando uma aplicação com o PM2

Suponha que você tenha uma aplicação Node.js no arquivo `app.js`. Para iniciar essa aplicação usando o PM2, utilize o comando:

```bash
pm2 start app.js
```

Esse comando vai iniciar a aplicação e o PM2 cuidará para que ela continue rodando, mesmo que haja falhas.

### 3. Listando os processos gerenciados pelo PM2

Para ver uma lista de todos os processos que o PM2 está gerenciando, use o comando:

```bash
pm2 list
```

Esse comando exibirá informações como o ID do processo, o status (online/offline), e o consumo de CPU e memória.

### 4. Monitorando sua aplicação

PM2 oferece uma interface de monitoramento que mostra informações em tempo real sobre o desempenho da sua aplicação:

```bash
pm2 monit
```

### 5. Logs das aplicações

Você pode visualizar os logs das suas aplicações diretamente pelo PM2:

```bash
pm2 logs
```

Isso exibe os logs em tempo real. Se você quiser ver os logs de um processo específico, pode usar:

```bash
pm2 logs [ID_DO_PROCESSO]
```

### 6. Reiniciando e recarregando aplicações

Para reiniciar uma aplicação (por exemplo, após alterações no código), use:

```bash
pm2 restart app.js
```

Se você precisar recarregar a aplicação sem tempo de inatividade, use o comando:

```bash
pm2 reload app.js
```

### 7. Parando e excluindo processos

Para parar uma aplicação gerenciada pelo PM2, use:

```bash
pm2 stop app.js
```

Para excluir completamente um processo do gerenciamento do PM2, use:

```bash
pm2 delete app.js
```

### 8. Salvando e restaurando processos

Se você deseja que suas aplicações sejam reiniciadas automaticamente após um reboot do servidor, você pode salvar o estado atual dos processos:

```bash
pm2 save
```

Para restaurar os processos após um reboot:

```bash
pm2 resurrect
```

### 9. Configuração de inicialização automática

Para garantir que o PM2 inicialize automaticamente suas aplicações quando o servidor for reiniciado, use o comando:

```bash
pm2 startup
```

Esse comando irá gerar um script para o seu sistema operacional, configurando o PM2 para iniciar no boot.

### 10. Exportando configurações para arquivo JSON

Se você deseja exportar a configuração atual das suas aplicações para um arquivo JSON, para facilitar o gerenciamento e automação, use:

```bash
pm2 save --json
```

Isso criará um arquivo `ecosystem.config.js`, que pode ser usado para iniciar seus processos:

```bash
pm2 start ecosystem.config.js
```

### Conclusão

O PM2 é uma ferramenta poderosa para gerenciar aplicações Node.js em produção. Ele oferece uma ampla gama de funcionalidades para monitoramento, gerenciamento de processos, e manutenção de alta disponibilidade para suas aplicações. Com os comandos acima, você já pode começar a gerenciar suas aplicações Node.js de forma eficiente.
