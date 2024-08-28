## **_Script de Utilização do Git para o GitHub\*_**

Este script cobre desde a criação de um repositório até operações avançadas, como rebase, cherry-pick, e squash.

```bash
#!/bin/bash

# 1. Configure seu nome de usuário e e-mail do Git
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@example.com"

# 2. Inicialize um novo repositório local
git init

# 3. Clone um repositório remoto existente
git clone https://github.com/usuario/repo.git

# 4. Verifique o status do repositório (arquivos modificados, staged, etc.)
git status

# 5. Adicione arquivos ao staging area
git add nome_do_arquivo          # Adiciona um arquivo específico
git add .                        # Adiciona todos os arquivos no diretório atual

# 6. Commit das alterações com uma mensagem
git commit -m "Mensagem descritiva do commit"

# 7. Configure o repositório remoto (origin)
git remote add origin https://github.com/usuario/repo.git

# 8. Envie (push) as alterações para o repositório remoto
git push -u origin main           # Primeiro push define a branch padrão
git push                          # Envia alterações após o primeiro push

# 9. Busque (pull) e sincronize alterações do repositório remoto
git pull origin main              # Busca e aplica alterações da branch 'main'

# 10. Verifique o histórico de commits
git log                           # Exibe todos os commits
git log --oneline --graph --all   # Exibe o histórico em uma única linha com gráfico

# 11. Crie e mude para uma nova branch
git branch nome-da-branch         # Cria uma nova branch
git checkout nome-da-branch       # Muda para a branch especificada
git checkout -b nova-branch       # Cria e muda para a nova branch

# 12. Criar uma nova branch a partir de outra branch
git checkout -b nova-branch outra-branch  # Cria e muda para 'nova-branch' baseada em 'outra-branch'

# 13. Mescle (merge) uma branch na branch atual
git checkout main                 # Muda para a branch 'main'
git merge nome-da-branch          # Mescla 'nome-da-branch' na 'main'

# 14. Resolver conflitos de mesclagem
# Após tentar um merge, se houver conflitos, edite manualmente os arquivos conflitantes para resolver.
git status                        # Verifique os arquivos conflitantes
# Após resolver conflitos, adicione os arquivos corrigidos
git add nome-do-arquivo-resolvido
git commit -m "Resolveu o conflito no arquivo"

# 15. Rebase: Mova commits de uma branch para outra
git checkout feature-branch
git rebase main                   # Rebase a branch 'feature-branch' na 'main'
# Se houver conflitos durante o rebase, resolva-os como no comando acima
git rebase --continue             # Continue o rebase após resolver os conflitos
git rebase --abort                # Aborte o rebase, se necessário

# 16. Squash: Combine múltiplos commits em um único commit
git rebase -i HEAD~3              # Squash os últimos 3 commits interativamente
# No editor, altere 'pick' para 'squash' nos commits que deseja combinar.

# 17. Cherry-pick: Aplique um commit específico em outra branch
git checkout main
git cherry-pick commit-sha        # 'commit-sha' é o hash do commit que você deseja aplicar

# 18. Reverter um commit específico
git revert commit-sha             # Cria um novo commit revertendo o commit especificado

# 19. Restabelecer (reset) um branch para um estado específico
git reset --hard commit-sha       # Restabelece a branch ao estado de 'commit-sha' apagando as alterações locais

# 20. Adicione uma tag a um commit específico
git tag -a v1.0 -m "Versão 1.0" commit-sha  # Adiciona uma tag anotada 'v1.0' ao commit especificado

# 21. Envie as tags para o repositório remoto
git push origin --tags

# 22. Buscar todas as alterações do repositório remoto sem aplicá-las
git fetch origin                  # Baixa as referências do repositório remoto

# 23. Visualize as diferenças entre commits
git diff commit-sha1 commit-sha2  # Mostra as diferenças entre dois commits
git diff HEAD~1 HEAD              # Mostra as diferenças entre o último e o penúltimo commit

# 24. Stash: Salvar mudanças não commitadas temporariamente
git stash                         # Salva todas as alterações não commitadas
git stash pop                     # Aplica as alterações salvas no stash
git stash list                    # Lista todos os stashes
git stash drop                    # Remove o stash mais recente

# 25. Trabalhar com submódulos (submodules)
git submodule add https://github.com/usuario/submodulo-repo.git caminho/submodulo
git submodule update --init       # Inicializa, clona e atualiza todos os submódulos

# 26. Cancelar um commit localmente (soft/hard)
git reset --soft HEAD~1           # Desfaz o último commit, mantendo as alterações no staging
git reset --hard HEAD~1           # Desfaz o último commit e todas as alterações locais

# 27. Verifique os arquivos rastreados e não rastreados
git ls-files                      # Lista todos os arquivos rastreados
git ls-files --others --exclude-standard # Lista arquivos não rastreados

# 28. Modificar uma mensagem de commit anterior
git commit --amend -m "Nova mensagem de commit"

# 29. Sincronizar seu fork com o repositório original
git remote add upstream https://github.com/original-usuario/original-repo.git
git fetch upstream
git merge upstream/main           # Mescla as mudanças do repositório original no fork

# 30. Renomear o repositório remoto
git remote rename origin novo-nome

# 31. Verificar as configurações do repositório remoto
git remote -v                     # Lista as URLs de repositório remoto configuradas

# 32. Reaplicar commits de uma branch antiga em uma nova
git checkout nova-branch
git cherry-pick old-branch~3..old-branch  # Reaplica os últimos 3 commits de 'old-branch' na 'nova-branch'

# 33. Rebasing interativo para resolver conflitos e organizar histórico
git rebase -i HEAD~N              # Reorganize ou modifique os últimos N commits interativamente

# Fim do Script
echo "Comandos Git executados com sucesso!"
```

### **Como Usar Este Script**

1. **Salvar o Script**: Salve o conteúdo acima em um arquivo com extensão `.sh`, como `git_commands.sh`.
2. **Tornar Executável**: Torne o script executável com o comando:
   ```bash
   chmod +x git_commands.sh
   ```
3. **Executar o Script**: Execute o script no terminal com o comando:
   ```bash
   ./git_commands.sh
   ```
