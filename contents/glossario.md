<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 📖 Glossário Git

## 🌳 Conceitos Básicos

### repository (repositório) 📁
Local onde o Git armazena todo o histórico do projeto
```powershell
# Criar novo repositório
git init

# Clonar repositório existente
git clone https://github.com/usuario/repo.git
```

### branch (ramificação) 🌿
Linha independente de desenvolvimento
```powershell
# Criar branch
git branch feature/login

# Mudar para branch
git checkout feature/login
```

### commit (confirmação) 💾
Snapshot do estado do projeto em um momento específico
```powershell
# Criar commit
git commit -m "feat: adiciona login"
```

### fork 🔱
Cópia pessoal de um repositório de terceiros
```powershell
# Fork é feito via interface do GitHub/GitLab
# Depois clone seu fork
git clone https://github.com/seu-usuario/repo-forkado.git
```

### pull request (PR) 📥
Solicitação para integrar mudanças de uma branch/fork em outra
```powershell
# Preparar PR
git push origin feature/nova-funcionalidade
# Criar PR via interface do GitHub/GitLab
```

## 🔄 Operações

### fetch ⬇️
Baixa objetos e referências de outro repositório
```powershell
# Buscar atualizações
git fetch origin
git fetch --all
```

### merge 🔗
Combina duas ou mais histórias de desenvolvimento
```powershell
# Merge de branch
git merge feature/login
```

### rebase 📋
Reaplica commits em cima de outra base
```powershell
# Rebase na main
git rebase main
```

### cherry-pick 🍒
Aplica mudanças de commits específicos
```powershell
# Aplicar commit específico
git cherry-pick abc123
```

### stash 📦
Armazena temporariamente mudanças não commitadas
```powershell
# Salvar mudanças
git stash save "trabalho em progresso"

# Recuperar mudanças
git stash pop
```

## 📍 Referências

### HEAD 🎯
Ponteiro para o commit atual
```powershell
# Ver HEAD atual
git rev-parse HEAD

# Mover HEAD
git checkout commit-hash
```

### origin/upstream 🔄
Referências para repositórios remotos
```powershell
# Ver remotes
git remote -v

# Adicionar upstream
git remote add upstream https://github.com/original/repo.git
```

### tag 🏷️
Marco específico no histórico do projeto
```powershell
# Criar tag
git tag v1.0.0

# Tag anotada
git tag -a v1.0.0 -m "Versão 1.0.0"
```

## 🛠️ Áreas de Trabalho

### working directory 📂
Diretório de trabalho atual
```powershell
# Ver status
git status

# Descartar mudanças
git checkout -- arquivo.txt
```

### staging area (index) 🔋
Área de preparação para commits
```powershell
# Adicionar à staging
git add arquivo.txt

# Remover da staging
git restore --staged arquivo.txt
```

### local repository 💾
Repositório na sua máquina
```powershell
# Ver commits locais
git log --oneline
```

### remote repository 🌐
Repositório em servidor remoto
```powershell
# Ver branches remotas
git branch -r

# Enviar mudanças
git push origin main
```

## 🔧 Ferramentas

### hook 🪝
Scripts executados em eventos específicos
```bash
#!/bin/bash
# .git/hooks/pre-commit
npm test
```

### submodule 📦
Repositório dentro de outro repositório
```powershell
# Adicionar submódulo
git submodule add https://github.com/lib/repo.git libs/repo

# Atualizar submódulos
git submodule update --init --recursive
```

### gitignore 🚫
Arquivo que lista o que Git deve ignorar
```plaintext
# .gitignore
node_modules/
.env
*.log
```

### git-lfs 📊
Sistema para arquivos grandes
```powershell
# Instalar LFS
git lfs install

# Rastrear arquivos grandes
git lfs track "*.psd"
```

## 🔍 Diagnóstico

### reflog 📜
Registro de todas as ações no repositório
```powershell
# Ver histórico de ações
git reflog

# Recuperar commit deletado
git reset --hard HEAD@{1}
```

### blame 👀
Mostra quem alterou cada linha
```powershell
# Ver histórico de arquivo
git blame arquivo.txt
```

### bisect 🔍
Busca binária por commits problemáticos
```powershell
# Iniciar bisect
git bisect start
git bisect bad HEAD
git bisect good v1.0.0
```

## ⚠️ Estados de Arquivo

### untracked ❓
Arquivo não rastreado pelo Git
```powershell
# Ver arquivos não rastreados
git status
```

### modified ✏️
Arquivo modificado desde último commit
```powershell
# Ver modificações
git diff arquivo.txt
```

### staged ✅
Arquivo pronto para commit
```powershell
# Ver arquivos staged
git diff --staged
```

### committed ✔️
Arquivo salvo no repositório
```powershell
# Ver último commit
git show HEAD
```

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>