## **_Gerar chave SSH e instalar Github_**

Para gerar uma chave SSH no Ubuntu e configurá-la para uso com o Git/GitHub, siga os passos abaixo:

### 1. **Gerar uma nova chave SSH**

Abra o terminal e execute o seguinte comando para gerar uma nova chave SSH:

```bash
ssh-keygen -t ed25519 -C "seu-email@example.com"
```

- Substitua `"seu-email@example.com"` pelo seu endereço de e-mail associado à sua conta do GitHub.
- Caso seu sistema não suporte o algoritmo `ed25519`, use `rsa` com `ssh-keygen -t rsa -b 4096 -C "seu-email@example.com"`.

Após executar o comando:

1. Pressione `Enter` para aceitar o local padrão do arquivo (`/home/seu_usuario/.ssh/id_ed25519`).
2. Digite uma senha (opcional) para proteger sua chave. Isso adiciona uma camada extra de segurança.

### 2. **Adicionar a chave SSH ao `ssh-agent`**

Execute os seguintes comandos para adicionar a chave SSH ao agente SSH:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### 3. **Copiar a chave SSH para o GitHub**

Agora, copie o conteúdo da sua chave pública SSH para o clipboard:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copie o texto que aparece (começa com `ssh-ed25519` ou `ssh-rsa`) para o clipboard.

### 4. **Adicionar a chave SSH ao GitHub**

1. Acesse sua conta no GitHub.
2. Clique na sua foto de perfil no canto superior direito e selecione **Settings** (Configurações).
3. No menu à esquerda, selecione **SSH and GPG keys**.
4. Clique no botão **New SSH key**.
5. Dê um nome para a chave (por exemplo, "Ubuntu PC") e cole a chave copiada na caixa de texto.
6. Clique em **Add SSH key**.

### 5. **Testar a conexão SSH com o GitHub**

Para verificar se a chave SSH foi configurada corretamente, execute:

```bash
ssh -T git@github.com
```

Se for a primeira vez que você se conecta ao GitHub via SSH, você verá uma mensagem solicitando a confirmação da identidade do host. Digite `yes` e pressione `Enter`.

Se tudo estiver configurado corretamente, você verá uma mensagem semelhante a:

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

### 6. **Configurar o Git para usar a chave SSH**

No terminal, defina seu nome de usuário e e-mail para o Git:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@example.com"
```

Pronto! Agora você está configurado para usar o Git/GitHub com autenticação SSH no Ubuntu.
