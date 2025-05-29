<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# ⚙️ Comandos Essenciais do Git

Saber usar o Git é uma habilidade fundamental para qualquer desenvolvedor, seja para trabalhar em equipe ou para gerenciar projetos pessoais. Abaixo estão os comandos essenciais do Git que todo desenvolvedor deve conhecer:

- `git init` 🛠️: Inicializa um repositório no diretório atual.
- `git status` 🔎: Exibe a situação atual da working tree (o que foi modificado e o que está preparado).
- `git add .` ➕: Adiciona arquivos modificados à área de preparação (staging area).
- `git rm --cached` 🗑️: Remove arquivos da área de preparação (desfaz o comando `add`).
- `git commit -m "mensagem do commit"` 💬: Salva definitivamente as alterações preparadas no histórico do repositório.
- `git log` 📜: Mostra o histórico de commits.
- `git diff` ⚡: Exibe as alterações entre diferentes commits ou entre a working tree e o repositório.
- `git restore` 🧹: Reverte as alterações em um arquivo, retornando ao estado do último commit.
- `git merge` 🔗: Combina mudanças de uma branch com a branch atual.
- `git pull` ⬇️: Atualiza a branch local com as alterações do repositório remoto.
- `git push` ⬆️: Envia as alterações da branch local para o repositório remoto.

## 🚀 Por que o Git é essencial para desenvolvedores?

- Controle de versão: Permite rastrear todas as alterações no código, facilitando a identificação de bugs e a reversão para versões anteriores.

- Colaboração em equipe: Facilita o trabalho em equipe, permitindo que várias pessoas trabalhem no mesmo projeto simultaneamente.

- Organização: Branches ajudam a separar funcionalidades, correções de bugs e desenvolvimento principal.

- Backup: O repositório remoto serve como um backup seguro do projeto.

- Integração com ferramentas modernas: O Git é a base de plataformas como GitHub, GitLab e Bitbucket, que oferecem funcionalidades adicionais como CI/CD, revisão de código e gerenciamento de projetos.

---

# ⚙️ Comandos Essenciais do Git

## 🔄 Comandos Diários

### Verificando Status e Histórico

1. **git status** 🔍
```powershell
# Ver status detalhado
git status

# Ver status resumido
git status -s
```

2. **git log** 📜
```powershell
# Ver histórico detalhado
git log

# Ver histórico resumido em uma linha
git log --oneline

# Ver histórico com gráfico
git log --graph --oneline --all

# Ver mudanças em um commit específico
git show <hash-do-commit>
```

### Trabalhando com Mudanças

1. **git add** ➕
```powershell
# Adicionar arquivo específico
git add arquivo.txt

# Adicionar todos os arquivos
git add .

# Adicionar partes específicas de um arquivo
git add -p arquivo.txt
```

2. **git commit** 💾
```powershell
# Commit básico
git commit -m "feat: adiciona login com Google"

# Adicionar e commitar em um comando
git commit -am "fix: corrige bug no formulário"

# Editar último commit
git commit --amend -m "nova mensagem"
```

3. **git restore** 🔄
```powershell
# Descartar mudanças em arquivo
git restore arquivo.txt

# Remover arquivo da área de staging
git restore --staged arquivo.txt

# Restaurar arquivo de um commit específico
git restore --source=HEAD~1 arquivo.txt
```

## 🌿 Trabalhando com Branches

### Gerenciamento de Branches

1. **Criar e Mudar** 🆕
```powershell
# Criar branch
git branch feature/login

# Criar e mudar para nova branch
git checkout -b feature/login

# Mudar de branch
git checkout main
```

2. **Listar e Deletar** 📋
```powershell
# Listar branches locais
git branch

# Listar branches remotas
git branch -r

# Listar todas as branches
git branch -a

# Deletar branch local
git branch -d feature/login

# Forçar deleção
git branch -D feature/login
```

## 🔄 Sincronização com Remoto

### Push e Pull

1. **git push** ⬆️
```powershell
# Push básico
git push origin main

# Push nova branch
git push -u origin feature/login

# Push forçado (usar com cautela!)
git push --force-with-lease origin main
```

2. **git pull** ⬇️
```powershell
# Pull básico
git pull origin main

# Pull com rebase
git pull --rebase origin main

# Fetch + Merge manual
git fetch origin
git merge origin/main
```

## 🛠️ Comandos Avançados

### Stash

```powershell
# Salvar mudanças temporariamente
git stash save "mensagem descritiva"

# Listar stashes
git stash list

# Aplicar stash específico
git stash apply stash@{0}

# Aplicar e remover último stash
git stash pop

# Remover stash específico
git stash drop stash@{0}
```

### Rebase Interativo

```powershell
# Rebase últimos 3 commits
git rebase -i HEAD~3

# Comandos disponíveis no rebase:
# p, pick = usar commit
# r, reword = usar commit, mas editar mensagem
# e, edit = usar commit, mas parar para alterar
# s, squash = juntar com commit anterior
# f, fixup = juntar com commit anterior (descartar mensagem)
# d, drop = remover commit
```

### Cherry-pick

```powershell
# Aplicar commit específico
git cherry-pick <hash-do-commit>

# Cherry-pick sem commit
git cherry-pick -n <hash-do-commit>
```

### Bisect

```powershell
# Iniciar bisect
git bisect start

# Marcar commit atual como ruim
git bisect bad

# Marcar commit antigo como bom
git bisect good <hash-do-commit>

# Finalizar bisect
git bisect reset
```

## 🔍 Comandos de Inspeção

### Diff

```powershell
# Ver mudanças não commitadas
git diff

# Ver mudanças staged
git diff --staged

# Ver mudanças entre commits
git diff <hash1>..<hash2>

# Ver mudanças em arquivo específico
git diff arquivo.txt
```

### Blame

```powershell
# Ver quem alterou cada linha
git blame arquivo.txt

# Ver com limite de linhas
git blame -L 10,20 arquivo.txt
```

## 💡 Dicas e Truques

1. **Aliases Úteis**
```powershell
# Configurar aliases comuns
git config --global alias.undo "reset HEAD~1"
git config --global alias.last "log -1 HEAD"
git config --global alias.visual "!gitk"
```

2. **Salvando Credenciais**
```powershell
# Salvar credenciais no Windows
git config --global credential.helper wincred

# Salvar credenciais no macOS
git config --global credential.helper osxkeychain
```

3. **Limpeza e Manutenção**
```powershell
# Limpar arquivos não rastreados
git clean -n  # dry run
git clean -f  # forçar remoção

# Compactar repositório
git gc --aggressive --prune=now
```

## ⚠️ Recuperação de Erros

1. **Reverter Commits**
```powershell
# Reverter último commit mantendo mudanças
git reset --soft HEAD~1

# Reverter último commit descartando mudanças
git reset --hard HEAD~1
```

2. **Recuperar Commits Perdidos**
```powershell
# Ver histórico de todas as ações
git reflog

# Recuperar commit específico
git checkout -b recuperacao <hash-do-commit>
```

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>
